---
title: Güvenliği Aşılmış Email Hesabına Yanıt Verme
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.collection:
- o365_security_incident_response
- m365-security
- m365solution-smb
- highpri
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
ms.localizationpriority: high
search.appverid:
- MET150
description: Microsoft 365'te bulunan araçları kullanarak güvenliği aşılmış bir e-posta hesabını tanımayı ve yanıtlamayı öğrenin.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: c2bc977d80cb2226f3348cf4d53715c5e079756e
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68054940"
---
# <a name="responding-to-a-compromised-email-account"></a>Güvenliği Aşılmış Email Hesabına Yanıt Verme

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Uygulandığı öğe**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365 için Microsoft Defender plan 1 ve plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

**Özet** Microsoft 365'te güvenliği aşılmış bir e-posta hesabını tanımayı ve yanıtlamayı öğrenin.

## <a name="what-is-a-compromised-email-account-in-microsoft-365"></a>Microsoft 365'te Güvenliği Aşılmış Email Hesabı nedir?

Microsoft 365 posta kutularına, verilere ve diğer hizmetlere erişim, kullanıcı adı ve parola veya PIN gibi kimlik bilgileri kullanılarak denetlenir. Hedeflenen kullanıcı dışında biri bu kimlik bilgilerini çaldığında, çalınan kimlik bilgilerinin gizliliğinin ihlal edildiği kabul edilir. Saldırgan bu kullanıcılarla özgün kullanıcı olarak oturum açabilir ve yasadışı eylemler gerçekleştirebilir.

Saldırgan, çalınan kimlik bilgilerini kullanarak kullanıcının Microsoft 365 posta kutusuna, SharePoint klasörlerine veya kullanıcının OneDrive'daki dosyalarına erişebilir. Yaygın olarak görülen bir eylem, saldırganın kuruluşun içindeki ve dışındaki alıcılara özgün kullanıcı olarak e-posta göndermesidir. Saldırgan verileri dış alıcılara e-postayla gönderdiğinizde buna veri sızdırma denir.

## <a name="symptoms-of-a-compromised-microsoft-email-account"></a>Güvenliği Aşılmış Bir Microsoft Email Hesabının Belirtileri

Kullanıcılar Microsoft 365 posta kutularındaki olağan dışı etkinlikleri fark edebilir ve bildirebilir. Bazı yaygın belirtiler şunlardır:

- Eksik veya silinmiş e-postalar gibi şüpheli etkinlikler.
- Diğer kullanıcılar, gönderenin **Gönderilmiş Öğeler** klasöründe karşılık gelen e-posta olmadan güvenliği aşılmış hesaptan e-posta alabilir.
- Hedeflenen kullanıcı veya yönetici tarafından oluşturulmamış gelen kutusu kurallarının varlığı. Bu kurallar e-postaları otomatik olarak bilinmeyen adreslere iletebilir veya **Notlar**, **Gereksiz Email** veya **RSS Abonelikleri** klasörlerine taşıyabilir.
- Kullanıcının görünen adı Genel Adres Listesi'nde değiştirilebilir.
- Kullanıcının posta kutusunun e-posta göndermesi engellendi.
- Microsoft Outlook veya Web üzerinde Outlook'daki (eski adıyla Outlook Web App) Gönderilmiş veya Silinmiş Öğeler klasörleri, "Londra'da takıldım, para gönder" gibi sık kullanılan ele geçirilmiş hesap iletilerini içerir.
- Ad, telefon numarası veya posta kodu gibi olağan dışı profil değişiklikleri güncelleştirildi.
- Birden çok parola değişikliği gibi olağan dışı kimlik bilgileri değişiklikleri gereklidir.
- Posta iletme kısa süre önce eklendi.
- Yakın zamanda sahte bankacılık imzası veya reçeteli ilaç imzası gibi sıra dışı bir imza eklendi.

Bir kullanıcı yukarıdaki belirtilerden herhangi birini bildirirse, daha fazla araştırma yapmanız gerekir. Microsoft 365 Defender portalı ve Azure portal, gizliliği tehlikeye girmiş olabileceğinden şüphelendiğiniz bir kullanıcı hesabının etkinliğini araştırmanıza yardımcı olacak araçlar sunar.

- **Microsoft 365 Defender portalındaki birleşik denetim günlükleri**: Şüpheli etkinlik gerçekleşmeden hemen önce geçerli tarihe kadar olan tarih aralığının sonuçlarını filtreleyerek şüpheli hesabın tüm etkinliklerini gözden geçirin. Arama sırasında etkinliklere filtre uygulamayın. Daha fazla bilgi için bkz [. Uyumluluk merkezinde denetim günlüğünde arama](../../compliance/search-the-audit-log-in-security-and-compliance.md) yapma.

