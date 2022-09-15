---
title: Kimliği doğrulanmamış paylaşım için en iyi yöntemler
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.collection:
- highpri
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
- m365initiative-externalcollab
ms.custom:
- seo-marvel-apr2020
- admindeeplinkSPO
ms.localizationpriority: high
f1.keywords: NOCSH
recommendations: false
description: Bu makalede, kimliği doğrulanmamış kullanıcılarla dosya ve klasör paylaşmaya yönelik en iyi yöntemler hakkında bilgi edineceksiniz.
ms.openlocfilehash: 2eccf02ee2481eb1e44230148aa778d1d43eeb52
ms.sourcegitcommit: 0af064e8b6778060f1bd365378d69b16fc9949b5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/15/2022
ms.locfileid: "67731176"
---
# <a name="best-practices-for-sharing-files-and-folders-with-unauthenticated-users"></a>Kimliği doğrulanmamış kullanıcılarla dosya ve klasör paylaşmaya yönelik en iyi yöntemler

Kimliği doğrulanmamış paylaşım (*Herkes* bağlantısı) kullanışlı olabilir ve çeşitli senaryolarda kullanışlıdır. *Herkesin* bağlantıları paylaşmanın en kolay yoludur: kişiler bağlantıyı kimlik doğrulaması olmadan açabilir ve başkalarına iletebilir.

Genellikle, bir kuruluştaki tüm içerik kimliği doğrulanmamış paylaşım için uygun değildir. Bu makalede, kullanıcılarınızın dosya ve klasörlerin kimliği doğrulanmamış paylaşımını kullanabileceği, ancak kuruluşunuzun içeriğini korumaya yardımcı olacak korumaların bulunduğu bir ortam oluşturmanıza yardımcı olacak seçenekler yer alır.

> [!NOTE]
> Kimliği doğrulanmamış paylaşımın çalışması için, kuruluşunuz ve kullanmakta olduğunuz tek tek site veya ekip için etkinleştirmeniz gerekir. Etkinleştirmek istediğiniz senaryo için bkz. [Kuruluşunuzun dışındaki kişilerle işbirliği](collaborate-with-people-outside-your-organization.md) yapmak.

## <a name="set-an-expiration-date-for-anyone-links"></a>Herkes bağlantıları için son kullanma tarihi ayarlama

Dosyalar genellikle uzun süre boyunca sitelerde, gruplarda ve ekiplerde depolanır. Bazen dosyaların yıllarca saklanmasını gerektiren veri saklama ilkeleri vardır. Bu tür dosyalar kimliği doğrulanmamış kişilerle paylaşılıyorsa, bu durum gelecekte dosyalara beklenmeyen erişim ve değişikliklere yol açabilir. Bu olasılığı azaltmak için *Herkes* bağlantıları için bir sona erme süresi yapılandırabilirsiniz.

*Herkes* bağlantısının süresi dolduktan sonra, içeriğe erişmek için kullanılamaz.

Kuruluş genelindeki Herkes bağlantıları için son kullanma tarihi ayarlamak için

1. SharePoint yönetim merkezini açın, **İlkeler'i** genişletin ve <a href="https://go.microsoft.com/fwlink/?linkid=2185222" target="_blank">**paylaşım'ı**</a> seçin.
1. **Herkes bağlantıları için süre sonu ve izin seçeneklerini seçin** altında **, Bu bağlantıların süresi bu kadar gün içinde dolmalıdır** onay kutusunu seçin.</br>
   ![SharePoint kuruluş düzeyinde Herkes bağlantısı süre sonu ayarlarının ekran görüntüsü.](../media/sharepoint-organization-anyone-link-expiration.png)
1. Kutuya gün sayısı yazın ve **Kaydet'e** tıklayın.

Süre sonu süresini değiştirirseniz, yeni ayar daha uzunsa mevcut bağlantılar geçerli süre sonu süresini tutar veya yeni ayar daha kısaysa yeni ayara güncelleştirilir.

Belirli bir sitedeki Herkes bağlantıları için son kullanma tarihi ayarlamak için

