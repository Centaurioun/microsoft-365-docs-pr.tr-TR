---
title: Android'de Uç Nokta için Microsoft Defender sorunlarını giderme
description: Android'de Uç Nokta için Microsoft Defender sorunlarını giderme
keywords: microsoft, defender, Uç Nokta için Microsoft Defender, mde, android, bulut, bağlantı, iletişim
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 73e87075f17413e361f380d7556dc3988ac4a7f7
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67693333"
---
# <a name="troubleshooting-issues-on-microsoft-defender-for-endpoint-on-android"></a>Android'de Uç Nokta için Microsoft Defender sorunlarını giderme

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Bir cihazı eklerken, uygulama yüklendikten sonra oturum açma sorunları görebilirsiniz.

Ekleme sırasında, uygulama cihazınıza yüklendikten sonra oturum açma sorunlarıyla karşılaşabilirsiniz.

Bu makalede, oturum açma sorunlarını gidermeye yardımcı olacak çözümler sağlanır.

## <a name="sign-in-failed---unexpected-error"></a>Oturum açma başarısız oldu - beklenmeyen hata

**Oturum açılamadı:** *Beklenmeyen hata, daha sonra deneyin*

:::image type="content" source="images/f9c3bad127d636c1f150d79814f35d4c.png" alt-text="Oturum açma başarısız oldu hatası Microsoft Defender 365 portalının oturum açma sayfasında beklenmeyen hata." lightbox="images/f9c3bad127d636c1f150d79814f35d4c.png":::

**İleti:**

Beklenmeyen hata, daha sonra deneyin

**Neden:**

Cihazınızda "Microsoft Authenticator" uygulamasının eski bir sürümü yüklüdür.

**Çözüm:**

