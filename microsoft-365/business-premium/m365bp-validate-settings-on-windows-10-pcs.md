---
title: Windows 10 bilgisayarlar için uygulama koruma ayarlarını doğrulama
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: microsoft-365-business
ms.subservice: business-premium
ms.localizationpriority: medium
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- Adm_TOC
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Microsoft 365 İş Ekstra uygulama koruma ayarlarının kullanıcılarınızın Windows 10 cihazlarında etkili olduğunu doğrulamayı öğrenin.
ms.openlocfilehash: bab1eea1bff77d559e160b8c363ad7c0a91b4100
ms.sourcegitcommit: db89873e22a12705ed313964c1bc2fa19d4fe719
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/15/2022
ms.locfileid: "67876969"
---
# <a name="validate-device-protection-settings-for-windows-10-or-11-pcs"></a>Windows 10 veya 11 bilgisayar için cihaz koruma ayarlarını doğrulama

## <a name="verify-that-windows-10-or-11-device-policies-are-set"></a>Windows 10 veya 11 cihaz ilkelerinin ayarlandığını doğrulayın

[Cihaz ilkelerini ayarladıktan](../business-premium/m365bp-protection-settings-for-windows-10-devices.md) sonra, ilkenin kullanıcıların cihazlarında etkili olması birkaç saat kadar sürebilir. Kullanıcıların cihazlarında çeşitli Windows Ayarları ekranlarına bakarak ilkelerin geçerli olduğunu onaylayabilirsiniz. Kullanıcılar Windows 10 veya 11 cihazlarında Windows Update ve Microsoft Defender Virüsten Koruma ayarlarını değiştiremeyeceğinden, birçok seçenek gri görünür.
  
1. **Ayarlar Güvenlik** \> **güncelleştirme &amp;** \> **Windows Update** \> **Yeniden başlatma seçenekleri'ne** gidin ve tüm ayarların gri renkte olduğunu onaylayın.

    ![Tüm Yeniden Başlatma seçenekleri gri görünür.](../business-premium/media/31308da9-18b0-47c5-bbf6-d5fa6747c376.png)
  
2. **Ayarlar Güvenlik** \> **&amp;** \> **Windows Update** \> **Gelişmiş seçenekler'e** gidin ve tüm ayarların gri renkte olduğunu onaylayın.

    ![Windows Gelişmiş güncelleştirme seçeneklerinin tümü gri görünür.](../business-premium/media/049cf281-d503-4be9-898b-c0a3286c7fc2.png)
  
3. **Ayarlar** \> **Güncelleştirme &amp; güvenliği** \> **Windows Update** \> **Gelişmiş seçenekler** \> **Güncelleştirmelerin nasıl teslimileceğini seçin'e** gidin.

    Bazı ayarların kuruluşunuz tarafından gizlendiğini veya yönetildiğini ve tüm seçeneklerin gri olduğunu belirten iletiyi (kırmızı) görebildiğinizi onaylayın.

    ![Güncelleştirmelerin nasıl teslimileceğini seçin sayfası, ayarların kuruluşunuz tarafından gizlendiğini veya yönetildiğini gösterir.](../business-premium/media/6b3e37c5-da41-4afd-9983-b4f406216b59.png)
  
4. Windows Defender Güvenlik Merkezi'ni açmak için **Ayarlar** \> **Güncelleştirme &amp; güvenliği'ne** \> gidin **Windows Defender** \> Güvenlik Merkezi \> **Virüs iş parçacığı koruması Virüs &amp;** **tehdit koruması &amp;**\> ayarları **Windows Defender Aç'a** tıklayın.

5. Tüm seçeneklerin gri renkte olduğunu doğrulayın.

    ![Virüs ve tehdit koruması ayarları gri görünür.](../business-premium/media/9ca68d40-a5d9-49d7-92a4-c581688b5926.png)
  
## <a name="related-content"></a>İlgili içerik

[İş için Microsoft 365 belgeleri ve kaynakları](/admin)

Windows 10 bilgisayarlar 
[için cihaz yapılandırmalarını ayarlama](../business-premium/m365bp-protection-settings-for-windows-10-devices.md)[İş için Microsoft 365 planlarının güvenliğini sağlamaya yönelik en iyi yöntemler](../admin/security-and-compliance/secure-your-business-data.md)

## <a name="next-objective"></a>Sonraki hedef

[Koruma ilkelerini gözden geçirme ve düzenleme](m365bp-view-edit-create-mdb-policies.md)
