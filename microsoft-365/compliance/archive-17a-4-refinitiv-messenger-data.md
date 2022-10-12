---
title: Microsoft 365'te Refinitiv Eikon Messenger verilerini arşivleme için bağlayıcı ayarlama
description: Bu verileri Microsoft 365'te içeri aktarmak ve arşivlemek için 17a-4 Refinitiv Eikon Messenger DataParser bağlayıcısı ayarlamayı ve kullanmayı öğrenin.
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
ms.openlocfilehash: 42207af8b272288e6e10d912d19771f58af1a2f2
ms.sourcegitcommit: 8d3c027592a638f411f87d89772dd3d39e92aab0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/12/2022
ms.locfileid: "68534486"
---
# <a name="set-up-a-connector-to-archive-refinitiv-eikon-messenger-data"></a>Refinitiv Eikon Messenger verilerini arşivleme için bağlayıcı ayarlama

[Refinitiv Eikon Messenger'daki](https://www.17a-4.com/refinitiv-messenger-dataparser/) verileri Microsoft 365 kuruluşunuzdaki kullanıcı posta kutularına aktarmak ve arşivlemek için 17a-4 LLC'deki Refinitiv Eikon Messenger DataParser'ı kullanın. DataParser, üçüncü taraf veri kaynağından öğeleri yakalamak ve bu öğeleri Microsoft 365'e aktarmak için yapılandırılmış bir Refinitiv Eikon Messenger bağlayıcısı içerir. Refinitiv Eikon Messenger DataParser bağlayıcısı Refinitiv Eikon Messenger verilerini e-posta iletisi biçimine dönüştürür ve ardından bu öğeleri Microsoft 365'teki kullanıcı posta kutularına aktarır.

Refinitiv Eikon Messenger verileri kullanıcı posta kutularında depolandıktan sonra, Dava Tutma, eBulma, bekletme ilkeleri ve bekletme etiketleri ve iletişim uyumluluğu gibi Microsoft Purview özelliklerini uygulayabilirsiniz. Microsoft 365'te verileri içeri aktarmak ve arşivlemek için Refinitiv Eikon Messenger bağlayıcısı kullanmak, kuruluşunuzun kamu ve mevzuat ilkeleriyle uyumlu kalmasına yardımcı olabilir.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="overview-of-archiving-refinitiv-eikon-messenger-data"></a>Refinitiv Eikon Messenger verilerini arşivleme hakkında genel bakış

Aşağıdaki genel bakış, Microsoft 365'te Refinitiv Eikon Messenger verilerini arşivleme amacıyla veri bağlayıcısı kullanma işlemini açıklar.

![Refinitiv Eikon Messenger verileri için 17a-4 arası arşivleme iş akışı.](../media/RefinitivMessengerDataParserConnectorWorkflow.png)

1. Kuruluşunuz Refinitiv Eikon Messenger DataParser'ı ayarlamak ve yapılandırmak için 17a-4 ile çalışır.

2. Refinitiv Eikon Messenger öğeleri düzenli olarak DataParser tarafından toplanır. DataParser ayrıca iletinin içeriğini e-posta iletisi biçimine dönüştürür.

3. Microsoft Purview uyumluluk portalı oluşturduğunuz Refinitiv Eikon Messenger DataParser bağlayıcısı DataParser'a bağlanır ve iletileri Microsoft bulutunda güvenli bir Azure Depolama konumuna aktarır.

4. Kullanıcı posta kutularında **Refinitiv Eikon Messenger DataParser** adlı Gelen Kutusu klasöründe bir alt klasör oluşturulur ve Refinitiv Eikon Messenger öğeleri bu klasöre aktarılır. Bağlayıcı, *Email* özelliğinin değerini kullanarak öğelerin hangi posta kutusuna aktarılacağını belirler. Her Refinitiv Eikon Messenger öğesi, her katılımcının e-posta adresiyle doldurulan bu özelliği içerir.

## <a name="before-you-set-up-a-connector"></a>Bağlayıcıyı ayarlamadan önce

- Microsoft bağlayıcıları için bir DataParser hesabı oluşturun. Hesap oluşturmak için [17a-4 LLC](https://www.17a-4.com/contact/) ile iletişime geçin. 1. Adımda bağlayıcıyı oluştururken bu hesapta oturum açmanız gerekir.

- 1. Adımda Refinitiv Eikon Messenger DataParser bağlayıcısını oluşturan (ve 3. Adımda tamamlayan) kullanıcıya Veri Bağlayıcısı Yönetici rolü atanmalıdır. Bu rol, uyumluluk portalındaki **Veri bağlayıcıları sayfasına bağlayıcı** eklemek için gereklidir. Bu rol varsayılan olarak birden çok rol grubuna eklenir. Bu rol gruplarının listesi için Güvenlik [& Uyumluluk Merkezi'ndeki İzinler bölümündeki "Güvenlik ve uyumluluk merkezlerindeki](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center) roller" bölümüne bakın. Alternatif olarak, kuruluşunuzdaki bir yönetici özel bir rol grubu oluşturabilir, Veri Bağlayıcısı Yönetici rolünü atayabilir ve ardından uygun kullanıcıları üye olarak ekleyebilir. Yönergeler için, [Microsoft Purview uyumluluk portalı İzinler](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group) bölümündeki "Özel rol grubu oluşturma" bölümüne bakın.

- Bu 17a-4 veri bağlayıcısı, Microsoft 365 US Government bulutundaki GCC ortamlarında kullanılabilir. Üçüncü taraf uygulamalar ve hizmetler, kuruluşunuzun müşteri verilerini Microsoft 365 altyapısının dışında olan ve bu nedenle Microsoft Purview ve veri koruma taahhütleri kapsamında olmayan üçüncü taraf sistemlerde depolamayı, iletmeyi ve işlemeyi içerebilir. Microsoft, üçüncü taraf uygulamalarına bağlanmak için bu ürünün kullanılmasının söz konusu üçüncü taraf uygulamaların FEDRAMP uyumlu olduğunu ifade ettiğini ifade etmemektedir.

## <a name="step-1-set-up-a-refinitiv-eikon-messenger-dataparser-connector"></a>1. Adım: Refinitiv Eikon Messenger DataParser bağlayıcısı ayarlama

İlk adım, uyumluluk portalındaki Veri bağlayıcıları sayfasına erişmek ve Refinitiv Eikon Messenger verileri için bir 17a-4 bağlayıcısı oluşturmaktır.

1. <https://compliance.microsoft.com> **Adresine gidip Veri bağlayıcıları** > **Refinitiv Eikon Messenger DataParser'ı** seçin.

2. **Refinitiv Eikon Messenger DataParser** ürün açıklaması sayfasında **Bağlayıcı ekle'yi** seçin.

3. **Hizmet koşulları** sayfasında **Kabul Et'i** seçin.

4. Bağlayıcıyı tanımlayan benzersiz bir ad girin ve **İleri'yi** seçin.

5. 17a-4 hesabınızda oturum açın ve Refinitiv Eikon Messenger DataParser bağlantı sihirbazındaki adımları tamamlayın.

## <a name="step-2-configure-the-refinitiv-eikon-messenger-dataparser-connector"></a>2. Adım: Refinitiv Eikon Messenger DataParser bağlayıcısını yapılandırma

Refinitiv Eikon Messenger DataParser bağlayıcısını yapılandırmak için 17a-4 Desteği ile çalışın.

## <a name="step-3-map-users"></a>3. Adım: Kullanıcıları eşleme

Refinitiv Eikon Messenger DataParser bağlayıcısı, verileri Microsoft 365'e aktarmadan önce kullanıcıları otomatik olarak Microsoft 365 e-posta adresleriyle eşler.

## <a name="step-4-monitor-the-refinitiv-eikon-messenger-dataparser-connector"></a>4. Adım: Refinitiv Eikon Messenger DataParser bağlayıcısını izleme

Refinitiv Eikon Messenger DataParser bağlayıcısı oluşturduktan sonra bağlayıcının durumunu uyumluluk portalında görüntüleyebilirsiniz.

1. Sol gezinti **bölmesinden Veri bağlayıcıları'na** <https://compliance.microsoft.com> gidin ve bunu seçin.

2. **Bağlayıcılar** sekmesini seçin ve ardından bağlayıcının özelliklerini ve bilgilerini içeren açılır sayfayı görüntülemek için oluşturduğunuz Refinitiv Eikon Messenger DataParser bağlayıcısını seçin.

3. Bağlayıcının durum günlüğünü açmak (veya kaydetmek) için **Kaynakla bağlayıcı durumu** altında **Günlüğü indir** bağlantısını seçin. Bu günlük, Microsoft buluta aktarılan veriler hakkında bilgi içerir. Daha fazla bilgi için bkz. [Veri bağlayıcıları için yönetici günlüklerini görüntüleme](data-connector-admin-logs.md).

## <a name="known-issues"></a>Bilinen sorunlar

Şu anda 10 MB'tan büyük eklerin veya öğelerin içeri aktarılmasını desteklemiyoruz. Daha büyük öğeler için destek daha sonraki bir tarihte sağlanacaktır.