Google Play Store'dan en son sürümü ve [Microsoft Authenticator'ı](https://play.google.com/store/apps/details?id=com.azure.authenticator) yükleyin ve yeniden deneyin.

## <a name="sign-in-failed---invalid-license"></a>Oturum açılamadı - geçersiz lisans

**Oturum açılamadı:** *Geçersiz lisans, lütfen yöneticiye başvurun*

:::image type="content" source="images/920e433f440fa1d3d298e6a2a43d4811.png" alt-text="Microsoft Defender 365 portalının oturum açma sayfasındaki yönerge iletişim ayrıntıları" lightbox="images/920e433f440fa1d3d298e6a2a43d4811.png":::

**İleti:** *Geçersiz lisans, lütfen yöneticiye başvurun*

**Neden:**

Atanmış Microsoft 365 lisansınız veya kuruluşunuzun Microsoft 365 Kurumsal aboneliği lisansı yok.

**Çözüm:**

Yardım için yöneticinize başvurun.

## <a name="report-unsafe-site"></a>Güvenli olmayan siteyi bildir

Kimlik avı web siteleri, kişisel veya finansal bilgilerinizi almak amacıyla güvenilir web sitelerini taklit ediyor. Kimlik avı sitesi olabilecek bir web sitesini bildirmek istiyorsanız [Ağ koruması hakkında geri bildirim sağlayın](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) sayfasını ziyaret edin.

## <a name="phishing-pages-arent-blocked-on-some-oem-devices"></a>Kimlik avı sayfaları bazı OEM cihazlarında engellenmez

**Şunlar için geçerlidir:** Yalnızca belirli OEM'ler

- **Xiaomi**

Android için Uç Nokta için Defender tarafından algılanan kimlik avı ve zararlı web tehditleri bazı Xiaomi cihazlarında engellenmez. Aşağıdaki işlevler bu cihazlarda çalışmaz.

:::image type="content" source="images/0c04975c74746a5cdb085e1d9386e713.png" alt-text="Site güvenli olmayan bir bildirim iletisi" lightbox="images/0c04975c74746a5cdb085e1d9386e713.png":::

**Neden:**

Xiaomi cihazları yeni bir izin modeli içerir. Bu, Android için Uç Nokta için Defender'ın arka planda çalışırken açılır pencereleri görüntülemesini engeller.

Xiaomi cihazları izni: "Arka planda çalışırken açılır pencereleri görüntüle."

:::image type="content" source="images/6e48e7b29daf50afddcc6c8c7d59fd64.png" alt-text="Microsoft Defender 365 portalındaki açılır ayar bölmesi" lightbox="images/6e48e7b29daf50afddcc6c8c7d59fd64.png":::

**Çözüm:**

Xiaomi cihazlarında gerekli izni etkinleştirin.

- Arka planda çalışırken açılır pencereleri görüntüleyin.

## <a name="unable-to-allow-permission-for-permanent-protection-during-onboarding-on-some-oem-devices"></a>Bazı OEM cihazlarında ekleme sırasında 'Kalıcı koruma' izni verilemiyor


**Şunlar için geçerlidir:** Yalnızca belirli OEM cihazları.

- **Xiaomi**

Defender Uygulaması, uygulama ekleme işleminin bir parçası olarak cihazlarda Pil İyileştirme/Kalıcı Koruma izni ister ve **İzin Ver'i** seçmek iznin ayarlanamadığı bir hata döndürür. Yalnızca "Kalıcı Koruma" adlı son izni etkiler. 

**Neden:**

Xiaomi, Android 11'de pil iyileştirme izinlerini değiştirdi. Uç Nokta için Defender'ın pil iyileştirmelerini yoksaymak için bu ayarı yapılandırmasına izin verilmez.

**Çözüm:**

>[!IMPORTANT]
>Bu sorun çözüldü. Ekleme işlemini tamamlamak için lütfen en son uygulama sürümüne güncelleştirin. Sorun devam ederse lütfen **[uygulama içi geri bildirim](/microsoft-365/security/defender-endpoint/android-support-signin#send-in-app-feedback)** gönderin.


## <a name="send-in-app-feedback"></a>Uygulama içi geri bildirim gönderme

Bir kullanıcı yukarıdaki bölümlerde henüz ele alınmamış bir sorunla karşılaşıyorsa veya listelenen adımları kullanarak çözülemiyorsa, kullanıcı **tanılama verileriyle** birlikte **uygulama içi geri bildirim** sağlayabilir. Ekibimiz daha sonra doğru çözümü sağlamak için günlükleri araştırabilir. Kullanıcılar aynı işlemi yapmak için aşağıdaki adımları izleyebilir:

1. Cihazınızda **MDE uygulamasını** açın ve sol üst köşedeki **profil simgesine** tıklayın.

    :::image type="content" source="images/select-profile-icon-1.jpg" alt-text="Uç Nokta için Microsoft Defender portalındaki profil simgesi" lightbox="images/select-profile-icon-1.jpg":::

2. "Geri bildirim & yardım" öğesini seçin.

    :::image type="content" source="images/selecthelpandfeedback2.png" alt-text="Uç Nokta için Microsoft Defender portalında seçilebilen Yardım & geri bildirim seçeneği" lightbox="images/selecthelpandfeedback2.png":::

3. "Microsoft'a geri bildirim gönder" seçeneğini belirleyin.

    :::image type="content" alt-text="Microsoft'a geri bildirim gönder'i seçin" source="images/send-feedback-to-microsoft-3.jpg":::

4. Verilen seçenekler arasından seçim yapın. Bir sorunu bildirmek için "Sorun bildirmek istiyorum" seçeneğini belirleyin.

    :::image type="content" source="images/report-issue-4.jpg" alt-text="Sorun bildirmek istiyorum seçeneği" lightbox="images/report-issue-4.jpg":::

5. Karşılaştığınız sorunun ayrıntılarını sağlayın ve "Tanılama verilerini gönder" seçeneğini işaretleyin. Ekibin size bir çözüm veya takip ile ulaşabilmesi için "E-posta adresinizi ekleyin" seçeneğini denetlemenizi öneririz.

    :::image type="content" source="images/finalsubmit5.png" alt-text="Ayrıntılar ekleyebileceğiniz ve tanılama verileri ekleyebileceğiniz bölme" lightbox="images/finalsubmit5.png":::

6. Geri bildirimi başarıyla göndermek için "Gönder"e tıklayın.

