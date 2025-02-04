---
title: Microsoft 365'te O2 Ağ verilerini arşivleye bağlayıcı ayarlama
description: Yöneticiler, Microsoft 365'teki O2 mobil ağından SMS ve MMS verilerini içeri aktarmak ve arşiv etmek için bir TeleMessage bağlayıcısı ayarlayabilir. Bu sayede Microsoft 365'teki üçüncü taraf veri kaynaklarından verileri arşivleyebilir, böylece kuruluşunuzun üçüncü taraf verilerini yönetmek için yasal tutma, içerik arama ve bekletme ilkeleri gibi uyumluluk özelliklerini kullanabilirsiniz.
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 04/06/2022
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- tier3
- purview-compliance
- data-connectors
ms.openlocfilehash: 949f9c9bd479c8ac22702ed3cbbf1b2429343128
ms.sourcegitcommit: ab45f2963e0635ff2cb9670f6f7b4c784f6a250e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/02/2022
ms.locfileid: "68812759"
---
# <a name="set-up-a-connector-to-archive-o2-network-data"></a>O2 Ağ verilerini arşivleye bağlayıcı ayarlama

O2 mobil ağından Kısa Mesajlaşma Hizmeti (SMS) iletilerini ve sesli çağrılarını içeri aktarmak ve arşivlemek için Microsoft Purview uyumluluk portalı bir TeleMessage bağlayıcısı kullanın. Bağlayıcıyı ayarlayıp yapılandırdıktan sonra, her gün bir kez kuruluşunuzun O2 Ağına bağlanır ve Microsoft 365'teki posta kutularına SMS ve sesli çağrıları içeri aktarır.

SMS iletileri ve sesli aramalar kullanıcı posta kutularında depolandıktan sonra, O2 Ağ verilerine Dava Tutma, İçerik Arama ve Microsoft 365 bekletme ilkeleri gibi Microsoft Purview özelliklerini uygulayabilirsiniz. Örneğin, İçerik Arama'yı kullanarak O2 Ağ SMS mesajlarında ve sesli aramalarında arama yapabilir veya O2 Ağ verilerini içeren posta kutusunu eBulma (Premium) durumundaki bir koruyucuyla ilişkilendirebilirsiniz. Microsoft 365'te verileri içeri aktarmak ve arşivlerken O2 Ağ bağlayıcısı kullanmak, kuruluşunuzun kamu ve mevzuat ilkeleriyle uyumlu kalmasına yardımcı olabilir.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="overview-of-archiving-o2-network-data"></a>O2 Ağ verilerini arşivleme genel bakış

Aşağıdaki genel bakış, Microsoft 365'te O2 Ağ verilerini arşivlerken bağlayıcı kullanma işlemini açıklar.

![O2 Ağ arşivleme iş akışı.](../media/O2NetworkConnectorWorkflow.png)

