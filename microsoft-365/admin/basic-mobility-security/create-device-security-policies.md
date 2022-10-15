---
title: Basic Mobility ve Security'de cihaz güvenlik ilkeleri oluşturma
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- scotvorg
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
- admindeeplinkEXCHANGE
search.appverid:
- MET150
description: Kuruluş bilgilerinizi koruyan cihaz ilkeleri oluşturmak için Temel Mobilite ve Güvenlik'i kullanın.
ms.openlocfilehash: 2a6124992f9126cd69dad4a8fcb5a1a84f8c39c6
ms.sourcegitcommit: 1f4c51d022d1cfb6c194bf0f0af9c2841c781d68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/14/2022
ms.locfileid: "68573735"
---
# <a name="create-device-security-policies-in-basic-mobility-and-security"></a>Basic Mobility ve Security'de cihaz güvenlik ilkeleri oluşturma

Microsoft 365'te kuruluş bilgilerinizi yetkisiz erişime karşı korumaya yardımcı olan cihaz ilkeleri oluşturmak için Basic Mobility ve Security'yi kullanabilirsiniz. Kuruluşunuzdaki herhangi bir mobil cihaza, cihaz kullanıcısının geçerli bir Microsoft 365 lisansına sahip olduğu ve cihazı Temel Mobilite ve Güvenlik'e kaydettiği herhangi bir mobil cihaza ilkeler uygulayabilirsiniz.

## <a name="before-you-begin"></a>Başlamadan önce

> [!IMPORTANT]
> Mobil cihaz ilkesi oluşturabilmeniz için önce Basic Mobility ve Security'yi etkinleştirmeniz ve ayarlamanız gerekir. Daha fazla bilgi için bkz. Temel Mobilite ve Güvenliğe Genel Bakış.

- Basic Mobility ve Security'nin desteklediği cihazlar, mobil cihaz uygulamaları ve güvenlik ayarları hakkında bilgi edinin. Bkz. [Temel Hareketlilik ve Güvenlik Özellikleri](capabilities.md).
- İlkeleri dağıtmak istediğiniz Microsoft 365 kullanıcılarını içeren ve Microsoft 365'e erişiminin engellenmesinin dışında tutmak isteyebileceğiniz kullanıcılar için güvenlik grupları oluşturun. Kuruluşunuza yeni bir ilke dağıtmadan önce, ilkeyi az sayıda kullanıcıya dağıtarak test etmenizi öneririz. yalnızca kendinizi veya ilkeyi sizin için test eden az sayıda Microsoft 365 kullanıcısını içeren bir güvenlik grubu oluşturabilir ve kullanabilirsiniz. Güvenlik grupları hakkında daha fazla bilgi edinmek için bkz. [Güvenlik grubu oluşturma, düzenleme veya silme](../email/create-edit-or-delete-a-security-group.md).
- Microsoft 365'te Temel Mobilite ve Güvenlik ilkeleri oluşturmak ve dağıtmak için Microsoft 365 genel yöneticisi olmanız gerekir. Daha fazla bilgi için bkz [. Güvenlik & Uyumluluk Merkezi'ndeki İzinler](../../security/office-365-security/permissions-in-the-security-and-compliance-center.md).
- İlkeleri dağıtmadan önce, kuruluşunuzun cihazı Temel Mobilite ve Güvenlik'e kaydetmenin olası etkilerini bilmesini sağlayın. İlkeleri nasıl ayarladığınıza bağlı olarak, uyumsuz cihazların Microsoft 365'e erişmesi engellenebilir ve kayıtlı bir cihazdaki yüklü uygulamalar, fotoğraflar ve kişisel bilgiler dahil olmak üzere veriler silinebilir.

> [!NOTE]
> <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">exchange yönetim merkezinde</a> oluşturulan mobil cihaz posta kutusu ilkelerini ve cihaz erişim kurallarını geçersiz Exchange ActiveSync Microsoft 365 İş Standart için Temel Mobilite ve Güvenlik'te oluşturulan ilkeler ve erişim kuralları. Bir cihaz Microsoft 365 İş Standart için Basic Mobility ve Security'ye kaydedildikten sonra, cihaza uygulanan tüm Exchange ActiveSync mobil cihaz posta kutusu ilkesi veya cihaz erişim kuralı yoksayılır. Exchange ActiveSync hakkında daha fazla bilgi edinmek için bkz. [Exchange Online'da Exchange ActiveSync](/exchange/clients-and-mobile-in-exchange-online/exchange-activesync/exchange-activesync).

