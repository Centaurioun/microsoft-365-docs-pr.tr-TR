---
title: Yönetim merkezinde grubu yönetme
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- Tier2
- scotvorg
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: admindeeplinkMAC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 74a1ef8b-3844-4d08-9980-9f8f7a36000f
description: Grup üyelerini kaldırma, e-posta adresini, grup adını veya açıklamasını düzenleme ve grubun çalışma şeklini özelleştirme gibi Microsoft 365 Grupları yönetmeyi öğrenin.
ms.openlocfilehash: 2f8536854f2787c0489b06691f6fca602178c39a
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2022
ms.locfileid: "68728675"
---
# <a name="manage-a-group-in-the-microsoft-365-admin-center"></a>Microsoft 365 yönetim merkezi bir grubu yönetme

[Bir Microsoft 365 grubu oluşturduktan ve grup](create-groups.md) üyeleri ekledikten sonra grubunuzu yapılandırabilirsiniz. Grup adını veya açıklamasını düzenleyebilir, sahipleri veya üyeleri yönetebilir ve dış gönderenlerin gruba e-posta gönderip gönderemeyeceğini ve grup konuşmalarının kopyalarını üyelere gönderip göndermeyeceğini belirtebilirsiniz.

konumundaki Microsoft 365 yönetim merkezi [https://admin.microsoft.com](https://admin.microsoft.com)gidin.

## <a name="edit-the-group-name-or-description"></a>Grup adını veya açıklamasını düzenleme

1. Yönetim merkezinde **Gruplar'ı** genişletin ve ardından <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">**Gruplar'a**</a> tıklayın.

2. Düzenlemek istediğiniz grubu seçin ve ardından **Adı ve açıklamayı düzenle'ye** tıklayın.

3. Adı ve açıklamayı güncelleştirip **Kaydet'i** seçin.

## <a name="manage-group-owners-and-members"></a>Grup sahiplerini ve üyeleri yönetme

1. Yönetim merkezinde **Gruplar'ı** genişletin ve ardından <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">**Gruplar'a**</a> tıklayın.

2. Ayarlar bölmesini açmak için yönetmek istediğiniz grubun adına tıklayın.

3. **Üyeler** sekmesinde, sahipleri veya üyeleri yönetmek isteyip istemediğinizi seçin.

4. Birini eklemek için **Ekle'yi** seçin veya birini kaldırmak için **X'e** tıklayın.

5. **Kapat**'a tıklayın.

## <a name="send-copies-of-conversations-to-group-members-inboxes"></a>Grup üyelerinin gelen kutularına konuşmaların kopyalarını gönderme
  
Bir grup oluşturmak için yönetim merkezini kullandığınızda, varsayılan olarak kullanıcılar gelen kutularına gönderilen grup e-postalarının kopyalarını alamaz, ancak kullanıcılar gelen kutularına gönderilen grup toplantısı davetlerinin kopyalarını alır. Konuşmaları görmek için gruba gitmeleri gerekir. Bu ayarı yönetim merkezinden değiştirebilirsiniz.

Bu ayarı açtığınızda, grup üyeleri Outlook Gelen Kutularına gönderilen grup e-postalarının ve toplantı davetlerinin bir kopyasını alır. E-postanın bu kopyasını okuyup silebilirler ve diğer kullanıcılar bundan etkilenmez. E-postanın bir kopyası Grup gelen kutusunda kalır.

Grup üyeleri, Outlook'ta grubu takip etmeyi durdurmayı seçerek bu e-postaları almayı geri çevirebilir.

1. Yönetim merkezinde **Gruplar'ı** genişletin ve ardından <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">**Gruplar'a**</a> tıklayın.

2. Ayarlar bölmesini açmak için yönetmek istediğiniz grubun adına tıklayın.

3. **Üyelerin grup iletilerinin ve takvim öğelerinin kopyalarını kendi gelen kutularına** almasını istiyorsanız **, Ayarlar** sekmesinde Grup konuşmalarının ve olaylarının kopyalarını grup üyelerine gönder'i seçin.

4. **Kaydet**'i seçin.

## <a name="let-people-outside-the-organization-email-the-group"></a>Kuruluş dışındaki kişilerin gruba e-posta göndermesine izin verme

info@contoso.com gibi bir şirket e-posta adresine sahip olmak istiyorsanız bu seçenek harikadır.
 
1. Yönetim merkezinde **Gruplar'ı** genişletin ve ardından <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">**Gruplar'a**</a> tıklayın.

2. Ayarlar bölmesini açmak için yönetmek istediğiniz grubun adına tıklayın.

3. Yönetim merkezi grupları listesinde, değiştirmek istediğiniz grubun adını seçin ve **ayarlar sekmesinde** **Dış gönderenlerin bu gruba e-posta göndermesine izin ver'i** seçin.
    
4. **Kaydet**'i seçin.

> [!NOTE]
> Kuruluş dışındaki kullanıcıların gruba e-posta gönderebilmesi 30 dakika kadar sürebilir.

## <a name="permanently-delete-a-microsoft-365-group"></a>Microsoft 365 grubunu kalıcı olarak silme

Bazen 30 günlük geçici silme süresinin dolmasını beklemeden bir grubu kalıcı olarak temizlemek isteyebilirsiniz. Bunu yapmak için PowerShell'i başlatın ve şu komutu çalıştırarak grubun nesne kimliğini alın:
 
 ```powershell
Get-AzureADMSDeletedGroup
```

Kalıcı olarak silmek istediğiniz grubun veya grupların nesne kimliğini not alın.
  
> [!CAUTION]
> Grubun temizlenmesi, grubu ve verilerini sonsuza kadar kaldırır. 
  
Grubu temizlemek için PowerShell'de şu komutu çalıştırın:

```powershell
Remove-AzureADMSDeletedDirectoryObject -Id <objectId>
```

To confirm that the group has been successfully purged, run the  *Get-AzureADMSDeletedGroup*  cmdlet again to confirm that the group no longer appears on the list of soft-deleted groups. In some cases it may take as long as 24 hours for the group and all of its data to be permanently deleted. 
  
## <a name="related-articles"></a>İlgili makaleler

[Microsoft 365 grubu oluşturma](create-groups.md)

[Microsoft 365 Grupları konuk erişimini yönetme](https://support.microsoft.com/office/bfc7a840-868f-4fd6-a390-f347bf51aff6)

[Microsoft 365 Grupları oluştururken kullanılacak etki alanını seçin](../../solutions/choose-domain-to-create-groups.md)

[Üyelerin bir Microsoft 365 grubu adına göndermesine veya göndermesine izin verme](../../solutions/allow-members-to-send-as-or-send-on-behalf-of-group.md)

[Dağıtım listelerini Microsoft 365 Grupları yükseltme](../manage/upgrade-distribution-lists.md)

[PowerShell ile Microsoft 365 Grupları yönetme](../../enterprise/manage-microsoft-365-groups-with-powershell.md)
