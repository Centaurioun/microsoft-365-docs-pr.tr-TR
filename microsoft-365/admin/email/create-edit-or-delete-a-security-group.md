---
title: Microsoft 365 yönetim merkezi güvenlik grubu oluşturma, düzenleme veya silme
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- Tier3
- scotvorg
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
- admindeeplinkMAC
- admindeeplinkEXCHANGE
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 55c96b32-e086-4c9e-948b-a018b44510cb
description: Güvenlik grubu oluşturmayı, düzenlemeyi veya silmeyi öğrenin.
ms.openlocfilehash: f205c300cf094a9368a49a412a312d96e0896352
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2022
ms.locfileid: "68719964"
---
# <a name="create-edit-or-delete-a-security-group-in-the-microsoft-365-admin-center"></a>Microsoft 365 yönetim merkezi güvenlik grubu oluşturma, düzenleme veya silme

Microsoft 365 **Grupları** sayfasında, SharePoint Online ve CRM Online'da aynı izinleri atamak için kullanabileceğiniz kullanıcı hesabı grupları oluşturabilirsiniz. Örneğin, bir yönetici belirli bir grup kişiye SharePoint sitesine erişim izni vermek için bir güvenlik grubu oluşturabilir. Yalnızca genel ve kullanıcı yönetimi yöneticilerinin güvenlik gruplarını oluşturma, düzenleme veya silme izinleri vardır; yönetici rolleri hakkında daha fazla bilgi için bkz. [Yönetici rolleri atama](../add-users/assign-admin-roles.md). 
  
Ayrıca, bir grup kullanıcıya e-posta göndermek ve izin atamak için kullanabileceğiniz [Exchange Online ve SharePoint Online'daki gruplar](#groups-in-exchange-online-and-sharepoint-online) ve kullanıcı hakları ve siteler ile site koleksiyonlarına erişim veren [Exchange Online ve SharePoint Online'daki gruplar](#groups-in-exchange-online-and-sharepoint-online) da bulunur. 
  
> [!IMPORTANT]
>  Site posta kutularını kullanmayı mı planlıyorsunuz? SharePoint sitesine tek tek eklemek yerine bir güvenlik grubu aracılığıyla eklenen tüm kullanıcılar yalnızca SharePoint'ten site posta kutusunu kullanabilir. Bu kullanıcılar Outlook'tan site posta kutusuna erişemez. Daha fazla bilgi için bkz[. Site Posta Kutuları yerine Microsoft 365 Grupları kullanma](https://support.microsoft.com/office/737d6b1f-67cc-41fe-8db8-f2d09dd1673b). 
  
## <a name="manage-security-groups-in-the-admin-center"></a>Yönetim merkezinde güvenlik gruplarını yönetme

### <a name="add-a-security-group"></a>Güvenlik grubu ekleme

1. Microsoft 365 yönetim merkezi **Gruplar** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">sayfasına gidin</a>.
  
2. **Gruplar** sayfasında **Grup ekle'yi** seçin.
    
3. **Grup türü seçin** sayfasında **Güvenlik'i** seçin. 
    
4. Grubun oluşturulmasını tamamlamak için adımları izleyin. 
 
### <a name="add-members-to-a-security-group"></a>Güvenlik grubuna üye ekleme
    
1. **Gruplar** sayfasında güvenlik grubu adını seçin ve **Üyeler** sekmesinde **Tümünü görüntüle ve üyeleri yönet'i** seçin. 
    
2. Grup bölmesinde **Üye ekle'yi** seçin, listeden kişiyi seçin veya **Arama** kutusuna eklemek istediğiniz kişinin adını yazın ve ardından **Kaydet'i** seçin.
    
    Üyeleri kaldırmak için adlarının yanındaki X işaretini seçin. 
  
### <a name="edit-a-security-group"></a>Güvenlik grubunu düzenleme

1. Yönetim merkezinde **Gruplar Grupları** \> sayfasına gidin.<a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank"></a>
  
2. **Gruplar** sayfasında grubun adını seçin. 
    
3. Ayarlar bölmesinde, grup ayrıntılarını veya üyeleri düzenlemek için **Genel** sekmesini veya **Üyeler** sekmesini seçin.

### <a name="delete-a-security-group"></a>Güvenlik grubunu silme

1. Yönetim merkezinde **Gruplar Grupları** >  sayfasına gidin.<a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank"></a>
    
2. **Gruplar** sayfasında grubun adını seçin. 
    
3. **Grubu sil'i** (wasetbin simgesi) seçin ve **sil'i** seçerek onaylayın.
    
    Grup silindikten sonra **Kapat'ı** seçin. 
    
## <a name="groups-in-exchange-online-and-sharepoint-online"></a>Exchange Online ve SharePoint Online'daki gruplar

Tümüne aynı anda e-posta gönderebilmek için kullanıcı grupları oluşturmak istiyorsanız, Exchange  **Alıcı Grupları'nı** \> **Yönetici** \> \> giderek Exchange yönetim merkezinde bunu yapabilirsiniz.<a href="https://go.microsoft.com/fwlink/?linkid=2183233" target="_blank"></a> Ardından **Yeni**![Ekle'yi](../../media/328ffb57-5f31-430a-b653-4a6b8e76d338.png) seçin ve oluşturmak istediğiniz grup türünü seçin: 
  
- **Dağıtım grubu**: İletileri bir kullanıcı grubuna dağıtmak için kullanılır. Buna  *posta özellikli dağıtım grubu* veya  *dağıtım listesi* de denir. Daha fazla bilgi için bkz. [Dağıtım gruplarını yönetme](/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups).
    
- **Güvenlik grubu**: İletileri bir kullanıcı grubuna dağıtmak veya kaynaklara erişim izinleri vermek için kullanılabilir. Bu gruba *posta özellikli güvenlik grubu* da denir. Daha fazla bilgi için bkz. [Posta özellikli güvenlik gruplarını yönetme](/Exchange/recipients/mail-enabled-security-groups).
    
- **Dinamik dağıtım grubu**: Tanımladığınız filtrelere ve koşullara göre her ileti gönderdiğinizde alıcı listesi yeniden hesaplanmış dağıtım grubu türüdür. Daha fazla bilgi için bkz. [Dinamik dağıtım gruplarını yönetme](/Exchange/recipients/dynamic-distribution-groups/dynamic-distribution-groups).
    
<a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange yönetim merkezinde</a> dağıtım grupları ve posta etkin güvenlik grupları oluşturduktan sonra, bunların adları ve kullanıcı listeleri **Güvenlik grupları** sayfasında görünür. Bu grupları iki farklı konumdan da silebilirsiniz, ancak yalnızca Exchange yönetim merkezinde düzenleyebilirsiniz. Dinamik dağıtım grupları **Güvenlik grupları** sayfasında gösterilmez. 
  
 Site koleksiyonu yaptığınızda SharePoint grupları otomatik olarak oluşturulur. Varsayılan gruplar, kullanıcılara hak ve erişim vermek için SharePoint'te varsayılan izin düzeylerini (bazen SharePoint rolleri olarak adlandırılır) kullanır. Daha fazla bilgi için bkz. [SharePoint Online'da varsayılan SharePoint grupları](/sharepoint/default-sharepoint-groups).
  
