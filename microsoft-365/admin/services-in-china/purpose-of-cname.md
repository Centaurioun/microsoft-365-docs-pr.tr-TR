---
title: MSOID için Office 365 CNAME kaydının amacı nedir?
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.collection:
- Tier2
- scotvorg
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
ms.service: microsoft-365-business
ms.localizationpriority: medium
search.appverid:
- BCS160
- MET150
- MOE150
ROBOTS: NOINDEX
description: Kimlik doğrulama işlemleri için sizi en iyi sunucuya yönlendiren Office 365 'MSOID' CNAME kaydı hakkında daha fazla bilgi edinin, böylece daha hızlı bir yanıt elde edersiniz.
monikerRange: o365-21vianet
ms.openlocfilehash: b8f199074a23cdbd994e032e1c1f47100cc46fd2
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2022
ms.locfileid: "68727905"
---
# <a name="whats-the-purpose-of-the-office-365-cname-record-for-msoid"></a>MSOID için Office 365 CNAME kaydının amacı nedir?

 Aradığınızı bulamazsanız, **[Etki Alanları SSS sayfasını inceleyin](../setup/domains-faq.yml)**. 
> [!NOTE]
> Aşağıdakiler yalnızca 21Vianet tarafından sağlanan **Office 365 için geçerlidir.
  
You may wonder why you need to add the "MSOID" CNAME record in Office 365. This is a record that has to be added for all custom domains, no matter which subscription you use. Why do you need it? It's a little technical, but essentially, it's so that you'll be directed to the best server for certain authentication processes, so you'll get faster response.
  
Technical details: When you run a client application that works with Office 365 such as Skype for Business Online, Outlook, Windows PowerShell or Microsoft Azure Active Directory Sync tool, your credentials must be authenticated. Office 365 uses a CNAME record to point to the correct authentication endpoint for your location, which ensures rapid authentication response times.
  
If this CNAME record is missing for your domain, these applications will use a default authentication endpoint in the United States, which means authentication might be slower. If this CNAME record isn't configured properly—for example, if you have a typo in the **Points to address**—these applications won't be able to authenticate.
  
 **Etki alanınızın DNS kayıtlarını Office 365 yönetiyorsa Office 365** bu CNAME kaydını sizin için ayarlar. 
  
 **DNS barındırma sağlayıcınızda etki alanınız için DNS kayıtlarını yönetiyorsanız, DNS barındırma** [sağlayıcınızın yönergelerini izleyerek](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md) bu kaydı kendiniz oluşturursunuz.
  
Office 365 dağıtımı planlıyorsanız ve eklemeniz veya güncelleştirmeniz gerekebilecek tüm DNS kayıtları hakkında daha fazla bilgi edinmek istiyorsanız, bunlar hakkında [başvuru: Office 365 için Dış Etki Alanı Adı Sistemi kayıtları](../../enterprise/external-domain-name-system-records.md) başlığı altında bu kayıtlar hakkında bilgi edinin.
