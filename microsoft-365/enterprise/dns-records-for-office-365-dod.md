---
title: Office 365 DoD için DNS kayıtları
ms.author: dzazzo
author: dzazzo
manager: dzazzo
ms.date: 05/19/2020
audience: ITPro
ms.topic: conceptual
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: Adm_O365
search.appverid:
- OGA150
- OGC150
- OGD150
- MOE150
ms.assetid: ''
description: 'Özet: Office 365 DoD için DNS kayıtları'
hideEdit: true
ms.openlocfilehash: a0b7c08805e5cdd07c798da3c45b3af82ceddd1d
ms.sourcegitcommit: 62368e5a48e569c8e475b07d194d7d8ff7d167ab
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/02/2022
ms.locfileid: "67556358"
---
# <a name="dns-records-for-office-365-dod"></a>Office 365 DoD için DNS kayıtları

*Bu makale Office 365 DoD ve Microsoft 365 DoD için geçerlidir*

Office 365 DoD'ye ekleme işleminin bir parçası olarak, SMTP ve SIP etki alanlarınızı Online Services kiracınıza eklemeniz gerekir.  Bunu, Azure AD PowerShell'deki New-MsolDomain cmdlet'ini kullanarak veya [Azure Kamu Portalı'nı](https://portal.azure.us) kullanarak etki alanını ekleme ve sahipliği kanıtlama işlemini başlatacaksınız.

Etki alanlarınızı kiracınıza ekledikten ve doğruladıktan sonra, aşağıdaki hizmetlere uygun DNS kayıtlarını eklemek için aşağıdaki kılavuzu kullanın.  Aşağıdaki tabloyu, gelen MX kayıtlarına ve mevcut Exchange Otomatik Bulma kayıtlarına göre kuruluşunuzun gereksinimlerine uyacak şekilde değiştirmeniz gerekebilir.  Herhangi bir kesintiyi veya e-postanın yanlış teslimini önlemek için bu DNS kayıtlarını mesajlaşma ekibinizle koordine etmenizi kesinlikle öneririz.

## <a name="exchange-online"></a>Exchange Online

| Tür | Öncelik | Ana bilgisayar adı | İşaret edilen adres veya değer | TTL |
| --- | --- | --- | --- | --- |
| MX | 0 | @ | *tenant.mail.protection.office365.us* (diğer ayrıntılar için aşağıya bakın) | Bir Saat |
| TXT | - | @ | v=spf1 include:spf.protection.office365.us -all | Bir Saat |
| CNAME | - | autodiscover | autodiscover-dod.office365.us | Bir Saat |

### <a name="exchange-autodiscover-record"></a>Exchange Otomatik Bulma kaydı

Şirket içinde Exchange Server varsa, Exchange Online geçiş yaparken mevcut kaydınızı yerinde bırakmanızı ve geçişinizi tamamladıktan sonra bu kaydı güncelleştirmenizi öneririz.

### <a name="exchange-online-mx-record"></a>MX Kaydını Exchange Online

Kabul edilen etki alanlarınızın MX kayıt değeri yukarıda belirtildiği gibi standart bir biçime sahiptir: *tenant.mail.protection.office365.us*, *kiracıyı varsayılan kiracı* adınızın ilk bölümüyle değiştirir.

Örneğin, kiracı adınız contoso.onmicrosoft.us ise MX kaydınızın değeri olarak **contoso.mail.protection.office365.us** kullanırsınız.

## <a name="skype-for-business-online"></a>Skype Kurumsal Çevrimiçi

### <a name="cname-records"></a>CNAME kayıtları

| Tür | Ana bilgisayar adı | İşaret edilen adres veya değer | TTL |
| --- | --- | --- | --- |
| CNAME | sip | sipdir.online.dod.skypeforbusiness.us | Bir Saat |
| CNAME | lyncdiscover | webdir.online.dod.skypeforbusiness.us | Bir Saat | 

### <a name="srv-records"></a>SRV kayıtları

| Tür | Hizmet | Protokol | Bağlantı noktası | Ağırlık | Öncelik | Name | Hedef | TTL |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| SRV | \_sip | \_tls | 443 | 1 | 100 | @ | sipdir.online.dod.skypeforbusiness.us | Bir Saat |
| SRV | \_sipfederationtls | \_Tcp | 5061 | 1 | 100 | @ | sipfed.online.dod.skypeforbusiness.us | Bir Saat |

## <a name="other-dns-records"></a>Diğer DNS kayıtları

> [!IMPORTANT]
> DNS bölgenizde mevcut bir *msoid* CNAME kaydı varsa, şu anda kaydı DNS'den **kaldırmanız** gerekir.  Msoid kaydı Microsoft 365 Kurumsal Uygulamaları *(eski adıyla Office 365 ProPlus)* ile uyumsuzdur ve etkinleştirmenin başarılı olmasını engeller.
