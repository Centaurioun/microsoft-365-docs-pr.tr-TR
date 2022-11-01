---
title: OneDrive Kiracılar Arası Kullanıcı Verileri Geçişi 4. Adım
ms.author: jhendr
author: JoanneHendrickson
manager: serdars
recommendations: true
audience: ITPro
ms.topic: article
ms.service: sharepoint-online
ms.subservice: sharepoint-migration
ms.localizationpriority: high
ms.collection:
- SPMigration
- M365-collaboration
- m365initiative-migratetom365
search.appverid: MET150
description: OneDrive Kiracılar arası geçiş özelliğinin 4. adımı
ms.openlocfilehash: 971646a4f8eff31c0b1f5a3fad62ba66e00713ea
ms.sourcegitcommit: 0c72639cc3dc74667a6b14343d303f318e70d457
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/01/2022
ms.locfileid: "68806334"
---
# <a name="step-4-pre-creating-users-and-groups"></a>4. Adım: Kullanıcıları ve grupları önceden oluşturma

Geçiş kapsamında OneDrive izinlerinin korunmasını sağlamak için, kullanıcıları kaynak kiracıdan hedef kiracıya hizalamak için bir eşleme dosyası oluşturulması gerekir.

## <a name="identify-users-and-groups-to-be-migrated"></a>Geçirilecek kullanıcıları ve grupları belirleme

1. Kaynaktan hedef kiracıya geçirilecek OneDrive sitelerinin tam listesini belirleyin.
2. Hedef kiracıya geçirilecek kullanıcıların ve grupların tam listesini hazırlayın.

## <a name="pre-create-users-and-groups-on-the-target-tenant"></a>Hedef kiracıda kullanıcıları ve grupları önceden oluşturma

1. Hedef kiracının dizininde gerektiğinde kullanıcıları ve grupları önceden oluşturun.
2. OneDrive hesapları hedef kiracıya geçen tüm kullanıcılar için hedef kiracıda yeni kullanıcı kimlikleri oluşturulmalıdır.
3. OneDrive hesapları hedef kiracıya geçen tüm kullanıcılara uygun OneDrive lisansı atanmalıdır.
4. Kaynak kiracıda kalan ancak hedef kiracıya geçen kaynaklara erişmesi gereken tüm kullanıcıların hedef kiracıda kendileri için yeni konuk kimlikleri oluşturulmuş olmalıdır.
5. OneDrive geçişi başlamadan önce önceden oluşturulmuş kullanıcıların uygun güvenlik gruplarının veya birleşik grupların üyesi olarak eklenmesi gerekir. 
6. Hedef kiracıda kullanıcı veya grup adı zaten varsa, farklı bir ada sahip bir kullanıcı veya grup oluşturun ve sonraki adım için bunu not edin.
7. Kullanıcıların OneDrive siteleri oluşturmasını önlemek için Hedef kiracıda OneDrive site oluşturmalarının kısıtlanmasını öneririz.

>[!Note]
>OneDrive site oluşturmayı kısıtlama hakkında daha fazla bilgi edinmek için bkz. [Bazı kullanıcılar için OneDrive oluşturmayı devre dışı bırakma](/sharepoint/manage-user-profiles#disable-onedrive-creation-for-some-users)

## <a name="step-5-prepare-the-identity-mapping-file"></a>5. Adım: [Kimlik eşleme dosyasını hazırlama](cross-tenant-onedrive-migration-step5.md)