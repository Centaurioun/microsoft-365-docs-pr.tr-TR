---
title: SharePoint, OneDrive ve Microsoft Teams için Güvenli Ekler
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: conceptual
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: 26261670-db33-4c53-b125-af0662c34607
ms.collection:
- M365-security-compliance
- SPO_Content
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: SharePoint Online, OneDrive İş ve Microsoft Teams'deki dosyalar için Office 365 için Microsoft Defender hakkında bilgi edinin.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 6767abfc3c658675484c05d506ee69ca9d198539
ms.sourcegitcommit: 2b89bcff547e00be3d38dc8d1e6cbcf8f41eba42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2022
ms.locfileid: "67597514"
---
# <a name="safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>SharePoint, OneDrive ve Microsoft Teams için Güvenli Ekler

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Uygulandığı öğe**
- [Office 365 için Microsoft Defender plan 1 ve plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[Office 365 için Microsoft Defender'daki](whats-new-in-defender-for-office-365.md) SharePoint, OneDrive ve Microsoft Teams için Güvenli Ekler, [Microsoft 365'teki ortak virüs algılama altyapısı](virus-detection-in-spo.md) tarafından zaman uyumsuz olarak zaten taranmış dosyalar için ek bir koruma katmanı sağlar. SharePoint, OneDrive ve Microsoft Teams için Güvenli Ekler, ekip sitelerinde ve belge kitaplıklarında kötü amaçlı olarak tanımlanan mevcut dosyaları algılamaya ve engellemeye yardımcı olur.

SharePoint, OneDrive ve Microsoft Teams için Güvenli Ekler varsayılan olarak etkin değildir. Bu özelliği açmak için bkz. [SharePoint, OneDrive ve Microsoft Teams için Güvenli Ekleri açma](turn-on-mdo-for-spo-odb-and-teams.md).

## <a name="how-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-works"></a>SharePoint, OneDrive ve Microsoft Teams için Güvenli Ekler nasıl çalışır?

SharePoint, OneDrive ve Microsoft Teams için Güvenli Ekler etkinleştirildiğinde ve bir dosyayı kötü amaçlı olarak tanımladığında, dosya depolarıyla doğrudan tümleştirme kullanılarak kilitlenir. Aşağıdaki görüntüde, kitaplıkta algılanan kötü amaçlı bir dosya örneği gösterilmektedir.

:::image type="content" source="../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png" alt-text="kötü amaçlı olarak algılanan OneDrive İş dosyaları" lightbox="../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png":::

Engellenen dosya belge kitaplığında ve web, mobil veya masaüstü uygulamalarında listelenmeye devam etse de, kişiler dosyayı açamaz, kopyalayamaz, taşıyamaz veya paylaşamaz. Ancak engellenen dosyayı silebilirler.

Mobil cihazda engellenen bir dosyanın nasıl göründüğüne ilişkin bir örnek aşağıda verilmişti:

:::image type="content" source="../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png" alt-text="Engellenen bir dosyayı OneDrive mobil uygulamasından OneDrive İş silme seçeneği" lightbox="../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png":::

Varsayılan olarak, kişiler engellenen bir dosyayı indirebilir. Engellenen bir dosyayı mobil cihazda indirme işlemi şöyle görünür:

:::image type="content" source="../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png" alt-text="OneDrive İş'de engellenen bir dosyayı indirme seçeneği" lightbox="../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png":::

SharePoint Online yöneticileri, kişilerin kötü amaçlı dosyaları indirmesini engelleyebilir. Yönergeler için bkz. [Kullanıcıların kötü amaçlı dosyaları indirmesini önlemek için SharePoint Online PowerShell kullanma](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).

Bir dosya kötü amaçlı olarak algılandığında kullanıcı deneyimi hakkında daha fazla bilgi edinmek için bkz. [SharePoint Online, OneDrive veya Microsoft Teams'de kötü amaçlı bir dosya bulunduğunda yapılması gerekenler](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).

## <a name="view-information-about-malicious-files-detected-by-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>SharePoint, OneDrive ve Microsoft Teams için Güvenli Ekler tarafından algılanan kötü amaçlı dosyalar hakkındaki bilgileri görüntüleme

SharePoint, OneDrive ve Microsoft Teams için Güvenli Ekler tarafından kötü amaçlı olarak tanımlanan dosyalar[, Office 365 için Microsoft Defender için raporlarda](view-reports-for-mdo.md) ve [Gezgin'de (ve gerçek zamanlı algılamalarda)](threat-explorer.md) gösterilir.

Bir dosya SharePoint, OneDrive ve Microsoft Teams için Güvenli Ekler tarafından kötü amaçlı olarak tanımlandığında, dosya karantinada da kullanılabilir, ancak yalnızca yöneticiler tarafından kullanılabilir. Daha fazla bilgi için bkz. [Office 365 için Defender'de karantinaya alınan dosyaları yönetme](manage-quarantined-messages-and-files.md#use-the-microsoft-365-defender-portal-to-manage-quarantined-files-in-defender-for-office-365).

## <a name="keep-these-points-in-mind"></a>Bu noktaları göz önünde bulundurun

- Office 365 için Defender SharePoint Online, OneDrive İş veya Microsoft Teams'deki her dosyayı taramaz. Bu, tasarımdan kaynaklanır. Dosyalar zaman uyumsuz olarak taranır. Bu işlem, kötü amaçlı dosyaları tanımlamak için akıllı buluşsal yöntemler ve tehdit sinyalleriyle birlikte paylaşım ve konuk etkinliği olaylarını kullanır.

- SharePoint sitelerinizin [Modern deneyimi](/sharepoint/guide-to-sharepoint-modern-experience) kullanacak şekilde yapılandırıldığından emin olun. Office 365 için Defender koruması, Modern deneyimin veya Klasik görünümün kullanılıp kullanılmadığını uygular; ancak bir dosyanın engellendiğine ilişkin görsel göstergeler yalnızca Modern deneyimde kullanılabilir.

- SharePoint, OneDrive ve Microsoft Teams için Güvenli Ekler, kuruluşunuzun Exchange Online Protection'de (EOP) istenmeyen posta ve kötü amaçlı yazılımdan korumanın yanı sıra Office 365 için Microsoft Defender'daki Güvenli Bağlantılar ve Güvenli Ekler'i de içeren genel tehdit koruma stratejisinin bir parçasıdır. Daha fazla bilgi için bkz[. Office 365 tehditlere karşı koruma](protect-against-threats.md).
