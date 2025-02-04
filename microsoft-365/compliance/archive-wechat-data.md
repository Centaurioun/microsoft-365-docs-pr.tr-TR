---
title: Microsoft 365'te WeChat verilerini arşivleye bağlayıcı ayarlama
description: Microsoft 365'te WeChat verilerini içeri aktarmak ve arşiv etmek için Microsoft Purview uyumluluk portalı bir bağlayıcı ayarlayın ve kullanın.
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
ms.openlocfilehash: 9f5e3a9d5b168c7b43a6c4f96bd143e0b205178c
ms.sourcegitcommit: ab45f2963e0635ff2cb9670f6f7b4c784f6a250e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/02/2022
ms.locfileid: "68814512"
---
# <a name="set-up-a-connector-to-archive-wechat-data"></a>WeChat verilerini arşivleye bağlayıcı ayarlama

WeChat ve WeCom çağrılarını, sohbetleri, ekleri, dosyaları ve geri çağrıları içeri aktarmak ve arşiv etmek için Microsoft Purview uyumluluk portalı TeleMessage bağlayıcısını kullanın. Bağlayıcıyı ayarlayıp yapılandırdıktan sonra, kuruluşunuzun TeleMessage hesabına bağlanır ve TeleMessage WeChat Arşivleyicisi'ni kullanarak çalışanların mobil iletişimini Microsoft 365'teki posta kutularına aktarır.

WeChat Arşivleyici bağlayıcısı verileri kullanıcı posta kutularında depolandıktan sonra, Dava Tutma, eBulma, In-Place Arşivleme, Denetim, İletişim uyumluluğu ve Microsoft 365 bekletme ilkeleri gibi Microsoft Purview özelliklerini WeChat iletişim verilerine uygulayabilirsiniz. Örneğin, İçerik Arama'yı kullanarak WeChat iletişiminde arama yapabilir veya WeChat Archiver bağlayıcı verilerini içeren posta kutusunu eBulma (Premium) durumundaki bir koruyucuyla ilişkilendirebilirsiniz. Microsoft 365'te verileri içeri aktarmak ve arşivlemek için WeChat Arşivleyici bağlayıcısı kullanmak, kuruluşunuzun kurumsal idare düzenlemeleri ve mevzuat ilkeleriyle uyumlu kalmasına yardımcı olabilir.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="overview-of-archiving-wechat-communication-data"></a>WeChat iletişim verilerini arşivleme hakkında genel bakış

Aşağıdaki genel bakış, Microsoft 365'te WeChat iletişim verilerini arşivleyen bir bağlayıcı kullanma işlemini açıklar.

![WeChat Arşivleyici verileri için arşivleme iş akışı.](../media/WeChatConnectorWorkflow.png)

1. Kuruluşunuz, WeChat Archiver bağlayıcısı ayarlamak için TeleMessage ile birlikte çalışır.

2. Kuruluşunuzun WeChat verileri gerçek zamanlı olarak TeleMessage sitesine kopyalanır.

3. Uyumluluk portalında oluşturduğunuz WeChat Arşivleyici bağlayıcısı her gün TeleMessage sitesine bağlanır ve önceki 24 saat içindeki e-posta iletilerini Microsoft Bulut'taki güvenli bir Azure Depolama alanına aktarır.

4. Bağlayıcı, mobil iletişim öğelerini belirli bir kullanıcının posta kutusuna aktarır. Belirli bir kullanıcının posta kutusunda WeChat Archiver adlı yeni bir klasör oluşturulur ve öğeler bu klasöre aktarılır. Bağlayıcı, *Kullanıcının Email adres* özelliğinin değerini kullanarak eşleme yapar. Her e-posta iletisi, e-posta iletisinin her katılımcısının e-posta adresiyle doldurulmuş olan bu özelliği içerir. *Kullanıcının Email adresi* özelliğinin değerini kullanarak otomatik kullanıcı eşlemesine ek olarak, csv eşleme dosyasını karşıya yükleyerek özel eşleme de tanımlayabilirsiniz. Bu eşleme dosyası Kullanıcının cep telefonu numarasını ve her kullanıcı için karşılık gelen Microsoft 365 posta kutusu adresini içermelidir. Otomatik kullanıcı eşlemesini etkinleştirir ve özel bir eşleme sağlarsanız, bağlayıcı her e-posta öğesi için önce özel eşleme dosyasına bakar. Kullanıcının cep telefonu numarasına karşılık gelen geçerli bir Microsoft 365 kullanıcısı bulamazsa bağlayıcı, e-posta öğesinin Kullanıcının e-posta adresi özelliğini kullanır. Bağlayıcı, özel eşleme dosyasında veya *kullanıcının e-posta öğesinin e-posta adresi* özelliğinde geçerli bir Microsoft 365 kullanıcısı bulamazsa, öğe içeri aktarılamaz.

## <a name="before-you-set-up-a-connector"></a>Bağlayıcıyı ayarlamadan önce

