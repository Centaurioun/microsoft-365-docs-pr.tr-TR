---
title: Fidye yazılımı saldırılarına yanıt verme
description: Bu makalede fidye yazılımı saldırılarına yanıt vermek için genelleştirilmiş bir playbook sağlanır.
search.appverid: MET150
author: nic-name
ms.author: noriordan
manager: dolmont
audience: ITPro
ms.topic: article
ms.date: 05/30/2022
ms.service: microsoft-365-security
ms.subservice: m365d
ms.localizationpriority: medium
ms.collection: M365-security-compliance
f1.keywords: NOCSH
ms.openlocfilehash: a3e0cc3c79829ad5a13a6da29858d6d7c60cf322
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/31/2022
ms.locfileid: "67469810"
---
# <a name="responding-to-ransomware-attacks"></a>Fidye yazılımı saldırılarına yanıt verme

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

Fidye yazılımı saldırısı altında olduğunuzdan veya şu anda bir fidye yazılımı saldırısı altında olduğunuzdan şüphelendiğinizde, olay yanıtı ekibinizle hemen güvenli iletişim kurun. Saldırıyı kesintiye uğratmak ve hasarı azaltmak için aşağıdaki yanıt aşamalarını gerçekleştirebilir:

* Araştırma ve kapsama
* Silme ve kurtarma

Bu makalede fidye yazılımı saldırılarına yanıt vermek için genelleştirilmiş bir playbook sağlanır. Bu makalede açıklanan adımları ve görevleri kendi güvenlik operasyonları playbook'unuza uyarlamayı göz önünde bulundurun.
NOT: Fidye yazılımı saldırılarını önleme hakkında bilgi için bkz. [Fidye yazılımlarına ve gasplara karşı hızlı koruma](/security/compass/protect-against-ransomware).

## <a name="containment"></a>Çevreleme

Kapsama ve araştırma mümkün olduğunca aynı anda gerçekleşmelidir; Ancak, araştırmak için daha fazla zaman elde etmek için hızla kapsamaya odaklanmanız gerekir. Bu adımlar, saldırının kapsamını belirlemenize ve yalnızca kullanıcı hesapları ve cihazlar gibi etkilenen varlıklarla yalıtmanıza yardımcı olur.

### <a name="step-1-assess-the-scope-of-the-incident"></a>1. Adım: Olayın kapsamını değerlendirme

Saldırının kapsamını keşfetmek için bu soru ve görev listesini inceleyin. Microsoft 365 Defender, olay yanıtı değerlendirmenize yardımcı olmak için etkilenen veya risk altındaki tüm varlıkların birleştirilmiş bir görünümünü sağlayabilir. Bkz[. Microsoft 365 Defender ile olay yanıtı](incidents-overview.md). Aşağıdakileri belirlemek için olaydaki uyarıları ve kanıt listesini kullanabilirsiniz:

* Hangi kullanıcı hesapları tehlikeye girebilir?
  * Yükü teslim etmek için hangi hesaplar kullanıldı?
* Hangi [eklenen](../defender-endpoint/investigate-machines.md) ve [bulunan](../defender-endpoint/device-discovery.md) cihazlar etkilenir ve nasıl etkilenir?
  * Kaynak cihazlar
  * Etkilenen cihazlar
  * Şüpheli cihazlar