1. SharePoint yönetim merkezini açın, **Siteler'i** genişletin ve <a href="https://go.microsoft.com/fwlink/?linkid=2185220" target="_blank">**etkin siteler'i**</a> seçin.
1. Değiştirmek istediğiniz siteyi ve ardından **Paylaşım'ı** seçin.
1. **Herkes bağlantıları için Gelişmiş ayarlar'ın** altında, **Herkes bağlantılarının Süre Sonu'nun** altında **Kuruluş düzeyi ayarıyla aynı** onay kutusunu temizleyin.</br>
   ![SharePoint site düzeyi Herkes bağlantısı süre sonu ayarlarının ekran görüntüsü.](../media/sharepoint-organization-anyone-link-expiration-site.png)
1. **Bu bağlantıların süresi bu kadar gün içinde dolmalıdır** seçeneğini belirleyin ve kutuya birkaç gün yazın.
1. **Kaydet**'i seçin.

*Herkes* bağlantısının süresi dolduğunda, dosya veya klasörün yeni *bir Herkes* bağlantısıyla yeniden paylaşılabildiğini unutmayın.

[Set-SPOSite](/powershell/module/sharepoint-online/set-sposite) kullanarak belirli bir site için *Herkes* bağlantısının süre sonunu ayarlayabilirsiniz. 

```powershell
Set-SPOSite -Identity https://contoso.sharepoint.com/sites/marketing -OverrideTenantAnonymousLinkExpirationPolicy $true -AnonymousLinkExpirationInDays 15
```

## <a name="set-link-permissions"></a>Bağlantı izinlerini ayarlama

Varsayılan olarak, bir dosyanın *Herkes* bağlantıları kişilerin dosyayı düzenlemesine, *Bir klasörün Herkes* bağlantıları ise kişilerin dosyaları düzenlemesine ve görüntülemesine ve yeni dosyaları klasöre yüklemesine olanak sağlar. Dosyalar ve klasörler için bu izinleri bağımsız olarak salt görüntüleme olarak değiştirebilirsiniz.

Kimliği doğrulanmamış paylaşıma izin vermek istiyorsanız ancak kuruluşunuzun içeriğini değiştiren kimliği doğrulanmamış kişiler konusunda endişeleriniz varsa, dosya ve klasör izinlerini **Görünüm** olarak ayarlamayı göz önünde bulundurun.

Kuruluş genelindeKim bağlantılar için izinleri ayarlamak için

1. SharePoint yönetim merkezini açın ve <a href="https://go.microsoft.com/fwlink/?linkid=2185222" target="_blank">**Paylaşım'ı**</a> seçin.
1. **"Herkes" bağlantıları için gelişmiş ayarlar'ın** altında, kullanmak istediğiniz dosya ve klasör izinlerini seçin.</br>
   ![SharePoint kuruluş düzeyinde Herkes bağlantısı izin ayarlarının ekran görüntüsü.](../media/sharepoint-organization-anyone-link-permissions.png)

*Herkes* bağlantıları **Görüntüle** olarak ayarlandığında, kullanıcılar dosya ve klasörleri konuklarla paylaşmaya ve *Belirli kişiler* bağlantılarını kullanarak düzenleme izinleri vermeye devam edebilir. Bu bağlantılar, kuruluşunuz dışındaki kişilerin konuk olarak kimlik doğrulamasını gerektirir ve bu bağlantılarla paylaşılan dosya ve klasörlerdeki konuk etkinliğini izleyebilir ve denetleyebilirsiniz.

## <a name="set-default-link-type-to-only-work-for-people-in-your-organization"></a>Varsayılan bağlantı türünü yalnızca kuruluşunuzdaki kişiler için çalışacak şekilde ayarlayın

Kuruluşunuz için *Herkes* paylaşım etkinleştirildiğinde varsayılan paylaşım bağlantısı normalde **Herkes** olarak ayarlanır. Bu, kullanıcılar için kullanışlı olsa da, yanlışlıkla kimliği doğrulanmamış paylaşım riskini artırabilir. Kullanıcı hassas bir belgeyi paylaşırken bağlantı türünü değiştirmeyi unutursa yanlışlıkla kimlik doğrulaması gerektirmeyen bir paylaşım bağlantısı oluşturabilir.

