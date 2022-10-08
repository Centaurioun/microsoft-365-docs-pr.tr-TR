---
title: Microsoft 365 Grupları, Teams ve SharePoint arasındaki etkileşimleri ayarlar
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection:
- highpri
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
recommendations: false
description: Microsoft 365 Grupları, Teams ve SharePoint arasındaki ayarlar etkileşimleri hakkında bilgi edinin
ms.openlocfilehash: 6d66b7e84d922108e83e8fa3e045272c82fd8f51
ms.sourcegitcommit: fce27da5140691b013a6f7c0ea9c88b4ea4b7c10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/23/2022
ms.locfileid: "67986344"
---
# <a name="settings-interactions-between-microsoft-365-groups-teams-and-sharepoint"></a>Microsoft 365 Grupları, Teams ve SharePoint arasındaki etkileşimleri ayarlar

Microsoft 365'te özellikle paylaşım ve grup/ekip ve SharePoint sitesi oluşturmayla ilgili bazı Microsoft 365 Grupları, Microsoft Teams ve SharePoint ayarları birbiriyle çakışıyor. Bu makale, bu etkileşimlerin açıklamalarını ve bu ayarlarla çalışmaya yönelik en iyi yöntemleri sağlar.

![SharePoint, Teams ve grup özelliklerinin Venn diyagramı.](../media/teams-groups-sharepoint-venn.png)

## <a name="the-effects-of-sharepoint-settings-on-groups-and-teams"></a>SharePoint ayarlarının gruplar ve ekipler üzerindeki etkileri

|SharePoint ayarı|Açıklama|Microsoft 365 grupları ve Teams üzerindeki etkisi|Öneri|
|:-----------------|:----------|:---------------------------------------|:-------------|
|Kuruluş ve site için dış paylaşım|Sitelerin, dosyaların ve klasörlerin kuruluş dışındaki kişilerle paylaşılıp paylaşılmadığını belirler.|SharePoint, gruplar ve Teams ayarları eşleşmiyorsa, ekipteki konukların siteye erişimi engellenebilir veya beklenmeyen dış erişim oluşabilir.|Paylaşım ayarlarını değiştirirken, grup bağlantılı ekip siteleri için Gruplar ayarlarını, Teams ayarlarını ve SharePoint site ayarlarını denetleyin.<br><br> Bkz [. Ekipteki konuklarla işbirliği yapma](./collaborate-as-team.md)|
|Etki alanına izin ver/engelle|İçeriğin belirtilen etki alanlarıyla paylaşılmasına izin verir veya engeller.|Gruplar ve Teams, SharePoint izin verilenler listesini veya blok listelerini tanımaz. SharePoint'te izin verilmeyen etki alanlarından kullanıcılar, ekip aracılığıyla SharePoint sitelerine veya içeriğine erişim elde edebilir.|Azure AD ve SharePoint için etki alanı izin verilenler listelerini veya blok listelerini birlikte yönetin. Etki alanlarına izin vermek ve etki alanlarını engellemek için kuruluş genelinde bir idare süreci oluşturun.<br><br>Bkz[. SharePoint etki alanı ayarları](/sharepoint/restricted-domains-sharing) ve [Azure AD etki alanı ayarları](/azure/active-directory/b2b/allow-deny-list)|
|Yalnızca belirli güvenlik gruplarındaki kullanıcıların harici olarak paylaşmasına izin ver|SharePoint sitelerini, klasörlerini ve dosyalarını harici olarak paylaşabilecek güvenlik gruplarını belirtir.|Bu ayar, ekip sahiplerinin ekipleri harici olarak paylaşmasını engellemez. Ekip konukları ilişkili SharePoint sitesine erişebilir.||
|SharePoint site paylaşım ayarları|Siteyi ekip üyeliği dışında paylaşabilecek kişileri belirler. Bu, ekip veya site sahibi tarafından yapılandırılır.|Bu ayar ekibi doğrudan etkilemez, ancak kullanıcıların bir siteye eklenmesine ve ekibin kendisine veya diğer Teams kaynaklarına erişmesine izin verebilir|Site paylaşımını doğrudan sınırlamak ve ekip aracılığıyla site erişimini yönetmek için bu ayarı kullanmayı göz önünde bulundurun.|
|Kullanıcıların SharePoint başlangıç sayfasından ve OneDrive'dan site oluşturmasına izin verme|Kullanıcıların yeni SharePoint siteleri oluşturup oluşturamadığını belirtir.|Bu ayar kapalıysa, kullanıcılar ekip oluşturarak gruba bağlı ekip siteleri oluşturmaya devam edebilir.||

## <a name="the-effects-of-groups-settings-on-teams"></a>Grup ayarlarının ekipler üzerindeki etkileri

|Microsoft 365 grupları ayarı|Açıklama|Teams üzerindeki etkisi|Öneri|
|:---------------------------|:----------|:--------------|:-------------|
|Adlandırma ilkeleri|Grup adı ön eklerini ve soneklerini ve grup oluşturma için engellenen sözcükleri belirtir|İlkeler, ekip oluşturan kullanıcılar için zorunlu tutulur.||
|Grup konuk erişimi|Kuruluş dışındaki kişilerin gruplara eklenip eklenebileceğini belirtir.|Gruplar veya Teams konuk paylaşım ayarları kapalıysa, ekip konuklarla paylaşılamaz.|Konuk paylaşım ayarlarını değiştirirken Teams, Gruplar ve ekiple ilişkilendirilmiş SharePoint sitesinin ayarlarını denetleyin.<br><br> Bkz [. Ekipteki konuklarla işbirliği yapma](./collaborate-as-team.md)|
|Güvenlik grubuna göre grup oluşturma|Gruplar yalnızca belirli bir güvenlik grubunun üyeleri tarafından oluşturulabilir.|Güvenlik grubunun üyesi olmayan kullanıcılar ekip oluşturamaz.|Grup isteme işleminizin ekip veya SharePoint sitesi isteme yönergeleri içerdiğine emin olun.|
|Grup süre sonu ilkesi|Etkin olarak kullanılmayan grupların otomatik olarak silineceği süreyi belirtir.|Grup silindiğinde ekip ve ilişkili SharePoint sitesi de silinir. Bekletme ilkeleri tarafından korunan içerik korunur.|Kullanılmayan ekiplerin, grupların ve sitelerin yayılmasını önlemek için süre sonu ilkelerini kullanın.|

## <a name="related-topics"></a>İlgili konular

[İşbirliği idaresi planlama önerileri](collaboration-governance-overview.md#collaboration-governance-planning-recommendations)

[İşbirliği idare planınızı oluşturma](collaboration-governance-first.md)

[Kuruluşunuzun dışındaki kişilerle işbirliği](./collaborate-with-people-outside-your-organization.md)

[SharePoint'te site oluşturmayı yönetme](/sharepoint/manage-site-creation)