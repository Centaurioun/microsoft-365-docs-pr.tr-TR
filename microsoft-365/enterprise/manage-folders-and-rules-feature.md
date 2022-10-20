---
title: Microsoft 365 Grupları'da Klasörleri ve Kuralları Yönet özelliği
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.custom:
- Adm_O365
- seo-marvel-apr2020
- admindeeplinkMAC
- admindeeplinkEXCHANGE
search.appverid: ''
ms.assetid: ''
description: Bu makalede, Microsoft 365 gruplarında klasör ve kural özelliğini yönetmeyi öğrenin.
ms.openlocfilehash: 470f8569cc064053b96ab1d39b318d875451267a
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68631379"
---
# <a name="manage-folders-and-rules-feature-in-microsoft-365-groups"></a>Microsoft 365 Grupları'da Klasörleri ve Kuralları Yönet özelliği

Kullanıcılar, grup posta kutularının içinde klasör oluşturup kurallar ayarlayarak grup e-postalarını etkili bir şekilde düzenleyebilir. Klasörler grup posta kutusunda oluşturulduktan sonra, kullanıcılar iletileri el ile ve **Kurallar'ı** kullanarak farklı klasörlere taşıyabilir ve kopyalayabilir.

Bu özellik şu anda yalnızca Outlook Web Uygulaması'nda kullanılabilir.

## <a name="enable-folders-and-rules-feature-for-microsoft-365-groups-in-outlook"></a>Outlook'ta Microsoft 365 Grupları için Klasörler ve Kuralları Etkinleştirme özelliği

Yönetici cmdlet'i `Set-OrganizationConfig -IsGroupFoldersAndRulesEnabled`yardımıyla özelliği etkinleştirebilir.

 - `[-IsGroupFoldersAndRulesEnabled<Boolean>]` -Isteğe bağlı

   parametresi, `IsGroupFoldersAndRulesEnabled` Kiracı için Klasörler ve Kurallar özelliğinin etkinleştirilip etkinleştirilmediğini belirtir.

   Olası değerler: true/false

   Varsayılan Değer: false

> [!NOTE]
> `IsGroupFoldersAndRulesEnabled` Bazı klasör ve kurallar oluşturulduktan sonra parametre kapatıldıktan sonra,
  > 
  > - Mevcut Klasörler ve Kurallar işlenmeye devam eder.
  > 
  > - Mevcut kurallar yürütülürken devam eder.
  > 
  > - Klasör Oluşturma/Yükseltme/Silme engellenir.
  > 
  > - İleti düzeyi eylemleri Kopyalama/Taşıma engellenir.

Özellik etkinleştirildikten sonra, varsayılan olarak yalnızca grubun sahibi klasör oluşturma, klasörü yeniden adlandırma, iletileri klasörler arasında taşıma ve kopyalama iznine sahiptir.
  
## <a name="enable-member-permission-option"></a>Üye iznini etkinleştir seçeneği

Gruptaki üyelerin grup posta kutusunda klasör oluşturması ve iletileri önceliklendirmesi gerekiyorsa, grup içeriğini düzenlemeye yönelik üye izninin yönetici tarafından kiracı düzeyinde ve grup sahibi tarafından sırasıyla grup düzeyinde etkinleştirilmesi gerekir.

Varsayılan olarak, bu ayar kiracı düzeyinde ve grup düzeyinde **kapalıdır**
  
Yönetici cmdlet'ini `IsGroupMemberAllowedToEditContent`kullanarak kiracıya üye iznini etkinleştirebilir.

 - `[-IsGroupMemberAllowedToEditContent<Boolean>]`-Isteğe bağlı

   parametresi, `IsGroupMemberAllowedToEditContent` grup sahibinin Klasörler ve Kurallar özellik içeriği düzenlemesi için üyelere izin verip veremeyeceğini belirtir.

   Olası değerler: True/False

   Varsayılan değer: false

Bu etkinleştirildikten sonra Grup sahipleri grup üyelerine klasör oluşturma, klasörleri yeniden adlandırma, kopyalama, taşıma ve silme olanağı sağlayabilir. Grup düzeyi üye izni, Grup sahipleri tarafından işlenir.

> [!NOTE]
> Yöneticiler cmdlet'ini kullanarak `Get-OrganizationConfig` ayarların geçerli değerini görebilir.

## <a name="block-move-message-capability"></a>"Taşı" ileti özelliğini engelle

Yöneticiler, cmdlet'ini `Set-OrganizationConfig -BlockMoveMessagesForGroupFold`kullanarak kiracı içindeki tüm Microsoft 365 grupları için İletiyi **taşı** seçeneğini engelleyebilir.

 - `[-BlockMoveMessagesForGroupFolders<Boolean>]` –Isteğe bağlı

   parametresi, `BlockMoveMessagesForGroupFolders` **Taşı** eyleminin devre dışı bırakılıp bırakılmadığını belirtir.

   Olası değerler: True/False

   Varsayılan değer: false

> [!NOTE]
> **Taşıma** kuralının oluşturulması da etkinleştirildiğinde `BlockMoveMessagesForGroupFolders` devre dışı bırakılır.

> [!NOTE]
> Web üzerinde Outlook ve Outlook Masaüstü Uygulaması kullanan karma kullanıcı kümeleri varsa bu yararlı olur. Klasörlerin kullanılamadığı Outlook Masaüstü Uygulaması'ndaki kullanıcılar, iletileri grup gelen kutusundan alabilir. 
  
  
  
