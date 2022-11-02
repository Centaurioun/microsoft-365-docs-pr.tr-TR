---
title: Microsoft 365'te Zoom Toplantıları verilerini arşivleye bağlayıcı ayarlama
description: Yöneticiler, Veritas Zoom Toplantıları'ndan Microsoft 365'e veri aktarıp arşivlemesi için bir bağlayıcı ayarlayabilir. Bu sayede Microsoft 365'teki üçüncü taraf veri kaynaklarından verileri arşivleyebilir, böylece kuruluşunuzun üçüncü taraf verilerini yönetmek için yasal tutma, içerik arama ve bekletme ilkeleri gibi uyumluluk özelliklerini kullanabilirsiniz.
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
ms.collection:
- tier3
- purview-compliance
- data-connectors
ms.openlocfilehash: a6414980adddf889a1ebcf2790dd3f2ae6ba10ba
ms.sourcegitcommit: ab45f2963e0635ff2cb9670f6f7b4c784f6a250e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/02/2022
ms.locfileid: "68811819"
---
# <a name="set-up-a-connector-to-archive-zoom-meetings-data"></a>Yakınlaştırma Toplantıları verilerini arşivleye bağlayıcı ayarlama

Microsoft 365 kuruluşunuzdaki kullanıcı posta kutularına Verileri Yakınlaştırma Toplantılarından içeri aktarmak ve arşiv etmek için Microsoft Purview uyumluluk portalı bir Veritas bağlayıcısı kullanın. Veritas, üçüncü taraf veri kaynağındaki öğeleri yakalamak (düzenli olarak) ve bu öğeleri Microsoft 365'e aktarmak için yapılandırılmış bir [Yakınlaştırma Toplantıları](https://globanet.com/zoom/) bağlayıcısı sağlar. Bağlayıcı, Toplantıları Yakınlaştır hesabından toplantıların içeriğini (sohbetler, kayıtlı dosyalar ve meta veriler dahil) e-posta iletisi biçimine dönüştürür ve ardından bu öğeleri Microsoft 365'teki kullanıcı posta kutularına aktarır.

Yakınlaştırma Toplantıları verileri kullanıcı posta kutularında depolandıktan sonra, Dava Tutma, eBulma, bekletme ilkeleri ve bekletme etiketleri ve iletişim uyumluluğu gibi Microsoft Purview özelliklerini uygulayabilirsiniz. Microsoft 365'te verileri içeri aktarmak ve arşivlerken Yakınlaştırma Toplantıları bağlayıcısı kullanmak, kuruluşunuzun kamu ve mevzuat ilkeleriyle uyumlu kalmasına yardımcı olabilir.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="overview-of-archiving-zoom-meetings-data"></a>Yakınlaştırma Toplantıları verilerini arşivlemeyle ilgili genel bakış

Aşağıdaki genel bakış, Microsoft 365'te Zoom Toplantıları verilerini arşivlerken bağlayıcı kullanma işlemini açıklar.

![Yakınlaştırma Toplantıları arşivleme iş akışı.](../media/ZoomMeetingsConnectorWorkflow.png)

1. Kuruluşunuz, Zoom Toplantıları sitesini ayarlamak ve yapılandırmak için Zoom Toplantıları ile birlikte çalışır.

2. Her 24 saatte bir, Zoom Toplantılarından toplantı öğeleri Veritas Merge1 sitesine kopyalanır. Bağlayıcı ayrıca toplantıların içeriğini e-posta iletisi biçimine dönüştürür.

3. Uyumluluk portalında oluşturduğunuz Yakınlaştırma Toplantıları bağlayıcısı, Veritas Merge1'e her gün bağlanır ve toplantı iletilerini Microsoft bulutunda güvenli bir Azure Depolama konumuna aktarır.

