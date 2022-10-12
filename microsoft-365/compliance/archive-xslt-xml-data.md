---
title: Microsoft 365'te XSLT/XML verilerini arşivleye bağlayıcı ayarlama
description: Yöneticiler, Microsoft 365'te Veritas'tan XSLT/XML verilerini içeri aktarmak ve arşivlemek için bir bağlayıcı ayarlayabilir. Bu bağlayıcı, kuruluşunuzun üçüncü taraf verilerini yönetmek için yasal saklama, içerik arama ve bekletme ilkeleri gibi uyumluluk özelliklerini kullanabilmeniz için Microsoft 365'teki üçüncü taraf veri kaynaklarından verileri arşivleyebilmenizi sağlar.
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
ms.openlocfilehash: 1e1260386974ebef71e8d4c70b4e327be64bb323
ms.sourcegitcommit: 8d3c027592a638f411f87d89772dd3d39e92aab0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/12/2022
ms.locfileid: "68533026"
---
# <a name="set-up-a-connector-to-archive-xsltxml-data"></a>XSLT/XML verilerini arşivleye bağlayıcı ayarlama

Web sayfası kaynağındaki verileri Microsoft 365 kuruluşunuzdaki kullanıcı posta kutularına aktarmak ve arşivlemek için Microsoft Purview uyumluluk portalı bir Veritas bağlayıcısı kullanın. Veritas, XML dosyalarını Microsoft 365'e aktarılabilir diğer dosya biçimlerine (HTML veya metin gibi) dönüştürmek için XSLT (Genişletilebilir Stil Sayfası Dil Dönüştürmeleri) kullanılarak oluşturulan dosyaların hızlı bir şekilde geliştirilmesine olanak tanıyan bir XSLT [/XML bağlayıcısı](https://globanet.com/xslt-xml) sağlar. Bağlayıcı, XSLT/XML kaynağındaki bir öğenin içeriğini e-posta iletisi biçimine dönüştürür ve ardından dönüştürülen öğeyi Microsoft 365 posta kutularına aktarır.

XSLT/XML verileri kullanıcı posta kutularında depolandıktan sonra, Dava Tutma, eBulma ve bekletme ilkeleri ile bekletme etiketleri gibi Microsoft Purview özelliklerini uygulayabilirsiniz. Microsoft 365'te verileri içeri aktarmak ve arşivlerken XSLT/XML bağlayıcısı kullanmak, kuruluşunuzun kamu ve mevzuat ilkeleriyle uyumlu kalmasına yardımcı olabilir.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="overview-of-archiving-xsltxml-data"></a>XSLT/XML verilerini arşivleme genel bakış

Aşağıdaki genel bakış, Microsoft 365'te XSLT/XML kaynak verilerini arşivlerken bağlayıcı kullanma işlemini açıklar.

![XSLT/XML verileri için iş akışı arşivleme.](../media/XSLT-XMLConnectorWorkflow.png)

1. Kuruluşunuz bir XSLT/XML sitesi ayarlamak ve yapılandırmak için XSLT/XML kaynağıyla çalışır.

2. 24 saatte bir, XSLT/XML kaynağından gelen sohbet iletileri Veritas Merge1 sitesine kopyalanır. Bağlayıcı ayrıca içeriği e-posta iletisi biçimine dönüştürür.

3. Uyumluluk portalında oluşturduğunuz XSLT/XML bağlayıcısı her gün Veritas Merge1 sitesine bağlanır ve iletileri Microsoft bulutunda güvenli bir Azure Depolama konumuna aktarır.

4. Bağlayıcı, 3. Adımda açıklandığı gibi otomatik kullanıcı eşlemesinin *Email* özelliğinin değerini kullanarak dönüştürülen ileti öğelerini belirli kullanıcıların posta kutularına aktarır. Kullanıcı posta kutularında Gelen Kutusu klasöründe **XSLT/XML** adlı yeni bir alt klasör oluşturulur ve ileti öğeleri bu klasöre aktarılır. Bağlayıcı bunu *Email* özelliğinin değerini kullanarak yapar. Her ileti, iletinin her katılımcısının e-posta adresiyle doldurulan bu özelliği içerir.

## <a name="before-you-begin"></a>Başlamadan önce

