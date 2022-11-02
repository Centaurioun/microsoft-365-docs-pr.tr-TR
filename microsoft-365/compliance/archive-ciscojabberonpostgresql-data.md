---
title: Microsoft 365'te PostgreSQL verilerini arşivleme amacıyla Cisco Jabber'ı arşivleme bağlayıcısı ayarlama
description: PostgreSQL'de Cisco Jabber'dan Microsoft 365'e veri içeri aktarmak ve arşivlemek için Microsoft Purview uyumluluk portalı bağlayıcıyı ayarlamayı ve kullanmayı öğrenin.
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- tier3
- purview-compliance
- data-connectors
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 040baf047d4e2e3b360db3bcf76b29217ce0cf4a
ms.sourcegitcommit: ab45f2963e0635ff2cb9670f6f7b4c784f6a250e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/02/2022
ms.locfileid: "68812475"
---
# <a name="set-up-a-connector-to-archive-cisco-jabber-on-postgresql-data"></a>PostgreSQL verilerinde Cisco Jabber'ı arşivleme bağlayıcısı ayarlama

Cisco Jabber platformundaki verileri Microsoft 365 kuruluşunuzdaki kullanıcı posta kutularına aktarmak ve arşivlemek için Microsoft Purview uyumluluk portalı bir Veritas bağlayıcısı kullanın. Veritas, üçüncü taraf veri kaynağındaki öğeleri yakalamak (düzenli olarak) ve bu öğeleri Microsoft 365'e aktarmak için yapılandırılmış [postgreSQL üzerinde Cisco Jabber](https://www.veritas.com/insights/merge1/jabber) bağlayıcısı sağlar. Bağlayıcı, PostgreSQL üzerinde Cisco Jabber'dan gelen iletiler, sohbetler ve paylaşılan içerik gibi içerikleri e-posta iletisi biçimine dönüştürür ve ardından bu öğeleri Microsoft 365'te kullanıcının posta kutusuna aktarır.

PostgreSQL'deki Cisco Jabber verileri kullanıcı posta kutularında depolandıktan sonra, Dava Tutma, eBulma, bekletme ilkeleri ve bekletme etiketleri gibi Microsoft Purview özelliklerini uygulayabilirsiniz. Microsoft 365'te verileri içeri aktarmak ve arşivlemek için PostgreSQL üzerinde Cisco Jabber bağlayıcısı kullanmak, kuruluşunuzun kamu ve mevzuat ilkeleriyle uyumlu kalmasına yardımcı olabilir.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="overview-of-archiving-cisco-jabber-on-postgresql-data"></a>PostgreSQL verilerinde Cisco Jabber'ı arşivleme işlemine genel bakış

Aşağıdaki genel bakış, Microsoft 365'te PostgreSQL üzerinde Cisco Jabber verilerini arşivleme amacıyla bağlayıcı kullanma işlemini açıklar.

![PostgreSQL verilerinde Cisco Jabber için arşivleme iş akışı.](../media/CiscoJabberonPostgreSQLConnectorWorkflow.png)

1. Kuruluşunuz PostgreSQL'de Cisco Jabber ile birlikte çalışarak PostgreSQL sitesinde Cisco Jabber'ı ayarlayıp yapılandırıyor.

2. Her 24 saatte bir PostgreSQL üzerindeki Cisco Jabber öğeleri Veritas Merge1 sitesine kopyalanır. Bağlayıcı ayrıca PostgreSQL'de Cisco Jabber öğelerini e-posta iletisi biçimine dönüştürür.

3. Uyumluluk portalında oluşturduğunuz PostgreSQL üzerinde Cisco Jabber bağlayıcısı, her gün Veritas Merge1 sitesine bağlanır ve Jabber içeriğini Microsoft bulutunda güvenli bir Azure Depolama konumuna aktarır.

