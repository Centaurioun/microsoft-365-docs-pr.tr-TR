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
ms.openlocfilehash: 107bb6e2b8ab08d871b0671491bc9098e02ed034
ms.sourcegitcommit: b386eaa33e1e5cdea59916247082b6e6e6a3d99e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/01/2022
ms.locfileid: "68807749"
---
# <a name="step-4-pre-creating-users-and-groups"></a>4. Adım: Kullanıcıları ve grupları önceden oluşturma

Bu, Kiracılar Arası OneDrive geçişini tamamlamak için tasarlanmış bir çözümdeki 4. Adımdır. Daha fazla bilgi için bkz. [Kiracılar arası OneDrive geçişine genel bakış](cross-tenant-onedrive-migration.md).

- 1. Adım: [Kaynağa ve hedef kiracılara bağlanma](cross-tenant-onedrive-migration-step1.md)
- 2. Adım: [Kaynak ile hedef kiracı arasında güven oluşturma](cross-tenant-onedrive-migration-step2.md) 
- 3. Adım: [Güvenin kurulduğunu doğrulama](cross-tenant-onedrive-migration-step3.md) 
- **4. Adım: [Kullanıcıları ve grupları önceden oluşturma](cross-tenant-onedrive-migration-step4.md)**  
- 5. Adım: [Kimlik eşlemesini hazırlama](cross-tenant-onedrive-migration-step5.md)
- 6. Adım: [Kiracılar arası OneDrive geçişi başlatma](cross-tenant-onedrive-migration-step6.md)
- 7. Adım: [Geçiş sonrası adımları](cross-tenant-onedrive-migration-step7.md)


## <a name="identify-users-and-groups-to-be-migrated"></a>Geçirilecek kullanıcıları ve grupları belirleme

Geçiş kapsamında OneDrive izinlerinin korunmasını sağlamak için, kullanıcıları kaynak kiracıdan hedef kiracıya hizalamak için bir eşleme dosyası oluşturulması gerekir.

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