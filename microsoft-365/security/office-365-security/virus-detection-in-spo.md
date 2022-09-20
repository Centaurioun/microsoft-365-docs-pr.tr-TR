---
title: SharePoint Online, OneDrive ve Microsoft Teams'de yerleşik virüs koruması
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: reference
ms.localizationpriority: medium
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: SharePoint Online'ın kullanıcıların karşıya yüklediği dosyalarda virüsleri nasıl algılayıp kullanıcıların dosyaları indirmesini veya eşitlemesini nasıl önlediği hakkında bilgi edinin.
ms.custom: seo-marvel-apr2020
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 948f5b58f7c5113f006c0fd6ccb4d84f0ce52c9d
ms.sourcegitcommit: 95ac076310ab9006ed92c69938f7ae771cd10826
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/20/2022
ms.locfileid: "67851006"
---
# <a name="built-in-virus-protection-in-sharepoint-online-onedrive-and-microsoft-teams"></a>SharePoint Online, OneDrive ve Microsoft Teams'de yerleşik virüs koruması

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Uygulandığı öğe**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365 için Microsoft Defender plan 1 ve plan 2](defender-for-office-365.md)

Microsoft 365, kullanıcıların SharePoint Online, OneDrive ve Microsoft Teams'e yüklediği dosyaları taramak için yaygın bir virüs algılama altyapısı kullanır. Bu koruma SharePoint Online, OneDrive ve Microsoft Teams içeren tüm aboneliklere dahildir.

> [!IMPORTANT]
> Yerleşik virüsten koruma özellikleri, virüsleri kapsamaya yardımcı olmak için bir yoldur. Bunlar ortamınız için kötü amaçlı yazılımlara karşı tek bir savunma noktası olarak tasarlanmamıştır. Tüm müşterilerin çeşitli katmanlarda kötü amaçlı yazılımdan korumayı araştırmalarını ve uygulamalarını ve kurumsal altyapılarının güvenliğini sağlamak için en iyi yöntemleri uygulamalarını öneririz. 

## <a name="what-happens-if-an-infected-file-is-uploaded-to-sharepoint-online"></a>Virüslü bir dosya SharePoint Online'a yüklenirse ne olur?

Microsoft 365 virüs algılama altyapısı dosyaları zaman uyumsuz olarak tarar (karşıya yükleme sonrasında bir süre). Bir dosya henüz zaman uyumsuz virüs algılama işlemi tarafından taranmadıysa ve kullanıcı dosyayı tarayıcıdan veya Teams'den indirmeye çalışırsa, indirmeye izin verilmeden önce SharePoint tarafından indirme sırasında bir tarama tetikler. **Tüm dosya türleri otomatik olarak taranmıyor**. Buluşsal yöntemler, taranacak dosyaları belirler. Bir dosyanın virüs içerdiği bulunduğunda, dosyaya bayrak eklenir. 

Şöyle olur:

1. Kullanıcı SharePoint Online'a bir dosya yükler.
2. SharePoint Online, virüs tarama işlemlerinin bir parçası olarak daha sonra dosyanın tarama ölçütlerini karşılayıp karşılamadığını belirler.
3. Dosya tarama ölçütlerini karşılıyorsa, virüs algılama altyapısı dosyayı tarar.
4. Taranan dosyanın içinde bir virüs bulunursa, virüs altyapısı dosyada dosyaya virüs bulaştığını belirten bir özellik ayarlar.

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a>Kullanıcı tarayıcıyı kullanarak virüslü bir dosyayı indirmeye çalıştığında ne olur?

Varsayılan olarak, kullanıcılar SharePoint Online'dan virüslü dosyaları indirebilir. Şöyle olur:

1. Bir web tarayıcısında, kullanıcı SharePoint Online'dan virüs bulaşmış bir dosyayı indirmeye çalışır.
2. Kullanıcıya dosyada bir virüs algılandığını belirten bir uyarı gösterilir. Kullanıcıya indirme işlemine devam etme ve cihazında virüsten koruma yazılımı kullanarak temizlemeye çalışma seçeneği verilir.

Bu davranışı, virüs koruması uyarı penceresinden bile kullanıcıların virüslü dosyaları indirememelerini sağlamak için yöneticiler SharePoint Online **[PowerShell'deki Set-SPOTenant cmdlet'indeki](/powershell/module/sharepoint-online/Set-SPOTenant)** *DisallowInfectedFileDownload* parametresini kullanabilir. *DisallowInfectedFileDownload* parametresi için $true değeri, kullanıcılar için algılanan/bocked dosyalara erişimi tamamen engeller.

Yönergeler için bkz. [Kullanıcıların kötü amaçlı dosyaları indirmesini önlemek için SharePoint Online PowerShell kullanma](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files).

## <a name="can-admins-bypass-disallowinfectedfiledownload-and-extract-infected-files"></a>Yöneticiler *DisallowInfectedFileDownload'u* atlayabilir ve virüslü dosyaları ayıklayabilir mi?

SharePoint yöneticilerinin ve genel yöneticilerin [Get-SPOMalwareFileContent](/powershell/module/sharepoint-online/get-spomalwarefilecontent) cmdlet'iyle SharePoint Online PowerShell'de kötü amaçlı yazılımdan etkilenen dosyaların adli dosya ayıklamalarını yapmalarına izin verilir. Yöneticilerin virüslü içeriği barındıran siteye erişmesi gerekmez. Dosya kötü amaçlı yazılım olarak işaretlendiği sürece, yöneticiler **get-SPOMalwareFileContent** kullanarak dosyayı ayıklayabilir. 

Bulaşmış dosya hakkında daha fazla bilgi için, yöneticiler algılanan kötü amaçlı yazılım türünü ve bulaşma durumunu görmek için **[Get-SPOMalwareFile](/powershell/module/sharepoint-online/get-spomalwarefile)** cmdlet'ini kullanabilir. 

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a>OneDrive eşitleme istemcisi virüslü bir dosyayı eşitlemeye çalıştığında ne olur?

Kötü amaçlı bir dosya OneDrive'a yüklendiğinde, kötü amaçlı yazılım olarak işaretlenmeden önce yerel makineyle eşitlenir. Kötü amaçlı yazılım olarak işaretlendikten sonra, kullanıcı artık eşitlenen dosyayı yerel makinesinden açamaz.

## <a name="extended-capabilities-with-microsoft-defender-for-office-365"></a>Office 365 için Microsoft Defender ile genişletilmiş özellikler

Aboneliğine [Office 365 için Microsoft Defender](defender-for-office-365.md) dahil edilmiş veya eklenti olarak satın alınmış Microsoft 365 kuruluşları, gelişmiş raporlama ve koruma için SharePoint, OneDrive ve Microsoft Teams için Güvenli Ekler'i etkinleştirebilir. Daha fazla bilgi için bkz. [SharePoint, OneDrive ve Microsoft Teams için Güvenli Ekler](mdo-for-spo-odb-and-teams.md).

## <a name="related-articles"></a>İlgili makaleler

[Microsoft 365'te kötü amaçlı yazılım ve fidye yazılımı koruması](/compliance/assurance/assurance-malware-and-ransomware-protection)

SharePoint Online, OneDrive ve Microsoft Teams'de virüsten koruma hakkında daha fazla bilgi için bkz. [Tehditlere karşı koruma](protect-against-threats.md) ve [SharePoint, OneDrive ve Microsoft Teams için Güvenli Ekler'i açma](turn-on-mdo-for-spo-odb-and-teams.md).