4. Bağlayıcı, [3. Adımda](#step-3-map-users-and-complete-the-connector-setup) açıklandığı gibi otomatik kullanıcı eşlemesinin *Email* özelliğinin değerini kullanarak dönüştürülen öğeleri belirli kullanıcıların posta kutularına aktarır. **PostgreSQL'de** Gelen Kutusu klasöründeki Cisco Jabber adlı bir alt klasör kullanıcı posta kutularında oluşturulur ve öğeler bu klasöre aktarılır. Bağlayıcı bunu *Email* özelliğinin değerini kullanarak yapar. Her Jabber öğesi, öğenin her katılımcısının e-posta adresiyle doldurulan bu özelliği içerir.

## <a name="before-you-begin"></a>Başlamadan önce

- Microsoft bağlayıcıları için bir Merge1 hesabı oluşturun. Bunu yapmak için [Veritas Müşteri Desteği'ne](https://www.veritas.com/content/support/en_US) başvurun. 1. Adımda bağlayıcıyı oluştururken bu hesapta oturum açmanız gerekir.

- 1. Adımda PostgreSQL'de Cisco Jabber bağlayıcısını oluşturan (ve 3. Adımda tamamlayan) kullanıcıya Veri Bağlayıcısı Yönetici rolü atanmalıdır. Bu rol, uyumluluk portalındaki **Veri bağlayıcıları sayfasına bağlayıcı** eklemek için gereklidir. Bu rol varsayılan olarak birden çok rol grubuna eklenir. Bu rol gruplarının listesi için Microsoft 365 Defender ve [Microsoft Purview uyumluluk portallarındaki Roller ve rol grupları bölümündeki "Defender ve uyumluluk portallarındaki roller](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-defender-and-compliance-portals)" bölümüne bakın. Alternatif olarak, kuruluşunuzdaki bir yönetici özel bir rol grubu oluşturabilir, Veri Bağlayıcısı Yönetici rolünü atayabilir ve ardından uygun kullanıcıları üye olarak ekleyebilir. Yönergeler için, [Microsoft Purview uyumluluk portalı İzinler](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group) bölümündeki "Özel rol grubu oluşturma" bölümüne bakın.

- Bu Veritas veri bağlayıcısı, Microsoft 365 US Government bulutundaki GCC ortamlarında genel önizleme aşamasındadır. Üçüncü taraf uygulamalar ve hizmetler, kuruluşunuzun müşteri verilerini Microsoft 365 altyapısının dışında olan ve bu nedenle Microsoft Purview ve veri koruma taahhütleri kapsamında olmayan üçüncü taraf sistemlerde depolamayı, iletmeyi ve işlemeyi içerebilir. Microsoft, üçüncü taraf uygulamalara bağlanmak için bu ürünün kullanıldığının, bu üçüncü taraf uygulamaların FEDRAMP uyumlu olduğunu ifade ettiğini ifade etmemektedir.

## <a name="step-1-set-up-the-cisco-jabber-on-postgresql-connector"></a>1. Adım: PostgreSQL'de Cisco Jabber bağlayıcısını ayarlama

İlk adım, uyumluluk portalındaki **Veri Bağlayıcıları** sayfasına erişmek ve Jabber verileri için bir bağlayıcı oluşturmaktır.

1. <https://compliance.microsoft.com> Adresine gidin ve **PostgreSQL'de Veri** **bağlayıcıları** &gt; Cisco Jabber'ı seçin.

2. **PostgreSQL'de Cisco Jabber** ürün açıklaması sayfasında **Bağlayıcı ekle'yi** seçin.

3. **Hizmet koşulları** sayfasında **Kabul Et'i** seçin.

4. Bağlayıcıyı tanımlayan benzersiz bir ad girin ve **İleri'yi** seçin.

5. Bağlayıcıyı yapılandırmak için Merge1 hesabınızda oturum açın.

## <a name="step-2-configure-the-cisco-jabber-on-postgresql-on-the-veritas-merge1-site"></a>2. Adım: Veritas Merge1 sitesinde PostgreSQL'de Cisco Jabber'ı yapılandırma

İkinci adım, Veritas Merge1 sitesindeki PostgreSQL üzerinde Cisco Jabber bağlayıcısını yapılandırmaktır. PostgreSQL'de Cisco Jabber bağlayıcısını yapılandırma hakkında bilgi için bkz. [Birleştirme1 Üçüncü Taraf Bağlayıcıları Kullanıcı Kılavuzu](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20PostgreSQL%20User%20Guide.pdf).

**Kaydet & Son'u** seçtikten sonra, uyumluluk portalındaki bağlayıcı sihirbazındaki **Kullanıcı eşleme** sayfası görüntülenir.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>3. Adım: Kullanıcıları eşleme ve bağlayıcı kurulumunu tamamlama

Kullanıcıları eşlemek ve uyumluluk portalında bağlayıcı kurulumunu tamamlamak için şu adımları izleyin:

1. **PostgreSQL kullanıcılarını Microsoft 365 kullanıcıları ile eşleme** sayfasında, otomatik kullanıcı eşlemesini etkinleştirin. PostgreSQL üzerindeki Cisco Jabber öğeleri, kuruluşunuzdaki kullanıcıların e-posta adreslerini içeren *Email* adlı bir özellik içerir. Bağlayıcı bu adresi bir Microsoft 365 kullanıcısı ile ilişkilendirebiliyorsa, öğeler söz konusu kullanıcının posta kutusuna aktarılır.

2. **İleri'yi** seçin, ayarlarınızı gözden geçirin ve yeni bağlayıcının içeri aktarma işleminin ilerleme durumunu görmek için **Veri bağlayıcıları** sayfasına gidin.

## <a name="step-4-monitor-the-cisco-jabber-on-postgresql-connector"></a>4. Adım: PostgreSQL üzerinde Cisco Jabber bağlayıcısını izleme

PostgreSQL üzerinde Cisco Jabber bağlayıcısını oluşturduktan sonra uyumluluk portalında bağlayıcı durumunu görüntüleyebilirsiniz.

1. Sol gezinti **bölmesinden Veri bağlayıcıları'na** <https://compliance.microsoft.com/> gidin ve bunu seçin.

2. **Bağlayıcılar** sekmesini ve ardından **PostgreSQL'de Cisco Jabber** bağlayıcısını seçerek bağlayıcı hakkındaki özellikleri ve bilgileri içeren açılır sayfayı görüntüleyin.

3. Bağlayıcının durum günlüğünü açmak (veya kaydetmek) için **Kaynakla bağlayıcı durumu** altında **Günlüğü indir** bağlantısını seçin. Bu günlük, Microsoft buluta aktarılan veriler hakkında bilgi içerir. Daha fazla bilgi için bkz. [Veri bağlayıcıları için yönetici günlüklerini görüntüleme](data-connector-admin-logs.md).

## <a name="known-issues"></a>Bilinen sorunlar

- Şu anda 10 MB'tan büyük eklerin veya öğelerin içeri aktarılmasını desteklemiyoruz. Daha büyük öğeler için destek daha sonraki bir tarihte sağlanacaktır.
