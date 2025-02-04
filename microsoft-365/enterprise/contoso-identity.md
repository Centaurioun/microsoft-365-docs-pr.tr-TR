---
title: Contoso Corporation için kimlik
author: kelleyvice-msft
f1.keywords:
- NOCSH
ms.author: kvice
manager: scotv
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- scotvorg
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso'nun Hizmet Olarak Kimlik'in (IDaaS) avantajlarından yararlanması ve çalışanları için bulut tabanlı kimlik doğrulaması ile iş ortakları ve müşterileri için federasyon kimlik doğrulaması sağlaması.
ms.openlocfilehash: 83c5444be2edafde4fc7b3cb677804e909837b72
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68179449"
---
# <a name="identity-for-the-contoso-corporation"></a>Contoso Corporation için kimlik

Microsoft, Azure Active Directory (Azure AD) aracılığıyla bulut tekliflerinde Hizmet Olarak Kimlik (IDaaS) sağlar. Kuruluş için Microsoft 365'i benimsemek için Contoso IDaaS çözümünün şirket içi kimlik sağlayıcısını kullanması ve mevcut güvenilen üçüncü taraf kimlik sağlayıcılarıyla federasyon kimlik doğrulamasını içermesi gerekiyordu.

## <a name="the-contoso-active-directory-domain-services-forest"></a>Contoso Active Directory Domain Services ormanı

Contoso, contoso\.com için dünyanın her bölgesi için bir tane olmak üzere yedi alt etki alanına sahip tek bir Active Directory Domain Services (AD DS) ormanı kullanır. Genel merkez, bölgesel merkez ofisleri ve uydu ofisleri yerel kimlik doğrulaması ve yetkilendirme için etki alanı denetleyicileri içerir.

Burada, dünyanın bölgesel merkezler içeren farklı bölümleri için bölgesel etki alanlarının bulunduğu Contoso ormanı yer alır.

:::image type="content" alt-text="Contoso'nun dünya genelindeki ormanı ve etki alanları." source="../media/contoso-identity/contoso-identity-fig1.png" lightbox="../media/contoso-identity/contoso-identity-fig1.png":::
 
Contoso, Microsoft 365 iş yükleri ve hizmetleri için kimlik doğrulaması ve yetkilendirme için contoso\.com ormanındaki hesapları ve grupları kullanmaya karar verdi.

## <a name="the-contoso-federated-authentication-infrastructure"></a>Contoso federasyon kimlik doğrulaması altyapısı

Contoso şunları sağlar:

- Müşteriler şirketin genel web sitesinde oturum açmak için Microsoft, Facebook veya Google Mail hesaplarını kullanır.
- Satıcılar ve iş ortakları LinkedIn, Salesforce veya Google Mail hesaplarını kullanarak şirketin iş ortağı extranetinde oturum açar.

Genel web sitesini, iş ortağı extranetini ve bir dizi Active Directory Federasyon Hizmetleri (AD FS) (AD FS) sunucusunu içeren Contoso DMZ aşağıdadır. DMZ, müşterileri, iş ortaklarını ve internet hizmetlerini içeren İnternet'e bağlıdır.

![Müşteriler ve iş ortakları için federasyon kimlik doğrulaması için Contoso desteği.](../media/contoso-identity/contoso-identity-fig2.png)
 
DMZ'deki AD FS sunucuları, genel web sitesine erişim için kimlik sağlayıcıları tarafından müşteri kimlik bilgilerinin ve iş ortağı extranetine erişim için iş ortağı kimlik bilgilerinin kimlik doğrulamasını kolaylaştırır.

Contoso bu altyapıyı kullanmaya ve bunu müşteri ve iş ortağı kimlik doğrulamasına ayırmaya karar verdi. Contoso kimlik mimarları bu altyapının [Azure AD B2B](/azure/active-directory/b2b/hybrid-organizations) ve [B2C](/azure/active-directory-b2c/solution-articles) çözümlerine dönüştürülmesiyle ilgili araştırma yürütmektedir.

## <a name="hybrid-identity-with-password-hash-synchronization-for-cloud-based-authentication"></a>Bulut tabanlı kimlik doğrulaması için parola karması eşitlemesi ile karma kimlik

Contoso, Microsoft 365 bulut kaynaklarına kimlik doğrulaması için şirket içi AD DS ormanını kullanmak istedi. Parola karması eşitlemesini (PHS) kullanmaya karar verdi.

PHS, şirket içi AD DS ormanını kurumsal abonelik için Microsoft 365'in Azure AD kiracısıyla eşitler, kullanıcı ve grup hesaplarını kopyalar ve kullanıcı hesabı parolalarının karma sürümünü kopyalar.

Contoso, dizin eşitlemesi yapmak için Azure AD Connect aracını Paris veri merkezinde bir sunucuya dağıttı.

Aşağıda Connect Azure AD çalıştıran sunucu Contoso AD DS ormanında değişiklikler olup olmadığını yoklar ve ardından bu değişiklikleri Azure AD kiracısıyla eşitler.

![Contoso PHS dizin eşitleme altyapısı.](../media/contoso-identity/contoso-identity-fig4.png)
 
## <a name="conditional-access-policies-for-zero-trust-identity-and-device-access"></a>Sıfır Güven kimliği ve cihaz erişimi için Koşullu Erişim ilkeleri

Contoso, üç koruma düzeyi için bir dizi Azure AD ve Intune [Koşullu Erişim ilkesi](../security/office-365-security/identity-access-policies.md) oluşturmuştur:

- *Başlangıç noktası* korumaları tüm kullanıcı hesapları için geçerlidir.
- *Kurumsal* korumalar üst düzey liderlik ve yönetici personel için geçerlidir.
- *Özel güvenlik* korumaları, yüksek oranda düzenlenmiş verilere erişimi olan finans, hukuk ve araştırma departmanlarındaki belirli kullanıcılar için geçerlidir.

Contoso kimliği ve cihaz Koşullu Erişim ilkelerinin sonucunda elde edilen küme aşağıdadır.

:::image type="content" alt-text="Contoso'nun kimlik ve cihaz Koşullu Erişim ilkeleri." source="../media/contoso-identity/contoso-identity-fig5.png" lightbox="../media/contoso-identity/contoso-identity-fig5.png":::
 
## <a name="next-step"></a>Sonraki adım

Contoso'un kuruluş genelinde [geçerli Windows 10 Enterprise dağıtmak ve tutmak](contoso-win10.md) için Microsoft Endpoint Configuration Manager altyapısını nasıl kullandığını öğrenin.

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft 365 için kimlik dağıtma](deploy-identity-solution-overview.md)

[Microsoft 365 Kurumsal’a genel bakış](microsoft-365-overview.md)

[Test laboratuvarı kılavuzları](m365-enterprise-test-lab-guides.md)