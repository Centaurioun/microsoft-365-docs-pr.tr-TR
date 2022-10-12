---
title: Microsoft 365'te Signal iletişim verilerini arşivleye bir bağlayıcı ayarlama
description: Yöneticiler, Microsoft 365'te Signal iletişim verilerini içeri aktarmak ve arşivlemek için bir TeleMessage bağlayıcısı ayarlayabilir. Bu sayede Microsoft 365'teki üçüncü taraf veri kaynaklarından verileri arşivleyebilir, böylece kuruluşunuzun üçüncü taraf verilerini yönetmek için yasal tutma, içerik arama ve bekletme ilkeleri gibi uyumluluk özelliklerini kullanabilirsiniz.
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
ms.openlocfilehash: 617e929d3d4de23445aa4a50cc95c26fea1444c6
ms.sourcegitcommit: 8d3c027592a638f411f87d89772dd3d39e92aab0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/12/2022
ms.locfileid: "68532904"
---
# <a name="set-up-a-connector-to-archive-signal-communications-data"></a>Sinyal iletişim verilerini arşivleye bir bağlayıcı ayarlama

Microsoft Purview uyumluluk portalı TeleMessage bağlayıcısını kullanarak Sinyal sohbetlerini, eklerini, dosyalarını ve silinen iletileri ve çağrıları içeri aktarın ve arşivleyin. Bağlayıcıyı ayarlayıp yapılandırdıktan sonra, kuruluşunuzun TeleMessage hesabına bağlanır ve TeleMessage Signal Archiver'ı kullanarak çalışanların mobil iletişimini Microsoft 365'teki posta kutularına aktarır.

Signal Archiver bağlayıcısı verileri kullanıcı posta kutularında depolandıktan sonra, Signal iletişim verilerine Dava Tutma, İçerik arama ve Microsoft 365 bekletme ilkeleri gibi Microsoft Purview özelliklerini uygulayabilirsiniz. Örneğin, İçerik aramasını kullanarak Sinyal iletişiminde arama yapabilir veya Signal Archiver bağlayıcı verilerini içeren posta kutusunu eBulma (Premium) durumundaki bir koruyucuyla ilişkilendirebilirsiniz. Microsoft 365'te verileri içeri aktarmak ve arşivlemek için Sinyal Arşivleyici bağlayıcısı kullanmak, kuruluşunuzun kurumsal idare düzenlemeleri ve mevzuat ilkeleriyle uyumlu kalmasına yardımcı olabilir.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="overview-of-archiving-signal-communications-data"></a>Sinyal iletişim verilerini arşivleme genel bakış

Aşağıdaki genel bakış, Microsoft 365'te Sinyal iletişim verilerini arşivlerken bağlayıcı kullanma işlemini açıklar.

![Sinyal iletişimleri arşivleme iş akışı.](../media/SignalConnectorWorkflow.png)