Varsayılan bağlantı ayarını yalnızca kuruluşunuzdaki kişiler için çalışan bir bağlantı olarak değiştirerek bu riski azaltabilirsiniz. Kimliği doğrulanmamış kişilerle paylaşmak isteyen kullanıcıların bu seçeneği özellikle belirtmesi gerekir.

Kuruluş için varsayılan dosya ve klasör paylaşım bağlantısını ayarlamak için:

1. SharePoint yönetim merkezini açın ve <a href="https://go.microsoft.com/fwlink/?linkid=2185222" target="_blank">**Paylaşım'ı**</a> seçin.
1. **Dosya ve klasör** **bağlantıları'nın altında Yalnızca kuruluşunuzdaki kişiler'i** seçin.

   ![SharePoint varsayılan bağlantı türü ayarının ekran görüntüsü.](../media/sharepoint-default-sharing-link-company-link.png)

1. **Kaydet'i** seçin

Belirli bir site için varsayılan dosya ve klasör paylaşım bağlantısını ayarlamak için:

1. SharePoint yönetim merkezini açın, **Siteler'i** genişletin ve <a href="https://go.microsoft.com/fwlink/?linkid=2185220" target="_blank">**etkin siteler'i**</a> seçin.
1. Değiştirmek istediğiniz siteyi ve ardından **Paylaşım'ı** seçin.
1. **Varsayılan paylaşım bağlantı türü'nün** altında **Kuruluş düzeyi ayarıyla aynı** onay kutusunu temizleyin.

   ![SharePoint site düzeyi varsayılan bağlantı türü ayarlarının ekran görüntüsü.](../media/sharepoint-organization-anyone-link-permissions-site.png)

1. **Yalnızca kuruluşunuzdaki kişiler** seçeneğini ve ardından **Kaydet'i** seçin.

## <a name="prevent-unauthenticated-sharing-of-sensitive-content"></a>Hassas içeriğin kimliği doğrulanmamış olarak paylaşılmasını engelleme

Hassas içeriğin kimliği doğrulanmamış paylaşımını önlemek için [Microsoft Purview Veri Kaybı Önleme (DLP)](../compliance/dlp-learn-about-dlp.md) kullanabilirsiniz. Veri kaybı önleme, dosyanın duyarlılık etiketine, bekletme etiketine veya dosyanın kendisindeki hassas bilgilere göre işlem yapabilir.

DLP kuralı oluşturmak için:

1. Microsoft Purview yönetim merkezinde [Veri kaybı önleme sayfasına](https://compliance.microsoft.com/datalossprevention) gidin.
2. **İlke oluştur'a** tıklayın.
3. **Özel'i** seçin ve **İleri'ye** tıklayın.
4. İlke için bir ad yazın ve **İleri'ye** tıklayın.
5. **İlkenin uygulanacağı konumlar** sayfasında **, SharePoint siteleri** ve **OneDrive hesapları** dışındaki tüm ayarları kapatın ve **ardından İleri'ye** tıklayın.
6. **İlke ayarlarını tanımla** sayfasında **İleri'ye** tıklayın.
7. **Gelişmiş DLP kurallarını özelleştir** sayfasında **Kural oluştur'a** tıklayın ve kural için bir ad yazın.
8. **Koşullar'ın** altında **Koşul ekle'ye** tıklayın ve **İçerik içerir'i** seçin.
9. **Ekle'ye** tıklayın ve kimliği doğrulanmamış paylaşımı önlemek istediğiniz bilgi türünü seçin.

   ![Koşul seçeneklerinin, hassas bilgi türlerinin, duyarlılık etiketlerinin ve bekletme etiketlerinin ekran görüntüsü.](../media/limit-accidental-exposure-dlp-conditions.png)

10. **Eylemler'in** altında **Eylem ekle'ye** tıklayın ve **Erişimi kısıtla veya Microsoft 365 konumlarındaki içeriği şifrele'yi** seçin.
11. **Erişimi kısıtla veya Microsoft 365 konumlarındaki içeriği şifrele** onay kutusunu seçin ve ardından **"Bağlantıya sahip herkes" seçenekleri aracılığıyla yalnızca içeriğe erişim izni verilen kişiler** seçeneğini belirleyin.

      ![DLP kuralı eylem seçeneklerinin ekran görüntüsü.](../media/limit-accidental-exposure-dlp-anyone-links.png)

12. **Kaydet'e** ve ardından **İleri'ye** tıklayın.
13. Test seçeneklerinizi belirleyin ve **İleri'ye** tıklayın.
14. **Gönder'e** ve ardından **Bitti'ye** tıklayın.

## <a name="protect-against-malicious-files"></a>Kötü amaçlı dosyalara karşı koruma

Anonim kullanıcıların dosyaları karşıya yüklemesine izin verdiğinizde, birinin kötü amaçlı bir dosyayı karşıya yükleme riski artar. Office 365 için Microsoft Defender Plan 1 veya Plan 2 lisanslarına sahip kuruluşlarda (örneğin, Microsoft 365 E5 veya eklenti olarak), karşıya yüklenen dosyaları korumalı bir sanal ortamda patlatıp güvenli olmayan dosyaları karantinaya almak için *Güvenli Ekler* özelliğini kullanabilirsiniz.

Yönergeler için bkz. [SharePoint, OneDrive ve Microsoft Teams için Güvenli Ekler'i açma](../security/office-365-security/turn-on-mdo-for-spo-odb-and-teams.md).

Microsoft 365 A5 veya E5 Güvenlik lisanslarınız varsa *, Güvenli Belgeler* özelliğini de açabilirsiniz (ve kullanabilirsiniz). Daha fazla bilgi için bkz. [Microsoft 365 A5 veya E5 Güvenliğinde Güvenli Belgeler](../security/office-365-security/safe-docs.md).

## <a name="add-copyright-information-to-your-files"></a>Dosyalarınıza telif hakkı bilgileri ekleme

Microsoft Purview yönetim merkezinde duyarlılık etiketleri kullanıyorsanız, kuruluşunuzun Office belgelerine otomatik olarak filigran veya üst bilgi veya alt bilgi eklemek için etiketlerinizi yapılandırabilirsiniz. Bu şekilde, paylaşılan dosyaların telif hakkı veya diğer sahiplik bilgilerini içerdiğini emin olabilirsiniz.

Etiketli bir dosyaya alt bilgi eklemek için

1. [Microsoft Purview yönetim merkezini](https://compliance.microsoft.com) açın.
2. Sol gezinti bölmesindeki **Çözümler'in** altında **Bilgi koruması'na** tıklayın.
3. Alt bilgi eklemek istediğiniz etikete tıklayın ve ardından **Etiketi düzenle'ye** tıklayın.
4. **İçerik işaretleme** sekmesine ulaşmak için **İleri'ye** tıklayın ve ardından İçerik **işaretlemeyi aç'ı** açın.
5. Eklemek istediğiniz metin türünün onay kutusunu seçin ve ardından **Metni özelleştir'e** tıklayın.
6. Belgelerinize eklenmesini istediğiniz metni yazın, istediğiniz metin seçeneklerini belirleyin ve **kaydet'e** tıklayın.</br>
   ![Duyarlılık etiketi için içerik işaretleme ayarlarının ekran görüntüsü.](../media/content-marking-for-anonymous-sharing.png)
7. Sihirbazın sonuna ulaşmak için **İleri'ye** tıklayın ve ardından **Etiketi kaydet'e** tıklayın.

Etiket için içerik işaretleme etkinleştirildiğinde, kullanıcı bu etiketi uyguladığında belirttiğiniz metin Office belgelerine eklenir.

## <a name="see-also"></a>Ayrıca Bkz

[Duyarlılık etiketlerine genel bakış](/Office365/SecurityCompliance/sensitivity-labels)

[Konuklarla paylaşırken dosyaların yanlışlıkla açığa alınmasını sınırlayın](share-limit-accidental-exposure.md)

[Güvenli bir konuk paylaşım ortamı oluşturma](create-secure-guest-sharing-environment.md)