## <a name="step-1-create-a-device-policy-and-deploy-to-a-test-group"></a>1. Adım: Cihaz ilkesi oluşturma ve test grubuna dağıtma

Başlamadan önce Basic Mobility and Security'yi etkinleştirdiğinizden ve ayarladığınızdan emin olun. Yönergeler için bkz. [Temel Mobilite ve Güvenliğe Genel Bakış](overview.md).

1. Tarayıcınızdan yazın <https://compliance.microsoft.com/basicmobilityandsecurity>.

2. **İlke oluştur'u** seçin.

   :::image type="content" source="../../media/basic-mobility-security/basic-mobility-microsoft-purview.png" alt-text="Temel Mobilite ve Güvenlik ilkesi ayarları.":::

3. **İlke ayarları** sayfasında, kuruluşunuzdaki mobil cihazlara uygulanmasını istediğiniz gereksinimleri belirtin.

4. **E-posta profilinin yönetilmesini gerektir**: Etkinleştirildiğinde, Basic Mobility ve Security tarafından yönetilen bir e-posta profili olmayan cihazlar uyumlu olarak kabul edilmez. Cihaz, doğru hedeflenmediğinde veya kullanıcı e-posta hesabını cihazda el ile ayarladıysa yönetilen e-posta profiline sahip olamaz. **Etkin değil** (varsayılan) ayarını bıraktığınızda, bu ayar uyumluluk veya uyumsuzluk açısından değerlendirilmez. Bu seçenek belirlendiğinde kullanıcıların nasıl uyumlu olabileceğine ilişkin yönergeler için bkz. [Mevcut bir e-posta hesabı bulundu](/intune-user-help/existing-company-email-account-found).

5. **Bu ilkeyi şimdi uygulamak istiyor musunuz?** sayfasında, bu ilkeyi uygulamak istediğiniz grupları seçin.

6. **Bu ilkeyi oluştur'u** seçin.

İlke, mobil cihazını kullanarak Microsoft 365'te bir sonraki oturum açışında ilkenin geçerli olduğu her kullanıcının cihazına iletilir. Kullanıcılar mobil cihazlarına daha önce bir ilke uygulamadıysa, ilkeyi dağıttıktan sonra cihazlarında Temel Mobilite ve Güvenlik'i kaydetme ve etkinleştirme adımlarını içeren bir bildirim alır. Daha fazla bilgi için bkz. [Mobil cihazınızı Temel Hareketlilik ve Güvenlik kullanarak kaydettirin](enroll-your-mobile-device.md). Intune Hizmeti tarafından barındırılan Basic Mobility ve Security'de kaydı tamamlayana kadar e-posta, OneDrive ve diğer hizmetlere erişim kısıtlanır. Intune Şirket Portalı uygulamasını kullanarak kaydı tamamladıktan sonra hizmetleri kullanabilirler ve ilke kendi cihazlarına uygulanır.

## <a name="step-2-verify-that-your-policy-works"></a>2. Adım: İlkenizin çalıştığını doğrulayın

Bir cihaz ilkesi oluşturduktan sonra, ilkeyi kuruluşunuza dağıtmadan önce beklediğiniz gibi çalışıp çalışmadığını denetleyin.