- WeChat arşiv bağlayıcısı ayarlamak için TeleMessage ile çalışın. Daha fazla bilgi için bkz [. Microsoft 365 için TeleMessage WeChat Archiver'ı etkinleştirme](https://www.telemessage.com/microsoft-365-activation-for-wechat-archiver/).

- Microsoft 365 için bir TeleMessage bağlayıcısı ayarlayın ve geçerli bir şirket yönetim hesabı alın. Daha fazla bilgi için bkz [. Microsoft 365 Mobil Arşivleme'yi sipariş etme](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-microsoft-365/).

- WeChat arşivlemeyi gerektiren tüm kullanıcıları TeleMessage hesabına kullanıcının Microsoft 365 hesabı için kullanılan e-posta adresiyle kaydedin.

- Tencent WeCom uygulamasını kuruluşunuzdaki kullanıcıların cep telefonlarına yüklemeniz ve etkinleştirmeniz gerekir. WeCom uygulaması, kullanıcıların diğer WeChat ve WeCom kullanıcılarıyla iletişim kurmasını ve sohbetini sağlar.

- Uyumluluk portalında WeChat Arşivleyici bağlayıcısı oluşturan kullanıcıya Veri Bağlayıcısı Yönetici rolü atanmalıdır. Bu rol, uyumluluk portalındaki **Veri bağlayıcıları sayfasına bağlayıcı** eklemek için gereklidir. Bu rol varsayılan olarak birden çok rol grubuna eklenir. Bu rol gruplarının listesi için Microsoft 365 Defender ve [Microsoft Purview uyumluluk portallarındaki Roller ve rol grupları bölümündeki "Defender ve uyumluluk portallarındaki roller](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-defender-and-compliance-portals)" bölümüne bakın. Alternatif olarak, kuruluşunuzdaki bir yönetici özel bir rol grubu oluşturabilir, Veri Bağlayıcısı Yönetici rolünü atayabilir ve ardından uygun kullanıcıları üye olarak ekleyebilir. Yönergeler için, [Microsoft Purview uyumluluk portalı İzinler](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group) bölümündeki "Özel rol grubu oluşturma" bölümüne bakın.

- Bu TeleMessage veri bağlayıcısı, Microsoft 365 US Government bulutundaki GCC ortamlarında kullanılabilir. Üçüncü taraf uygulamalar ve hizmetler, kuruluşunuzun müşteri verilerini Microsoft 365 altyapısının dışında olan ve bu nedenle Microsoft Purview ve veri koruma taahhütleri kapsamında olmayan üçüncü taraf sistemlerde depolamayı, iletmeyi ve işlemeyi içerebilir. Microsoft, üçüncü taraf uygulamalara bağlanmak için bu ürünün kullanıldığının, bu üçüncü taraf uygulamaların FEDRAMP uyumlu olduğunu ifade ettiğini ifade etmemektedir.

## <a name="create-a-wechat-archiver-connector"></a>WeChat Arşivleyici bağlayıcısı oluşturma

Uyumluluk portalında bir WeChat Arşivleyici bağlayıcısı oluşturmak için bu bölümdeki adımları izleyin. Bağlayıcı, TeleMessage sitesine bağlanmak ve WeChat iletişim verilerini Microsoft 365'teki ilgili kullanıcı posta kutularına aktarmak için sağladığınız bilgileri kullanır.

1. Veri **bağlayıcıları** > **WeChat Arşivleyicisi'ne**<https://compliance.microsoft.com> gidin ve bunu seçin.

2. **WeChat Archiver** ürün açıklaması sayfasında **Bağlayıcı ekle'yi** seçin

3. **Hizmet koşulları** sayfasında **Kabul Et'i** seçin.

4. **TeleMessage'da Oturum Aç** sayfasındaki 3. Adım'ın altında aşağıdaki kutulara gerekli bilgileri girin ve **İleri'yi** seçin.

    - **Kullanıcı adı**: TeleMessage kullanıcı adınız.

    - **Parola**: TeleMessage parolanız.

5. Bağlayıcı oluşturulduktan sonra açılır pencereyi kapatarak sonraki sayfaya gidebilirsiniz.

6. Kullanıcı eşleme sayfasında otomatik kullanıcı **eşlemesini** etkinleştirin. Özel kullanıcı eşleme CSV dosyasını da karşıya yükleyebilirsiniz.

7. **İleri'yi** seçin, ayarlarınızı gözden geçirin ve ardından **Son'u** seçerek bağlayıcıyı oluşturun.

8. Yeni **bağlayıcının** içeri aktarma işleminin ilerleme durumunu görmek için **Veri bağlayıcıları sayfasındaki Bağlayıcılar** sekmesine gidin.

## <a name="known-issues"></a>Bilinen sorunlar

- Şu anda 10 MB'tan büyük eklerin veya öğelerin içeri aktarılmasını desteklemiyoruz. Daha büyük öğeler için destek daha sonraki bir tarihte sağlanacaktır.
