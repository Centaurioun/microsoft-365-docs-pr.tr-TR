---
title: TeleMessage Kurumsal Numara Arşivleyicisi'nden verileri arşivleye bir bağlayıcı ayarlama
description: Yöneticiler, TeleMessage Enterprise Number Archiver'dan SMS ve MMS verilerini içeri aktarmak ve arşivlemek için bir bağlayıcı ayarlayabilir. Bu, kuruluşunuzun üçüncü taraf verilerini yönetmek için yasal tutma, içerik arama ve bekletme ilkeleri gibi uyumluluk özelliklerini kullanabilmeniz için Microsoft Purview'daki üçüncü taraf veri kaynaklarından verileri arşivlemenizi sağlar.
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
ms.openlocfilehash: f1547c8f382c243367e7130795282bef8bf13797
ms.sourcegitcommit: 8d3c027592a638f411f87d89772dd3d39e92aab0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/12/2022
ms.locfileid: "68535564"
---
# <a name="set-up-a-connector-to-archive-enterprise-number-data"></a>Kurumsal Numara verilerini arşivleye bağlayıcı ayarlama

Enterprise Number Archiver'dan Kısa Mesajlaşma Hizmeti (SMS) ve Multimedya Mesajlaşma Hizmeti (MMS) iletilerini, sohbet iletilerini, sesli arama kayıtlarını ve sesli arama günlüklerini içeri aktarmak ve arşiv etmek için Microsoft Purview uyumluluk portalı bir TeleMessage bağlayıcısı kullanın. Bağlayıcıyı ayarlayıp yapılandırdıktan sonra, her gün bir kez kuruluşunuzun TeleMessage hesabına bağlanır ve TeleMessage Kurumsal Numara Arşivleyicisi'ni kullanarak çalışanların mobil iletişim verilerini Microsoft 365'teki posta kutularına aktarır.

TeleMessage Kurumsal Numara Arşivleyici bağlayıcısı verileri kullanıcı posta kutularında depolandıktan sonra, Dava Tutma, İçerik Arama, In-Place Arşivleme, Denetim, İletişim uyumluluğu ve Microsoft 365 bekletme ilkeleri gibi Microsoft Purview özelliklerini Kurumsal Numara Arşivleyici verilerine uygulayabilirsiniz. Örneğin, İçerik Arama'yı kullanarak TeleMessage Kurumsal Numara Arşivleyici SMS, MMS ve Sesli Arama'da arama yapabilir veya Kurumsal Numara Arşivleyici bağlayıcısı verilerini içeren posta kutusunu eBulma (Premium) durumundaki bir koruyucuyla ilişkilendirebilirsiniz. Microsoft 365'te verileri içeri aktarmak ve arşivlemek için Kurumsal Numara Arşivleyici bağlayıcısı kullanmak, kuruluşunuzun kamu ve mevzuat ilkeleriyle uyumlu kalmasına yardımcı olabilir.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="overview-of-archiving-enterprise-number-data"></a>Kurumsal Numara verilerini arşivleme genel bakış

Aşağıdaki genel bakış, Microsoft 365'te Kurumsal Ağ verilerini arşivlerken bağlayıcı kullanma işlemini açıklar.

![Kurumsal Numara arşivleme iş akışı.](../media/EnterpriseNumberConnectorWorkflow.png)

