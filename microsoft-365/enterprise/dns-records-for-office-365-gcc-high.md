---
title: Office 365 GCC High için DNS kayıtları
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
description: 'Özet: Office 365 GCC High için DNS kayıtları'
hideEdit: true
ms.openlocfilehash: 6a7970fd795408099aea9018d66422845db2f1ad
ms.sourcegitcommit: e9323a90a1156c10b037abca3e16d7367ef92dd7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/02/2022
ms.locfileid: "67570069"
---
# <a name="dns-records-for-office-365-gcc-high"></a>Office 365 GCC High için DNS kayıtları

*Bu makale Office 365 GCC High ve Microsoft 365 GCC High için geçerlidir*

Office 365 GCC High'a ekleme işleminin bir parçası olarak, SMTP ve SIP etki alanlarınızı Çevrimiçi Hizmetler kiracınıza eklemeniz gerekir.  Bunu, Azure AD PowerShell'deki New-MsolDomain cmdlet'ini kullanarak veya [Azure Kamu Portalı'nı](https://portal.azure.us) kullanarak etki alanını ekleme ve sahipliği kanıtlama işlemini başlatacaksınız.

Etki alanlarınızı kiracınıza ekledikten ve doğruladıktan sonra, aşağıdaki hizmetlere uygun DNS kayıtlarını eklemek için aşağıdaki kılavuzu kullanın.  Aşağıdaki tabloyu, gelen MX kayıtlarına ve mevcut Exchange Otomatik Bulma kayıtlarına göre kuruluşunuzun gereksinimlerine uyacak şekilde değiştirmeniz gerekebilir.  Herhangi bir kesintiyi veya e-postanın yanlış teslimini önlemek için bu DNS kayıtlarını mesajlaşma ekibinizle koordine etmenizi kesinlikle öneririz.

## <a name="exchange-online"></a>Exchange Online

| Tür | Öncelik | Ana bilgisayar adı | İşaret edilen adres veya değer | TTL |
| --- | --- | --- | --- | --- |
| MX | 0 | @ | *tenant.mail.protection.office365.us* (diğer ayrıntılar için aşağıya bakın) | Bir Saat |
| TXT | - | @ | v=spf1 include:spf.protection.office365.us -all | Bir Saat |
| CNAME | - | autodiscover | autodiscover.office365.us | Bir Saat |

### <a name="exchange-autodiscover-record"></a>Exchange Otomatik Bulma kaydı

Şirket içinde Exchange Server varsa, Exchange Online geçiş yaparken mevcut kaydınızı yerinde bırakmanızı ve geçişinizi tamamladıktan sonra bu kaydı güncelleştirmenizi öneririz. 

### <a name="exchange-online-mx-record"></a>MX Kaydını Exchange Online

Kabul edilen etki alanlarınızın MX kayıt değeri yukarıda belirtildiği gibi standart bir biçime sahiptir: *tenant.mail.protection.office365.us*, *kiracıyı varsayılan kiracı* adınızın ilk bölümüyle değiştirir.

Örneğin, kiracı adınız contoso.onmicrosoft.us ise MX kaydınızın değeri olarak **contoso.mail.protection.office365.us** kullanırsınız.

## <a name="skype-for-business-online"></a>Skype Kurumsal Çevrimiçi

### <a name="cname-records"></a>CNAME kayıtları

| Tür | Ana bilgisayar adı | İşaret edilen adres veya değer | TTL |
| --- | --- | --- | --- |
| CNAME | sip | sipdir.online.gov.skypeforbusiness.us | Bir Saat |
| CNAME | lyncdiscover | webdir.online.gov.skypeforbusiness.us | Bir Saat |

### <a name="srv-records"></a>SRV kayıtları

| Tür | Hizmet | Protokol | Bağlantı noktası | Ağırlık | Öncelik | Name | Hedef | TTL |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| SRV | \_sip | \_tls | 443 | 1 | 100 | @ | sipdir.online.gov.skypeforbusiness.us | Bir Saat |
| SRV | \_sipfederationtls | \_Tcp | 5061 | 1 | 100 | @ | sipfed.online.gov.skypeforbusiness.us | Bir Saat |

## <a name="other-dns-records"></a>Diğer DNS kayıtları

> [!IMPORTANT]
> DNS bölgenizde mevcut bir *msoid* CNAME kaydı varsa, şu anda kaydı DNS'den **kaldırmanız** gerekir.  Msoid kaydı Microsoft 365 Kurumsal Uygulamaları *(eski adıyla Office 365 ProPlus)* ile uyumsuzdur ve etkinleştirmenin başarılı olmasını engeller.
