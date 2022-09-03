---
title: IPv6 üzerinden anonim gelen e-posta desteği ekleme
f1.keywords:
- NOCSH
author: chrisda
ms.author: chrisda
manager: chrisda
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: b68df621-0a5f-4824-8abc-41e0c4fd1398
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Yönetici, Exchange Online ve Exchange Online Protection'da IPv6 kaynaklarından anonim gelen e-posta desteğini yapılandırmayı öğrenebilir.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: ea64d73177c18fcfde55caa6637815361f90560d
ms.sourcegitcommit: 2b89bcff547e00be3d38dc8d1e6cbcf8f41eba42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2022
ms.locfileid: "67598295"
---
# <a name="add-support-for-anonymous-inbound-email-over-ipv6-in-microsoft-365"></a>Microsoft 365'te IPv6 üzerinden anonim gelen e-posta desteği ekleme

**Uygulandığı öğe**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365 için Microsoft Defender plan 1 ve plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Online posta kutularına ve Exchange Online posta kutuları olmayan tek başına Exchange Online Protection (EOP) kuruluşlarına sahip Microsoft 365 kuruluşları, IPv6 üzerinden anonim gelen e-postayı destekler. Kaynak IPv6 e-posta sunucusu aşağıdaki gereksinimlerin ikisini de karşılamalıdır:

- Kaynak IPv6 adresi, hedefin IPv6 adresinden etki alanı adını bulmasını sağlayan geçerli bir ters DNS arama (PTR) kaydına sahip olmalıdır.

- Gönderenin SPF doğrulamasını ( [RFC 7208'de](https://tools.ietf.org/html/rfc7208) tanımlanır) veya [DKIM doğrulamasını](http://dkim.org/) ( [RFC 6376'da tanımlanır) geçirmesi](https://www.rfc-editor.org/rfc/rfc6376.txt) gerekir.

Kuruluşunuzun IPv6 üzerinden anonim gelen e-posta alabilmesi için bir yöneticinin Microsoft desteğine başvurması ve bunu istemesi gerekir. Destek isteği açma hakkında yönergeler için bkz. [İş ürünleri için desteğe başvurma - yardım Yönetici](../../admin/get-help-support.md).

Kuruluşunuzda anonim gelen IPv6 ileti desteği etkinleştirildikten sonra, ileti hizmet tarafından sağlanan normal ileti filtreleme işleminden geçer.

## <a name="troubleshooting"></a>Sorun giderme

- Kaynak e-posta sunucusunda IPv6 ters DNS arama kaydı yoksa, iletiler aşağıdaki hatayla reddedilir:

  > 450 4.7.25 Hizmet kullanılamıyor, IPv6 adresi gönderiliyor [2a01:111:f200:2004::240] ters DNS kaydına sahip olmalıdır.

- Gönderen SPF veya DKIM doğrulamasını geçmezse iletiler aşağıdaki hatayla reddedilir:

  > 450 4.7.26 Hizmet kullanılamıyor, IPv6 üzerinden gönderilen ileti [2a01:111:f200:2004::240] SPF veya DKIM doğrulamasını geçmelidir.

- Kabul etmeden önce anonim IPv6 iletileri almaya çalışırsanız, ileti aşağıdaki hatayla reddedilir:

  > 550 5.2.1 Hizmet kullanılamıyor, [contoso.com] IPv6 üzerinden e-posta kabul etmiyor.

## <a name="related-topics"></a>İlgili konular

[DKIM imzalı iletileri doğrulama desteği](support-for-validation-of-dkim-signed-messages.md)
