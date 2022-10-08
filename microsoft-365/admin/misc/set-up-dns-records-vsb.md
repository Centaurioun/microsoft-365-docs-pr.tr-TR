---
title: Etki alanınızı Microsoft 365'e bağlayın
f1.keywords:
- CSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: high
ms.collection:
- scotvorg
- highpri
- M365-subscription-management
- Adm_O365
- Adm_O365_Setup
search.appverid:
- MET150
ROBOTS: NOINDEX, NOFOLLOW
description: Microsoft 365 ile etki alanınızı doğrulamayı ve DNS kayıtları oluşturmayı öğrenin.
ms.custom:
- VSBFY23
- AdminSurgePortfolio
ms.openlocfilehash: fa6c25e8ac2bca0646455d81f7a4390be3b173b5
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68204837"
---
# <a name="connect-your-domain-to-microsoft-365"></a>Etki alanınızı Microsoft 365'e bağlayın

> [!NOTE]
> Etki alanı eklemezseniz, siz ekleyene kadar kuruluşunuzdaki kişiler e-posta adresleri için onmicrosoft.com etki alanını kullanır. Kullanıcıları eklemeden önce etki alanınızı eklemek önemlidir; böylelikle onları iki kez ayarlamanız gerekmez.

Aradığınızı aşağıda bulamazsanız, [Etki Alanları SSS sayfasını inceleyin](../setup/domains-faq.yml).

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Etki alanınız için e-postanın Microsoft'a gelmesi için bir MX kaydı ekleyin

MX kaydına yönelik bilgileri, yönetim merkezi etki alanı kurulum sihirbazından alırsınız.

Barındırma sağlayıcınızın web sitesinde yeni bir MX kaydı ekleyin.
Alanların aşağıdaki değerlere ayarlandığından emin olun:

- Kayıt Türü: `MX`
- Öncelik: Kullanılabilir en yüksek değere ayarlayın; genellikle `0` olur.
- Ana Bilgisayar Adı: `@`
- İşaret edilen adres: Yönetim merkezindeki değeri kopyalayın ve buraya yapıştırın.
- TTL: `3600` (veya varsayılan sağlayıcınız)

Kaydı kaydedin ve ardından diğer tüm MX kayıtlarını kaldırın.

## <a name="add-a-cname-record-to-connect-users-to-their-mailboxes"></a>Kullanıcıları posta kutularına bağlamak için CNAME kaydı ekleme

CNAME kayıtlarına yönelik bilgileri, yönetim merkezi etki alanı kurulum sihirbazından alırsınız.

Barındırma sağlayıcınızın web sitesine aşağıdaki CNAME kaydını ekleyin. Her birinde alanların aşağıdaki değerlere ayarlandığından emin olun:

- Kayıt Türü: `CNAME (Alias)`
- Ana Bilgisayar: Yönetim merkezinden kopyaladığınız değerleri buraya yapıştırın.
- İşaret edilen adres: Yönetim merkezindeki değeri kopyalayın ve buraya yapıştırın.
- TTL: `3600` (veya varsayılan sağlayıcınız)

## <a name="add-a-txt-record-to-help-prevent-spam"></a>İstenmeyen postaları önlemeye yardımcı olmak için TXT kaydı ekleme

**Başlamadan önce:** Etki alanınız için zaten bir SPF kaydınız varsa Microsoft 365 için yeni SPF kaydı oluşturmayın. Bunun yerine, her iki değer kümesini de içeren *tek bir* SPF kaydınız olacak şekilde gerekli Microsoft 365 değerlerini barındırma sağlayıcılarınızın web sitesindeki geçerli kayda ekleyin.

Barındırma sağlayıcınızın web sitesinde, mevcut SPF kaydını düzenleyin veya bir SPF kaydı oluşturun.
Alanların aşağıdaki değerlere ayarlandığından emin olun:

- Kayıt Türü: `TXT (Text)`
- Ana Bilgisayar: `@`
- TXT Değeri: `v=spf1 include:spf.protection.outlook.com -all`
- TTL: `3600` (veya varsayılan sağlayıcınız)

Kaydı kaydedin.

Şu [SPF doğrulama araçlarından](/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain) birini kullanarak SPF kaydınızı doğrulayın.

SPF kimlik sahtekarlığını önlemeye yardımcı olmak için tasarlanmıştır, ancak SPF’nin koruma sağlayamayacağı bazı kimlik sahtekarlığı yöntemleri vardır. Bunlara karşı korunmak için, SPF’yi ayarladıktan sonra Microsoft 365 için DKIM ve DMARC’yi de ayarlamanız gerekir.

Başlamak için bkz. [Microsoft 365’te etki alanınızdan gönderilen giden e-postayı doğrulamak için DKIM kullanma](../../security/office-365-security/use-dkim-to-validate-outbound-email.md) ve [Microsoft 365’te e-postayı doğrulamak için DMARC kullanma](../../security/office-365-security/use-dmarc-to-validate-email.md).

Son olarak, kurulumunuzu tamamlamak için yönetim merkezi etki alanı kurulum sihirbazına dönün.
