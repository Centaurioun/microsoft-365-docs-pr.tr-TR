---
title: Microsoft OneDrive LTI'yi Tuval ile tümleştirme
ms.author: danismith
author: DaniEASmith
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: microsoft-365-business
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
ms.localizationpriority: medium
description: Tuval için Microsoft OneDrive LTI ile ödevler oluşturun ve notlayın, kurs içeriği derleyin ve dosyalar üzerinde gerçek zamanlı olarak işbirliği yapın.
ms.openlocfilehash: 405a47ee9ff510e452fa632eaef52b07aba2876b
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68203914"
---
# <a name="integrate-microsoft-onedrive-lti-with-canvas"></a>Microsoft OneDrive LTI'yi Tuval ile tümleştirme

Bu makale, Tuval için Microsoft OneDrive LTI'yi ayarlaması gereken eğitim BT yöneticilerine yöneliktir.

Eğitimciler için Tuval'de OneDrive LTI kullanma yönergeleri için bkz. [Microsoft OneDrive'ı LMS'nizle kullanma](https://support.microsoft.com/topic/use-microsoft-onedrive-with-your-lms-c2ddeb48-f695-4267-94f2-14f7ff1b7bdd).

Microsoft OneDrive LTI'yi Tuval ile tümleştirmek iki adımlı bir işlemdir. İlk adım Tuval'de Microsoft OneDrive'ı etkinleştirirken ikinci adım, Microsoft OneDrive LTI'yi Tuval kurslarında kullanılabilir hale getirir.

## <a name="recommended-browser-settings"></a>Önerilen tarayıcı ayarları

- Tanımlama bilgileri Microsoft OneDrive için etkinleştirilmelidir.
- Açılır pencereler Microsoft OneDrive için engellenmemelidir.

> [!NOTE]
>
> - Tanımlama bilgileri Chrome tarayıcı gizli modunda varsayılan olarak etkin değildir ve etkinleştirilmesi gerekir.
> - Microsoft OneDrive LTI, Microsoft Edge tarayıcısında özel modda çalışır. Tanımlama bilgilerini engellemediğinizden emin olun (varsayılan olarak etkindir).

## <a name="enable-microsoft-onedrive-lti-in-canvas"></a>Tuvalde Microsoft OneDrive LTI'yi etkinleştirme

> [!IMPORTANT]
> Bu tümleştirmeyi gerçekleştiren kişi Canvas yöneticisi ve Microsoft 365 kiracısının yöneticisi olmalıdır.

1. <a href="https://onedrivelti.microsoft.com/admin" target="_blank">Microsoft OneDrive LTI Kayıt Portalı'da</a> oturum açın
2. **Yönetici Onay** düğmesini seçin ve izinleri kabul edin.

   > [!CAUTION]
   > Bu adım gerçekleştirilmezse, aşağıdaki adım size bir hata verir ve hatayı aldıktan sonra bu adımı bir saat boyunca gerçekleştiremezsiniz.

3. **Yeni LTI Kiracısı oluştur** düğmesini seçin. LTI Kaydı sayfasında açılan **listeden Tuval'i** seçin ve Canvas örneğinizin temel URL'sini girin.

   > [!NOTE]
   > Tuval örneğininiz ise, `https://contoso.test.instructure.com`tam URL girilmelidir.

   :::image type="content" source="media/OneDrive-LTI-07.png" alt-text="LTI tüketici platformunu ve URL metin alanını seçmek için açılan alan içeren LTI kiracı yönetimi sayfası.":::

4. **Kopyala** düğmesini (sağdaki iki sayfayı üst üste gösteren bir simge) seçerek JSON'yi kopyalayın. Bu, Tuval'de anahtarı oluşturmak için kullanılır.

   :::image type="content" source="media/OneDrive-LTI-08.png" alt-text="Görüntülenen JSON metnini kopyalayacak ve Tuval'de anahtar oluşturma için kullanılabilir hale getiren kopyala düğmesini gösteren resim.":::

5. Tuval örneğinizde yönetici olarak oturum açın ve sayfanın sol tarafındaki menüden **Geliştirici Anahtarları'nı** seçin. Açılan listeden, sayfanın sağ üst kısmındaki açılan **listedeN LTI Anahtarı'nı** seçerek bir geliştirici anahtarı oluşturun.

   :::image type="content" source="media/OneDrive-LTI-14.png" alt-text="Geliştirici Anahtarları'nın seçili olduğu sol gezinti çubuğunu ve sayfanın sağındaki açılan listeden LTI anahtarı girişini gösteren ekran görüntüsü.":::

