---
title: Çift bayt karakter kümesi sürüm notları için Microsoft Purview desteği
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- tier1
- purview-compliance
search.appverid:
- MOE150
- MET150
description: Çift bayt karakter kümeleri için destek için sürüm notları.
ms.openlocfilehash: 3851b0d0b49faecc123704ee2930fbd3d6ce6360
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68631820"
---
# <a name="support-for-double-byte-character-set-release-notes"></a>Çift bayt karakter kümesi sürüm notları desteği

 Microsoft 365 Information Protection artık aşağıdakiler için çift bayt karakter kümesi dillerini destekliyor:

- Çince (basitleştirilmiş)
- Çince (geleneksel)
- Korean
- Japanese

Bu destek hassas bilgi türleri ve anahtar sözcük sözlükleri için kullanılabilir ve Microsoft Purview Veri Kaybı Önleme (Exchange Online, SharePoint Online, OneDrive İş ve Teams için), İletişim Uyumluluğu, Office uygulamalarında Otomatik Etiketleme ve Microsoft Defender for Cloud Apps.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="known-issues"></a>Bilinen sorunlar

- E-postaya eklenmiş bir metin dosyası bayt sırası işareti (BOM) olmadan UTF-8 biçimindeyse, e-posta İletişim Uyumluluğu ilkesi tarafından algılanmaz.

- İletişim Uyumluluğu ilkeleri, ilke koşulu için bir cümle girilirse değerleri algılayamaz: "İleti bu sözcüklerden herhangi birini içeriyor". İlkede belirtilen metin bir sözcük olarak yazılmışsa algılanabilir; ancak, bir cümlenin ortasında yazılmışsa algılanmaz.

- Sözlükleri tür bilgileri olarak belirten İletişim Uyumluluğu ilkeleri, Teams özel sohbetlerini ve kanal sohbetlerini algılamaz.

- Bu aşamada İletişim Uyumluluğu için aşağıdaki koşullar desteklenmez (gelecekte bu sorunları düzeltmeyi planlıyoruz): 
  - "İleti bu sözcüklerden herhangi birini içeriyor"
  - "İleti bu sözcüklerin hiçbirini içermiyor"
  - "Ek bu sözcüklerden herhangi birini içeriyor"
  - "Ek bu sözcüklerden herhangi birini içeriyor"

- Veri kaybı önleme ilkeleri, Japonca da dahil olmak üzere Doğu Asya dilleri için aşağıda belirtilen koşullar dışında, en son yayınlanan üç sürümü çalıştıran macOS cihazlarda (önizleme) uygulanabilir.
  - Japonya banka hesap numarası gibi yerleşik şablon kullanma gibi tam genişlikli sayılar algılanmadı
  - Sınırlayıcıları olmayan sayılar algılanmadı
  - Hassas bir bilgi türü için yarım genişlikte boşlukla ayrılmış anahtar sözcükler algılanmadı. Örneğin: Japonca sözcük hassas bilgi türünde ayarlanır ve tümce içindeyse sözlük algılanmadı
  - İngilizce ve Japonca (東京2020) içeren sözcükler algılanmadı

Bunun yerine, iletiler ve ekler arasındaki desenleri algılayacak anahtar sözcük sözlüğüne sahip özel bir Hassas Bilgi Türü (SIT) oluşturmanızı ve bu özel SIT'i İletişim Uyumluluğu ilke koşulu olarak kullanmanızı öneririz.
