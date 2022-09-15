---
title: Üyelerin grup adına göndermesine veya göndermesine izin verme
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- highpri
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
ms.custom: admindeeplinkEXCHANGE
search.appverid:
- MET150
ms.assetid: 0ad41414-0cc6-4b97-90fb-06bec7bcf590
recommendations: false
description: Grup üyelerinin Microsoft 365 grubu olarak e-posta göndermesine veya microsoft 365 grubu adına e-posta göndermesine nasıl izin vereceğinizi öğrenin.
ms.openlocfilehash: d6e334a2fffcc1be760ccef045a50d1e9b154bc4
ms.sourcegitcommit: 0af064e8b6778060f1bd365378d69b16fc9949b5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/15/2022
ms.locfileid: "67728439"
---
# <a name="allow-members-to-send-as-or-send-on-behalf-of-a-group"></a>Üyelerin grup adına göndermesine veya göndermesine izin verme

Microsoft 365 grubunun Farklı **gönder** veya **Adına gönder** izinleri verilmiş bir üyesi, grup olarak veya grup adına e-posta gönderebilir. (Gruptaki konuklara bu izinler verilemez.)

Bu makalede bir genel yöneticinin veya Exchange yöneticisinin bu izinleri nasıl ayarlayabildiği açıklanmaktadır.
  
Örneğin, Megan Bowen **Eğitim** Microsoft 365 grubunun bir parçasıysa ve grup üzerinde **Farklı Gönder** izinleri varsa, grup olarak bir e-posta gönderirse **Eğitim grubu** e-postayı göndermiş gibi görünür. 
  
**Adına Gönder** izni, kullanıcının Microsoft 365 grubu adına e-posta göndermesine olanak tanır. Örneğin, Alex Wilber **Pazarlama** Microsoft 365 grubunun bir parçasıysa ve **Adına Gönder** izinlerine sahipse ve grup olarak bir e-posta gönderiyorsa, e-posta **Alex Wilber tarafından Pazarlama adına** gönderilmiş gibi görünür.

> [!IMPORTANT]
> Belirli bir kullanıcı için Farklı **Gönder** veya **Adına Gönder'i** yapılandırabilirsiniz, ancak ikisini birden yapılandıramayın. Her ikisini de yapılandırdığınızda, varsayılan olarak **Farklı gönder'e** ayarlanır.

> [!NOTE]
> Karma Exchange yapılandırmalarında Mac için Outlook farklı **gönder** ve **Adına gönder** desteklenmez.
    
## <a name="allow-members-to-send-email-as-a-group"></a>Üyelerin grup olarak e-posta göndermesine izin ver

Bu bölümde, kullanıcıların Exchange Online'deki<a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange yönetim merkezinde (EAC)</a> grup olarak e-posta göndermesine nasıl izin ver bağlantısı açıklanmaktadır.
  
1. Exchange yönetim merkezinde **Alıcı Grupları'na** \> gidin.<a href="https://go.microsoft.com/fwlink/?linkid=2183233" target="_blank"></a>
    
2. Kullanıcıların farklı göndermesine izin vermek istediğiniz grubu seçin. 
    
3. **Ayarlar Temsilcileri** > **yönet'i seçin**.
    
4. **Temsilci ekle** bölümünde, **Farklı gönder** erişimi olmasını istediğiniz kullanıcının e-posta adresini girin.
  
5. Açılan listeden **İzin Türü** olarak **Farklı gönder'i** seçin.

6.  **Değişiklikleri kaydet'i** seçin.
    
    
## <a name="allow-members-to-send-email-on-behalf-of-a-group"></a>Üyelerin grup adına e-posta göndermesine izin verme

Bu bölümde, kullanıcıların Exchange Online'deki <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange yönetim merkezinde (EAC)</a> bir grup adına e-posta göndermesine nasıl izin verileceği açıklanır.
  
1. Exchange yönetim merkezinde **Alıcı Grupları'na** \> gidin.<a href="https://go.microsoft.com/fwlink/?linkid=2183233" target="_blank"></a>
    
2. Kullanıcıların adına göndermesine izin vermek istediğiniz grubu seçin. 
    
3. **Ayarlar Temsilcileri** > **yönet'i seçin**.
    
4. **Temsilci ekle** bölümünde, **Farklı gönder** erişimi olmasını istediğiniz kullanıcının e-posta adresini girin.
  
5. Açılan **listeden İzin Türü'nü** **Adına gönder'i** seçin.

6.  **Değişiklikleri kaydet'i** seçin.

## <a name="related-articles"></a>İlgili makaleler

[Microsoft 365 grubundan veya adına e-posta gönderme](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b)

[İşbirliği idaresi planlama önerileri](collaboration-governance-overview.md#collaboration-governance-planning-recommendations)

[İşbirliği idare planınızı oluşturma](collaboration-governance-first.md)

[Microsoft 365 grupları hakkında daha fazla bilgi edinin](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[Add-RecipientPermission](/powershell/module/exchange/add-recipientpermission)

[Set-UnifiedGroup](/powershell/module/exchange/set-unifiedgroup)