* Olayla ilişkili tüm ağ iletişimlerini belirleyin.
* Hangi uygulamalar etkilenir?
* Hangi yükler yayıldı?
* Saldırgan güvenliği aşılmış cihazlarla nasıl iletişim kuruyor? (Ağ koruması [etkinleştirilmelidir](../defender-endpoint/enable-network-protection.md)):
  * IP ve URL için bir blok eklemek için [göstergeler sayfasına](../defender-endpoint/indicator-ip-domain.md#create-indicators-for-ips-and-urlsdomains) gidin (bu bilgilere sahipseniz).
* Yük teslim ortamı neydi?

### <a name="step-2-preserve-existing-systems"></a>2. Adım: Mevcut sistemleri koruma

Mevcut sistemleri saldırılara karşı korumak için bu görev ve soruların listesini inceleyin:

* Çevrimiçi yedeklemeleriniz varsa, saldırının söz konusu olduğundan emin olana kadar yedekleme sisteminin ağ bağlantısını kesmeyi göz önünde bulundurun, bkz[. Fidye yazılımlarına karşı koruma sağlamak için yedekleme ve geri yükleme planı | Microsoft Docs](/security/compass/backup-plan-to-protect-against-ransomware).
* Yakın ve etkin bir fidye yazılımı dağıtımıyla karşılaşıyor veya bu dağıtımı bekliyorsanız:
  * Saldırının bir parçası olduğundan şüphelendiğiniz [ayrıcalıklı ve yerel hesapları askıya alın](/investigate-users.md). Bunu, Microsoft 365 Defender portalındaki olayın özelliklerindeki **Kullanıcılar** sekmesinden yapabilirsiniz.
  * Tüm [uzak oturum açma oturumlarını](/defender-for-identity/playbook-domain-dominance) durdurun.
  * Güvenliği aşılmış kullanıcı hesabı parolalarını sıfırlayın ve güvenliği aşılmış kullanıcı hesaplarının kullanıcılarının yeniden oturum açmasını gerekli kılar.
  * Güvenliği aşılmış olabilecek kullanıcı hesapları için de aynı işlemi yapın.
  * Paylaşılan yerel hesapların güvenliği aşıldıysa, BT yöneticinizin kullanıma sunulan tüm cihazlarda parola değişikliğini zorunlu kılmanıza yardımcı olmasını sağlayın. Örnek Kusto sorgusu:

```kusto
DeviceLogonEvents | where DeviceName  contains (AccountDomain) | take 10 
```

* Henüz yalıtılmış olmayan ve kritik altyapının parçası olmayan cihazlar için:
  * Güvenliği aşılmış cihazları ağdan yalıtın, ancak kapatmayın.
  * Kaynak veya yayıcı cihazları tanımlarsanız, önce bunları yalıtın.
* Analiz için güvenliği aşılmış sistemleri koruma.

### <a name="step-3-prevent-the-spread"></a>3. Adım: Yayılmayı engelleme

Saldırının ek varlıklara yayılmasının engellenmesi için bu listeyi kullanın.

* Saldırıda paylaşılan yerel hesaplar kullanılıyorsa Yerel [Hesapların Uzaktan Kullanımını Engellemeyi](https://techcommunity.microsoft.com/t5/microsoft-security-baselines/blocking-remote-use-of-local-accounts/ba-p/701042) göz önünde bulundurun.
  * Yerel yönetici olan tüm ağ oturum açma işlemleri için Kusto sorgusu:

```kusto
DeviceLogonEvents
| where IsLocalAdmin == true and AccountDomain == DeviceName
| extend IsLocalLogon = tobool(todynamic(AdditionalFields).IsLocalLogon)
| where IsLocalLogon==false
```

* RDP olmayan oturum açma işlemleri için Kusto sorgusu (çoğu ağ için daha gerçekçi):

```kusto
DeviceLogonEvents
| where IsLocalAdmin == true and AccountDomain == DeviceName and LogonType != 'RemoteInteractive'
| extend IsLocalLogon = tobool(todynamic(AdditionalFields).IsLocalLogon)
| where IsLocalLogon==false
```

* Virüs bulaşmış dosyalar için karantinaya alın ve göstergeler ekleyin.
* Virüsten koruma çözümünüzün en uygun koruma durumunda yapılandırılabilir olduğundan emin olun. Microsoft Defender Virüsten Koruma için buna şunlar dahildir:
  * [Gerçek zamanlı koruma](../defender-endpoint/configure-real-time-protection-microsoft-defender-antivirus.md) etkindir.
  * [Kurcalama koruması](../defender-endpoint/prevent-changes-to-security-settings-with-tamper-protection.md) etkindir. Microsoft 365 Defender portalında **, Kurcalama koruması > Ayarlar > Uç Noktalar > Gelişmiş özellikler'i** seçin.
  * [Saldırı yüzeyi azaltma (ASR)](../defender-endpoint/enable-attack-surface-reduction.md) kuralları etkindir.
  * [Bulut koruması](../defender-endpoint/enable-attack-surface-reduction.md) etkindir.
* Exchange ActiveSync ve OneDrive eşitleme devre dışı bırakın.
  * Posta kutusunun Exchange ActiveSync devre dışı bırakmak için bkz. [Exchange Online'da kullanıcılar için Exchange ActiveSync devre dışı bırakma](/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-exchange-activesync).
  * Posta kutusuna diğer erişim türlerini devre dışı bırakmak için bkz:
    * [Posta kutusu için MAPI'yi etkinleştirme veya devre dışı bırakma](/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi).
    * [Bir kullanıcı için POP3 veya IMAP4 erişimini etkinleştirin veya devre dışı bırakın](/exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access).
  * OneDrive eşitleme duraklatılması, bulut verilerinizin virüs bulaşmış olabilecek cihazlar tarafından güncelleştirilmesinden korunmasına yardımcı olur. Daha fazla bilgi için bkz. [OneDrive'da eşitlemeyi duraklatma ve sürdürme](https://support.microsoft.com/office/how-to-pause-and-resume-sync-in-onedrive-2152bfa4-a2a5-4d3a-ace8-92912fb4421e).
* Etkilenen sistemlere ilgili düzeltme eklerini ve yapılandırma değişikliklerini uygulayın.
* İç ve dış denetimleri kullanarak fidye yazılımı iletişimlerini engelleyin.
* Önbelleğe alınmış içeriği temizleme

## <a name="investigation"></a>Soruşturma

Saldırıyı araştırmak ve yanıtınızı planlamak için bu bölümü kullanın.

### <a name="assess-your-current-situation"></a>Geçerli durumunuzu değerlendirme

* Başlangıçta fidye yazılımı saldırısının farkında olmanıza neden olan şey nedir?
  * BT personeli yedeklemelerin silindiğini fark etme, virüsten koruma uyarıları, uç nokta algılama ve yanıt (EDR) uyarıları veya şüpheli sistem değişiklikleri gibi ilk tehdidi belirlediyse, genellikle bu makalede açıklanan kapsama eylemleriyle saldırıyı engellemek için hızlı kararlı önlemler almak mümkündür.
* Olayı ilk olarak hangi tarih ve saatle öğrendiniz?
  * Bu tarihte cihazlara hangi sistem ve güvenlik güncelleştirmeleri yüklenmedi? Bu, diğer cihazlarda ele alınabilmeleri için hangi güvenlik açıklarından yararlanılmış olabileceğini anlamak için önemlidir.
  * Bu tarihte hangi kullanıcı hesapları kullanıldı?
  * Bu tarihten sonra hangi yeni kullanıcı hesapları oluşturuldu?
  * Olayın gerçekleştiği sırada otomatik olarak başlamak için hangi programlar eklendi?
* Saldırganın şu anda sistemlere eriştiğine dair bir gösterge var mı?
  * Olağan dışı etkinlik yaşayan şüpheli bir sistem var mı?
  * Saldırgan tarafından aktif olarak kullanılan şüpheli bir hesap var mı?
  * EDR, güvenlik duvarı, VPN, web proxy'si ve diğer günlüklerde etkin komut ve denetim (C2) sunucuları olduğuna dair bir kanıt var mı?

### <a name="identify-the-ransomware-process"></a>Fidye yazılımı işlemini tanımlama

* [Gelişmiş avcılığı](/microsoft-365/security/defender/advanced-hunting-overview.md) kullanarak, diğer cihazlardaki işlem oluşturma olaylarında tanımlanan işlemi arayın.

### <a name="look-for-exposed-credentials-in-the-infected-devices"></a>Virüslü cihazlarda kullanıma sunulan kimlik bilgilerini arayın

* Kimlik bilgileri tehlikeye girmiş olabilecek kullanıcı hesapları için hesap parolalarını sıfırlayın ve kullanıcıların yeniden oturum açmasını sağlayın.
* Aşağıdaki GÇA'lar yanal hareketi gösterebilir:

<details>
  <summary>Genişletmek için tıklayın</summary>

* SuspiciousExploratoryCommands
* MLFileBasedAlert
* IfeoDebuggerPersistence
* SuspiciousRemoteFileDropAndExecution
* ExploratoryWindowsCommands
* IoaStickyKeys
* Mimikatz Defender Amplifikatör
* PARINACOTA tarafından kullanılan ağ tarama aracı
* DefenderServerAlertMSSQLServer
* SuspiciousLowReputationFileDrop
* SuspiciousServiceExecution
* AdminUserAddition
* MimikatzArtifactsDetector
* Scuba-WdigestEnabledToAccessCredentials
* DefenderMalware
* MLSuspCmdBehavior
* MLSuspiciousRemoteInvocation
* SuspiciousRemoteComponentInvocation
* SuspiciousWmiProcessCreation
* MLCmdBasedWithRemoting
* İşlem Erişimleri Lsass
* Şüpheli Rundll32 İşlem Yürütmesi
* BitsAdmin
* DefenderCobaltStrikeDetection
* DefenderHacktool
* IoaSuspPSCommandline
* Metasploit
* MLSuspToolBehavior
* RegistryQueryForPasswords
* SuspiciousWdavExclusion
* ASEPRegKey
* CobaltStrikeExecutionDetection
* DefenderBackdoor
* DefenderBehaviorSuspiciousActivity
* DefenderMalwareExecuted
* DefenderServerAlertDomainController
* DupTokenPrivilegeEscalationDetector
* FakeWindowsBinary
* IoaMaliciousCmdlets
* LivingOffTheLandBinary
* MicrosoftSignedBinaryAbuse
* MicrosoftSignedBinaryScriptletAbuse
* MLFileBasedWithRemoting
* MLSuspSvchostBehavior
* ReadSensitiveMemory
* RemoteCodeInjection-IREnabled
* Scuba-EchoSeenOverPipeOnLocalhost
* Scuba-SuspiciousWebScriptFileDrop
* odbcconf tarafından şüpheli DLL kaydı
* Şüpheli DPAPI Etkinliği
* Şüpheli Exchange İşlem Yürütmesi
* Şüpheli zamanlanmış görev başlatma
* SuspiciousLdapQueryDetector
* SuspiciousScheduledTaskRegistration
* Güvenilmeyen uygulama bir RDP bağlantısı açar

</details>

### <a name="identify-the-line-of-business-lob-apps-that-are-unavailable-due-to-the-incident"></a>Olay nedeniyle kullanılamayan iş kolu (LOB) uygulamalarını belirleme

* Uygulama için kimlik gerekiyor mu?
  * Kimlik doğrulaması nasıl gerçekleştirilir?
  * Sertifikalar veya gizli diziler gibi kimlik bilgileri nasıl depolanır ve yönetilir?
* Uygulamanın, yapılandırmasının ve verilerinin değerlendirilen yedeklemeleri kullanılabilir mi?
* Risk altındaki kurtarma işleminizi belirleyin.

## <a name="eradication-and-recovery"></a>Silme ve kurtarma

Tehdidi ortadan kaldırıp zarar görmüş kaynakları kurtarmak için bu adımları kullanın.

### <a name="step-1-verify-your-backups"></a>1. Adım: Yedeklemelerinizi doğrulama

Çevrimdışı yedeklemeleriniz varsa, büyük olasılıkla fidye yazılımı yükünü (kötü amaçlı yazılım) ortamınızdan kaldırdıktan ve Microsoft 365 kiracınızda yetkisiz erişim olmadığını doğruladıktan sonra şifrelenmiş verileri geri yükleyebilirsiniz.

### <a name="step-2-add-indicators"></a>2. Adım: Gösterge ekleme

Bilinen saldırgan iletişim kanallarını gösterge olarak, güvenlik duvarlarında, ara sunucularınızda ve uç noktalarda engellenmiş olarak ekleyin.

### <a name="step-3-reset-compromised-users"></a>3. Adım: Güvenliği aşılmış kullanıcıları sıfırlama

Güvenliği aşılmış bilinen tüm kullanıcı hesaplarının parolalarını sıfırlayın ve yeni bir oturum açma gerektirir.

* Domain Admins grubunun üyeleri gibi geniş bir yönetim yetkilisine sahip tüm ayrıcalıklı hesapların parolalarını sıfırlamayı göz önünde bulundurun.
* Bir saldırgan tarafından bir kullanıcı hesabı oluşturulmuş olabilirse, hesabı devre dışı bırakın. Olay için güvenlik adli işlemlerini gerçekleştirmeye yönelik bir plan olmadığı sürece hesabı silmeyin.

### <a name="step-4-isolate-attacker-control-points"></a>4. Adım: Saldırgan denetim noktalarını yalıtma

Kuruluş içindeki bilinen tüm saldırgan denetim noktalarını İnternet'ten yalıtın.

### <a name="step-5-remove-malware"></a>5. Adım: Kötü amaçlı yazılımları kaldırma

Kötü amaçlı yazılımları etkilenen cihazlardan kaldırın.

* Fidye yazılımıyla ilişkili yükü algılamak ve kaldırmak için tüm şüpheli bilgisayarlarda ve cihazlarda tam, güncel bir virüsten koruma taraması çalıştırın.
* Verileri veya eşlenen ağ sürücülerinin hedeflerini eşitleyen cihazları taramayı unutmayın.

### <a name="step-6-recover-files-on-a-cleaned-device"></a>6. Adım: Temizlenen bir cihazda dosyaları kurtarma

Temizlenmiş bir cihazdaki dosyaları kurtarma.

* Yerel dosya ve klasörlerinizi kurtarmaya çalışmak için Windows 7'de Windows 11, Windows 10, Windows 8.1 ve Sistem Koruması'nda [Dosya Geçmişi'ni](https://support.microsoft.com/help/17128) kullanabilirsiniz.

### <a name="step-7-recover-files-in-onedrive-for-business"></a>7. Adım: OneDrive İş dosyaları kurtarma

OneDrive İş dosyaları kurtarma.

* OneDrive İş'da Dosyaları Geri Yükleme özelliği, OneDrive'ın tamamını son 30 gün içinde önceki bir noktaya geri yüklemenizi sağlar. Daha fazla bilgi için bkz. [OneDrive'ınızı yeniden yükleyin](https://support.microsoft.com/office/restore-your-onedrive-fa231298-759d-41cf-bcd0-25ac53eb8a15).

### <a name="step-8-recover-deleted-email"></a>8. Adım: Silinen e-postayı kurtarma

Silinen e-postayı kurtarın.

* Fidye yazılımının bir posta kutusunda tüm e-postayı sildiği nadir durumlarda, silinen öğeleri kurtarabilirsiniz. Bkz[. Exchange Online'da kullanıcının posta kutusunda silinen iletileri kurtarma](/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages).

### <a name="step-9-re-enable-exchange-activesync-and-onedrive-sync"></a>9. Adım: Exchange ActiveSync ve OneDrive eşitleme yeniden etkinleştirme

* Bilgisayarlarınızı ve cihazlarınızı temizledikten ve verileri kurtardıktan sonra, daha önce 3. adımda devre dışı bırakmış olduğunuz Exchange ActiveSync ve OneDrive eşitleme yeniden etkinleştirebilirsiniz.
