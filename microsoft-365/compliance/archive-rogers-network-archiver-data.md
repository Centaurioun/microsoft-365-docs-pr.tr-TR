---
title: Microsoft 365'te Rogers Network verilerini arşivleye bağlayıcı ayarlama
description: Yöneticiler, Microsoft 365'te Rogers Network verilerini içeri aktarmak ve arşiv etmek için bir TeleMessage bağlayıcısı ayarlayabilir. Bu sayede Microsoft 365'teki üçüncü taraf veri kaynaklarından verileri arşivleyebilir, böylece kuruluşunuzun üçüncü taraf verilerini yönetmek için yasal tutma, içerik arama ve bekletme ilkeleri gibi uyumluluk özelliklerini kullanabilirsiniz.
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
ms.openlocfilehash: 6ab8805ba76bd93bd02806a25a0c62ae2fb1c2a0
ms.sourcegitcommit: 8d3c027592a638f411f87d89772dd3d39e92aab0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/12/2022
ms.locfileid: "68535256"
---
# <a name="set-up-a-connector-to-archive-rogers-network-data"></a>Rogers Network verilerini arşivleye bir bağlayıcı ayarlama

Rogers mobil ağından SMS ve MMS verilerini içeri aktarmak ve arşiv etmek için Microsoft Purview uyumluluk portalı TeleMessage bağlayıcısını kullanın. [Rogers Network Archiver bağlayıcısını](https://www.telemessage.com/mobile-archiver/network-archiver/rogers/) ayarlayıp yapılandırdıktan sonra kuruluşunuzun Rogers mobil ağına bağlanır ve SMS ve MMS verilerini Microsoft 365'teki posta kutularına aktarır.

Rogers mobil ağındaki veriler kullanıcı posta kutularında depolandıktan sonra, verilere Dava Tutma, İçerik araması ve Microsoft 365 bekletme ilkeleri gibi Microsoft Purview özelliklerini uygulayabilirsiniz. Örneğin, İçerik araması veya Microsoft Purview eKeşif (Standart) servis talebiyle ilişkilendirilmiş bir arama kullanarak Rogers mobil ağından SMS ve MMS iletilerini arayabilirsiniz. Microsoft 365'te verileri içeri aktarmak ve arşivlemek için Rogers Network Archiver bağlayıcısı kullanmak, kuruluşunuzun kurumsal idare düzenlemeleri ve mevzuat ilkeleriyle uyumlu kalmasına yardımcı olabilir.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="overview-of-archiving-rogers-mobile-network-data"></a>Rogers mobil ağ verilerini arşivleme hakkında genel bakış

Aşağıdaki genel bakış, Bağlayıcı kullanarak Rogers SMS ve MMS verilerini Microsoft 365'te arşivlemektedir.

![Rogers Ağ arşivleme iş akışı.](../media/RogersNetworkConnectorWorkflow.png)

1. Kuruluşunuz, Rogers Network Archiver bağlayıcısı ayarlamak için TeleMessage ile birlikte çalışır. Daha fazla bilgi için bkz [. Microsoft 365 için TeleMessage Rogers Ağ Arşivleyicisini Etkinleştirme](https://www.telemessage.com/microsoft-365-activation-for-the-rogers-network-archiver/).

2. Kuruluşunuzun Rogers mobil ağ verileri gerçek zamanlı olarak TeleMessage sitesine kopyalanır.

3. Uyumluluk portalında oluşturduğunuz Rogers Ağ Arşivleyicisi bağlayıcısı her gün TeleMessage sitesine bağlanır ve önceki 24 saat içindeki e-posta iletilerini Microsoft Bulut'taki güvenli bir Azure Depolama alanına aktarır.

4. Bağlayıcı, mobil iletişim öğelerini belirli bir kullanıcının posta kutusuna aktarır. Belirli bir kullanıcının posta kutusunda Rogers SMS/MMS Ağ Arşivleyicisi adlı yeni bir klasör oluşturulur ve öğeler bu klasöre aktarılır. Bağlayıcı, *eşlemeyi Kullanıcının Email adresi* özelliğinin değerini kullanarak yapar. Her e-posta iletisi, e-posta iletisinin her katılımcısının e-posta adresiyle doldurulmuş olan bu özelliği içerir.

   *Kullanıcının Email adresi* özelliğinin değerini kullanarak otomatik kullanıcı eşlemesine ek olarak, csv eşleme dosyasını karşıya yükleyerek özel eşleme de tanımlayabilirsiniz. Bu eşleme dosyası Kullanıcının cep telefonu numarasını ve her kullanıcı için karşılık gelen Microsoft 365 posta kutusu adresini içermelidir. Otomatik kullanıcı eşlemesini etkinleştirir ve özel bir eşleme sağlarsanız, bağlayıcı her e-posta öğesi için önce özel eşleme dosyasına bakar. Kullanıcının cep telefonu numarasına karşılık gelen geçerli bir Microsoft 365 kullanıcısı bulamazsa, bağlayıcı kullanıcının e-posta öğesinin e-posta adresi özelliğini kullanır. Bağlayıcı, özel eşleme dosyasında veya *kullanıcının e-posta öğesinin e-posta adresi* özelliğinde geçerli bir Microsoft 365 kullanıcısı bulamazsa, öğe içeri aktarılamaz.

## <a name="before-you-set-up-a-connector"></a>Bağlayıcıyı ayarlamadan önce

- [TeleMessage'dan Rogers Network Archiver hizmetini](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365/) sipariş edin ve kuruluşunuz için geçerli bir yönetim hesabı alın. Uyumluluk merkezinde bağlayıcıyı oluştururken bu hesapta oturum açmanız gerekir.

- Rogers Network arşivlemeyi gerektiren tüm kullanıcıları TeleMessage hesabına kaydedin. Kullanıcıları kaydederken, Microsoft 365 hesapları için kullanılan e-posta adresini kullandığınızdan emin olun.

- Çalışanlarınızın O2 mobil ağında şirkete ait ve şirkete ait cep telefonlarına sahip olması gerekir. Microsoft 365'te iletileri arşivleme, çalışana ait veya "Kendi Cihazlarını Getir (KCG) cihazları için kullanılamaz.

- Ekleme formlarını tamamlayabilmeniz ve rogers'tan ileti arşivleme hizmetini sipariş edebilmeniz için kuruluşunuzun Rogers hesabı ve faturalama iletişim bilgilerini alın.

- 3. Adımda Rogers Ağ Arşivleyici bağlayıcısı oluşturan kullanıcıya Veri Bağlayıcısı Yönetici rolü atanmalıdır. Bu rol, uyumluluk portalındaki **Veri bağlayıcıları sayfasına bağlayıcı** eklemek için gereklidir. Bu rol varsayılan olarak birden çok rol grubuna eklenir. Bu rol gruplarının listesi için Güvenlik [& Uyumluluk Merkezi'ndeki İzinler bölümündeki "Güvenlik ve uyumluluk merkezlerindeki](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center) roller" bölümüne bakın. Alternatif olarak, kuruluşunuzdaki bir yönetici özel bir rol grubu oluşturabilir, Veri Bağlayıcısı Yönetici rolünü atayabilir ve ardından uygun kullanıcıları üye olarak ekleyebilir. Yönergeler için, [Microsoft Purview uyumluluk portalı İzinler](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group) bölümündeki "Özel rol grubu oluşturma" bölümüne bakın.

- Bu TeleMessage veri bağlayıcısı, Microsoft 365 US Government bulutundaki GCC ortamlarında kullanılabilir. Üçüncü taraf uygulamalar ve hizmetler, kuruluşunuzun müşteri verilerini Microsoft 365 altyapısının dışında olan ve bu nedenle Microsoft Purview ve veri koruma taahhütleri kapsamında olmayan üçüncü taraf sistemlerde depolamayı, iletmeyi ve işlemeyi içerebilir. Microsoft, üçüncü taraf uygulamalara bağlanmak için bu ürünün kullanıldığının, bu üçüncü taraf uygulamaların FEDRAMP uyumlu olduğunu ifade ettiğini ifade etmemektedir.

## <a name="create-a-rogers-network-archiver-connector"></a>Rogers Network Archiver bağlayıcısı oluşturma

Önceki bölümde açıklanan önkoşulları tamamladıktan sonra, uyumluluk portalında Rogers Ağ Arşivleyicisi bağlayıcısını oluşturabilirsiniz. Bağlayıcı, TeleMessage sitesine bağlanmak ve Rogers SMS/MMS verilerini Microsoft 365'teki ilgili kullanıcı posta kutusu kutularına aktarmak için sağladığınız bilgileri kullanır.

1. <https://compliance.microsoft.com> Adresine gidin ve **Veri bağlayıcıları Rogers** > **Ağ Arşivleyicisi'ne** tıklayın.

2. **Rogers Network Archiver** ürün açıklaması sayfasında **Bağlayıcı ekle'yi** seçin.

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