1. Kuruluşunuz, Kurumsal Numara Arşivleyici bağlayıcısı ayarlamak için TeleMessage ile birlikte çalışır. Diğer ayrıntılar için [buraya](https://www.telemessage.com/office365-activation-for-enterprise-number-archiver/) bakın.

2. Uyumluluk portalında oluşturduğunuz Kurumsal Numara Arşivleyici bağlayıcısı her gün TeleMessage sitesine bağlanır ve önceki 24 saat içindeki e-posta iletilerini Microsoft Bulut'taki güvenli bir Azure Depolama alanına aktarır.

3. Bağlayıcı, mobil iletişim öğelerini belirli bir kullanıcının posta kutusuna aktarır. Belirli bir kullanıcının posta kutusunda Kurumsal Numara Arşivleyicisi adlı yeni bir klasör oluşturulur ve öğeler bu klasöre aktarılır. Bağlayıcı, *Kullanıcının Email adres* özelliğinin değerini kullanarak eşleme yapar. Her e-posta iletisi, e-posta iletisinin her katılımcısının e-posta adresiyle doldurulmuş olan bu özelliği içerir. *Kullanıcının Email adresi* özelliğinin değerini kullanarak otomatik kullanıcı eşlemesine ek olarak, csv eşleme dosyasını karşıya yükleyerek özel eşleme de tanımlayabilirsiniz. Bu eşleme dosyası Kullanıcının cep telefonu numarasını ve her kullanıcı için karşılık gelen Microsoft 365 posta kutusu adresini içermelidir. Otomatik kullanıcı eşlemesini etkinleştirir ve özel bir eşleme sağlarsanız, bağlayıcı her e-posta öğesi için önce özel eşleme dosyasına bakar. Kullanıcının cep telefonu numarasına karşılık gelen geçerli bir Microsoft 365 kullanıcısı bulamazsa bağlayıcı, e-posta öğesinin Kullanıcının e-posta adresi özelliğini kullanır. Bağlayıcı, özel eşleme dosyasında veya *kullanıcının e-posta öğesinin e-posta adresi* özelliğinde geçerli bir Microsoft 365 kullanıcısı bulamazsa, öğe içeri aktarılamaz.

## <a name="before-you-set-up-a-connector"></a>Bağlayıcıyı ayarlamadan önce

Kurumsal Numara Arşivleyicisi verilerini arşivlerken gereken uygulama adımlarından bazıları Microsoft 365'in dışındadır ve bağlayıcıyı uyumluluk merkezinde oluşturabilmeniz için önce tamamlanması gerekir.

- [TeleMessage'dan Kurumsal Numara Arşivleyicisi hizmetini](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365) sipariş edin ve kuruluşunuz için geçerli bir yönetim hesabı alın. Uyumluluk merkezinde bağlayıcıyı oluştururken bu hesapta oturum açmanız gerekir.

- Kurumsal Numara SMS/MMS Ağ arşivlemeyi gerektiren tüm kullanıcıları TeleMessage hesabına kaydedin. Kullanıcıları kaydederken, Microsoft 365 hesapları için kullanılan e-posta adresini kullandığınızdan emin olun.

- Çalışanlarınızın cep telefonlarına TeleMessage Enterprise Number Archiver uygulamasını yükleyin ve etkinleştirin.

- Kurumsal Sayı Arşivleyici bağlayıcısı oluşturan kullanıcıya Veri Bağlayıcısı Yönetici rolü atanmalıdır. Bu rol, uyumluluk portalındaki **Veri bağlayıcıları sayfasına bağlayıcı** eklemek için gereklidir. Bu rol varsayılan olarak birden çok rol grubuna eklenir. Bu rol gruplarının listesi için Güvenlik [& Uyumluluk Merkezi'ndeki İzinler bölümündeki "Güvenlik ve uyumluluk merkezlerindeki](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center) roller" bölümüne bakın. Alternatif olarak, kuruluşunuzdaki bir yönetici özel bir rol grubu oluşturabilir, Veri Bağlayıcısı Yönetici rolünü atayabilir ve ardından uygun kullanıcıları üye olarak ekleyebilir. Yönergeler için, [Microsoft Purview uyumluluk portalı İzinler](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group) bölümündeki "Özel rol grubu oluşturma" bölümüne bakın.

- Bu TeleMessage veri bağlayıcısı, Microsoft 365 US Government bulutundaki GCC ortamlarında kullanılabilir. Üçüncü taraf uygulamalar ve hizmetler, kuruluşunuzun müşteri verilerini Microsoft 365 altyapısının dışında olan ve bu nedenle Microsoft Purview ve veri koruma taahhütleri kapsamında olmayan üçüncü taraf sistemlerde depolamayı, iletmeyi ve işlemeyi içerebilir. Microsoft, üçüncü taraf uygulamalara bağlanmak için bu ürünün kullanıldığının, bu üçüncü taraf uygulamaların FEDRAMP uyumlu olduğunu ifade ettiğini ifade etmemektedir.

## <a name="create-an-enterprise-number-archiver-connector"></a>Kurumsal Numara Arşivleyici bağlayıcısı oluşturma

Önceki bölümde açıklanan önkoşulları tamamladıktan sonra, uyumluluk portalında bir Kurumsal Numara Arşivleyici bağlayıcısı oluşturabilirsiniz. Bağlayıcı, TeleMessage sitesine bağlanmak ve SMS, MMS ve sesli arama iletilerini Microsoft 365'teki ilgili kullanıcı posta kutusu kutularına aktarmak için sağladığınız bilgileri kullanır.

1. [https://compliance.microsoft.com](https://compliance.microsoft.com/) Adresine gidin ve **Veri bağlayıcıları** \> **Kurumsal Numara Arşivleyicisi'ne** tıklayın.

2. **Kurumsal Numara Arşivleyicisi** ürün açıklaması sayfasında **Bağlayıcı ekle'yi** seçin

3. **Hizmet koşulları** sayfasında **Kabul Et'i** seçin.

4. **TeleMessage'da Oturum Aç** sayfasındaki 3. Adım'ın altında aşağıdaki kutulara gerekli bilgileri girin ve **İleri'yi** seçin.

   - **Username:** TeleMessage kullanıcı adınız.

   - **Parola:** TeleMessage parolanız.

5. Bağlayıcı oluşturulduktan sonra açılır pencereyi kapatabilir ve sonraki sayfaya gidebilirsiniz.

6. Kullanıcı eşleme sayfasında otomatik kullanıcı **eşlemesini** etkinleştirin. Özel eşlemeyi etkinleştirmek için, kullanıcı eşleme bilgilerini içeren bir CSV dosyasını karşıya yükleyin ve **ardından İleri'yi** seçin.

7. Ayarlarınızı gözden geçirin ve ardından **Son'u** seçerek bağlayıcıyı oluşturun.

8. Yeni bağlayıcının içeri aktarma işleminin ilerleme durumunu görmek için **Veri bağlayıcıları sayfasındaki Bağlayıcılar** sekmesine gidin.

## <a name="known-issues"></a>Bilinen sorunlar

- Şu anda 10 MB'tan büyük eklerin veya öğelerin içeri aktarılmasını desteklemiyoruz. Daha büyük öğeler için destek daha sonraki bir tarihte sağlanacaktır.
