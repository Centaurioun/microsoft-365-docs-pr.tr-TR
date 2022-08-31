---
title: Microsoft 365 Defender deneme laboratuvarınızı veya pilot ortamınızı ayarlama
description: Microsoft 365 Defender portalına erişin ve Microsoft 365 Defender deneme laboratuvarı ortamınızı ayarlayın
keywords: Deneme kurulumu Microsoft 365 Defender, pilot kurulum Microsoft 365 Defender, Microsoft 365 Defender deneyin Microsoft 365 Defender değerlendirme laboratuvarı kurulumu
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: lovina-saldanha
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
- highpri
ms.topic: article
ms.openlocfilehash: 116efc949edace902b8e71abb27f5c091407fb14
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/31/2022
ms.locfileid: "67482284"
---
# <a name="set-up-your-microsoft-365-defender-trial-in-a-lab-environment"></a>laboratuvar ortamında Microsoft 365 Defender denemenizi ayarlama 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**
- Microsoft 365 Defender 

Bu konu, özel bir laboratuvar ortamı ayarlamanız için size yol gösterir. Üretimde deneme ayarlama hakkında bilgi için yeni [Değerlendirme ve pilot Microsoft 365 Defender](eval-overview.md) kılavuzuna bakın. 

## <a name="create-an-office-365-e5-trial-tenant"></a>Office 365 E5 deneme kiracısı oluşturma
>[!NOTE]
>Zaten bir Office 365 veya Azure Active Directory aboneliğiniz varsa, Office 365 E5 deneme kiracısı oluşturma adımlarını atlayabilirsiniz.

1. [Office 365 E5 ürün portalına](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) gidin ve **Ücretsiz deneme'yi** seçin.

   :::image type="content" source="../../media/mtp-eval-9.png" alt-text="Office 365 E5 ücretsiz deneme sayfası" lightbox="../../media/mtp-eval-9.png":::
  
2. E-posta adresinizi (kişisel veya kurumsal) girerek deneme kaydını tamamlayın. **Hesabı ayarla'ya** tıklayın.

   :::image type="content" source="../../media/mtp-eval-10.png" alt-text="Office 365 E5 deneme kaydı kurulum sayfası" lightbox="../../media/mtp-eval-10.png":::

3. Adınızı, soyadınızı, iş telefon numaranızı, şirket adınızı, şirket boyutunuzu ve ülkenizi veya bölgenizi girin.  

   :::image type="content" source="../../media/mtp-eval-11.png" alt-text="Ad, telefon ve şirket ayrıntılarını soran Office 365 E5 deneme kaydı kurulum sayfası" lightbox="../../media/mtp-eval-11.png":::
   
   > [!NOTE]
   > Burada ayarladığınız ülke veya bölge, Office 365 barındırılacak veri merkezi bölgesini belirler.
  
4. Doğrulama tercihinizi seçin: kısa mesaj veya arama yoluyla. **Doğrulama Kodunu Gönder'e** tıklayın. 

   :::image type="content" source="../../media/mtp-eval-12.png" alt-text="Doğrulama tercihini isteyen Office 365 E5 deneme kaydı kurulum sayfası" lightbox="../../media/mtp-eval-12.png":::

5. Kiracınız için özel etki alanı adını ayarlayın ve **İleri'ye** tıklayın.

   :::image type="content" source="../../media/mtp-eval-13.png" alt-text="Özel etki alanı adınızı ayarlayabileceğiniz Office 365 E5 deneme kaydı kurulum sayfası" lightbox="../../media/mtp-eval-13.png":::
 
6. Kiracı için Genel Yönetici olacak ilk kimliği ayarlayın. **Ad** ve **Parola** girin. **Kaydol'a** tıklayın.

   :::image type="content" source="../../media/mtp-eval-14.png" alt-text="İş kimliğinizi ayarlayabileceğiniz Office 365 E5 deneme kaydı kurulum sayfası" lightbox="../../media/mtp-eval-14.png":::

