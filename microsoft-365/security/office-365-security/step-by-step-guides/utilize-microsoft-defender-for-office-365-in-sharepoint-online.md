---
title: SharePoint Online'da Office 365 için Microsoft Defender kullanma
description: SharePoint Online'da Office 365 için Microsoft Defender ve OneDrive İş kullanarak değer elde edebilirsiniz.
search.product: ''
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTBen
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-guidance-templates
- m365-security
- tier3
ms.topic: how-to
ms.subservice: mdo
search.appverid: met150
ms.openlocfilehash: a6f527c8cbc7815da0c54d0958a24b459e0bb8f9
ms.sourcegitcommit: 2ff545246fec060ea7829da5afbc1cdc698d51ab
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2022
ms.locfileid: "68363573"
---
# <a name="use-microsoft-defender-for-office-365-with-sharepoint-online"></a>SharePoint Online ile Office 365 için Microsoft Defender kullanma

Microsoft Office SharePoint Online yaygın olarak kullanılan bir kullanıcı işbirliği ve dosya depolama aracıdır. Aşağıdaki adımlar, SharePoint Online'daki saldırı yüzeyi alanının azaltılmasına ve bu işbirliği aracının kuruluşunuzda güvenli kalmasına yardımcı olur. Ancak, güvenlik ve üretkenlik arasında bir denge olduğunu ve bu adımların tümünün kurumsal risk profilinizle ilgili olmayabileceğini unutmayın. Bir göz atın, test edin ve bu dengeyi koruyun.

## <a name="what-youll-need"></a>İhtiyacınız olan şey

- Office 365 için Microsoft Defender Plan 1
- Yeterli izinler (SharePoint yöneticisi/güvenlik yöneticisi).
- Microsoft Office SharePoint Online (Microsoft 365'in bir parçası).
- Bu adımları gerçekleştirmek için beş-on dakika.

## <a name="turn-on-microsoft-defender-for-office-365-in-sharepoint-online"></a>SharePoint Online'da Office 365 için Microsoft Defender açma

Office 365 için Microsoft Defender için lisanslanırsa **(aka.ms/trymdo ücretsiz 90 günlük değerlendirme) Microsoft Teams'de** sıfır günlük kötü amaçlı yazılımlara ve tıklama koruma süresine karşı sorunsuz koruma sağlayabilirsiniz.

Daha fazla bilgi edinmek [için 1. Adım: SharePoint, OneDrive ve Microsoft Teams için Güvenli Ekler'i açmak üzere Microsoft 365 Defender portalını kullanma makalesini](/microsoft-365/security/office-365-security/turn-on-mdo-for-spo-odb-and-teams#step-1-use-the-microsoft-365-defender-portal-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams) okuyun.

1. [Güvenlik merkezinin güvenli ekler yapılandırma sayfasında oturum açın](https://security.microsoft.com/safeattachmentv2).
1. **Genel ayarlar'ı** seçin.
1. **SharePoint, OneDrive ve Microsoft Teams için Office 365 için Defender aç** ayarının **açık** olduğundan emin olun.
1. **Kaydet**'i seçin.

## <a name="stop-infected-file-downloads-from-sharepoint-online"></a>SharePoint Online'dan virüslü dosya indirmelerini durdurma

Varsayılan olarak, kullanıcılar SharePoint, OneDrive ve Microsoft Teams için Güvenli Ekler tarafından algılanan kötü amaçlı dosyaları açamaz, taşıyamaz, kopyalayamaz veya paylaşamaz. Ancak *İndir seçeneği hala* kullanılabilir durumdadır ve *devre dışı bırakılmalıdır*.

Daha fazla bilgi edinmek için [2. Adım: (*Önerilen*) Kullanıcıların kötü amaçlı dosyaları indirmesini önlemek için SharePoint Online PowerShell kullanma](/microsoft-365/security/office-365-security/turn-on-mdo-for-spo-odb-and-teams#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files) bölümünü okuyun.

1. [SharePoint Online PowerShell'i açın ve bağlanın](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).
1. Şu komutu çalıştırın: **Set-SPOTenant -DisallowInfectedFileDownload $true**.

### <a name="further-reading"></a>Daha fazla okuma

[SharePoint sitelerinin ve dosyalarının güvenliğini sağlamaya yönelik ilke önerileri](/microsoft-365/security/office-365-security/sharepoint-file-access-policies)