- **Azure AD portalında Oturum açma günlüklerini ve diğer risk raporlarını Azure AD**: Şu sütunlardaki değerleri inceleyin:
  - IP adresini gözden geçirme
  - oturum açma konumları
  - oturum açma süreleri
  - oturum açma başarılı veya başarısız

## <a name="how-to-secure-and-restore-email-function-to-a-suspected-compromised-microsoft-365-account-and-mailbox"></a>Güvenliği aşılmış olduğundan şüphelenilen bir Microsoft 365 hesabı ve posta kutusuna e-posta işlevinin güvenliğini sağlama ve geri yükleme

> [!VIDEO https://videoplayercdn.osi.office.net/hub/?csid=ux-cms-en-us-msoffice&uuid=RE2jvOb&AutoPlayVideo=false]

Hesabınıza yeniden erişim elde ettikten sonra bile, saldırgan hesabın denetimini sürdürmesini sağlayan arka kapı girişleri eklemiş olabilir.

Ele geçirenin hesabınızı kontrol etmeye devam etmediğinden emin olmak için hesabınıza yeniden erişim kazanmak için aşağıdaki adımların tümünü o kadar çabuk yapmanız gerekir. Bu adımlar, ele geçiricinin hesabınıza eklemiş olabileceği tüm arka kapı girişlerini kaldırmanıza yardımcı olur. Bu adımları gerçekleştirdikten sonra, bilgisayarınızın gizliliğinin tehlikeye atıldığından emin olmak için bir virüs taraması çalıştırmanızı öneririz.

### <a name="step-1-reset-the-users-password"></a>1. Adım Kullanıcının parolasını sıfırlama

[Birisi için iş parolasını sıfırlama](../../admin/add-users/reset-passwords.md#reset-my-admin-password) başlığındaki yordamları izleyin.

> [!IMPORTANT]
>
> - Saldırgan bu noktada posta kutusuna hala erişebildiğinden, yeni parolayı hedeflenen kullanıcıya e-posta yoluyla göndermeyin.
>
> - Parolanın güçlü olduğundan ve büyük ve küçük harfler, en az bir sayı ve en az bir özel karakter içerdiğinden emin olun.
>
> - Son beş parolanızdan hiçbirini yeniden kullanma. Parola geçmişi gereksinimi daha yeni bir parolayı yeniden kullanmanıza izin verse de, saldırganın tahmin bile edemeyebileceği bir parola seçmelisiniz.
>
> - Şirket içi kimliğiniz Microsoft 365 ile birleştirilmişse, parolanızı şirket içinde değiştirmeniz ve ardından güvenliğin aşılmasına ilişkin yöneticinize bildirmeniz gerekir.
>
> - Uygulama parolalarını güncelleştirin. Kullanıcı hesabı parolası sıfırlandığında uygulama parolaları otomatik olarak iptal edilmiyor. Kullanıcı mevcut uygulama parolalarını silip yeni parolalar oluşturmalıdır. Yönergeler için [Ek güvenlik doğrulama sayfasında uygulama parolaları oluşturma ve silme bölümüne](/azure/active-directory/user-help/multi-factor-authentication-end-user-app-passwords#create-and-delete-app-passwords-from-the-additional-security-verification-page) bakın.
>
> - Özellikle yönetim ayrıcalıklarına sahip hesaplarda güvenliğin aşılmasını önlemek için Multi-Factor Authentication'ı (MFA) etkinleştirmenizi kesinlikle öneririz. MFA hakkında daha fazla bilgi edinmek için [Çok faktörlü kimlik doğrulamasını ayarlama](../../admin/security-and-compliance/set-up-multi-factor-authentication.md) bölümüne gidin.

### <a name="step-2-remove-suspicious-email-forwarding-addresses"></a>2. Adım Şüpheli e-posta iletme adreslerini kaldırma

1. konumundaki Microsoft 365 yönetim merkezi <https://admin.microsoft.com>**Etkin Kullanıcılar'a** \> gidin. **Doğrudan Etkin kullanıcılar** sayfasına gitmek için kullanın<https://admin.microsoft.com/Adminportal/Home#/users>.

2. **Etkin kullanıcılar** sayfasında, söz konusu kullanıcı hesabını bulun ve onay kutusunu seçmeden kullanıcıyı (satır) seçin.

3. Görüntülenen ayrıntılar açılır listesinde **Posta** sekmesini seçin.

4. **Email iletme** bölümündeki değer **Uygulandıysa**, **E-posta iletmeyi yönet'e** tıklayın. Görüntülenen **E-posta iletmeyi yönet** açılır öğesinde, **Bu posta kutusuna gönderilen tüm e-postaları ilet'i** temizleyin ve **değişiklikleri kaydet'e** tıklayın.

### <a name="step-3-disable-any-suspicious-inbox-rules"></a>3. Adım Şüpheli gelen kutusu kurallarını devre dışı bırakma

1. Web üzerinde Outlook kullanarak kullanıcının posta kutusunda oturum açın.

2. Dişli simgesine tıklayın ve **Posta'ya** tıklayın.

3. **Gelen Kutusu ve süpürme kuralları'na** tıklayın ve kuralları gözden geçirin.

4. Şüpheli kuralları devre dışı bırakın veya silin.

### <a name="step-4-unblock-the-user-from-sending-mail"></a>4. Adım Kullanıcının posta gönderme engellemesini kaldırma

Güvenliği aşılmış olduğundan şüphelenilen posta kutusu istenmeyen e-posta göndermek için yasadışı olarak kullanıldıysa, posta kutusunun posta göndermesi engellenmiş olabilir.

Posta kutusunun posta gönderme engelini kaldırmak için, [istenmeyen posta e-postası gönderdikten sonra Kısıtlanmış Kullanıcılar portalından kullanıcı kaldırma'daki](removing-user-from-restricted-users-portal-after-spam.md) yordamları izleyin.

### <a name="step-5-optional-block-the-user-account-from-signing-in"></a>5. Adım İsteğe bağlı: Kullanıcı hesabının oturum açmasını engelleme

> [!IMPORTANT]
> Güvenliği aşılmış olduğundan şüphelenilen hesabın, erişimi yeniden etkinleştirmenin güvenli olduğuna inanana kadar oturum açmasını engelleyebilirsiniz.

1. konumundaki Microsoft 365 yönetim merkezi <https://admin.microsoft.com>**Etkin Kullanıcılar'a** \> gidin. **Doğrudan Etkin kullanıcılar** sayfasına gitmek için kullanın<https://admin.microsoft.com/Adminportal/Home#/users>.

2. **Etkin kullanıcılar** sayfasında kullanıcı hesabını bulun ve seçin, Diğer simgesine](../../media/ITPro-EAC-MoreOptionsIcon.png) tıklayın ![ve oturum **açma durumunu düzenle'yi** seçin.

3. Görüntülenen **Oturum açmayı engelle** bölmesinde **Bu kullanıcının oturum açmasını engelle'yi** seçin ve ardından **Değişiklikleri kaydet'e** tıklayın.

4. konumundaki Exchange yönetim merkezinde (EAC) <https://admin.exchange.microsoft.com>**Alıcılar** \> **Posta Kutuları'na** gidin. Doğrudan **Posta Kutuları** sayfasına gitmek için kullanın <https://admin.exchange.microsoft.com/#/mailboxes>.

5. **Posta Kutuları** sayfasında kullanıcıyı bulun ve seçin. Açılan posta kutusu ayrıntıları açılır öğesinde aşağıdaki adımları uygulayın:
   - **Email uygulamalar** bölümünde **E-posta uygulamaları ayarlarını yönet'i** seçin. Görüntülenen **E-posta uygulamaları için ayarları yönet** açılır penceresinde, iki durumlu düğmeyi sağ ![Devre Dışı Bırak'a taşıyarak tüm kullanılabilir ayarları engelleyin.](../../media/scc-toggle-on.png):
     - **Web üzerinde Outlook**
     - **Outlook masaüstü (MAPI)**
     - **Exchange Web Hizmetleri**
     - **Mobil (Exchange ActiveSync)**
     - **IMAP**
     - **POP3**

   İşiniz bittiğinde **Kaydet'e** ve ardından **Kapat'a** tıklayın.

### <a name="step-6-optional-remove-the-suspected-compromised-account-from-all-administrative-role-groups"></a>6. Adım İsteğe bağlı: Güvenliği aşılmış olduğundan şüphelenilen hesabı tüm yönetim rol gruplarından kaldırın

> [!NOTE]
> Yönetici rol grubu üyeliği, hesap güvenli hale getirildikten sonra geri yüklenebilir.

1. konumundaki Microsoft 365 yönetim merkezi <https://admin.microsoft.com>aşağıdaki adımları uygulayın:
   1. **Kullanıcılar** \> **Etkin kullanıcılar**'a gidin. **Doğrudan Etkin kullanıcılar** sayfasına gitmek için kullanın<https://admin.microsoft.com/Adminportal/Home#/users>.
   2. **Etkin kullanıcılar** sayfasında kullanıcı hesabını bulun ve seçin, Diğer simgesine](../../media/ITPro-EAC-MoreOptionsIcon.png) tıklayın ![ve ardından **Rolleri yönet'i** seçin.
   3. Hesaba atanan tüm yönetim rollerini kaldırın. İşiniz bittiğinde **Değişiklikleri kaydet'e** tıklayın.

2. Microsoft 365 Defender portalında <https://security.microsoft.com>aşağıdaki adımları uygulayın:
   1. **İzinler & rolleri** \> **Email & işbirliği rolleri Rolleri'ne** \> gidin. **doğrudan İzinler** sayfasına gitmek için kullanın<https://security.microsoft.com/emailandcollabpermissions>.
   2. **İzinler** sayfasında, listedeki her rol grubunu seçin ve görüntülenen ayrıntılar açılır öğesinin **Üyeler** bölümünde kullanıcı hesabını arayın. Rol grubu kullanıcı hesabını içeriyorsa aşağıdaki adımları uygulayın:
      1. **Üyeler** bölümünde **Düzenle**'ye tıklayın.
      2. Görüntülenen **Üyeleri seçin öğesini düzenleme** açılır listesinde **Düzenle'ye** tıklayın.
      3. Görüntülenen **Üyeleri seçin** açılır öğesinde **Kaldır'a** tıklayın.
      4. Görüntülenen açılır öğede kullanıcı hesabını seçin ve **kaldır'a** tıklayın.

         İşiniz bittiğinde **Bitti**, **Kaydet'e** ve ardından **Kapat'a** tıklayın.

3. konumundaki Exchange yönetim merkezinde <https://admin.exchange.microsoft.com/>aşağıdaki adımları uygulayın:
   1. **Roller** \> **Yönetici roller'i** seçin. **Doğrudan Yönetici rolleri** sayfasına gitmek için kullanın<https://admin.exchange.microsoft.com/#/adminRoles>.
   2. **Yönetici rolleri** sayfasında, her rol grubunu el ile seçin ve ayrıntılar bölmesinde Kullanıcı hesaplarını doğrulamak için **Atanan** sekmesini seçin. Rol grubu kullanıcı hesabını içeriyorsa aşağıdaki adımları uygulayın:
      1. Kullanıcı hesabını seçin.
      2. Click the ![Sil simgesi.](../../media/m365-cc-sc-delete-icon.png).

         Bitirdiğinizde, **Kaydet**'i tıklatın.

### <a name="step-7-optional-additional-precautionary-steps"></a>7. Adım İsteğe bağlı: Ek önlem adımları

1. Gönderilen öğelerinizi doğruladığınızdan emin olun. Kişi listenizdeki kişileri hesabınızın gizliliğinin ihlal edildiği konusunda bilgilendirmeniz gerekebilir. Saldırgan onlardan para istemiş olabilir, kimlik sahtekarlığına, örneğin farklı bir ülkede mahsur kalmış olmanıza ve paraya ihtiyacınız olduğunu ya da saldırgan bilgisayarlarını ele geçirmeleri için onlara bir virüs gönderebileceğini belirtmiş olabilir.

2. Alternatif e-posta hesabı olarak bu Exchange hesabını kullanan diğer tüm hizmetler tehlikeye girmiş olabilir. İlk olarak, Microsoft 365 aboneliğiniz için bu adımları uygulayın ve ardından diğer hesaplarınız için bu adımları uygulayın.

3. Telefon numaraları ve adresler gibi iletişim bilgilerinizin doğru olduğundan emin olun.

## <a name="see-also"></a>Ayrıca bkz.

- [Microsoft 365'te Outlook Kurallarını ve Özel Form Ekleme Saldırılarını Algılama ve Düzeltme](detect-and-remediate-outlook-rules-forms-attack.md)
- [İnternet Suç Şikayet Merkezi](https://www.ic3.gov/Home/Ransomware)
- [Menkul Kıymetler ve Değişim Komisyonu - "Kimlik Avı" Dolandırıcılığı](https://www.sec.gov/investor/pubs/phishing.htm)
- İstenmeyen postaları doğrudan Microsoft'a ve yöneticinize bildirmek için [Rapor İletisi eklentisini kullanın](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)