1. Tarayıcınızdan yazın [https://compliance.microsoft.com/basicmobilityandsecurity](https://compliance.microsoft.com/basicmobilityandsecurity).
2. **Yönetilen cihazların listesini görüntüle'yi** seçin.
3. İlkenin uygulandığı kullanıcı cihazlarının durumunu denetleyin. Cihazların **Durumunun** Yönetilen olmasını istiyorsunuz **.**
4. Bir cihazı seçtikten sonra **Fabrika sıfırlama** veya **Yönet** düğmesinden **şirket verilerini kaldır** düğmesine tıklayarak da cihazda tam veya seçmeli temizleme yapabilirsiniz. Yönergeler için bkz. [Microsoft 365'te mobil cihazı silme.

## <a name="step-3-deploy-a-policy-to-your-organization"></a>3. Adım: Kuruluşunuza ilke dağıtma

Bir cihaz ilkesi oluşturup beklendiği gibi çalıştığını doğruladıktan sonra, bunu kuruluşunuza dağıtın.

1. Tarayıcınızın türü: [https://compliance.microsoft.com/basicmobilityandsecurity](https://compliance.microsoft.com/basicmobilityandsecurity).
2. Dağıtmak istediğiniz ilkeyi seçin ve **Uygulanan Gruplar'ın** yanındaki **Düzenle'yi** seçin.
3. Eklenecek grubu arayın ve **Seç'e** tıklayın.
4. **Kapat** ve **Ayarı değiştir'i seçin.**
5. **Kapat** ve **İlkeyi düzenle'yi seçin.**

İlke, microsoft 365'te mobil cihazlarından bir sonraki oturum açışında ilkenin geçerli olduğu her kullanıcının mobil cihazına iletilir. Kullanıcıların mobil cihazlarına bir ilke uygulanmamışsa, cihazlarında Basic Mobility ve Security için kaydetme ve etkinleştirme adımlarını içeren bir bildirim alır. Kaydı tamamladıktan sonra ilke kendi cihazlarına uygulanır. Daha fazla bilgi için bkz. [Mobil cihazınızı Temel Hareketlilik ve Güvenlik kullanarak kaydettirin](enroll-your-mobile-device.md).

## <a name="step-4-block-email-access-for-unsupported-devices"></a>4. Adım: Desteklenmeyen cihazlar için e-posta erişimini engelleme

Kuruluş bilgilerinizin güvenliğini sağlamaya yardımcı olmak için, Basic Mobility ve Security tarafından desteklenmeyen mobil cihazlar için Microsoft 365 e-postasına uygulama erişimini engellemeniz gerekir. Desteklenen cihazların listesi için bkz [. Desteklenen cihazlar](../../admin/basic-mobility-security/capabilities.md).

**Uygulama erişimini engellemek için:**

1. Tarayıcınızdan yazın [https://compliance.microsoft.com/basicmobilityandsecurity](https://compliance.microsoft.com/basicmobilityandsecurity).
2. **Kuruluş genelinde cihaz erişim ayarlarını yönet'i** seçin.
3. Desteklenmeyen cihazları engellemek **için, Cihaz Microsoft 365 için Temel MobilIte ve Güvenlik tarafından desteklenmiyorsa** altında **Access'i** seçin ve ardından **Kaydet'i** seçin.

   :::image type="content" source="../../media/basic-mobility-security/basic-mobility-access.png" alt-text="Temel Mobilite ve Güvenlik erişimi engelleme seçeneği.":::

## <a name="step-5-choose-security-groups-to-be-excluded-from-conditional-access-checks"></a>5. Adım: Koşullu erişim denetimlerinin dışında tutulacak güvenlik gruplarını seçme

Bazı kişileri mobil cihazlarında koşullu erişim denetimlerinin dışında tutmak istiyorsanız ve bu kişiler için bir veya daha fazla güvenlik grubu oluşturduysanız, güvenlik gruplarını buraya ekleyin. Bu gruplardaki kişilerin desteklenen mobil cihazları için herhangi bir ilke zorunlu tutulmaz. Kuruluşunuzda Artık Temel Mobilite ve Güvenlik kullanmak istemiyorsanız bu seçenek önerilir.

1. Tarayıcınızdan yazın [https://compliance.microsoft.com/basicmobilityandsecurity](https://compliance.microsoft.com/basicmobilityandsecurity).

2. **Kuruluş genelinde cihaz erişim ayarlarını yönet'i** seçin.

   :::image type="content" source="../../media/basic-mobility-security/basic-mobility-microsoft-purview.png" alt-text="Temel Mobilite ve Güvenlik bir ilke seçeneği oluşturur.":::

3. Microsoft 365'e erişimin engellenmesinin dışında tutmak istediğiniz kullanıcıları içeren güvenlik grubunu eklemek için **Ekle'yi** seçin. Bir kullanıcı bu listeye eklendiğinde, desteklenmeyen bir cihaz kullanırken Microsoft 365 e-postasına erişebilir.

4. **Grup seçin** panelinde kullanmak istediğiniz güvenlik grubunu seçin.

5. Adı ve ardından **Kaydet** **Ekle'yi** >  seçin.

6. **Kuruluş genelinde cihaz erişim ayarları** panelinde **Kaydet'i** seçin.

   :::image type="content" source="../../media/basic-mobility-security/basic-mobility-groups.png" alt-text="Temel Mobilite ve Güvenlik erişime izin ver seçeneği.":::

## <a name="what-is-the-impact-of-security-policies-on-different-device-types"></a>Güvenlik ilkelerinin farklı cihaz türleri üzerindeki etkisi nedir?

Kullanıcı cihazlarına bir ilke uyguladığınızda, her cihaz üzerindeki etkisi cihaz türleri arasında biraz değişiklik gösterir. İlkelerin farklı cihazlar üzerindeki etkisinin örnekleri için aşağıdaki tabloya bakın.

|**Güvenlik İlkesi**|**Android**|**Samsung KNOX**|**iOS**|**Notlar**|
|:-----|:-----|:-----|:-----|:-----|
|Şifrelenmiş yedekleme gerektir|Hayır|Evet|Evet|iOS şifreli yedekleme gereklidir.|
|Bulut yedeklemesini engelleme|Evet|Evet|Evet|Android'de Google yedeklemesini (gri), denetimli iOS'ta bulut yedeklemesini engelleyin.|
|Belge eşitlemesini engelle|Hayır|Hayır|Evet|iOS: Denetimli iOS cihazlarında buluttaki belgeleri engelleyin.|
|Fotoğraf eşitlemeyi engelle |Hayır|Hayır|Evet|iOS (yerel): Fotoğraf Akışını engelle.|
|Ekran yakalamayı engelle |Hayır|Evet|Evet|Denendiğinde engellendi.|
|Görüntülü konferansı engelle |Hayır|Hayır|Evet|FaceTime, Skype veya diğer cihazlarda değil denetimli iOS cihazlarında engellenir.|
|Tanılama verilerinin gönderilmesini engelleme |Hayır|Evet|Evet|Android'de Google kilitlenme raporu göndermeyi engelle.|
|Uygulama mağazasına erişimi engelleme |Hayır|Evet|Evet|Android giriş sayfasında app store simgesi eksik, Windows'ta devre dışı ve denetimli iOS cihazları.|
|Uygulama mağazası için parola iste |Hayır|Hayır|Evet|iOS: iTunes satın alma işlemleri için parola gereklidir.|
|Çıkarılabilir depolama birimine bağlantıyı engelle |Hayır|Evet|Yok|Android: SD kart ayarlarda gri görünüyor, Windows kullanıcıya bildirir, yüklü uygulamalar kullanılamaz|
|Bluetooth bağlantısını engelle |Notlara bakın|Notlara bakın|Evet|Android'de bir ayar olarak BlueTooth'u devre dışı bırakamıyoruz. Bunun yerine BlueTooth gerektiren tüm işlemleri devre dışı bırakıyoruz: Gelişmiş Ses Dağıtımı, Ses/Video Uzaktan Kumanda, tutmadan kullanımlı cihazlar, kulaklık, Telefon Rehberi Erişimi ve Seri Bağlantı Noktası. Bunlardan herhangi biri kullanıldığında sayfanın en altında küçük bir bildirim iletisi görüntülenir.|

## <a name="what-happens-when-you-delete-a-policy-or-remove-a-user-from-the-policy"></a>İlkeyi sildiğinizde veya bir kullanıcıyı ilkeden kaldırdığınızda ne olur?

İlkeyi sildiğinizde veya ilkenin dağıtıldığı gruptan bir kullanıcıyı kaldırdığınızda, ilke ayarları, Microsoft 365 e-posta profili ve önbelleğe alınmış e-postalar kullanıcının cihazından kaldırılabilir. Farklı cihaz türleri için nelerin kaldırıldığını görmek için aşağıdaki tabloya bakın.

|**Kaldırılanlar**|**iOS**|**Android (Samsung KNOX dahil)**|
|:-----|:-----|:-----|
|Yönetilen e-posta profilleri<sup>1</sup>|Evet|Hayır|
|Bulut yedeklemesini engelleme|Evet|Hayır|

<sup>1</sup> İlke **Email profili yönetilir seçeneği seçili olarak dağıtıldıysa**, yönetilen e-posta profili ve bu profildeki önbelleğe alınmış e-postalar kullanıcı cihazından silinir.

İlke, her kullanıcı için mobil cihazdan kaldırılır ve bu ilke, cihazlarının Temel Mobilite ve Güvenlik ile bir sonraki iadesinde geçerli olur. Bu kullanıcı cihazları için geçerli olan yeni bir ilke dağıtırsanız, basic mobility and security'ye yeniden kaydolmaları istenir.

Ayrıca bir cihazı tamamen silebilir veya kuruluş bilgilerini cihazdan seçmeli olarak silebilirsiniz. Daha fazla bilgi için bkz [. Basic Mobility and Security'de mobil cihazı temizleme](wipe-mobile-device.md).

## <a name="related-content"></a>İlgili içerik

[Temel Mobilite ve Güvenliğe Genel Bakış](overview.md) (makale)\
[Temel Mobilite ve Güvenliğin Özellikleri](capabilities.md) (makale)