7. Office 365 E5 deneme kiracısı sağlamayı tamamlamak için **Kuruluma Git'e** tıklayın.

   :::image type="content" source="../../media/mtp-eval-15.png" alt-text="Kuruluma Git düğmesine tıklamayı isteyen Office 365 E5 deneme kaydı kurulum sayfası" lightbox="../../media/mtp-eval-15.png":::

8. Şirket etki alanınızı Office 365 kiracısına bağlayın. [İsteğe bağlı] **Zaten sahip olduğunuz bir etki alanına bağlan'ı** seçin ve etki alanı adınızı yazın. **İleri**'ye tıklayın.

   :::image type="content" source="../../media/mtp-eval-16.png" alt-text="Oturum açma ve e-posta bilgilerinizi kişiselleştirmeniz gereken Office 365 E5 Kurulumu sayfası" lightbox="../../media/mtp-eval-16.png":::
 
9. Etki alanı sahipliğini doğrulamak için txt veya MX kaydı ekleyin. ETKI alanınıza TXT veya MX kaydını ekledikten sonra **Doğrula'yı** seçin.

   :::image type="content" source="../../media/mtp-eval-17.png" alt-text="Etki alanınızı doğrulamak için MX kaydının TXT'sini eklemeniz gereken Office 365 E5 kurulum sayfası" lightbox="../../media/mtp-eval-17.png":::
 
10. [İsteğe bağlı] Kiracınız için daha fazla kullanıcı hesabı oluşturun. **İleri'ye** tıklayarak bu adımı atlayabilirsiniz.

    :::image type="content" source="../../media/mtp-eval-18.png" alt-text="Daha fazla kullanıcı ekleyebileceğiniz Office 365 E5 kurulum sayfası" lightbox="../../media/mtp-eval-18.png":::
 
11. [İsteğe bağlı] Office uygulamalarını indirin. Bu adımı atlamak için **İleri'ye** tıklayın. 

    :::image type="content" source="../../media/mtp-eval-19.png" alt-text="Office uygulamalarınızı yükleyebileceğiniz Office 365 E5 sayfası" lightbox="../../media/mtp-eval-19.png":::

12. [İsteğe bağlı] E-posta iletilerini geçirme. Bu adımı yine atlayabilirsiniz.

    :::image type="content" source="../../media/mtp-eval-20.png" alt-text="E-posta iletilerinin geçirilip geçirilmeyeceğini ayarlayabileceğiniz Office 365 E5" lightbox="../../media/mtp-eval-20.png":::
 
13. çevrimiçi hizmetler'ı seçin. **Exchange'i** seçin ve **İleri'ye** tıklayın. 

    :::image type="content" source="../../media/mtp-eval-21.png" alt-text="çevrimiçi hizmetler seçebileceğiniz Office 365 E5" lightbox="../../media/mtp-eval-21.png":::

14. Etki alanınıza MX, CNAME ve TXT kayıtlarını ekleyin. Tamamlandığında **Doğrula'yı** seçin.

    :::image type="content" source="../../media/mtp-eval-22.png" alt-text="Buradaki Office 365 E5 DNS kayıtlarınızı ekleyebilirsiniz" lightbox="../../media/mtp-eval-22.png":::
 
15. Tebrikler, Office 365 kiracınızın sağlamasını tamamladınız.

    :::image type="content" source="../../media/mtp-eval-23.png" alt-text="kurulumu tamamlama onayı Office 365 E5 sayfası" lightbox="../../media/mtp-eval-23.png":::
    

## <a name="enable-microsoft-365-trial-subscription"></a>Microsoft 365 deneme aboneliğini etkinleştirme

>[!NOTE]
>Deneme sürümüne kaydolmak, size bir ay boyunca kullanabileceğiniz 25 kullanıcı lisansı verir. Ayrıntılar için bkz. [Microsoft 365 aboneliğini deneme veya satın alma](../../commerce/try-or-buy-microsoft-365.md) .

