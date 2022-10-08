---
title: Grupları karşılaştırma
ms.reviewer: arvaradh
f1.keywords: CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: high
ms.collection:
- scotvorg
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
- admindeeplinkMAC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 758759ad-63ee-4ea9-90a3-39f941897b7d
description: Microsoft 365 Grup üyeleri konuşmalar, dosyalar ve takvim etkinlikleri, Stream ve Planner için bir grup e-postası ve paylaşılan çalışma alanı alır.
ms.openlocfilehash: 1065a9d8321f16391f01a2153c18ea11f7f52136
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68191375"
---
# <a name="compare-groups"></a>Grupları karşılaştırma

Microsoft 365 yönetim merkezi <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">**Gruplar**</a> bölümünde şu tür grupları oluşturabilir ve yönetebilirsiniz: 

- **Microsoft 365 Grupları**, hem şirket içinde hem de dışında kullanıcılar arasında işbirliği için kullanılır. SharePoint ve Planner gibi işbirliği hizmetlerini içerir.
- **Dağıtım grupları** , bir grup kişiye e-posta bildirimleri göndermek için kullanılır.
- **SharePoint** siteleri gibi kaynaklara erişim vermek için güvenlik grupları kullanılır.
- **Posta özellikli güvenlik grupları** , SharePoint gibi kaynaklara erişim vermek ve bu kullanıcılara e-posta bildirimleri göndermek için kullanılır.
- **Paylaşılan posta kutuları**, şirket bilgileri veya destek e-posta adresi gibi birden çok kişinin aynı posta kutusuna erişmesi gerektiğinde kullanılır.
- **Dinamik dağıtım grupları** , bir kuruluştaki e-posta iletilerinin ve diğer bilgilerin toplu olarak gönderilmesini hızlandırmak için oluşturulur.

Bazı gruplar dinamik üyelik veya e-postaya izin verir.

||Microsoft 365 Grupları|Dağıtım grupları|Güvenlik grupları|Posta özellikli güvenlik grupları|Paylaşılan posta kutuları|Dinamik dağıtım grupları|
|:----|:----|:----|:----|:----|:----|:----|
|**Posta etkin**|Evet|Evet|Hayır|Evet|Evet|Evet|
|**Azure AD'de dinamik üyelik**|Evet|Hayır|Evet|Hayır|Hayır|Hayır|

Bu grup türlerinin tümü Power Automate ile kullanılabilir.

## <a name="microsoft-365-groups"></a>Microsoft 365 Grupları

Microsoft 365 Grupları, hem şirket içinde hem de dışında kullanıcılar arasında işbirliği için kullanılır. Her Microsoft 365 Grubu ile üyeler konuşmalar, dosyalar ve takvim etkinlikleri, Stream ve Planner için bir grup e-postası ve paylaşılan çalışma alanı alır.

Yönetici [tarafından etkinleştirildiği](manage-guest-access-in-groups.md) sürece, kuruluşunuzun dışından kişileri bir gruba ekleyebilirsiniz. Artık, dış gönderenlerin de grup e-posta adreslerine e-posta göndermesine izin verebilirsiniz.

