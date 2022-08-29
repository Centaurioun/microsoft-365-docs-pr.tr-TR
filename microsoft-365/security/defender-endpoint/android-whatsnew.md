---
title: Android'de Uç Nokta için Microsoft Defender'deki yenilikler
description: Android'de önceki Uç Nokta için Microsoft Defender sürümlerine yönelik önemli değişiklikler hakkında bilgi edinin.
keywords: microsoft, defender, Uç Nokta için Microsoft Defender, mac, installation, macos, whatsnew
ms.prod: m365-security
ms.mktglfcycl: security
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-security-compliance
ms.topic: reference
ms.technology: mde
ms.openlocfilehash: 4300aadd6ab57561592621a0d1aeb54887d70320
ms.sourcegitcommit: f1b3ecde15e5cbbeadaf51b2cadb6b1d677fc265
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2022
ms.locfileid: "67437793"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-android"></a>Android'de Uç Nokta için Microsoft Defender'deki yenilikler

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

>[!IMPORTANT]
> Uç Nokta için Microsoft Defender'ın **Kötü amaçlı yazılımdan koruma altyapısı** genel kullanıma sunuldu. Tüm kullanıcıların bu yeni kötü amaçlı yazılımdan koruma özelliğini kullanabilmesi için **1.0.3815.0000'in** üzerinde bir Uç Nokta için Microsoft Defender sürümüne sahip olması gerekir. 1.0.3815.0000'in altındaki Uç Nokta için Microsoft Defender sürümdeki kullanıcılara, Uç Nokta için Microsoft Defender uygulamalarını güncelleştirmek için bildirimler ve uygulama içi katman iletileri gönderilir. Kullanıcılar, katman iletisinde sağlanan bağlantıya tıklayarak yönetilen play store'a gidebilir ve uygulamayı güncelleştirebilir. 
>
> Kullanıcılar play store'a erişemiyorsa uygulama şirket portalı üzerinden güncelleştirilebilir. 

## <a name="privacy-controls"></a>Gizlilik Denetimleri

