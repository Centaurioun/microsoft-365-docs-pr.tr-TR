---
title: Windows cihazlarda Office 2013 için Modern kimlik doğrulamasını etkinleştirme
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
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
- okr_smb
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7dc1c01a-090f-4971-9677-f1b192d6c910
description: Microsoft Office 2013 yüklü cihazlar için modern kimlik doğrulamasını etkinleştirmek için kayıt defteri anahtarlarını ayarlamayı öğrenin.
ms.openlocfilehash: a272eacc546aa4d9dadbf9acac1ae1372f332209
ms.sourcegitcommit: 87283bb02ca750286f7c069f811b788730ed5832
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2022
ms.locfileid: "68663334"
---
# <a name="enable-modern-authentication-for-office-2013-on-windows-devices"></a>Windows cihazlarda Office 2013 için Modern kimlik doğrulamasını etkinleştirme

Microsoft Windows bilgisayarlarda Microsoft Office 2013, Modern kimlik doğrulamayı destekler. Ancak, bunu açmak için aşağıdaki kayıt defteri anahtarlarını yapılandırmanız gerekir:

|Kayıt defteri anahtarı|Tür|Değer|
|:---|:---:|:---:|
|HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell|REG_DWORD|1|
|HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Common\Identity\EnableADAL|REG_DWORD|1|
|HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Common\Identity\Version|REG_DWORD|1|

> [!NOTE]
> Modern kimlik doğrulaması Office 2016 veya sonraki sürümlerde zaten etkindir. Office'in sonraki sürümleri için bu kayıt defteri anahtarlarını ayarlamanız gerekmez.