1. [Microsoft 365 Yönetici Merkezi'nde](https://admin.microsoft.com/) **Faturalama'ya** tıklayın ve ardından **Hizmetleri satın al'a** gidin.

2. **Microsoft 365 E5'ı** seçin ve **Ücretsiz denemeyi başlat'a** tıklayın. 

   :::image type="content" source="../../media/mtp-eval-24.png" alt-text="ücretsiz denemeyi Microsoft 365 E5 başlat sayfası" lightbox="../../media/mtp-eval-24.png":::

3. Doğrulama tercihinizi seçin: kısa mesaj veya arama yoluyla. Karar verdikten sonra telefon numarasını girin, Seçiminize bağlı olarak **Bana mesaj gönder'i** veya **Beni ara'yı** seçin.

   :::image type="content" source="../../media/mtp-eval-25.png" alt-text="Robot olmadığınızı kanıtlamak için kod göndermek için iletişim bilgilerini isteyen Microsoft 365 E5 Ücretsiz denemeyi başlat sayfası" lightbox="../../media/mtp-eval-25.png":::
 
4. Doğrulama kodunu girin ve **Ücretsiz denemenizi başlatın'a** tıklayın.

   :::image type="content" source="../../media/mtp-eval-26.png" alt-text="Robot olmadığınızı kanıtlamak için sistemin gönderdiği doğrulama kodunu doldurabileceğiniz Microsoft 365 E5 Ücretsiz denemeyi başlat sayfası" lightbox="../../media/mtp-eval-26.png":::

5. Microsoft 365 E5 deneme sürümünüzü onaylamak için **Şimdi deneyin'e** tıklayın.

   :::image type="content" source="../../media/mtp-eval-27.png" alt-text="Başlamak için Şimdi dene düğmesini saatle Microsoft 365 E5 Ücretsiz denemeyi başlat sayfası" lightbox="../../media/mtp-eval-27.png":::
 
6. **Microsoft 365 Yönetici Merkezi** > **Kullanıcıları** > **Etkin kullanıcıları'na** gidin. Kullanıcı hesabınızı seçin, **Ürün lisanslarını yönet'i** seçin, ardından lisansı Office 365 E5 **Microsoft 365 E5** olarak değiştirin. **Kaydet**'e tıklayın.

   :::image type="content" source="../../media/mtp-eval-28.png" alt-text="Microsoft 365 E5 lisansını seçebileceğiniz Microsoft 365 Yönetici Merkezi sayfası" lightbox="../../media/mtp-eval-28.png":::
 
7. Genel yönetici hesabını yeniden seçin ve **ardından Kullanıcı adını yönet'e** tıklayın.

   :::image type="content" source="../../media/mtp-eval-29.png" alt-text="Hesap ve Kullanıcı adını yönet'i seçebileceğiniz Microsoft 365 Yönetici Merkezi sayfası" lightbox="../../media/mtp-eval-29.png":::

8. [İsteğe bağlı] Önceki adımlarda seçtiklerinize bağlı olarak etki alanını *onmicrosoft.com* kendi etki alanınıza değiştirin. **Değişiklikleri kaydet**’e tıklayın.

   :::image type="content" source="../../media/mtp-eval-30.png" alt-text="Etki alanı tercihinizi değiştirebileceğiniz Microsoft 365 Yönetici Merkezi sayfası" lightbox="../../media/mtp-eval-30.png":::

## <a name="next-step"></a>Sonraki adım
|[3. Aşama: ekleme & yapılandırma](config-m365d-eval.md) | Microsoft 365 Defender deneme laboratuvarınız veya pilot ortamınız için her Microsoft 365 Defender sütununu yapılandırın ve uç noktalarınızı ekleme.
|:-------|:-----|