## <a name="how-is-a-security-group-different-from-security-groups-i-create-in-sharepoint"></a>Bir güvenlik grubunun SharePoint'te oluşturduğum güvenlik gruplarından farkı nedir?

Güvenlik grupları SharePoint, Exchange, MDM, Windows ve daha fazlası ile kullanılabilir. SharePoint'te oluşturduğunuz bir güvenlik grubu yalnızca bu SharePoint site koleksiyonu tarafından tanınır.
  
## <a name="do-i-have-to-use-security-groups-for-my-organization-to-be-secure"></a>Kuruluşumun güvenliğini sağlamak için güvenlik gruplarını kullanmam gerekiyor mu?

Hayır. Bu, kuruluşunuz için güvenliği yönetmenin yalnızca bir yoludur. Her zaman kullanıcı izinlerini ve sitelere tek tek erişim vekleyebilirsiniz. Ancak güvenlik gruplarıyla daha büyük kullanıcı gruplarını kolayca yönetebilirsiniz.
  
## <a name="can-i-send-email-to-a-security-group"></a>Güvenlik grubuna e-posta gönderebilir miyim?

Evet. Ancak grupları e-posta ve işbirliği için kullanmak istiyorsanız, bunun yerine [bir Microsoft 365 grubu oluşturmanızı](../create-groups/create-groups.md) öneririz. 

## <a name="related-content"></a>İlgili içerik

[Microsoft 365 yönetim merkezi bir grup oluşturma](../create-groups/create-groups.md) (makale)\
[Kullanıcılarınıza Microsoft 365 Grupları açıklama](../create-groups/explain-groups-knowledge-worker.md) (makale)\
[Microsoft 365 yönetim merkezi grubu yönetme](../create-groups/manage-groups.md) (makale)