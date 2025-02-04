---
title: Microsoft 365'te Slack eKeşif verilerini arşivleye bağlayıcı ayarlama
description: Yöneticiler, Verileri Veritas Slack eKeşif'ten Microsoft 365'e aktarmak ve arşivlemesi için bir bağlayıcı ayarlayabilir. Bu bağlayıcı, Microsoft 365'teki üçüncü taraf veri kaynaklarından verileri arşivlenizi sağlar. Bu verileri arşivledikten sonra, üçüncü taraf verilerini yönetmek için yasal tutma, içerik arama ve bekletme ilkeleri gibi uyumluluk özelliklerini kullanabilirsiniz.
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
ms.openlocfilehash: 1e5cf305c3d87b0d2c10ea90ff3be7014916dbf0
ms.sourcegitcommit: ab45f2963e0635ff2cb9670f6f7b4c784f6a250e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/02/2022
ms.locfileid: "68813154"
---
# <a name="set-up-a-connector-to-archive-slack-ediscovery-data"></a>Slack eKeşif verilerini arşivleye bağlayıcı ayarlama

Microsoft 365 kuruluşunuzdaki posta kutularına sosyal medya, anlık ileti ve belge işbirliği platformlarından üçüncü taraf verileri içeri aktarmak ve arşiv uygulamak için Microsoft Purview uyumluluk portalı bir Veritas bağlayıcısı kullanın. Veritas, üçüncü taraf veri kaynağından (düzenli olarak) öğeleri yakalamak ve ardından bu öğeleri Microsoft 365'e aktarmak için yapılandırılmış bir [Slack](https://globanet.com/slack/) bağlayıcısı sağlar. Slack, Slack API'sinden iletileri ve dosyaları çeker, bunları bir e-posta iletisi biçimine dönüştürür ve ardından öğeyi kullanıcı posta kutularına aktarır.

Slack eBulma verileri kullanıcı posta kutularında depolandıktan sonra, Dava Tutma, eBulma, bekletme ilkeleri ve bekletme etiketleri ve iletişim uyumluluğu gibi Microsoft Purview özelliklerini uygulayabilirsiniz. Microsoft 365'te verileri içeri aktarmak ve arşivlerken Slack bağlayıcısı kullanmak, kuruluşunuzun kamu ve mevzuat ilkeleriyle uyumlu kalmasına yardımcı olabilir.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="overview-of-archiving-slack-ediscovery-data"></a>Slack eKeşif verilerini arşivleme işlemine genel bakış

Aşağıdaki genel bakış, Microsoft 365'te Slack bilgilerini arşivlerken bağlayıcı kullanma işlemini açıklar.

![Slack arşivleme iş akışı.](../media/SlackConnectorWorkflow.png)

1. Kuruluşunuz Slack sitesi ayarlamak ve yapılandırmak için Slack ile birlikte çalışır.

2. 24 saatte bir Slack eKeşif'ten gelen sohbet iletileri Veritas Merge1 sitesine kopyalanır. Bağlayıcı ayrıca sohbet iletisinin içeriğini e-posta iletisi biçimine dönüştürür.

3. Uyumluluk portalında oluşturduğunuz Slack eKeşif bağlayıcısı her gün Veritas Merge1 sitesine bağlanır ve sohbet iletilerini Microsoft bulutunda güvenli bir Azure Depolama konumuna aktarır.

4. Bağlayıcı, 3. Adımda açıklandığı gibi, *Email özelliğinin* ve otomatik kullanıcı eşlemesinin değerini kullanarak dönüştürülen sohbet iletisi öğelerini belirli kullanıcıların posta kutularına aktarır. Kullanıcı posta kutularında Gelen Kutusu klasöründe **Slack eKeşif** adlı yeni bir alt klasör oluşturulur ve sohbet iletisi öğeleri bu klasöre aktarılır. Bağlayıcı, *Email* özelliğinin değerini kullanarak öğelerin hangi posta kutusuna aktarılacağını belirler. Her sohbet iletisi, sohbet iletisinin her katılımcısının e-posta adresiyle doldurulmuş olan bu özelliği içerir.

## <a name="before-you-begin"></a>Başlamadan önce