Microsoft 365 Grupları[, Azure Active Directory'de dinamik üyelik için yapılandırılabilir](/azure/active-directory/users-groups-roles/groups-change-type) ve grup üyelerinin departman, konum, başlık gibi kullanıcı özniteliklerine göre otomatik olarak eklenmesine veya kaldırılmasına olanak tanır.

Microsoft 365 Grupları iOS için Outlook ve Android için Outlook gibi mobil uygulamalar aracılığıyla erişilebilir.

[Yönetici tarafından etkinleştirilirse](../../solutions/allow-members-to-send-as-or-send-on-behalf-of-group.md), ileti gönderebilir ya da grup üyeleri farklı olarak ya da grup e-posta adresi adına gönderim yapabilir. 

Microsoft 365 grupları [, Azure Active Directory'de dinamik gruplar](/azure/active-directory/enterprise-users/groups-dynamic-rule-member-of) aracılığıyla iç içe geçmeyi destekler.

Microsoft 365 Grupları, kişilere site için izin vermek için üç SharePoint grubundan birine (Sahipler, Üyeler veya Ziyaretçiler) eklenebilir.

## <a name="distribution-groups"></a>Dağıtım grupları

[Dağıtım grupları](/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups) bir kişi grubuna bildirim göndermek için kullanılır. Yönetici tarafından etkinleştirildiyse, dış e-posta alabilirler.

Dağıtım grupları, en çok da "A Binasındaki Kişiler" ya da "Contoso'daki herkes"gibi belirlenmiş bir grup kişiye bilgi yayınlamanız gereksinim duyduğunuz durumlar için uygundur.

Dağıtım grupları [Microsoft 365 Grupları yükseltilebilir](../manage/upgrade-distribution-lists.md).

Dağıtım grupları Microsoft Teams'deki bir ekime eklenebilir, ancak grubun kendisi değil yalnızca üyeler eklenir.

Microsoft 365 Grupları dağıtım gruplarının üyesi olamaz.

## <a name="dynamic-distribution-groups"></a>Dinamik dağıtım grupları 

[Dinamik dağıtım grupları](/exchange/recipients-in-exchange-online/manage-dynamic-distribution-groups/manage-dynamic-distribution-groups) , departman veya konum gibi belirli özniteliklere sahip kişilere posta göndermek için kullanılan posta özellikli gruplardır. Bu öznitelikler Azure AD yerine Exchange yönetim merkezinde tanımlanır.

Tanımlı bir üye kümesi içeren normal dağıtım gruplarından farklı olarak, dinamik dağıtım gruplarının üyelik listesi, tanımladığınız filtrelere ve koşullara göre gruba her ileti gönderildiğinde hesaplanır. Dinamik bir dağıtım grubuna bir e-posta iletisi gönderildiğinde, bu ileti kuruluştaki söz konusu grup için tanımlanan ölçütlere uyan tüm alıcılara teslim edilir.

## <a name="security-groups"></a>Güvenlik grupları

[Güvenlik grupları](../email/create-edit-or-delete-a-security-group.md) , SharePoint gibi Microsoft 365 kaynaklarına erişim vermek için kullanılır. Her kaynağa ayrı ayrı kullanıcı eklemek yerine yalnızca grubu yönetmeniz gerektiğinde yönetimi kolaylaştırabilir.

Güvenlik grupları kullanıcıları veya cihazları içerebilir. Aygıtlar için bir güvenlik grubu oluşturma, Intune gibi mobil cihaz yönetim hizmetleriyle kullanılabilir.

Güvenlik grupları, [Azure Active Directory 'de dinamik üyelik için yapılandırılabilir](/azure/active-directory/users-groups-roles/groups-change-type), grup üyelerinin veya cihazların departman, konum veya ünvan gibi kullanıcı özniteliklerine; ya da işletim sistemi sürümü gibi aygıt özniteliklerinine dayalı olarak otomatik olarak eklenmesine veya kaldırılmasına izin verir.

Güvenlik grupları bir takıma eklenebilir.

Microsoft 365 Grupları güvenlik gruplarının üyesi olamaz.

## <a name="mail-enabled-security-groups"></a>Posta özellikli güvenlik grupları

Posta özellikli güvenlik grupları, değişken olarak Azure Active Directory aracılığıyla yönetilmesi ve cihaz içeremeyeceği durumlar dışında normal güvenlik gruplarıyla aynı işlevi görür.

Bunlar grubun tüm üyelerine e-posta gönderme özelliğini içerir.

Posta özellikli güvenlik grupları ekiliğe eklenebilir.

## <a name="shared-mailboxes"></a>Paylaşılan posta kutuları

[Paylaşılan posta kutuları](../email/create-a-shared-mailbox.md), birden çok kişinin aynı posta kutusuna, örneğin şirket bilgileri veya e-posta adresi, alma masa veya birden fazla kişi tarafından paylaşılabilen başka bir işleve ulaşması gerektiğinde kullanılır.

Yönetici bu özelliği etkinleştirdiyse paylaşılan posta kutuları dış e-posta alabilir.

Paylaşılan posta kutuları, işbirliği için kullanılabilecek bir takvim içerir.

Grup posta kutusu izinleri olan kullanıcılar, yönetici bu kullanıcıya bunu yapmak için izin vermişse posta kutusu e-posta adresi olarak gönderebilir veya posta kutusu adına gönderebilir. Kullanıcılar "Contoso Desteği" veya "Resepsiyon Masası Oluşturma"dan e-posta gönderebileceğinden, bu özellikle yardım ve destek posta kutuları için yararlıdır.

Paylaşılan posta kutusunu Microsoft 365 Grubuna geçirmek mümkün değildir.

## <a name="related-content"></a>İlgili içerik

[Microsoft 365 Grupları hakkında bilgi edinin](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[Dağıtım listelerini Outlook'ta Microsoft 365 Grupları yükseltme](/microsoft-365/admin/manage/upgrade-distribution-lists)

[Neden Outlook'ta dağıtım listelerinizi gruplara yükseltmelisiniz?](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188)