6. Yapılandır sayfasındaki **Yöntem** açılan menüsünde, yöntem olarak **JSON Yapıştır'ı** seçin ve 4. Adımda kopyaladığınız JSON metnini görüntülenen metin alanına yapıştırın.

    > [!TIP]
    > **İsteğe Bağlı Adım:** Okulunuzun eğitimcileri, kendi kurslarının gezintisinde hangi bağlantıların görüneceğini kendileri denetlemek isterse kopyalanan JSON'da parametresini değiştirebilirsiniz ``default`` . ``default`` Parametre otomatik olarak ayarlanır``enabled``; ancak parametresini ``default`` ``disabled`` olarak değiştirmek, eğitimcilerin kendi kurslarının gezintisini seçmesine olanak tanır.
    >
    > Eğitimcilerin kurs gezinti bağlantılarını nasıl değiştirebileceği hakkında daha fazla bilgi için bkz. [Kurs Gezintisi bağlantılarını yönetmek Nasıl yaparım??](https://community.canvaslms.com/t5/Instructor-Guide/How-do-I-manage-Course-Navigation-links/ta-p/1020)

7. Ardından **Ek ayarlar** açılan listesini genişletin ve **Gizlilik Düzeyi'ni** **Genel** olarak ayarlayın. 
  
   **Gizlilik Düzeyi'nin** **Genel** olarak ayarlanması, kurs üyelerinin adlarının işbirliği için diğer üyelere görünmesini sağlar.

8. Anahtarı kaydettiğinizde Tuval'de **Kapalı** durumda kullanılabilir duruma gelir. Anahtarı **Açık** duruma getirin ve sonraki adımda kullanılacak **Ayrıntılar** sütununda verilen anahtarı kopyalayın.

   :::image type="content" source="media/OneDrive-LTI-19.png" alt-text="Anahtarı kapalı durumda ayarlanmış Tuval sayfası. Bu özelliğin açık olması ve anahtarın bu sayfadaki ayrıntılar sütunundan kopyalanması gerekir.":::

9. Microsoft OneDrive LTI Kayıt portalına dönün ve anahtarı **Tuval İstemci Kimliği** alanına yapıştırın. Hazır olduğunuzda **İleri'yi** seçin.

   :::image type="content" source="media/OneDrive-LTI-20.png" alt-text="Anahtarın kopyalanması gereken JSON metnini ve metin kutusunu gösteren LTI kiracı kaydı sayfası.":::

10. Değişikliklerinizi gözden geçirin ve kaydedin. Başarılı kayıtta bir ileti görüntülenir.

11. Kayıt ayrıntılarınız, giriş sayfasındaki **LTI Kiracılarını Görüntüle** düğmesi seçilerek de gözden geçirilebilir.

Gelecekteki sürümler ek yönetici onayı gerektirebilir. Bu gibi durumlarda yalnızca 1. ve 2. adımları yinelemeniz gerekir.

## <a name="enable-microsoft-onedrive-lti-in-canvas-courses"></a>Tuval Kurslarında Microsoft OneDrive LTI'yi etkinleştirme

Tuval yöneticisi tüm kurslar için Microsoft OneDrive LTI'yi etkinleştirebilir. Belirli bir kursta (tüm kurslarda değil) Microsoft OneDrive LTI gerekiyorsa, kurs eğitmeninin kurs ayarlarında aynı adımları izlemesi gerekir.

1. Yönetici olarak oturum açın ve **Ayarlar** bölümüne gidin.
2. **Uygulamalar** bölümüne gidin ve **Uygulama Yapılandırmalarını Görüntüle** düğmesini seçin.
3. **Uygulama Ekle** düğmesini seçin.
4. **Yapılandırma Türü** açılan listesinde **İstemci Kimliğine Göre** seçeneğini belirleyin.
5. Daha önce oluşturulan geliştirici anahtarının değerini **İstemci Kimliği** alanına yapıştırın ve **Gönder** düğmesini seçin.

:::image type="content" source="media/OneDrive-LTI-31.png" alt-text="Yapılandırma türü açılan menüsünün altında İstemci kimliğine göre seçeneğini gösteren uygulama ekle sayfası.":::

## <a name="collaboration-settings-for-microsoft-onedrive-lti-in-canvas-courses"></a>Tuval Kurslarında Microsoft OneDrive LTI için İşbirliği Ayarları

OneDrive İşbirliği'nin eğitimciler ve öğrenciler için çalışması için **Dış İşbirliği Araçları** ayarının kapalı olduğundan emin olun. **Dış İşbirliği Aracı** ayarını kapatmak için aşağıdaki adımları izleyin.

1. Tuval'de yönetici olarak oturum açın ve **Ayarlar** bölümüne gidin.
1. **Özellik Seçenekleri** bölümüne ve ardından **Kurs** bölümüne gidin.
1. **Dış İşbirliği Aracı** iki durumlu düğmesini kapalı konuma ayarlayın.

tek tek öğrencilere ve bir kurstaki öğrenci gruplarına işbirlikleri atanabilir. Tuval Grupları'ndaki işbirlikleri şu anda desteklenmemektedir.

Tek tek öğrencilere atama varsayılan olarak çalışır. Öğrenci gruplarına işbirliği atamak için şu adımları izleyin:

1. Canvas'da yönetici olarak oturum açın ve **Geliştirici Anahtarları** bölümüne gidin.
1. değeri `170000000000710` olan anahtarı bulun ve **Açık** olarak ayarlayın.