Android'de Uç Nokta için Microsoft Defender hem Yöneticiler hem de Son Kullanıcılar için Gizlilik Denetimleri'ni etkinleştirir. Bu, kayıtlı (MDM) ve kaydı kaldırılmış (MAM) cihazlar (önizlemede) denetimlerini içerir. Yöneticiler uyarı raporunda gizliliği yapılandırırken, Son Kullanıcılar da kendi kuruluşlarıyla paylaşılan bilgileri yapılandırabilir. Daha fazla bilgi için bkz [. gizlilik denetimleri (MDM)](/microsoft-365/security/defender-endpoint/android-configure#privacy-controls) ve [gizlilik denetimleri (MAM)](/microsoft-365/security/defender-endpoint/android-configure-mam#configure-privacy-controls).

## <a name="optional-permissions-and-disable-web-protection"></a>İsteğe Bağlı İzinler ve Web Korumasını Devre Dışı Bırakma

Android'de Uç Nokta için Microsoft Defender, ekleme akışında **İsteğe Bağlı İzinler'i** etkinleştirir. Şu anda ekleme akışında MDE için gereken izinler zorunlu. Bu özellik sayesinde yönetici, ekleme sırasında zorunlu **VPN** ve **Erişilebilirlik** izinlerini zorlamadan cihazlara MDE dağıtabilir. Son Kullanıcılar zorunlu izinler olmadan uygulamayı ekleyebilir ve daha sonra bu izinleri gözden geçirebilir. Bu özellik şu anda yalnızca kaydı kaldırılmış cihazlar (MAM) için mevcuttur. Daha fazla bilgi için bkz. [isteğe bağlı izinler](/microsoft-365/security/defender-endpoint/android-configure-mam#optional-permissions).


## <a name="microsoft-defender-on-android-enterprise-byod-personal-profile"></a>Android kurumsal KCG kişisel profilinde Microsoft Defender
Uç Nokta için Microsoft Defender artık Android Kurumsal kişisel profilinde (yalnızca KCG) kötü amaçlı yazılım taraması, kimlik avı bağlantılarından koruma, ağ koruması ve güvenlik açığı yönetimi gibi tüm temel özelliklerle desteklenmektedir. Bu destek, kişisel profilde kullanıcı gizliliğini sağlamak için [gizlilik denetimleriyle](/microsoft-365/security/defender-endpoint/android-configure#privacy-controls) birleştirilir. Daha fazla bilgi için [duyuruyu](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/announcing-the-public-preview-of-defender-for-endpoint-personal/ba-p/3370979) ve [dağıtım kılavuzunu](/microsoft-365/security/defender-endpoint/android-intune#set-up-microsoft-defender-in-personal-profile-on-android-enterprise-in-byod-mode) okuyun.

## <a name="network-protection"></a>Ağ koruması
Uç Nokta için Microsoft Defender'da Ağ Koruması artık genel önizleme aşamasındadır. Ağ koruması, sahte Wi-Fi ilgili tehditlere, ananas cihazları gibi sahte donanımlara karşı koruma sağlar ve ilgili bir tehdit algılandığında kullanıcıya bildirir. Kullanıcılar güvenli olmayan bir bağlantıya bağlandıklarında güvenli ağlara bağlanmak ve ağları değiştirmek için kılavuzlu bir deneyim de görür.

Özelliği Microsoft Endpoint Manager Yönetici merkezinden yapılandırma gibi esneklik sunmak için çeşitli yönetici denetimleri içerir. Yöneticiler, Android cihazlardan Uç Nokta için Defender tarafından gönderilen verileri yapılandırmak için gizlilik denetimlerini de etkinleştirebilir. 

Bu genel önizlemeye katılmak istiyorsanız lütfen kiracı kimliğinizi networkprotection@microsoft.com bizimle paylaşın. Daha fazla bilgi için bkz. [ağ koruması](/microsoft-365/security/defender-endpoint/android-configure).

>[!NOTE]
>Microsoft Defender artık 1.0.3011.0302'nin altındaki sürümler için desteklenmiyor. Kullanıcıların cihazlarının güvenliğini sağlamak için en son sürümlere yükseltmeleri istenir.
Güncelleştirmek için kullanıcılar aşağıdaki adımları kullanabilir:
>1. İş profilinizde Yönetilen Play Store'a gidin.
>2. Sağ üst köşedeki profil simgesine dokunun ve "Uygulamaları ve cihazı yönet" seçeneğini belirleyin.
>3. Kullanılabilir güncelleştirmeler altında MDE'yi bulun ve güncelleştir'i seçin.
>
>Herhangi bir sorunla karşılaşırsanız [uygulama içi geri bildirim gönderin](/security/defender-endpoint/android-support-signin#send-in-app-feedback).

## <a name="microsoft-defender-for-endpoint-is-now-microsoft-defender-in-the-play-store"></a>Uç Nokta için Microsoft Defender artık Play store'da Microsoft Defender'dır

Uç Nokta için Microsoft Defender artık play store'da **Microsoft Defender** olarak kullanılabilir. Bu güncelleştirmeyle, uygulama **ABD bölgesindeki Tüketiciler** için önizleme olarak kullanıma sunulacaktır. Uygulamada iş veya kişisel hesabınızla nasıl oturum açtığınıza bağlı olarak, Uç Nokta için Microsoft Defender özelliklerine veya kişiler için Microsoft Defender özelliklerine erişebilirsiniz. Daha fazla ayrıntı için [lütfen bu bloga](https://www.microsoft.com/microsoft-365/microsoft-defender-for-individuals) bakın.

## <a name="vulnerability-management"></a>Güvenlik Açığı Yönetimi

25 Ocak 2022'de Android ve iOS'ta güvenlik açığı yönetiminin genel kullanıma sunulduğu duyuruldu. Diğer ayrıntılar için [buradaki techcommunity gönderisine](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/announcing-general-availability-of-vulnerability-management/ba-p/3071663) bakın.

## <a name="upcoming-permission-changes-for-microsoft-defender-for-endpoint-running-android-11-or-later-nov-2021"></a>Android 11 veya sonraki bir sürümü çalıştıran Uç Nokta için Microsoft Defender için yaklaşan izin değişiklikleri (2021'in 2021'in Başında)

Sürüm Derlemesi: 1.0.3501.0301 Sürüm ayı: Kasım 2021 Uç Nokta için Microsoft Defender[, Google'ın](https://developer.android.com/distribute/play-policies#APILevel30) Android API 30'a yükseltmesi için gereken bu güncelleştirmeyi yayımladı. Bu değişiklik, Android 11 veya sonraki bir sürümü çalıştıran cihazlar için [yeni depolama iznine](https://developer.android.com/training/data-storage/manage-all-files#all-files-access-google-play) erişmek isteyen kullanıcılara sorulacaktır. Kullanıcıların Defender uygulamasını sürüm 1.0.3501.0301 veya sonraki bir sürümle güncelleştirdikten sonra bu yeni depolama iznini kabul etmeleri gerekir. Bu, Uç Nokta için Defender'ın uygulama güvenliği özelliğinin herhangi bir kesinti olmadan çalışmasını sağlar. Daha fazla bilgi için aşağıdaki bölümleri gözden geçirin.

**Bu durum kuruluşunuzu nasıl etkiler:** Bu değişiklikler, Android 11 veya sonraki sürümleri çalıştıran cihazlarda Uç Nokta için Microsoft Defender kullanıyorsanız ve Uç Nokta için Defender'ı 1.0.3501.0301 veya sonraki bir derlemeyi yayınlayacak şekilde güncelleştirdiyseniz geçerlilik kazanır.

> [!NOTE]
> Yeni depolama izinleri, yönetici tarafından Microsoft Endpoint Manager aracılığıyla 'Otomatik Onaylama' için yapılandırılamaz. Kullanıcının bu izne erişim sağlamak için işlem gerçekleştirmesi gerekir.

- **Kullanıcı deneyimi:** Kullanıcılar, uygulama güvenliği için eksik izni belirten bir bildirim alır. Kullanıcı bu izni reddederse cihazda 'Uygulama güvenliği' işlevi kapatılır. Kullanıcı izni kabul etmez veya reddedmezse, onaylanana kadar cihazının kilidini açarken veya uygulamayı açarken istem almaya devam eder.

> [!NOTE]
> Kuruluşunuz 'Kurcalama koruması' özelliğinin önizlemesini kullanıyorsa ve yeni depolama izinleri kullanıcı tarafından en son sürüme güncelleştirildikten sonra 7 gün içinde verilmediyse, kullanıcı şirket kaynaklarına erişimi kaybedebilir.

**Hazırlanmak için yapmanız gerekenler:**

Uç Nokta için Defender'ı 1.0.3501.0301 veya sonraki bir sürüme güncelleştirdikten sonra istendiğinde kullanıcılarınıza ve yardım masanıza (varsa) yeni izinleri kabul etmelerinin gerekeceğini bildirin. İzinleri kabul etmek için kullanıcılar şunları yapmalıdır:

1. Uç Nokta için Defender uygulama içi bildirimine dokunun veya Uç Nokta için Defender uygulamasını açın. Kullanıcılar, gerekli izinleri listeleyen bir ekran görür. Depolama izninin yanında yeşil bir onay işareti eksik olacaktır.

2. **Başlat'a** dokunun.

3. **Tüm dosyaları yönetmek için Erişime izin ver** iki durumlu düğmesine dokunun.

4. Cihaz artık korunuyor.

  > [!NOTE]
  > Bu izin, Uç Nokta için Microsoft Defender kullanıcının cihazındaki depolama alanına erişmesine olanak tanır ve bu da kötü amaçlı ve istenmeyen uygulamaları algılamaya ve kaldırmaya yardımcı olur. Uç Nokta için Microsoft Defender yalnızca Android uygulama paketi dosyasına (.apk) erişir/tarar. İş Profili olan cihazlarda Uç Nokta için Defender yalnızca işle ilgili dosyaları tarar.