4. Bağlayıcı, 3. Adımda açıklandığı gibi, *Email* özelliğinin ve otomatik kullanıcı eşlemesinin değerini kullanarak dönüştürülen toplantı öğelerini belirli kullanıcıların posta kutularına aktarır. Gelen Kutusu klasöründeki **Zoom Meetings** adlı yeni bir alt klasör kullanıcı posta kutularında oluşturulur ve toplantı öğeleri bu klasöre aktarılır. Bağlayıcı bunu *Email* özelliğinin değerini kullanarak yapar. Her toplantı öğesi, toplantının her katılımcısının e-posta adresiyle doldurulan bu özelliği içerir.

## <a name="before-you-begin"></a>Başlamadan önce

- Microsoft bağlayıcıları için bir Veritas Merge1 hesabı oluşturun. Bu hesabı oluşturmak için [Veritas Müşteri Desteği'ne](https://globanet.com/ms-connectors-contact) başvurun. 1. Adımda bağlayıcıyı oluştururken bu hesapta oturum açarsınız.

- Kuruluşunuzun Zoom Business veya Zoom Enterprise hesabının kullanıcı adını ve parolasını alın. Yakınlaştırma Toplantıları bağlayıcısını yapılandırırken 2. Adımda bu hesapta oturum açmanız gerekir.

- [Zoom Market'te](https://marketplace.zoom.us) aşağıdaki uygulamaları oluşturun:

  - OAuth uygulaması

  - JWT uygulaması

  Bu uygulamaları oluşturduktan sonra, Yakınlaştırma platformu belirteçleri oluşturmak için kullanılan bir dizi benzersiz kimlik bilgisi oluşturur. Bu belirteçler, Yakınlaştırma hesabınıza bağlandığında ve öğeleri Merge1 sitesine kopyaladığında bağlayıcının kimliğini doğrulamak için kullanılır. 2. Adımda Yakınlaştırma bağlayıcısını yapılandırırken bu belirteçleri kullanacaksınız.

  OAuth ve JWT uygulamalarını oluşturma hakkında adım adım yönergeler için bkz. [Birleştirme1 Üçüncü Taraf Bağlayıcıları Kullanıcı Kılavuzu](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Zoom%20Meetings%20User%20Guide%20.pdf).

- 1. Adımda Yakınlaştırma Toplantıları bağlayıcısını oluşturan (ve 3. Adımda tamamlayan) kullanıcıya Veri Bağlayıcısı Yönetici rolü atanmalıdır. Bu rol, uyumluluk portalındaki **Veri bağlayıcıları sayfasına bağlayıcı** eklemek için gereklidir. Bu rol varsayılan olarak birden çok rol grubuna eklenir. Bu rol gruplarının listesi için Microsoft 365 Defender ve [Microsoft Purview uyumluluk portallarındaki Roller ve rol grupları bölümündeki "Defender ve uyumluluk portallarındaki roller](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-defender-and-compliance-portals)" bölümüne bakın. Alternatif olarak, kuruluşunuzdaki bir yönetici özel bir rol grubu oluşturabilir, Veri Bağlayıcısı Yönetici rolünü atayabilir ve ardından uygun kullanıcıları üye olarak ekleyebilir. Yönergeler için, [Microsoft Purview uyumluluk portalı İzinler](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group) bölümündeki "Özel rol grubu oluşturma" bölümüne bakın.

- Bu Veritas veri bağlayıcısı, Microsoft 365 US Government bulutundaki GCC ortamlarında genel önizleme aşamasındadır. Üçüncü taraf uygulamalar ve hizmetler, kuruluşunuzun müşteri verilerini Microsoft 365 altyapısının dışında olan ve bu nedenle Microsoft Purview ve veri koruma taahhütleri kapsamında olmayan üçüncü taraf sistemlerde depolamayı, iletmeyi ve işlemeyi içerebilir. Microsoft, üçüncü taraf uygulamalara bağlanmak için bu ürünün kullanıldığının, bu üçüncü taraf uygulamaların FEDRAMP uyumlu olduğunu ifade ettiğini ifade etmemektedir.

## <a name="step-1-set-up-the-zoom-meetings-connector"></a>1. Adım: Yakınlaştırma Toplantıları bağlayıcısını ayarlama

İlk adım, uyumluluk portalında **Veri Bağlayıcıları'na** erişmek ve bir Yakınlaştırma Toplantıları bağlayıcısı oluşturmaktır.

1. **Veri bağlayıcıları** > **Yakınlaştırma Toplantıları'na**[https://compliance.microsoft.com](https://compliance.microsoft.com/) gidin ve bu seçeneği belirleyin.

2. **Yakınlaştırma Toplantıları** ürün açıklaması sayfasında **Bağlayıcı ekle'yi** seçin.

3. **Hizmet koşulları** sayfasında **Kabul Et'i** seçin.

4. Bağlayıcıyı tanımlayan benzersiz bir ad girin ve **İleri'yi** seçin.

5. Bağlayıcıyı yapılandırmak için Merge1 hesabınızda oturum açın.

## <a name="step-2-configure-the-zoom-meetings-connector"></a>2. Adım: Yakınlaştırma Toplantıları bağlayıcısını yapılandırma

İkinci adım, Birleştirme1 sitesinde Yakınlaştırma Toplantıları bağlayıcısını yapılandırmaktır. Veritas Merge1 sitesinde Yakınlaştırma Toplantıları bağlayıcısını yapılandırma hakkında daha fazla bilgi için bkz. [Birleştirme1 Üçüncü Taraf Bağlayıcıları Kullanıcı Kılavuzu](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Zoom%20Meetings%20User%20Guide%20.pdf).

**Kaydet & Son'u** seçtikten sonra, uyumluluk portalındaki bağlayıcı sihirbazındaki **Kullanıcı eşleme** sayfası görüntülenir.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>3. Adım: Kullanıcıları eşleme ve bağlayıcı kurulumunu tamamlama

1. **Dış kullanıcıları Microsoft 365 kullanıcıları ile eşle** sayfasında otomatik kullanıcı eşlemesini etkinleştirin.

   Yakınlaştırma Toplantıları öğeleri, kuruluşunuzdaki kullanıcıların e-posta adreslerini içeren *Email* adlı bir özellik içerir. Bağlayıcı bu adresi bir Microsoft 365 kullanıcısı ile ilişkilendirebiliyorsa, öğeler söz konusu kullanıcının posta kutusuna aktarılır

2. **İleri'yi** seçin, ayarlarınızı gözden geçirin ve yeni bağlayıcının içeri aktarma işleminin ilerleme durumunu görmek için **Veri bağlayıcıları** sayfasına gidin.

## <a name="step-4-monitor-the-zoom-meetings-connector"></a>4. Adım: Yakınlaştırma Toplantıları bağlayıcısını izleme

Yakınlaştırma Toplantıları bağlayıcısını oluşturduktan sonra bağlayıcının durumunu uyumluluk portalında görüntüleyebilirsiniz.

1. Sol gezinti **bölmesinden Veri bağlayıcıları'na** [https://compliance.microsoft.com](https://compliance.microsoft.com) gidin ve bunu seçin.

2. **Bağlayıcılar** sekmesini seçin ve ardından Açılır sayfayı görüntülemek için **Toplantıları Yakınlaştır** bağlayıcısını seçin. Bu sayfa, bağlayıcı hakkındaki özellikleri ve bilgileri içerir.

3. Bağlayıcının durum günlüğünü açmak (veya kaydetmek) için **Kaynakla bağlayıcı durumu** altında **Günlüğü indir** bağlantısını seçin. Bu günlük, Microsoft buluta aktarılan veriler hakkında bilgi içerir. Daha fazla bilgi için bkz. [Veri bağlayıcıları için yönetici günlüklerini görüntüleme](data-connector-admin-logs.md).

## <a name="known-issues"></a>Bilinen sorunlar

- Şu anda 10 MB'tan büyük eklerin veya öğelerin içeri aktarılmasını desteklemiyoruz. Daha büyük öğeler için destek daha sonraki bir tarihte sağlanacaktır.

- Yakınlaştırma Toplantıları bağlayıcısının çalışması için, Yakınlaştırma Toplantıları'nı ayarlarken kayıtları etkinleştirmeniz gerekir.