1. Kuruluşunuz, O2 Ağ bağlayıcısı ayarlamak için TeleMessage ve O2 ile birlikte çalışır. Daha fazla bilgi için bkz. [O2 Ağ Arşivleyicisi](https://www.telemessage.com/office365-activation-for-o2-network-archiver).

2. Her 24 saatte bir, kuruluşunuzun O2 Ağından gelen SMS mesajları ve sesli aramalar TeleMessage sitesine kopyalanır.

3. Uyumluluk portalında oluşturduğunuz O2 Ağ bağlayıcısı her gün TeleMessage sitesine bağlanır ve önceki 24 saat içindeki SMS iletilerini ve sesli aramaları Microsoft bulutunda güvenli bir Azure Depolama konumuna aktarır. Bağlayıcı ayrıca SMS iletilerinin ve sesli aramaların içeriğini bir e-posta iletisi biçimine dönüştürür.

4. Bağlayıcı, mobil iletişim öğelerini belirli kullanıcıların posta kutusuna aktarır. Belirli bir kullanıcının posta kutusunda **O2 SMS ve Ses Ağı Arşivleyicisi** adlı yeni bir klasör oluşturulur ve öğeler bu klasöre aktarılır. Bağlayıcı bu eşlemeyi *Kullanıcının Email adres* özelliğinin değerini kullanarak yapar. Her SMS mesajı ve sesli arama, iletinin her katılımcısının e-posta adresiyle doldurulmuş olan bu özelliği içerir.

   *Kullanıcının Email adresi* özelliğinin değerini kullanarak otomatik kullanıcı eşlemesine ek olarak, csv eşleme dosyasını karşıya yükleyerek özel eşleme de tanımlayabilirsiniz. Bu eşleme dosyası, kuruluşunuzdaki kullanıcılar için cep telefonu numarasını ve buna karşılık gelen Microsoft 365 e-posta adresini içerir. Hem otomatik kullanıcı eşlemesini hem de özel eşlemeyi etkinleştirirseniz, her O2 öğesi için bağlayıcı önce özel eşleme dosyasına bakar. Kullanıcının cep telefonu numarasına karşılık gelen geçerli bir Microsoft 365 kullanıcısı bulamazsa bağlayıcı, içeri aktarmaya çalıştığı öğenin e-posta adresi özelliğindeki değerleri kullanır. Bağlayıcı, özel eşleme dosyasında veya O2 öğesinin e-posta adresi özelliğinde geçerli bir Microsoft 365 kullanıcısı bulamazsa, öğe içeri aktarılamaz.

## <a name="before-you-set-up-a-connector"></a>Bağlayıcıyı ayarlamadan önce

O2 Ağ verilerini arşivlerken gereken uygulama adımlarından bazıları Microsoft 365'in dışındadır ve uyumluluk merkezinde bağlayıcı oluşturabilmeniz için önce tamamlanması gerekir.

- [TeleMessage'dan O2 Ağ Arşivleyicisi hizmetini](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365/) sipariş edin ve kuruluşunuz için geçerli bir yönetim hesabı alın. Uyumluluk merkezinde bağlayıcıyı oluştururken bu hesapta oturum açmanız gerekir.

- TeleMessage ekleme formlarını doldurabilmeniz ve ileti arşivleme hizmetini O2'den sipariş edebilmeniz için O2 Ağ hesabınızın ve faturalama iletişim bilgilerinizi alın.

- O2 SMS ve Voice Network arşivlemeyi gerektiren tüm kullanıcıları TeleMessage hesabına kaydedin. Kullanıcıları kaydederken, Microsoft 365 hesapları için kullanılan e-posta adresini kullandığınızdan emin olun.

- Çalışanlarınızın O2 mobil ağında şirkete ait ve şirkete ait cep telefonlarına sahip olması gerekir. Microsoft 365'te iletileri arşivleme, çalışana ait veya "Kendi Cihazlarını Getir (KCG) cihazları için kullanılamaz.

- O2 Ağ bağlayıcısı oluşturan kullanıcıya Veri Bağlayıcısı Yönetici rolü atanmalıdır. Bu rol, uyumluluk portalındaki **Veri bağlayıcıları sayfasına bağlayıcı** eklemek için gereklidir. Bu rol varsayılan olarak birden çok rol grubuna eklenir. Bu rol gruplarının listesi için Microsoft 365 Defender ve [Microsoft Purview uyumluluk portallarındaki Roller ve rol grupları bölümündeki "Defender ve uyumluluk portallarındaki roller](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-defender-and-compliance-portals)" bölümüne bakın. Alternatif olarak, kuruluşunuzdaki bir yönetici özel bir rol grubu oluşturabilir, Veri Bağlayıcısı Yönetici rolünü atayabilir ve ardından uygun kullanıcıları üye olarak ekleyebilir. Yönergeler için, [Microsoft Purview uyumluluk portalı İzinler](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group) bölümündeki "Özel rol grubu oluşturma" bölümüne bakın.

- Bu TeleMessage veri bağlayıcısı, Microsoft 365 US Government bulutundaki GCC ortamlarında kullanılabilir. Üçüncü taraf uygulamalar ve hizmetler, kuruluşunuzun müşteri verilerini Microsoft 365 altyapısının dışında olan ve bu nedenle Microsoft Purview ve veri koruma taahhütleri kapsamında olmayan üçüncü taraf sistemlerde depolamayı, iletmeyi ve işlemeyi içerebilir. Microsoft, üçüncü taraf uygulamalara bağlanmak için bu ürünün kullanıldığının, bu üçüncü taraf uygulamaların FEDRAMP uyumlu olduğunu ifade ettiğini ifade etmemektedir.

## <a name="create-an-o2-network-connector"></a>O2 Ağ bağlayıcısı oluşturma

Önceki bölümde açıklanan önkoşulları tamamladıktan sonra uyumluluk portalında bir O2 Ağ bağlayıcısı oluşturabilirsiniz. Bağlayıcı, TeleMessage sitesine bağlanmak ve SMS iletilerini ve sesli çağrıları Microsoft 365'teki ilgili kullanıcı posta kutusu kutularına aktarmak için sağladığınız bilgileri kullanır.

1. [https://compliance.microsoft.com](https://compliance.microsoft.com/) Adresine gidin ve **Veri bağlayıcıları** \> **O2 Ağ'ı** seçin.

2. **O2 Ağ** ürün açıklaması sayfasında **Bağlayıcı ekle'yi** seçin

3. **Hizmet koşulları** sayfasında **Kabul Et'i** seçin.

4. **TeleMessage'da Oturum Aç** sayfasındaki 3. Adım'ın altında aşağıdaki kutulara gerekli bilgileri girin ve **İleri'yi** seçin.

   - **Username:** TeleMessage kullanıcı adınız.

   - **Parola:** TeleMessage parolanız.

5. Bağlayıcı oluşturulduktan sonra açılır pencereyi kapatabilir ve sonraki sayfaya gidebilirsiniz.

6. Kullanıcı eşleme sayfasında otomatik kullanıcı **eşlemesini** etkinleştirin ve **İleri'yi** seçin. Özel eşlemeye ihtiyacınız olması durumunda bir CSV dosyasını karşıya yükleyin ve **İleri'yi** seçin.

7. Ayarlarınızı gözden geçirin ve ardından **Son'u** seçerek bağlayıcıyı oluşturun.

8. Yeni bağlayıcının içeri aktarma işleminin ilerleme durumunu görmek için **Veri bağlayıcıları sayfasındaki Bağlayıcılar** sekmesine gidin.

## <a name="known-issues"></a>Bilinen sorunlar

- Şu anda 10 MB'tan büyük eklerin veya öğelerin içeri aktarılmasını desteklemiyoruz. Daha büyük öğeler için destek daha sonraki bir tarihte sağlanacaktır.
