---
title: Exchange Online posta kutularında gereksiz e-posta ayarlarını yapılandırma
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.collection:
- M365-security-compliance
description: Yöneticiler, Exchange Online posta kutularında gereksiz e-posta ayarlarını yapılandırmayı öğrenebilir. Bu ayarların çoğu Outlook veya Web üzerinde Outlook kullanıcıların kullanımına sunulmuştur.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 9f8c5ed64526b03cb4a47b06962be94274517789
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/31/2022
ms.locfileid: "67483486"
---
# <a name="configure-junk-email-settings-on-exchange-online-mailboxes"></a>Exchange Online posta kutularında gereksiz e-posta ayarlarını yapılandırma

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Uygulandığı öğe**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365 için Microsoft Defender plan 1 ve plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

posta kutuları Exchange Online olan Microsoft 365 kuruluşlarında, kuruluş istenmeyen posta önleme ayarları Exchange Online Protection (EOP) tarafından denetlenir. Daha fazla bilgi için bkz. [EOP'de istenmeyen posta koruması](anti-spam-protection.md).

Ancak, yöneticilerin Exchange Online'deki tek tek posta kutularında yapılandırabileceği belirli istenmeyen posta önleme ayarları da vardır:

> [!NOTE]
> EOP artık iletileri gereksiz e-posta kuralı yerine Gereksiz Email klasörüne yönlendirmek için kendi posta akışı teslim aracısını kullanıyor. **Set-MailboxJunkEmailConfiguration** cmdlet'indeki _Enabled_ parametresinin artık posta akışı üzerinde hiçbir etkisi yoktur. EOP, iletileri istenmeyen posta önleme ilkelerinde ayarlanan eylemlere göre yönlendirir. Kullanıcının Güvenilir Gönderen listesi ve Engellenen Gönderenler listesi her zamanki gibi çalışmaya devam eder.

- **İletileri istenmeyen posta önleme ilkelerine göre Gereksiz Email klasörüne taşıma**: İstenmeyen posta filtreleme kararı için **İletiyi Gereksiz Email klasörüne taşı** eylemiyle bir istenmeyen posta önleme ilkesi yapılandırıldığında, ileti posta kutusuna teslim edildikten sonra Gereksiz Email klasörüne taşınır. İstenmeyen posta önleme ilkelerindeki istenmeyen posta filtreleme kararları hakkında daha fazla bilgi için bkz. [EOP'de istenmeyen posta önleme ilkelerini yapılandırma](configure-your-spam-filter-policies.md). Benzer şekilde, sıfır saatlik otomatik temizleme (ZAP) teslim edilen bir iletinin istenmeyen posta veya kimlik avı olduğunu belirlerse, ileti İletiyi Gereksiz Email klasörüne taşı istenmeyen posta filtreleme karar eylemleri için **Gereksiz Email klasörüne** taşınır. ZAP hakkında daha fazla bilgi için bkz. [Exchange Online'de Sıfır saat otomatik temizleme (ZAP).](zero-hour-auto-purge.md)

- **Kullanıcıların Outlook'ta veya Web üzerinde Outlook kendileri için yapılandırabilecekleri gereksiz e-posta ayarları**: _Güvenli liste koleksiyonu_, her posta kutusunda Güvenilir Gönderenler listesi, Güvenilir Alıcılar listesi ve Engellenen Gönderenler listesidir. Bu listelerdeki girdiler, iletinin Gelen Kutusu'na mı yoksa Gereksiz Email klasörüne mi taşındığını belirler. Kullanıcılar, Güvenli Liste koleksiyonunu Outlook'ta veya Web üzerinde Outlook (eski adıyla Outlook Web App) kendi posta kutuları için yapılandırabilir. Yöneticiler, güvenli liste koleksiyonunu herhangi bir kullanıcının posta kutusunda yapılandırabilir.

EOP, istenmeyen posta filtreleme kararı eylemine göre iletileri Önemsiz Email klasörüne **taşıyabilir İletiyi Gereksiz Email klasörüne** veya posta kutusundaki Engellenen Gönderenler listesine taşıyabilir ve iletilerin Gereksiz Email klasörüne (posta kutusundaki Güvenilir Gönderenler listesine göre) teslim edilmesini önleyebilir.

Yöneticiler, posta kutularındaki güvenli liste koleksiyonundaki girdileri yapılandırmak için Exchange Online PowerShell kullanabilir (Güvenilir Gönderenler listesi, Güvenilir Alıcılar listesi ve Engellenen Gönderenler listesi).

> [!NOTE]
> Kullanıcıların kendi Güvenilir Gönderenler listelerine ekledikleri gönderenlerden gelen iletiler, EOP'nin bir parçası olarak içerik filtrelemeyi atlar (SCL -1'dir). Kullanıcıların Outlook'ta Güvenilir Gönderenler listesine girdi eklemesini önlemek için, bu makalenin devamında yer alan [Outlook'ta gereksiz e-posta ayarları hakkında](#about-junk-email-settings-in-outlook) bölümünde belirtildiği gibi grup ilkesi kullanın. İletilere ilke filtreleme, İçerik filtreleme ve Office 365 için Defender denetimleri uygulanmaya devam eder.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Başlamadan önce bilmeniz gerekenler

- Exchange Online PowerShell'i yalnızca bu makaledeki yordamları yapmak için kullanabilirsiniz. Exchange Online PowerShell'e bağlanmak için bkz[. Exchange Online PowerShell'e bağlanma](/powershell/exchange/connect-to-exchange-online-powershell).

- Bu makaledeki yordamları gerçekleştirebilmeniz için önce Exchange Online'de size izinler atanmalıdır. Özellikle, **Posta Alıcıları** rolüne (varsayılan olarak **Kuruluş Yönetimi**, **Alıcı Yönetimi** ve **Özel Posta Alıcıları** rol gruplarına atanır) veya **Kullanıcı Seçenekleri** rolüne (varsayılan olarak **Kuruluş Yönetimi** ve **Yardım Masası** rol gruplarına atanır) ihtiyacınız vardır. Exchange Online rol gruplarına kullanıcı eklemek için bkz. [Exchange Online rol gruplarını değiştirme](/Exchange/permissions-exo/role-groups#modify-role-groups). Exchange Online [PowerShell'e erişimleri](/powershell/exchange/disable-access-to-exchange-online-powershell) olduğu sürece, varsayılan izinlere sahip kullanıcıların bu yordamları kendi posta kutularında da gerçekleştirebileceklerini unutmayın.

- EOP'nin şirket içi Exchange posta kutularını koruduğu karma ortamlarda, şirket içi Exchange'de posta akışı kurallarını (aktarım kuralları olarak da bilinir) yapılandırmanız gerekir. Bu posta akışı kuralları, posta kutusunda gereksiz e-posta kuralının iletiyi Gereksiz Email klasörüne taşıyabilmesi için EOP istenmeyen posta filtreleme kararını çevirir. Ayrıntılar için bkz. [Karma ortamlarda gereksiz Email klasörüne istenmeyen posta göndermek için EOP'yi yapılandırma](/exchange/standalone-eop/configure-eop-spam-protection-hybrid).

- Paylaşılan posta kutuları için güvenilir gönderenler tasarım gereği Azure AD ve EOP ile eşitlenmez.

## <a name="use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox"></a>Exchange Online PowerShell kullanarak posta kutusunda güvenli liste koleksiyonunu yapılandırma

Posta kutusunda güvenli liste koleksiyonu Güvenilir Gönderenler listesini, Güvenilir Alıcılar listesini ve Engellenen Gönderenler listesini içerir. Varsayılan olarak, kullanıcılar güvenli liste koleksiyonunu Outlook'ta veya Web üzerinde Outlook kendi posta kutularında yapılandırabilir. Yöneticiler, kullanıcının posta kutusunda güvenli liste koleksiyonunu yapılandırmak için **Set-MailboxJunkEmailConfiguration** cmdlet'indeki ilgili parametreleri kullanabilir. Bu parametreler aşağıdaki tabloda açıklanmıştır.

|Set-MailboxJunkEmailConfiguration parametresi|Web üzerinde Outlook ayarı|
|---|---|
|_BlockedSendersAndDomains_|**Bu gönderenlerden veya etki alanlarından gelen e-postayı Gereksiz Email klasörüme taşıma**|
|_Kişiler Güvenildi_|**Kişilerimden gelen e-postaya güven**|
|_TrustedListsOnly_|**Yalnızca Güvenilir gönderenler ve etki alanları listemdeki adreslerden gelen e-postalara ve Güvenli posta listelerine güven**|
|_TrustedSendersAndDomains_<sup>\*</sup>|**Bu gönderenlerden gelen e-postaları Gereksiz Email klasörüme taşıma**|

<sup>\*</sup>**Notlar**:

- Exchange Online'da, Güvenilir Gönderenler listesindeki veya _TrustedSendersAndDomains_ parametresindeki **etki alanı girişleri** tanınmaz, bu nedenle yalnızca e-posta adreslerini kullanın. Dizin eşitlemeli tek başına EOP'de etki alanı girişleri varsayılan olarak eşitlenmez, ancak etki alanları için eşitlemeyi etkinleştirebilirsiniz. Daha fazla bilgi için bkz. [KB3019657](https://support.microsoft.com/help/3019657).
- **Set-MailboxJunkEmailConfiguration** cmdlet'ini kullanarak Güvenli Alıcılar listesini doğrudan değiştiremezsiniz (_TrustedRecipientsAndDomains_ parametresi çalışmaz). Güvenilir Gönderenler listesini değiştirirsiniz ve bu değişiklikler Güvenilir Alıcılar listesiyle eşitlenir.

Bir posta kutusunda güvenli liste koleksiyonunu yapılandırmak için aşağıdaki söz dizimini kullanın:

```PowerShell
Set-MailboxJunkEmailConfiguration <MailboxIdentity> -BlockedSendersAndDomains <EmailAddressesOrDomains | $null> -ContactsTrusted <$true | $false> -TrustedListsOnly <$true | $false> -TrustedSendersAndDomains  <EmailAddresses | $null>
```

Birden çok değer girmek ve _BlockedSendersAndDomains ve TrustedSendersAndDomains_ parametrelerinin varolan _girdilerinin_ üzerine yazmak için aşağıdaki söz dizimini kullanın: `"<Value1>","<Value2>"...`. Var olan diğer girdileri etkilemeden bir veya daha fazla değer eklemek veya kaldırmak için aşağıdaki söz dizimini kullanın: `@{Add="<Value1>","<Value2>"... ; Remove="<Value3>","<Value4>...}`

Bu örnekte, Ori Epstein'in posta kutusunda güvenli liste koleksiyonu için aşağıdaki ayarlar yapılandırılır:

- shopping@fabrikam.com değerini Engellenen Gönderenler listesine ekleyin.
- Güvenilir Gönderenler listesinden ve Güvenilir Alıcılar listesinden chris@fourthcoffee.com değeri kaldırın.
- Kişiler klasöründeki kişileri güvenilir gönderen olarak ele alınacak şekilde yapılandırılır.

```PowerShell
Set-MailboxJunkEmailConfiguration "Ori Epstein" -BlockedSendersAndDomains @{Add="shopping@fabrikam.com"} -TrustedSendersAndDomains @{Remove="chris@fourthcoffee.com"} -ContactsTrusted $true
```

Bu örnek, kuruluştaki tüm kullanıcı posta kutularındaki Engellenen Gönderenler listesinden etki alanı contoso.com kaldırır.

```PowerShell
$All = Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited; $All | foreach {Set-MailboxJunkEmailConfiguration $_.Name -BlockedSendersAndDomains @{Remove="contoso.com"}}
```

Ayrıntılı söz dizimi ve parametre bilgileri için bkz [. Set-MailboxJunkEmailConfiguration](/powershell/module/exchange/set-mailboxjunkemailconfiguration).

> [!NOTE]
>
> - Kullanıcı posta kutusunu hiç açmadıysa, önceki komutları çalıştırdığınızda bir hata alabilirsiniz. Toplu işlemlerde bu hatayı engellemek için **Set-MailboxJunkEmailConfiguration** komutuna ekleyin`-ErrorAction SilentlyContinue`.
> - Outlook Önemsiz Email Filtresi ek güvenli liste koleksiyonu ayarlarına sahiptir (örneğin, **E-posta gönderdiğim kişileri Otomatik olarak Güvenilir Gönderenler listesine ekle**). Daha fazla bilgi için bkz[. Gördüğünüz iletileri denetlemek için Gereksiz Email Filtrelerini kullanma](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077).

### <a name="how-do-you-know-this-worked"></a>Bunun çalıştığını nasıl anlarsınız?

Bir posta kutusunda güvenli liste koleksiyonunu başarıyla yapılandırdığınızdan emin olmak için aşağıdaki yordamlardan birini kullanın:

- değerini posta kutusunun adı, diğer adı veya e-posta adresiyle değiştirin _\<MailboxIdentity\>_ ve özellik değerlerini doğrulamak için aşağıdaki komutu çalıştırın:

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List trusted*,contacts*,blocked*
  ```

  Değer listesi çok uzunsa şu söz dizimini kullanın:

  ```PowerShell
  (Get-MailboxJunkEmailConfiguration -Identity <MailboxIdentity>).BlockedSendersAndDomains
  ```

## <a name="about-junk-email-settings-in-outlook"></a>Outlook'ta gereksiz e-posta ayarları hakkında

Outlook'ta kullanılabilen istemci tarafı Gereksiz Email Filtre ayarlarını etkinleştirmek, devre dışı bırakmak ve yapılandırmak için grup ilkesi kullanın. Daha fazla bilgi için bkz. [Kurumlar için Microsoft 365 Uygulamaları, Office 2019 ve Office 2016 için Yönetim Şablonu dosyaları (ADMX/ADML) ve Office Özelleştirme Aracı ve](https://www.microsoft.com/download/details.aspx?id=49030) [grup ilkesi kullanarak Güvenilir Gönderenler listesi gibi gereksiz e-posta ayarlarını dağıtma](https://support.microsoft.com/help/2252421).

Outlook Önemsiz Email Filtresi varsayılan değere ayarlandığında **, Ev** \> **Gereksiz Gereksiz** \> **Gereksiz E-posta Seçenekleri Seçenekleri'nde** \> **Otomatik filtreleme yok** olarak ayarlandığında, Outlook iletileri istenmeyen posta olarak sınıflandırmaya çalışmaz, ancak yine de teslimden sonra iletileri Önemsiz Email klasörüne taşımak için güvenli liste koleksiyonunu (Güvenilir Gönderenler listesi, Güvenilir Alıcılar listesi ve Engellenen Gönderenler listesi) kullanır. Bu ayarlar hakkında daha fazla bilgi için bkz[. Gereksiz Email Filtresine Genel Bakış](https://support.microsoft.com/office/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089).

> [!NOTE]
> Microsoft 365 kuruluşlarında Gereksiz Email Filtresi'ni EOP'den gelen istenmeyen posta filtreleme kararlarıyla gereksiz çakışmaları (hem pozitif hem de negatif) önlemek için Outlook'ta **Otomatik filtreleme yok** olarak bırakmanızı öneririz.

Outlook Önemsiz Email Filtresi **Düşük** veya **Yüksek** olarak ayarlandığında, Outlook Önemsiz Email Filtresi istenmeyen postaları tanımlamak ve Gereksiz Email klasörüne taşımak için kendi SmartScreen filtre teknolojisini kullanır. Bu istenmeyen posta sınıflandırması, EOP tarafından belirlenen istenmeyen posta güvenilirlik düzeyinden (SCL) ayrıdır. Aslında, Outlook EOP'den SCL'yi yoksayar (EOP iletiyi istenmeyen posta filtrelemeyi atlamak için işaretlemediği sürece) ve iletinin istenmeyen posta olup olmadığını belirlemek için kendi ölçütlerini kullanır. Elbette EOP ve Outlook'tan gelen istenmeyen posta kararının aynı olması mümkündür. Bu ayarlar hakkında daha fazla bilgi için bkz[. Gereksiz Email Filtresi'nde koruma düzeyini değiştirme](https://support.microsoft.com/office/e89c12d8-9d61-4320-8c57-d982c8d52f6b).

> [!NOTE]
> Kasım 2016'da Microsoft, Exchange ve Outlook'ta SmartScreen filtreleri için istenmeyen posta tanım güncelleştirmeleri üretmeyi durdurdu. Mevcut SmartScreen istenmeyen posta tanımları yerinde bırakıldı, ancak zaman içinde etkinliği büyük olasılıkla azalacaktır. Daha fazla bilgi için bkz. [Outlook ve Exchange'de SmartScreen desteğini kullanımdan kaldırma](https://techcommunity.microsoft.com/t5/exchange-team-blog/deprecating-support-for-smartscreen-in-outlook-and-exchange/ba-p/605332).

Bu nedenle, Outlook Gereksiz Email Filtresi iletileri Gereksiz Email klasörüne taşımak için posta kutusunun güvenli liste koleksiyonunu ve kendi istenmeyen posta sınıflandırmasını kullanabilir.

Hem Outlook hem de Web üzerinde Outlook güvenli liste koleksiyonunu destekler. Güvenli liste koleksiyonu Exchange Online posta kutusuna kaydedilir, bu nedenle Outlook'taki güvenli liste koleksiyonundaki değişiklikler Web üzerinde Outlook'da görünür ve bunun tersi de geçerlidir.

## <a name="limits-for-junk-email-settings"></a>Gereksiz e-posta ayarları için sınırlar

Kullanıcının posta kutusunda depolanan güvenli liste koleksiyonu (Güvenilir Gönderenler listesi, Güvenilir Alıcılar listesi ve Engellenen Gönderenler listesi) de EOP ile eşitlenir. Dizin eşitlemesi ile safelist koleksiyonu Azure AD ile eşitlenir.

- Kullanıcının posta kutusunda güvenli liste koleksiyonu, tüm listeleri ve ek gereksiz e-posta filtresi ayarlarını içeren 510 KB sınırına sahiptir. Bir kullanıcı bu sınırı aşarsa şuna benzer bir Outlook hatası alır:

  > Sunucu Gereksiz E-posta listelerine eklenemiyor/eklenemiyor. Sunucuda izin verilen boyutun üzerindesiniz. Sunucudaki Gereksiz E-posta filtresi, Gereksiz E-posta listeleriniz sunucunun izin verdiği boyuta küçültülene kadar devre dışı bırakılır.

  Bu sınır ve nasıl değiştireceği hakkında daha fazla bilgi için bkz. [KB2669081](https://support.microsoft.com/help/2669081).

- EOP'deki eşitlenmiş güvenli liste koleksiyonu aşağıdaki eşitleme sınırlarına sahiptir:
  - **Kişilerimden gelen güven e-postası** etkinleştirildiyse, Güvenilir Gönderenler listesindeki, Güvenilir Alıcılar listesindeki ve dış kişilerdeki toplam girdi sayısı 1024.
  - Engellenen Gönderenler listesinde ve Engellenen Etki Alanları listesinde toplam 500 girdi.

  1024 giriş sınırına ulaşıldığında aşağıdaki işlemler gerçekleşir:

  - Liste, PowerShell ve Web üzerinde Outlook girdilerini kabul etme işlemini durdurur, ancak hiçbir hata görüntülenmez.

    Outlook kullanıcıları, 510 KB'lık Outlook sınırına ulaşana kadar 1024'ten fazla giriş eklemeye devam edebilir. EOP filtresi posta kutusuna teslim etmeden önce iletiyi engellemediği sürece (posta akışı kuralları, kimlik sahtekarlığı önleme vb.) Outlook bu ek girdileri kullanabilir.

- Dizin eşitlemesi ile girişler aşağıdaki sırayla Azure AD eşitlenir:
  1. **Kişilerimden gelen e-postaya güven etkinse, kişilere posta** gönderin.
  2. Güvenilir Gönderen listesi ve Güvenilir Alıcı listesi, ilk 1024 girdileri için her değişiklik yapıldığında birleştirilir, yinelenenleri kaldırılır ve alfabetik olarak sıralanır.

  İlk 1024 girdileri kullanılır ve ilgili bilgiler ileti üst bilgilerinde damgalanır.

  1024'ün üzerindeki Azure AD eşitlenmemiş girişler Outlook tarafından işlenir (Web üzerinde Outlook değil) ve ileti üst bilgilerinde hiçbir bilgi damgalanmaz.

Gördüğünüz gibi, **Kişilerimden gelen e-postaya güven** ayarının etkinleştirilmesi eşitlenebilen Güvenilir Gönderenlerin ve Güvenilir Alıcıların sayısını azaltır. Sorun buysa, bu özelliği kapatmak için grup ilkesi kullanmanızı öneririz:

- Dosya adı: outlk16.opax
- İlke ayarı: **Kişilerden gelen e-postaya güven**