>[!IMPORTANT]
> Microsoft 365'te Exchange Online posta kutuları için temel kimlik doğrulaması kapalıdır. Başka bir deyişle, Outlook 2013 modern kimlik doğrulaması kullanacak şekilde yapılandırılmamışsa bağlanma özelliğini kaybeder. Daha fazla bilgi için bkz. [Exchange Online'da temel kimlik doğrulaması](https://techcommunity.microsoft.com/t5/exchange-team-blog/basic-authentication-deprecation-in-exchange-online-september/ba-p/3609437).

## <a name="software-requirements"></a>Yazılım gereksinimleri

Office 2013 istemci uygulamaları için MFA'yı etkinleştirmek için, [Tıkla-çalıştır tabanlı bir yüklemeniz](http://howtomicrosoftofficetutorials.blogspot.com/2016/12/plan-for-multi-factor-authentication.html#bk_clicktorun) veya [MSI tabanlı](http://howtomicrosoftofficetutorials.blogspot.com/2016/12/plan-for-multi-factor-authentication.html#bk_msi) bir yüklemeniz olup olmadığına bağlı olarak aşağıdaki yazılımların (aşağıda listelenen sürüm veya sonraki bir sürüm) yüklü olması gerekir.

Office yüklemenizin Tıkla-Çalıştır mı yoksa MSI tabanlı mı olduğunu belirlemek için:

1.    Outlook 2013'ü başlatın.
2.    **Dosya** **menüsünden Office Hesabı'nı** seçin.
3.    Outlook 2013 Tıkla-Çalıştır yüklemeleri için **Güncelleştirme Seçenekleri** öğesi görüntülenir. MSI tabanlı yüklemeler için **Güncelleştirme Seçenekleri** öğesi görüntülenmez.

      :::image type="content" source="../../security/defender-endpoint/images/office-2013-run-installation.png" alt-text="Office 2013'ün ekran görüntüsü":::

### <a name="click-to-run-installations"></a>Tıkla-çalıştır yüklemeleri

Tıkla-çalıştır yüklemeleri için aşağıdaki dosyaların yüklü olması gerekir. Dosya sürümünüz listelenen dosya sürümüne eşit veya ondan büyük değilse, güncelleştirmek için aşağıdaki adımları izleyin.

|Dosya adı|Bilgisayarınızdaki yükleme yolu|Dosya sürümü|
|---|---|---|
|MSO.DLL|C:\Program Files\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\MSO.DLL|15.0.4753.1001|
|Csı. DLLL|CSI.DLL C:\Program Files\Microsoft Office 15\root\office15\csi.dll|15.0.4753.1000|
|Groove.EXE*|C:\Program Files\Microsoft Office 15\root\office15\GROOVE.exe|15.0.4763.1000|
|Outlook.exe|C:\Program Files\Microsoft Office 15\root\office15\OUTLOOK.exe|15.0.4753.1002|
|ADAL.DLL|C:\Program Files\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\ADAL.DLL|1.0.2016.624|
|Iexplore.exe|C:\Program Files\Internet Explorer|Değişir|

\* Groove.EXE Office yüklemenizin bir parçası değilse, Azure Active Directory Kimlik Doğrulama Kitaplığı'nın (ADAL) çalışması için yüklenmesi gerekmez. Ancak, Groove.EXE varsa tabloda listelenen dosya sürümü gereklidir.

### <a name="msi-based-installations"></a>MSI tabanlı yüklemeler

MSI tabanlı yüklemeler için aşağıdaki dosyaların yüklü olması gerekir. Dosya sürümünüz listelenen dosya sürümüne eşit veya ondan büyük değilse, güncelleştirmek için Güncelleştirmenin alınacağı yer sütunundaki bağlantıyı kullanın.

|Dosya adı|Bilgisayarınızdaki yükleme yolu|Güncelleştirmenin alınacağı yer|Sürüm|
|---|---|---|---|
|MSO.DLL|C:\Program Files\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\MSO.DLL|[KB3085480](https://support.microsoft.com/en-us/topic/description-of-the-security-update-for-office-2013-september-10-2019-0d171ba2-2eba-a2ca-a54d-c0f568de6bcc)|15.0.4753.1001|
|Csı. DLLL|CSI.DLL C:\Program Files\Microsoft Office 15\root\office15\csi.dll|[KB3172545](https://support.microsoft.com/en-us/topic/july-11-2017-update-for-office-2013-kb3172545-d6b47054-04d5-5154-40ba-3436d1e0efdb)|15.0.4753.1000|
|Groove.EXE*|C:\Program Files\Microsoft Office 15\root\office15\GROOVE.exe|[KB4022226](https://support.microsoft.com/en-us/topic/august-7-2018-update-for-onedrive-for-business-for-office-2013-kb4022226-6163bb26-cbde-eb16-ac42-abfda7afbf68)|15.0.4763.1000|
|Outlook.exe|C:\Program Files\Microsoft Office 15\root\office15\OUTLOOK.exe|[KB4484096](https://support.microsoft.com/en-us/topic/october-1-2019-update-for-outlook-2013-kb4484096-6513145a-cc75-1cd1-72b7-78cb62d8476b)|15.0.4753.1002|
|ADAL.DLL|C:\Program Files\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\ADAL.DLL|[KB3085565](https://support.microsoft.com/en-us/topic/july-5-2016-update-for-office-2013-kb3085565-1d1a6d24-fbd4-1bae-242f-a35e0e2aba40)|1.0.2016.624|
|Iexplore.exe|C:\Program Files\Internet Explorer|[MS14-052](https://support.microsoft.com/en-us/topic/ms14-052-cumulative-security-update-for-internet-explorer-september-9-2014-17d29b71-9e78-0bc1-8961-7b812d04e4e1)|Geçerli değil|

\* Groove.EXE Office yüklemenizin bir parçası değilse, Azure Active Directory Kimlik Doğrulama Kitaplığı'nın (ADAL) çalışması için yüklenmesi gerekmez. Ancak, Groove.EXE varsa tabloda listelenen dosya sürümü gereklidir.

## <a name="enable-modern-authentication-for-office-2013-clients"></a>Office 2013 istemcileri için modern kimlik doğrulamayı etkinleştirme

1. Outlook'u kapatın.

2. Aşağıdaki metni kopyalayıp Not Defteri'ne yapıştırın:

   ```text
   Windows Registry Editor Version 5.00

   [HKEY_CURRENT_USER\Software\Microsoft\Exchange]
   "AlwaysUseMSOAuthForAutoDiscover"=dword:00000001

   [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Common]

   [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Common\Identity]
   "EnableADAL"=dword:00000001
   "Version"=dword:00000001
   ```

3. Dosyayı bulmak kolay bir konuma .txt yerine .reg dosya uzantısıyla kaydedin. Örneğin, `C:\Data\Office2013_Enable_ModernAuth.reg`.

4. Dosya Gezgini açın (eski adıyla Windows Gezgini), az önce kaydettiğiniz .reg dosyasının konumuna gidin ve çift tıklayın.

5. Görüntülenen **Kullanıcı hesabı denetimi** iletişim kutusunda, uygulamanın cihazınızda değişiklik yapmasına izin vermek için **Evet'e** tıklayın.

6. Görüntülenen **Kayıt Defteri Düzenleyicisi** uyarı iletişim kutusunda, değişiklikleri kabul etmek için **Evet'e** tıklayın.

Kayıt defteri anahtarlarını ayarladıktan sonra, Office 2013 uygulamalarını Microsoft 365 ile çok faktörlü kimlik doğrulamasını (MFA) kullanacak şekilde ayarlayabilirsiniz. Daha fazla bilgi için bkz. [Çok faktörlü kimlik doğrulamasını ayarlama](set-up-multi-factor-authentication.md).

Şu anda Herhangi bir Office istemci uygulamasında oturum açtıysanız, değişikliğin geçerli olması için oturumu kapatıp yeniden açmanız gerekir. Aksi takdirde, kimlik kurulana kadar MRU ve dolaşım ayarları kullanılamaz.

## <a name="disable-modern-authentication-on-devices"></a>Cihazlarda modern kimlik doğrulamayı devre dışı bırakma

Cihazda modern kimlik doğrulamasını devre dışı bırakma yordamı çok benzer, ancak daha az kayıt defteri anahtarı gereklidir ve değerlerini 0 olarak ayarlamanız gerekir.

|Kayıt defteri anahtarı|Tür|Değer|
|---|:---:|:---:|
|HKEY_CURRENT_USER\Software\Microsoft\Windows\Shell|REG_DWORD|0|
|HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL|REG_DWORD|0|

```text
Windows Registry Editor Version 5.00

[HKEY_CURRENT_USER\Software\Microsoft\Exchange]
"AlwaysUseMSOAuthForAutoDiscover"=dword:00000000

[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Common]

[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Common\Identity]
"EnableADAL"=dword:00000000
```

## <a name="related-content"></a>İlgili içerik

[Office 2013'te ikinci bir doğrulama yöntemiyle oturum açma](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)

[Outlook parola ister ve Office 365 bağlanmak için Modern Kimlik Doğrulaması kullanmaz](/outlook/troubleshoot/authentication/outlook-prompt-password-modern-authentication-enabled)
