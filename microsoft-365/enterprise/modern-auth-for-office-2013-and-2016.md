---
title: Office 2013 ve Office 2016 istemci uygulamalarında modern kimlik doğrulaması nasıl çalışır?
ms.author: tracyp
author: MSFTTracyP
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- MED150
- GMA150
- GPA150
- GEA150
- BCS160
ms.assetid: e4c45989-4b1a-462e-a81b-2a13191cf517
ms.collection:
- scotvorg
- M365-security-compliance
description: Microsoft 365 modern kimlik doğrulama özelliklerinin Office 2013 ve 2016 istemci uygulamalarında nasıl farklı çalıştığını öğrenin.
ms.openlocfilehash: e22f4106d52301acccebe53c6b42caa3663e2787
ms.sourcegitcommit: a250d043a2e42ecbc7b86147468d1660af5a6ba7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2022
ms.locfileid: "68672985"
---
# <a name="how-modern-authentication-works-for-office-2013-office-2016-and-office-2019-client-apps"></a>Modern kimlik doğrulaması Office 2013, Office 2016 ve Office 2019 istemci uygulamalarında nasıl çalışır?

*Bu makale hem Microsoft 365 Kurumsal hem de Office 365 Kurumsal için geçerlidir.*

Office 2013, Office 2016 ve Office 2019 istemci uygulamalarının Exchange Online, SharePoint Online ve Skype Kurumsal Online için Microsoft 365 kiracısında kimlik doğrulama yapılandırmasına dayalı modern kimlik doğrulama özelliklerini nasıl kullandığını öğrenmek için bu makaleyi okuyun.

> [!NOTE]
> Office 2010 ve Office Mac 2011 gibi eski istemci uygulamaları modern kimlik doğrulamasını desteklemez ve yalnızca temel kimlik doğrulamasıyla kullanılabilir.

## <a name="availability-of-modern-authentication-for-microsoft-365-services"></a>Microsoft 365 hizmetleri için modern kimlik doğrulamasının kullanılabilirliği

Microsoft 365 hizmetleri için modern kimlik doğrulamasının varsayılan durumu şunlardır:

- varsayılan olarak Exchange Online için **açıktır**. [Kapatmak veya açmak için bkz. Exchange Online'de modern kimlik doğrulamasını etkinleştirme veya devre dışı bırakma](https://support.office.com/article/58018196-f918-49cd-8238-56f57f38d662).

- SharePoint Online için varsayılan olarak **açıktır** .

- Skype Kurumsal Online için varsayılan olarak **açıktır**. Kapatmak veya açmak için bkz[. Modern kimlik doğrulaması için Skype Kurumsal Online'ı etkinleştirme](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx).

> [!NOTE]
> 1 Ağustos 2017'den **önce** oluşturulan kiracılar için modern kimlik doğrulaması, Exchange Online ve Skype Kurumsal Online için varsayılan olarak **kapatılır**.

## <a name="sign-in-behavior-of-office-client-apps"></a>Office istemci uygulamalarının oturum açma davranışı

Office 2013 istemci uygulamaları varsayılan olarak eski kimlik doğrulamasını destekler. Eski, Microsoft Çevrimiçi Oturum Açma Yardımcısı'nı veya temel kimlik doğrulamasını desteklediği anlamına gelir. Bu istemcilerin modern kimlik doğrulama özelliklerini kullanabilmesi için Windows istemcisinde kayıt defteri anahtarlarının ayarlanmış olması gerekir. Yönergeler için bkz. [Windows cihazlarında Office 2013 için Modern Kimlik Doğrulamasını Etkinleştirme](https://support.office.com/article/7dc1c01a-090f-4971-9677-f1b192d6c910).

> [!IMPORTANT]
> Microsoft 365'te Exchange Online posta kutuları için temel kimlik doğrulaması kullanımı kullanım dışı bırakılıyor. Başka bir deyişle, Outlook 2013 modern kimlik doğrulaması kullanacak şekilde yapılandırılmamışsa bağlanma özelliğini kaybeder. Temel kimlik doğrulamasının kullanımdan kaldırılması hakkında daha fazla bilgi için [bu makaleyi](https://techcommunity.microsoft.com/t5/exchange-team-blog/basic-authentication-deprecation-in-exchange-online-september/ba-p/3609437) okuyun.

To enable modern authentication for any devices running Windows (for example on laptops and tablets), that have Microsoft Office 2013 installed, you need to set the following registry keys. The keys have to be set on each device that you want to enable for modern authentication:

|**Kayıt defteri anahtarı**|**Tür**|**Değer** |
|:-------|:------:|--------:|
|HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL  |REG_DWORD  |1  |
|HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version |REG_DWORD |1 |
|HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell |REG_DWORD |1 |

Skype Kurumsal ile nasıl çalıştığı hakkında bilgi edinmek için [Skype Kurumsal ile Modern Kimlik Doğrulaması (ADAL) kullanma](./hybrid-modern-auth-overview.md) bölümünü okuyun.

## <a name="software-requirements"></a>Yazılım gereksinimleri

Office 2013 istemci uygulamalarında çok faktörlü kimlik doğrulamasını (MFA) etkinleştirmek için, aşağıda listelenen yazılımı (aşağıda listelenen sürümde veya *sonraki* bir sürümde) yüklemiş olmanız gerekir. İşlem, yükleme türünüz (MSI tabanlı veya Tıkla-çalıştır aracılığıyla) bağlı olarak farklıdır.

İlk olarak, aşağıdaki adımlarla Office yüklemenizin MSI tabanlı mı yoksa Tıkla-çalıştır mı olduğunu öğrenin.

1. Outlook 2013'ü başlatın.
2. **Dosya** menüsünde **Office Hesabı'nı** seçin.
3. Outlook 2013 *Tıkla-Çalıştır* yüklemeleri için bir **Güncelleştirme Seçenekleri** öğesi görüntülenir. MSI tabanlı yüklemelerde Güncelleştirme Seçenekleri öğesi görüntülenmez.
    1. Tıkla-Çalıştır **Güncelleştirme Seçenekleri** düğmesi size 'Güncelleştirmeler otomatik olarak indirilir ve yüklenir' sözlerini ve geçerli sürümünüzü söyler.

### <a name="click-to-run-based-installations"></a>Tıkla-Çalıştır tabanlı yüklemeler

Tıkla-çalıştır tabanlı yüklemeler için aşağıda listelenen bir dosya sürümünde veya *daha sonraki* bir dosya sürümünde aşağıdaki yazılımların yüklü *olması gerekir*. Dosya sürümünüz listelenen dosya sürümüne eşit veya ondan büyük değilse, aşağıdaki adımları kullanarak güncelleştirin.


|Dosya adı  |Bilgisayarınızdaki yükleme yolu  |Dosya sürümü  |
|---------|---------|---------|
|MSO.DLL     |C:\Program Files\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\MSO.DLL       |15.0.4753.1001       |
|CSI.DLL   |CSI.DLL C:\Program Files\Microsoft Office 15\root\office15\csi.dll         |15.0.4753.1000        |
|Groove.EXE*     |C:\Program Files\Microsoft Office 15\root\office15\GROOVE.exe       |15.0.4763.1000      |
|Outlook.exe     |C:\Program Files\Microsoft Office 15\root\office15\OUTLOOK.exe         |15.0.4753.1002     |
|ADAL.DLL    |C:\Program Files\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\ADAL.DLL       |1.0.2016.624         |
|Iexplore.exe    |C:\Program Files\Internet Explorer     |değişir         |

\* Groove.EXE bileşeni Office yüklemenizde yoksa, ADAL'nin çalışması için yüklenmesi gerekmez. Ancak varsa, burada listelenen Groove.EXE için derleme gereklidir.

### <a name="msi-based-installations"></a>MSI tabanlı yüklemeler

MSI tabanlı yüklemeler için aşağıdaki yazılımların aşağıda listelenen dosya sürümünde veya *daha sonraki* bir dosya sürümünde yüklü *olması gerekir*. Dosya sürümünüz aşağıda listelenen dosya sürümüne eşit veya bundan büyük değilse, *KB Makalesini Güncelleştir* sütunundaki bağlantıyı kullanarak güncelleştirin.


|Dosya adı  |Bilgisayarınızdaki yükleme yolu  |Güncelleştirmenin alınacağı yer  |Sürüm  |
|---------|---------|---------|---------|
|MSO.DLL|C:\Program Files\Common Files\Microsoft Shared\OFFICE15\MSO.DLL     |[KB3085480](https://support.microsoft.com/en-us/topic/description-of-the-security-update-for-office-2013-september-10-2019-0d171ba2-2eba-a2ca-a54d-c0f568de6bcc)        |15.0.4753.1001       |
|CSI.DLL|C:\Program Files\Common Files\Microsoft Shared\OFFICE15\Csi.dll     |[KB3172545](https://support.microsoft.com/en-us/topic/july-11-2017-update-for-office-2013-kb3172545-d6b47054-04d5-5154-40ba-3436d1e0efdb)        |15.0.4753.1000         |
|Groove.exe*|C:\Program Files\Microsoft Office\Office15\GROOVE.EXE            |[KB4022226](https://support.microsoft.com/en-us/topic/august-7-2018-update-for-onedrive-for-business-for-office-2013-kb4022226-6163bb26-cbde-eb16-ac42-abfda7afbf68)        |15.0.4763.1000         |
|Outlook.exe|C:\Program Files\Microsoft Office\Office15\OUTLOOK.EXE          |[KB4484096](https://support.microsoft.com/en-us/topic/october-1-2019-update-for-outlook-2013-kb4484096-6513145a-cc75-1cd1-72b7-78cb62d8476b)        |15.0.4753.1002         |
|ADAL.DLL|C:\Program Files\Common Files\Microsoft Shared\OFFICE15\ADAL.DLL   |[KB3085565](https://support.microsoft.com/en-us/topic/july-5-2016-update-for-office-2013-kb3085565-1d1a6d24-fbd4-1bae-242f-a35e0e2aba40)        |1.0.2016.624         |
|Iexplore.exe|C:\Program Files\Internet Explorer                             |[MS14-052](https://support.microsoft.com/en-us/topic/ms14-052-cumulative-security-update-for-internet-explorer-september-9-2014-17d29b71-9e78-0bc1-8961-7b812d04e4e1)         |Geçerli değil         |

\* Groove.EXE bileşeni Office yüklemenizde yoksa, ADAL'nin çalışması için yüklenmesi gerekmez. Ancak varsa, burada listelenen Groove.EXE için derleme gereklidir.

Office 2016 ve Office 2019 istemcileri varsayılan olarak modern kimlik doğrulamasını destekler ve istemcinin bu yeni akışları kullanması için hiçbir eylem gerekmez. Ancak, eski kimlik doğrulamasını kullanmak için açık eylem gerekir.

Modern kimlik doğrulamasının açık olup olmamasına bağlı olarak Office 2013, Office 2016 ve Office 2019 istemci kimlik doğrulamasının Microsoft 365 hizmetleriyle nasıl çalıştığını görmek için aşağıdaki bağlantılara tıklayın.

- [Exchange Online](modern-auth-for-office-2013-and-2016.md#BK_EchangeOnline)

- [SharePoint Online](modern-auth-for-office-2013-and-2016.md#BK_SharePointOnline)

- [Skype Kurumsal Çevrimiçi Sürüm](modern-auth-for-office-2013-and-2016.md#BK_SFBO)

<a name="BK_EchangeOnline"> </a>
### <a name="exchange-online"></a>Exchange Online

Aşağıdaki tabloda, office 2013, Office 2016 ve Office 2019 istemci uygulamalarının modern kimlik doğrulamasıyla veya modern kimlik doğrulaması olmadan Exchange Online bağlandığındaki kimlik doğrulama davranışı açıklanmaktadır.

|Office istemci uygulaması sürümü***|Kayıt defteri anahtarı var mı?***|Modern kimlik doğrulaması açık mı?***|Kiracı için modern kimlik doğrulaması açık kimlik doğrulaması davranışı (varsayılan)***|Kiracı için modern kimlik doğrulaması kapalıyken kimlik doğrulama davranışı***|
|:-----|:-----|:-----|:-----|:-----|
|Office 2019  <br/> |No <br> AlwaysUseMSOAuthForAutoDiscover = 1 <br/> |Evet  <br/> |Outlook 2013, 2016 veya 2019'da modern kimlik doğrulamayı zorlar. <br/> [Daha fazla bilgi](https://support.microsoft.com/help/3126599/outlook-prompts-for-password-when-modern-authentication-is-enabled)|Outlook istemcisi içinde modern kimlik doğrulamasını zorlar.<br/> |
|Office 2019  <br/> |Hayır veya EnableADAL = 1  <br/> |Evet  <br/> |Önce modern kimlik doğrulaması denendi. Sunucu modern kimlik doğrulama bağlantısını reddederse temel kimlik doğrulaması kullanılır. Kiracı etkinleştirilmediğinde sunucu modern kimlik doğrulamasını reddeder.  <br/> |Önce modern kimlik doğrulaması denendi. Sunucu modern kimlik doğrulama bağlantısını reddederse temel kimlik doğrulaması kullanılır. Kiracı etkinleştirilmediğinde sunucu modern kimlik doğrulamasını reddeder.  <br/> |
|Office 2019  <br/> |Evet, EnableADAL = 1  <br/> |Evet  <br/> |Önce modern kimlik doğrulaması denendi. Sunucu modern kimlik doğrulama bağlantısını reddederse temel kimlik doğrulaması kullanılır. Kiracı etkinleştirilmediğinde sunucu modern kimlik doğrulamasını reddeder.  <br/> |Önce modern kimlik doğrulaması denendi. Sunucu modern kimlik doğrulama bağlantısını reddederse temel kimlik doğrulaması kullanılır. Kiracı etkinleştirilmediğinde sunucu modern kimlik doğrulamasını reddeder.  <br/> |
|Office 2019  <br/> |Evet, EnableADAL=0  <br/> |Hayır  <br/> |Temel kimlik doğrulaması  <br/> |Temel kimlik doğrulaması  <br/> |
|Office 2016  <br/> |No <br> AlwaysUseMSOAuthForAutoDiscover = 1 <br/> |Evet  <br/> |2013, 2016 veya 2019'da modern kimlik doğrulamayı zorlar. <br/> [Daha fazla bilgi](https://support.microsoft.com/help/3126599/outlook-prompts-for-password-when-modern-authentication-is-enabled)|Outlook istemcisi içinde modern kimlik doğrulamasını zorlar.<br/> |
|Office 2016  <br/> |Hayır veya EnableADAL = 1  <br/> |Evet  <br/> |Önce modern kimlik doğrulaması denendi. Sunucu modern kimlik doğrulama bağlantısını reddederse temel kimlik doğrulaması kullanılır. Kiracı etkinleştirilmediğinde sunucu modern kimlik doğrulamasını reddeder.  <br/> |Önce modern kimlik doğrulaması denendi. Sunucu modern kimlik doğrulama bağlantısını reddederse temel kimlik doğrulaması kullanılır. Kiracı etkinleştirilmediğinde sunucu modern kimlik doğrulamasını reddeder.  <br/> |
|Office 2016  <br/> |Evet, EnableADAL = 1  <br/> |Evet  <br/> |Önce modern kimlik doğrulaması denendi. Sunucu modern kimlik doğrulama bağlantısını reddederse temel kimlik doğrulaması kullanılır. Kiracı etkinleştirilmediğinde sunucu modern kimlik doğrulamasını reddeder.  <br/> |Önce modern kimlik doğrulaması denendi. Sunucu modern kimlik doğrulama bağlantısını reddederse temel kimlik doğrulaması kullanılır. Kiracı etkinleştirilmediğinde sunucu modern kimlik doğrulamasını reddeder.  <br/> |
|Office 2016  <br/> |Evet, EnableADAL=0  <br/> |Hayır  <br/> |Temel kimlik doğrulaması  <br/> |Temel kimlik doğrulaması  <br/> |
|Office 2013  <br/> |Hayır  <br/> |Hayır  <br/> |Temel kimlik doğrulaması  <br/> |Temel kimlik doğrulaması  <br/> |
|Office 2013  <br/> |Evet, EnableADAL = 1  <br/> |Evet  <br/> |Önce modern kimlik doğrulaması denendi. Sunucu modern kimlik doğrulama bağlantısını reddederse temel kimlik doğrulaması kullanılır. Kiracı etkinleştirilmediğinde sunucu modern kimlik doğrulamasını reddeder.  <br/> |Önce modern kimlik doğrulaması denendi. Sunucu modern kimlik doğrulama bağlantısını reddederse temel kimlik doğrulaması kullanılır. Kiracı etkinleştirilmediğinde sunucu modern kimlik doğrulamasını reddeder.  <br/> |

<a name="BK_SharePointOnline"> </a>
### <a name="sharepoint-online"></a>SharePoint Online

Aşağıdaki tabloda, Office 2013, Office 2016 ve Office 2019 istemci uygulamalarının SharePoint Online'a modern kimlik doğrulamasıyla veya modern kimlik doğrulaması olmadan bağlandığındaki kimlik doğrulama davranışı açıklanmaktadır.

|Office istemci uygulaması sürümü***|Kayıt defteri anahtarı var mı?***|Modern kimlik doğrulaması açık mı?***|Kiracı için modern kimlik doğrulaması açık kimlik doğrulaması davranışı (varsayılan)***|Kiracı için modern kimlik doğrulaması kapalıyken kimlik doğrulama davranışı***|
|:-----|:-----|:-----|:-----|:-----|
|Office 2019  <br/> |Hayır veya EnableADAL = 1  <br/> |Evet  <br/> |Yalnızca modern kimlik doğrulaması.  <br/> |Bağlantı kurulamaz.  <br/> |
|Office 2019  <br/> |Evet, EnableADAL = 1  <br/> |Evet  <br/> |Yalnızca modern kimlik doğrulaması.  <br/> |Bağlantı kurulamaz.  <br/> |
|Office 2019  <br/> |Evet, EnableADAL = 0  <br/> |Hayır  <br/> |Yalnızca Microsoft Çevrimiçi Oturum Açma Yardımcısı.  <br/> |Yalnızca Microsoft Çevrimiçi Oturum Açma Yardımcısı.  <br/> |
|Office 2016  <br/> |Hayır veya EnableADAL = 1  <br/> |Evet  <br/> |Yalnızca modern kimlik doğrulaması.  <br/> |Bağlantı kurulamaz.  <br/> |
|Office 2016  <br/> |Evet, EnableADAL = 1  <br/> |Evet  <br/> |Yalnızca modern kimlik doğrulaması.  <br/> |Bağlantı kurulamaz.  <br/> |
|Office 2016  <br/> |Evet, EnableADAL = 0  <br/> |Hayır  <br/> |Yalnızca Microsoft Çevrimiçi Oturum Açma Yardımcısı.  <br/> |Yalnızca Microsoft Çevrimiçi Oturum Açma Yardımcısı.  <br/> |
|Office 2013  <br/> |Hayır  <br/> |Hayır  <br/> |Yalnızca Microsoft Çevrimiçi Oturum Açma Yardımcısı.  <br/> |Yalnızca Microsoft Çevrimiçi Oturum Açma Yardımcısı.  <br/> |
|Office 2013  <br/> |Evet, EnableADAL = 1  <br/> |Evet  <br/> |Yalnızca modern kimlik doğrulaması.  <br/> |Bağlantı kurulamaz.  <br/> |

### <a name="skype-for-business-online"></a>Skype Kurumsal Çevrimiçi
<a name="BK_SFBO"> </a>

Aşağıdaki tabloda Office 2013, Office 2016 ve Office 2019 istemci uygulamalarının Skype Kurumsal Online'a modern kimlik doğrulamasıyla veya modern kimlik doğrulaması olmadan bağlandıklarında kimlik doğrulama davranışı açıklanmaktadır.

|Office istemci uygulaması sürümü***|Kayıt defteri anahtarı var mı?***|Modern kimlik doğrulaması açık mı?***|Kiracı için modern kimlik doğrulaması açık durumda kimlik doğrulama davranışı***|Kiracı için modern kimlik doğrulaması kapalıyken kimlik doğrulama davranışı (varsayılan)***|
|:-----|:-----|:-----|:-----|:-----|
|Office 2019  <br/> |Hayır veya EnableADAL = 1  <br/> |Evet  <br/> |Önce modern kimlik doğrulaması denendi. Sunucu modern kimlik doğrulama bağlantısını reddederse Microsoft Çevrimiçi Oturum Açma Yardımcısı kullanılır. Skype Kurumsal Çevrimiçi kiracılar etkinleştirilmediğinde sunucu modern kimlik doğrulamayı reddeder.  <br/> |Önce modern kimlik doğrulaması denendi. Sunucu modern kimlik doğrulama bağlantısını reddederse Microsoft Çevrimiçi Oturum Açma Yardımcısı kullanılır. Skype Kurumsal Çevrimiçi kiracılar etkinleştirilmediğinde sunucu modern kimlik doğrulamayı reddeder.  <br/> |
|Office 2019  <br/> |Evet, EnableADAL = 1  <br/> |Evet  <br/> |Önce modern kimlik doğrulaması denendi. Sunucu modern kimlik doğrulama bağlantısını reddederse Microsoft Çevrimiçi Oturum Açma Yardımcısı kullanılır. Skype Kurumsal Çevrimiçi kiracılar etkinleştirilmediğinde sunucu modern kimlik doğrulamayı reddeder.  <br/> |Önce modern kimlik doğrulaması denendi. Sunucu modern kimlik doğrulama bağlantısını reddederse Microsoft Çevrimiçi Oturum Açma Yardımcısı kullanılır. Skype Kurumsal Çevrimiçi kiracılar etkinleştirilmediğinde sunucu modern kimlik doğrulamayı reddeder.  <br/> |
|Office 2019  <br/> |Evet, EnableADAL = 0  <br/> |Hayır  <br/> |Yalnızca Microsoft Çevrimiçi Oturum Açma Yardımcısı.  <br/> |Yalnızca Microsoft Çevrimiçi Oturum Açma Yardımcısı.  <br/> |
|Office 2016  <br/> |Hayır veya EnableADAL = 1  <br/> |Evet  <br/> |Önce modern kimlik doğrulaması denendi. Sunucu modern kimlik doğrulama bağlantısını reddederse Microsoft Çevrimiçi Oturum Açma Yardımcısı kullanılır. Skype Kurumsal Çevrimiçi kiracılar etkinleştirilmediğinde sunucu modern kimlik doğrulamayı reddeder.  <br/> |Önce modern kimlik doğrulaması denendi. Sunucu modern kimlik doğrulama bağlantısını reddederse Microsoft Çevrimiçi Oturum Açma Yardımcısı kullanılır. Skype Kurumsal Çevrimiçi kiracılar etkinleştirilmediğinde sunucu modern kimlik doğrulamayı reddeder.  <br/> |
|Office 2016  <br/> |Evet, EnableADAL = 1  <br/> |Evet  <br/> |Önce modern kimlik doğrulaması denendi. Sunucu modern kimlik doğrulama bağlantısını reddederse Microsoft Çevrimiçi Oturum Açma Yardımcısı kullanılır. Skype Kurumsal Çevrimiçi kiracılar etkinleştirilmediğinde sunucu modern kimlik doğrulamayı reddeder.  <br/> |Önce modern kimlik doğrulaması denendi. Sunucu modern kimlik doğrulama bağlantısını reddederse Microsoft Çevrimiçi Oturum Açma Yardımcısı kullanılır. Skype Kurumsal Çevrimiçi kiracılar etkinleştirilmediğinde sunucu modern kimlik doğrulamayı reddeder.  <br/> |
|Office 2016  <br/> |Evet, EnableADAL = 0  <br/> |Hayır  <br/> |Yalnızca Microsoft Çevrimiçi Oturum Açma Yardımcısı.  <br/> |Yalnızca Microsoft Çevrimiçi Oturum Açma Yardımcısı.  <br/> |
|Office 2013  <br/> |Hayır  <br/> |Hayır  <br/> |Yalnızca Microsoft Çevrimiçi Oturum Açma Yardımcısı.  <br/> |Yalnızca Microsoft Çevrimiçi Oturum Açma Yardımcısı.  <br/> |
|Office 2013  <br/> |Evet, EnableADAL = 1  <br/> |Evet  <br/> |Önce modern kimlik doğrulaması denendi. Sunucu modern kimlik doğrulama bağlantısını reddederse Microsoft Çevrimiçi Oturum Açma Yardımcısı kullanılır. Skype Kurumsal Çevrimiçi kiracılar etkinleştirilmediğinde sunucu modern kimlik doğrulamayı reddeder.  <br/> |Yalnızca Microsoft Çevrimiçi Oturum Açma Yardımcısı.  <br/> |

## <a name="see-also"></a>Ayrıca bkz.

[Windows cihazlarında Office 2013 için Modern Kimlik Doğrulamasını etkinleştirme](../admin/security-and-compliance/enable-modern-authentication.md)

[Microsoft 365 için çok faktörlü kimlik doğrulama](../admin/security-and-compliance/multi-factor-authentication-microsoft-365.md)

[Çok faktörlü kimlik doğrulaması ile Microsoft 365'te oturum açma](https://support.microsoft.com/office/sign-in-to-microsoft-365-with-multi-factor-authentication-2b856342-170a-438e-9a4f-3c092394d3cb)

[Microsoft 365 Kurumsal genel bakış](microsoft-365-overview.md)