- Microsoft bağlayıcıları için bir Veritas Merge1 hesabı oluşturun. Bu hesabı oluşturmak için [Veritas Müşteri Desteği'ne](https://www.veritas.com/content/support/) başvurun. 1. Adımda bağlayıcıyı oluştururken bu hesapta oturum açarsınız.

- 1. Adımda XSLT/XML bağlayıcısını oluşturan (ve 3. Adımda tamamlayan) kullanıcıya Veri Bağlayıcısı Yönetici rolü atanmalıdır. Bu rol, uyumluluk portalındaki **Veri bağlayıcıları sayfasına bağlayıcı** eklemek için gereklidir. Bu rol varsayılan olarak birden çok rol grubuna eklenir. Bu rol gruplarının listesi için Güvenlik [& Uyumluluk Merkezi'ndeki İzinler bölümündeki "Güvenlik ve uyumluluk merkezlerindeki](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center) roller" bölümüne bakın. Alternatif olarak, kuruluşunuzdaki bir yönetici özel bir rol grubu oluşturabilir, Veri Bağlayıcısı Yönetici rolünü atayabilir ve ardından uygun kullanıcıları üye olarak ekleyebilir. Yönergeler için, [Microsoft Purview uyumluluk portalı İzinler](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group) bölümündeki "Özel rol grubu oluşturma" bölümüne bakın.

- Bu Veritas veri bağlayıcısı, Microsoft 365 US Government bulutundaki GCC ortamlarında genel önizleme aşamasındadır. Üçüncü taraf uygulamalar ve hizmetler, kuruluşunuzun müşteri verilerini Microsoft 365 altyapısının dışında olan ve bu nedenle Microsoft Purview ve veri koruma taahhütleri kapsamında olmayan üçüncü taraf sistemlerde depolamayı, iletmeyi ve işlemeyi içerebilir. Microsoft, üçüncü taraf uygulamalara bağlanmak için bu ürünün kullanıldığının, bu üçüncü taraf uygulamaların FEDRAMP uyumlu olduğunu ifade ettiğini ifade etmemektedir.

## <a name="step-1-set-up-an-xsltxml-connector"></a>1. Adım: XSLT/XML bağlayıcısı ayarlama

İlk adım, uyumluluk portalında **Veri Bağlayıcıları'na** erişmek ve XSLT/XML verileri için bir bağlayıcı oluşturmaktır.

1. [https://compliance.microsoft.com](https://compliance.microsoft.com/) Adresine gidin ve **Veri bağlayıcıları** > **XSLT/XML'i** seçin.

2. **XSLT/XML** ürün açıklaması sayfasında **Yeni bağlayıcı ekle'yi** seçin.

3. **Hizmet koşulları** sayfasında **Kabul Et'i** seçin.

4. Bağlayıcıyı tanımlayan benzersiz bir ad girin ve **İleri'yi** seçin.

5. Bağlayıcıyı yapılandırmak için Merge1 hesabınızda oturum açın.

## <a name="step-2-configure-an-xsltxml-connector"></a>2. Adım: XSLT/XML bağlayıcısı yapılandırma

İkinci adım, Merge1 sitesinde XSLT/XML bağlayıcısını yapılandırmaktır. Veritas Merge1 sitesinde XSLT/XML bağlayıcısını yapılandırma hakkında bilgi için bkz. [Birleştirme1 Üçüncü Taraf Bağlayıcıları Kullanıcı Kılavuzu](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20XSLT-XML%20User%20Guide%20.pdf).

**Kaydet & Son'u** seçtikten sonra, uyumluluk portalındaki bağlayıcı sihirbazındaki **Kullanıcı eşleme** sayfası görüntülenir.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>3. Adım: Kullanıcıları eşleme ve bağlayıcı kurulumunu tamamlama

1. Kullanıcıları eşlemek ve uyumluluk portalında bağlayıcı kurulumunu tamamlamak için aşağıdaki adımları izleyin:

2. **XSLT/XML kullanıcılarını Microsoft 365 kullanıcılarıyla eşle** sayfasında otomatik kullanıcı eşlemesini etkinleştirin. XSLT/XML öğeleri, kuruluşunuzdaki kullanıcıların e-posta adreslerini içeren *Email* adlı bir özellik içerir. Bağlayıcı bu adresi bir Microsoft 365 kullanıcısı ile ilişkilendirebiliyorsa, öğeler söz konusu kullanıcının posta kutusuna aktarılır.

3. **İleri'yi** seçin, ayarlarınızı gözden geçirin ve yeni bağlayıcının içeri aktarma işleminin ilerleme durumunu görmek için **Veri bağlayıcıları** sayfasına gidin.

## <a name="step-4-monitor-the-xsltxml-connector"></a>4. Adım: XSLT/XML bağlayıcısını izleme

XSLT/XML bağlayıcısını oluşturduktan sonra bağlayıcının durumunu uyumluluk portalında görüntüleyebilirsiniz.

1. Sol gezinti **bölmesinden Veri bağlayıcıları'na** [https://compliance.microsoft.com](https://compliance.microsoft.com) gidin ve bunu seçin.

2. **Bağlayıcılar** sekmesini ve ardından açılır sayfayı görüntülemek için **XSLT/XML** bağlayıcısını seçin. Bu sayfa, bağlayıcı hakkındaki özellikleri ve bilgileri içerir.

3. Bağlayıcının durum günlüğünü açmak (veya kaydetmek) için **Kaynakla bağlayıcı durumu** altında **Günlüğü indir** bağlantısını seçin. Bu günlük, Microsoft buluta aktarılan veriler hakkında bilgi içerir. Daha fazla bilgi için bkz. [Veri bağlayıcıları için yönetici günlüklerini görüntüleme](data-connector-admin-logs.md).

## <a name="known-issues"></a>Bilinen sorunlar

- Şu anda 10 MB'tan büyük eklerin veya öğelerin içeri aktarılmasını desteklemiyoruz. Daha büyük öğeler için destek daha sonraki bir tarihte sağlanacaktır.