1. Kuruluşunuz Bir Signal Archiver bağlayıcısı ayarlamak için TeleMessage ile birlikte çalışır. Daha fazla bilgi için bkz [. Microsoft 365 için TeleMessage Signal Archiver'ı etkinleştirme](https://www.telemessage.com/microsoft-365-activation-for-signal-archiver/).

2. Kuruluşunuzun Sinyal verileri gerçek zamanlı olarak TeleMessage sitesine kopyalanır.

3. Uyumluluk portalında oluşturduğunuz Signal Archiver bağlayıcısı her gün TeleMessage sitesine bağlanır ve önceki 24 saat içindeki e-posta iletilerini Microsoft Bulut'taki güvenli bir Azure Depolama alanına aktarır.

4. Bağlayıcı, mobil iletişim öğelerini belirli bir kullanıcının posta kutusuna aktarır. Belirli bir kullanıcının posta kutusunda Signal Archiver adlı yeni bir klasör oluşturulur ve öğeler bu klasöre aktarılır. Bağlayıcı, *eşlemeyi Kullanıcının Email adresi* özelliğinin değerini kullanarak yapar. Her e-posta iletisi, e-posta iletisinin her katılımcısının e-posta adresiyle doldurulmuş olan bu özelliği içerir.

   *Kullanıcının Email adresi* özelliğinin değerini kullanarak otomatik kullanıcı eşlemesine ek olarak, csv eşleme dosyasını karşıya yükleyerek özel eşleme de tanımlayabilirsiniz. Bu eşleme dosyası Kullanıcının cep telefonu numarasını ve her kullanıcı için karşılık gelen Microsoft 365 posta kutusu adresini içermelidir. Otomatik kullanıcı eşlemesini etkinleştirir ve özel bir eşleme sağlarsanız, bağlayıcı her e-posta öğesi için önce özel eşleme dosyasına bakar. Kullanıcının cep telefonu numarasına karşılık gelen geçerli bir Microsoft 365 kullanıcısı bulamazsa bağlayıcı, e-posta öğesinin Kullanıcının e-posta adresi özelliğini kullanır. Bağlayıcı, özel eşleme dosyasında veya *kullanıcının e-posta öğesinin e-posta adresi* özelliğinde geçerli bir Microsoft 365 kullanıcısı bulamazsa, öğe içeri aktarılamaz.

## <a name="before-you-set-up-a-connector"></a>Bağlayıcıyı ayarlamadan önce

- [TeleMessage'dan Signal Archiver hizmetini](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365/) sipariş edin ve kuruluşunuz için geçerli bir yönetim hesabı alın. Uyumluluk merkezinde bağlayıcıyı oluştururken bu hesapta oturum açmanız gerekir.

- Sinyal arşivlemeyi gerektiren tüm kullanıcıları TeleMessage hesabına kaydedin. Kullanıcıları kaydederken, Microsoft 365 hesapları için kullanılan e-posta adresini kullandığınızdan emin olun.

- Signal Archiver uygulamasını çalışanlarınızın cep telefonlarına yükleyin ve etkinleştirin. Signal Archiver uygulaması, diğer Signal kullanıcılarıyla iletişim kurmalarını ve sohbet etmelerini sağlar.

- 3. Adımda Sinyal Arşivleyici bağlayıcısı oluşturan kullanıcıya Veri Bağlayıcısı Yönetici rolü atanmalıdır. Bu rol, uyumluluk portalındaki **Veri bağlayıcıları sayfasına bağlayıcı** eklemek için gereklidir. Bu rol varsayılan olarak birden çok rol grubuna eklenir. Bu rol gruplarının listesi için Güvenlik [& Uyumluluk Merkezi'ndeki İzinler bölümündeki "Güvenlik ve uyumluluk merkezlerindeki](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center) roller" bölümüne bakın. Alternatif olarak, kuruluşunuzdaki bir yönetici özel bir rol grubu oluşturabilir, Veri Bağlayıcısı Yönetici rolünü atayabilir ve ardından uygun kullanıcıları üye olarak ekleyebilir. Yönergeler için, [Microsoft Purview uyumluluk portalı İzinler](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group) bölümündeki "Özel rol grubu oluşturma" bölümüne bakın.

- Bu TeleMessage veri bağlayıcısı, Microsoft 365 US Government bulutundaki GCC ortamlarında kullanılabilir. Üçüncü taraf uygulamalar ve hizmetler, kuruluşunuzun müşteri verilerini Microsoft 365 altyapısının dışında olan ve bu nedenle Microsoft Purview ve veri koruma taahhütleri kapsamında olmayan üçüncü taraf sistemlerde depolamayı, iletmeyi ve işlemeyi içerebilir. Microsoft, üçüncü taraf uygulamalara bağlanmak için bu ürünün kullanıldığının, bu üçüncü taraf uygulamaların FEDRAMP uyumlu olduğunu ifade ettiğini ifade etmemektedir.

## <a name="create-a-signal-archiver-connector"></a>Sinyal Arşivleyici bağlayıcısı oluşturma

Önceki bölümde açıklanan önkoşulları tamamladıktan sonra uyumluluk portalında Signal Archiver bağlayıcısını oluşturabilirsiniz. Bağlayıcı, TeleMessage sitesine bağlanmak için sağladığınız bilgileri kullanır ve Signal iletişim verilerini Microsoft 365'teki ilgili kullanıcı posta kutusu kutularına aktarır.

1. **Veri bağlayıcıları** > **Sinyal Arşivleyicisi'ne**<https://compliance.microsoft.com> gidin ve bunu seçin.

2. **Signal Archiver** ürün açıklaması sayfasında **Bağlayıcı ekle'yi seçin.**

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
