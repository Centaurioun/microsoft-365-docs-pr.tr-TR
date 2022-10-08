---
title: Paylaşılan posta kutularında sorunları çözme
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
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
- MSStore_Link
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
description: Paylaşılan posta kutularını ayarlarken hata alabilirsiniz. Paylaşılan posta kutularıyla ilgili sorun yaşıyorsanız bu çözümleri deneyin.
ms.openlocfilehash: bc272dcd9ad74b4f9ab7e93915fd9fa9becd33aa
ms.sourcegitcommit: 99b174a8d431092b3cf7d650593248671297fd91
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2022
ms.locfileid: "68298220"
---
# <a name="resolve-issues-with-shared-mailboxes"></a>Paylaşılan posta kutularında sorunları çözme

Paylaşılan posta kutusu oluştururken veya kullanırken hata iletileri görürseniz bu olası çözümleri deneyin. 

## <a name="error-when-creating-shared-mailboxes"></a>Paylaşılan posta kutuları oluşturulurken hata oluştu

Hata iletisini görürseniz, **"smtp:<paylaşılan posta kutusu adı\>" proxy adresi veya "\<name>" LegacyExchangeDN'si tarafından zaten kullanılıyordur. Lütfen başka bir ara sunucu adresi seçin**; bu, paylaşılan posta kutusuna zaten kullanımda olan bir ad vermeye çalıştığınız anlamına gelir. Örneğin, paylaşılan posta kutularını info@domain1 ve info@domain2 olarak adlandırmak istediğinizi varsayalım. Bunu yapmanın iki yolu vardır:

- PowerShell Exchange Online kullanın. Yönergeler için bu blog gönderisini izleyin: [Farklı Etki Alanlarında Aynı Diğer Adla Paylaşılan Posta Kutuları Oluşturma](https://blog.quadrotech-it.com/blog/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365/)

- İkinci paylaşılan posta kutusuna hatayla ilgili olarak başlangıçtan farklı bir ad verin. Ardından yönetim merkezinde paylaşılan posta kutusunu istediğiniz gibi yeniden adlandırın.

## <a name="error-about-not-having-send-permissions-when-using-a-shared-mailbox"></a>Paylaşılan posta kutusu kullanırken gönderme izinlerine sahip olmama hatası

Paylaşılan bir posta kutusu oluşturduysanız ve ardından bu posta kutusundan bir ileti göndermeye çalışıyorsanız şunu alabilirsiniz:

**Bu ileti gönderilemedi. İletiyi belirtilen kullanıcı adına gönderme izniniz yok.**

Microsoft 365 çoğaltma gecikmesi sorunu yaşadığında bu ileti görüntülenir. Yeni paylaşılan posta kutunuz (veya eklenen kullanıcı) hakkındaki bilgiler tüm veri merkezlerimizde çoğaltıldığında, bir saat veya daha fazla bir zaman içinde ortadan kaldırılmalıdır. Bir saat bekleyin ve sonra ileti göndermeyi yeniden deneyin.

## <a name="related-content"></a>İlgili içerik

[Paylaşılan posta kutuları hakkında](about-shared-mailboxes.md) (makale)\
[Paylaşılan posta kutusu oluşturma](create-a-shared-mailbox.md) (makale)\
[Paylaşılan posta kutusunu yapılandırma](configure-a-shared-mailbox.md) (makale)\
[Kullanıcı posta kutusunu paylaşılan posta kutusuna dönüştürme](convert-user-mailbox-to-shared-mailbox.md) (makale)\
[Paylaşılan posta kutusundan lisans kaldırma](remove-license-from-shared-mailbox.md) (makale)