- Microsoft bağlayıcıları için bir Veritas Merge1 hesabı oluşturun. Hesap oluşturmak için [Veritas Müşteri Desteği'ne](https://globanet.com/ms-connectors-contact) başvurun. 1. Adımda bağlayıcıyı oluştururken bu hesapta oturum açarsınız.

- Kuruluşunuzun Slack kurumsal hesabının kullanıcı adını ve parolasını alın. Slack'i yapılandırırken 2. Adımda bu hesapta oturum açmanız gerekir.

- 1. Adımda Slack eKeşif bağlayıcısını oluşturan (ve 3. Adımda tamamlayan) kullanıcıya Veri Bağlayıcısı Yönetici rolü atanmalıdır. Bu rol, uyumluluk portalındaki **Veri bağlayıcıları sayfasına bağlayıcı** eklemek için gereklidir. Bu rol varsayılan olarak birden çok rol grubuna eklenir. Bu rol gruplarının listesi için Microsoft 365 Defender ve [Microsoft Purview uyumluluk portallarındaki Roller ve rol grupları bölümündeki "Defender ve uyumluluk portallarındaki roller](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-defender-and-compliance-portals)" bölümüne bakın. Alternatif olarak, kuruluşunuzdaki bir yönetici özel bir rol grubu oluşturabilir, Veri Bağlayıcısı Yönetici rolünü atayabilir ve ardından uygun kullanıcıları üye olarak ekleyebilir. Yönergeler için, [Microsoft Purview uyumluluk portalı İzinler](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group) bölümündeki "Özel rol grubu oluşturma" bölümüne bakın.

- Bu Veritas veri bağlayıcısı, Microsoft 365 US Government bulutundaki GCC ortamlarında genel önizleme aşamasındadır. Üçüncü taraf uygulamalar ve hizmetler, kuruluşunuzun müşteri verilerini Microsoft 365 altyapısının dışında olan ve bu nedenle Microsoft Purview ve veri koruma taahhütleri kapsamında olmayan üçüncü taraf sistemlerde depolamayı, iletmeyi ve işlemeyi içerebilir. Microsoft, üçüncü taraf uygulamalara bağlanmak için bu ürünün kullanıldığının, bu üçüncü taraf uygulamaların FEDRAMP uyumlu olduğunu ifade ettiğini ifade etmemektedir.

## <a name="step-1-set-up-the-slack-ediscovery-connector"></a>1. Adım: Slack eKeşif bağlayıcısını ayarlama

İlk adım, uyumluluk portalındaki **Veri Bağlayıcıları** sayfasına erişmek ve Slack verileri için bir bağlayıcı oluşturmaktır.

1. [https://compliance.microsoft.com](https://compliance.microsoft.com/) Adresine gidin ve **Veri bağlayıcıları** > **Slack eKeşif'i** seçin.

2. **Slack eKeşif** ürün açıklaması sayfasında **Bağlayıcı ekle'yi** seçin.

3. **Hizmet koşulları** sayfasında **Kabul Et'i** seçin.

4. Bağlayıcıyı tanımlayan benzersiz bir ad girin ve **İleri'yi** seçin.

5. Bağlayıcıyı yapılandırmak için Merge1 hesabınızda oturum açın.

## <a name="step-2-configure-slack-ediscovery"></a>2. Adım: Slack eKeşif'i yapılandırma

İkinci adım, Merge1 sitesinde Slack eKeşif bağlayıcısını yapılandırmaktır. Veritas Merge1 sitesinde Slack eKeşif bağlayıcısını yapılandırma hakkında daha fazla bilgi için bkz. [Birleştirme1 Üçüncü Taraf Bağlayıcıları Kullanıcı Kılavuzu](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Slack%20eDiscovery%20User%20Guide.pdf).

**Kaydet & Son'u** seçtikten sonra, uyumluluk portalındaki bağlayıcı sihirbazındaki **Kullanıcı eşleme** sayfası görüntülenir.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>3. Adım: Kullanıcıları eşleme ve bağlayıcı kurulumunu tamamlama

1. **Dış kullanıcıları Microsoft 365 kullanıcıları ile eşle** sayfasında otomatik kullanıcı eşlemesini etkinleştirin.

   Slack eBulma öğeleri, kuruluşunuzdaki kullanıcıların e-posta adreslerini içeren *Email* adlı bir özellik içerir. Bağlayıcı bu adresi bir Microsoft 365 kullanıcısı ile ilişkilendirebiliyorsa, öğeler söz konusu kullanıcının posta kutusuna aktarılır.

2. **İleri'yi** seçin, ayarlarınızı gözden geçirin ve yeni bağlayıcının içeri aktarma işleminin ilerleme durumunu görmek için **Veri bağlayıcıları** sayfasına gidin.

## <a name="step-4-monitor-the-slack-ediscovery-connector"></a>4. Adım: Slack eKeşif bağlayıcısını izleme

Slack eKeşif bağlayıcısını oluşturduktan sonra bağlayıcının durumunu uyumluluk portalında görüntüleyebilirsiniz.

1. Sol gezinti **bölmesinden Veri bağlayıcıları'na** [https://compliance.microsoft.com](https://compliance.microsoft.com) gidin ve bunu seçin.

2. Açılır sayfayı görüntülemek için **Bağlayıcılar** sekmesini ve ardından **Slack eKeşif** bağlayıcısını seçin. Bu sayfa, bağlayıcı hakkındaki özellikleri ve bilgileri içerir.

3. Bağlayıcının durum günlüğünü açmak (veya kaydetmek) için **Kaynakla bağlayıcı durumu** altında **Günlüğü indir** bağlantısını seçin. Bu günlük, Microsoft buluta aktarılan veriler hakkında bilgi içerir. Daha fazla bilgi için bkz. [Veri bağlayıcıları için yönetici günlüklerini görüntüleme](data-connector-admin-logs.md).

## <a name="known-issues"></a>Bilinen sorunlar

- Şu anda 10 MB'tan büyük eklerin veya öğelerin içeri aktarılmasını desteklemiyoruz. Daha büyük öğeler için destek daha sonraki bir tarihte sağlanacaktır.
