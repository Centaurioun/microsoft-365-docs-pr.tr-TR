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
ms.openlocfilehash: 3643db4b8d255809fc0ad125b76173b7d3b1a3d3
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68188339"
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
