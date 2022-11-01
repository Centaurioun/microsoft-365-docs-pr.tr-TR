---
title: Multi-Geo'da Kullanıcı Testi
description: Multi-Geo'da kullanıcı testi hakkında bilgi edinin
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.reviewer: dmwmsft
ms.service: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.date: ''
ms.custom:
- it-pro
ms.collection:
- M365-subscription-management
ms.openlocfilehash: c150743b97e31e06ca1107dd3e5669b5296ad67c
ms.sourcegitcommit: 0c72639cc3dc74667a6b14343d303f318e70d457
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/01/2022
ms.locfileid: "68806125"
---
# <a name="user-testing-in-multi-geo"></a>Multi-Geo'da Kullanıcı Testi

Azure Active Directory'de (Azure AD) iki tür kullanıcı nesnesi vardır: yalnızca bulut kullanıcıları ve eşitlenmiş kullanıcılar. Lütfen kullanıcı türünüz için uygun yönergeleri izleyin.

>[!TIP]
>Çok coğrafi konumu daha geniş kuruluşunuza dağıtmadan önce test kullanıcısı veya küçük bir kullanıcı grubuyla doğrulamalara başlamanızı öneririz.

## <a name="synchronize-users-preferred-data-location-using-azure-ad-connect"></a>Azure AD Connect kullanarak kullanıcının Tercih Edilen Veri Konumunu eşitleme

Şirketinizin kullanıcıları bir şirket içi Active Directory sisteminden Azure AD eşitlenmişse PreferredDataLocation'ları AD'de doldurulmalı ve Azure AD ile eşitlenmelidir.

Azure Active Directory Connect eşitlemesindeki işlemi izleyin: Şirket içi Active Directory Etki Alanı Hizmetlerinizden (AD DS) Tercih Edilen Veri Konumu eşitlemesini Azure AD olarak yapılandırmak <a href="/azure/active-directory/hybrid/how-to-connect-sync-feature-preferreddatalocation" target="_blank">için Microsoft 365 kaynakları için tercih edilen veri konumunu yapılandırın</a>.

Kullanıcının Tercih Edilen Veri Konumunu standart kullanıcı oluşturma iş akışınızın bir parçası olarak ayarlamanızı öneririz.

>[!IMPORTANT]
>OneDrive sağlanmamış yeni kullanıcılar için hesabı lisanslayıp kullanıcının PDL'sinin eşitlenmesinin ardından en az 48 saat bekleyin ve kullanıcının OneDrive İş oturum açılabilmesi için değişikliklerin yayılması için Azure AD. (Kullanıcı OneDrive İş sağlamak için oturum açmadan önce tercih edilen veri konumunu ayarlamak, kullanıcının yeni OneDrive'ını doğru konumda sağlamayı güvence altına alır.)

## <a name="setting-preferred-data-location-for-cloud-only-users"></a>Yalnızca bulut kullanıcıları için Tercih Edilen Veri Konumunu ayarlama

Şirketinizin kullanıcıları bir şirket içi Active Directory sisteminden Azure AD eşitlenmemişse( yani Microsoft 365 veya Azure AD'de oluşturulmuşsa) için PDL'nin Microsoft Azure Active Directory Modülü kullanılarak ayarlanması gerekir Windows PowerShell.

Bu bölümdeki yordamlar<a href="https://www.powershellgallery.com/packages/MSOnline/1.1.166.0" target="_blank">, Windows PowerShell Modülü için Microsoft Azure Active Directory Modülü</a> gerektirir. Bu modülü zaten yüklediyseniz lütfen en son sürüme güncelleştirdiğinizden emin olun.

_Kiracınız_ için bir dizi genel yönetici kimlik bilgileriyle [bağlanın ve oturum açın](connect-to-microsoft-365-powershell.md).

Kullanıcılarınızın her biri için tercih edilen veri konumunu ayarlamak için [Set-MsolUser](/powershell/module/msonline/set-msoluser) cmdlet'ini kullanın. Örneğin:

```PowerShell
Set-MsolUser -UserPrincipalName Robyn.Buckley@Contoso.com -PreferredDatalocation EUR
```

tercih edilen veri konumunun düzgün güncelleştirildiğini doğrulamak için Get-MsolUser cmdlet'ini kullanabilirsiniz. Örneğin:

```PowerShell
Get-MsolUser -UserPrincipalName Robyn.Buckley@Contoso.com.PreferredDatalocation
```

Kullanıcının Tercih Edilen Veri Konumunu standart kullanıcı oluşturma iş akışınızın bir parçası olarak ayarlamanızı öneririz.

>[!IMPORTANT]
>veya OneDrive sağlanmamış yeni kullanıcılara, hesabı lisanslayıp kullanıcının PDL'sinin ayarlanmasından sonra kullanıcının OneDrive'da oturum açana kadar değişikliklerin yayılması için en az 48 saat bekleyin. (Kullanıcı OneDrive İş sağlamak için oturum açmadan önce tercih edilen veri konumunu ayarlamak, kullanıcının yeni OneDrive'ını doğru konumda sağlamayı güvence altına alır.)

## <a name="onedrive-for-business-provisioning-and-the-effect-of-pdl"></a>OneDrive İş Sağlama ve PDL'nin etkisi

Kullanıcının _Kiracı'da_ oluşturulmuş bir OneDrive İş sitesi varsa, PDL'sini ayarlamak mevcut OneDrive'ını otomatik olarak taşımaz. Kullanıcının OneDrive'larını taşımak için bkz. [Coğrafi Taşıma OneDrive İş](move-onedrive-between-geo-locations.md).

> [!NOTE]
> Exchange Online PLD değişirse ve MailboxRegion artık Posta Kutusu Veritabanı Coğrafi Konum koduyla eşleşmiyorsa kullanıcının posta kutusunu otomatik olarak yeniden yer değiştirir. Daha fazla bilgi için bkz. [Çok coğrafi ortamda Exchange Online posta kutularını yönetme](administering-exchange-online-multi-geo.md).

Kullanıcının _Kiracı_ içinde bir OneDrive İş sitesi yoksa, kullanıcının PDL'sinin şirketin uydu konumlarından biriyle eşleşeceği varsayılarak, pdl değerine uygun olarak OneDrive İş sağlanır.
