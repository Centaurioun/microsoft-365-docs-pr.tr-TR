---
title: Microsoft 365 Grupları ile SharePoint arasındaki etkileşimleri ayarlar
ms.reviewer: mmclean
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
description: Microsoft 365 Grupları ve SharePoint arasındaki ayarlar etkileşimleri hakkında bilgi edinin
ms.openlocfilehash: bbf15581e91f2c4399ccc03d49cd4d886ef5b4f2
ms.sourcegitcommit: fce27da5140691b013a6f7c0ea9c88b4ea4b7c10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/23/2022
ms.locfileid: "67986762"
---
# <a name="settings-interactions-between-microsoft-365-groups-and-sharepoint"></a>Microsoft 365 Grupları ile SharePoint arasındaki etkileşimleri ayarlar

Microsoft 365'te özellikle paylaşım ve grup ve ekip sitesi oluşturmayla ilgili bazı Microsoft 365 Grupları ve SharePoint ayarları birbiriyle çakışıyor. Bu makale, bu etkileşimlerin açıklamalarını ve bu ayarlarla çalışmaya yönelik en iyi yöntemleri sağlar.

![SharePoint, Yammer ve grup özelliklerinin Venn diyagramı.](../media/groups-sharepoint-venn.png)

## <a name="the-effects-of-sharepoint-settings-on-microsoft-365-groups"></a>SharePoint ayarlarının Microsoft 365 grupları üzerindeki etkileri

|SharePoint ayarı|Açıklama|Microsoft 365 grupları üzerindeki etkisi|Öneri|
|:-----------------|:----------|:-----------------------------|:-------------|
|Kuruluş ve site için dış paylaşım|Sitelerin, dosyaların ve klasörlerin kuruluş dışındaki kişilerle paylaşılıp paylaşılmadığını belirler.|SharePoint ve grup ayarları eşleşmiyorsa, gruptaki konukların siteye erişimi engellenebilir veya dış erişim grupta değil, sitede kullanılabilir olabilir.|Paylaşım ayarlarını değiştirirken, gruba bağlı ekip siteleri için hem Gruplar ayarlarını hem de SharePoint site ayarlarını denetleyin.<br><br>Bkz. [Sitedeki konuklarla işbirliği yapma](./collaborate-in-site.md).|
|Etki alanına izin ver/engelle|İçeriğin belirtilen etki alanlarıyla paylaşılmasına izin verir veya engeller.|Gruplar SharePoint izin verilenler listelerini veya blok listelerini tanımaz. SharePoint'te izin verilmeyen etki alanlarından kullanıcılar bir grup aracılığıyla SharePoint'e erişim sağlayabilir.|Azure AD ve SharePoint için etki alanı izin verilenler listelerini veya blok listelerini birlikte yönetin. Etki alanlarına izin vermek ve etki alanlarını engellemek için kuruluş genelinde bir idare süreci oluşturun.<br><br>Bkz[. SharePoint etki alanı ayarları](/sharepoint/restricted-domains-sharing) ve [Azure AD etki alanı ayarları](/azure/active-directory/b2b/allow-deny-list)|
|Yalnızca belirli güvenlik gruplarındaki kullanıcıların harici olarak paylaşmasına izin ver|Siteleri, klasörleri ve dosyaları harici olarak paylaşabilecek güvenlik gruplarını belirtir.|Bu ayar, grupları dış olarak paylaşan grup sahiplerini etkilemez. Grup konukları ilişkili SharePoint sitesine erişebilir.||
|SharePoint site paylaşım ayarları|Siteyi doğrudan grup üyeliği dışında paylaşabilecek kişileri belirler. Bu, grup veya site sahibi tarafından yapılandırılır.|Bu ayar grubu doğrudan etkilemez, ancak kullanıcıların bir siteye eklenmesine ve diğer grup kaynaklarına erişimi olmamasına izin verebilir|Site paylaşımını doğrudan sınırlamak ve grup üzerinden site erişimini yönetmek için bu ayarı kullanmayı göz önünde bulundurun.|
|Kullanıcıların SharePoint başlangıç sayfasından ve OneDrive'dan site oluşturmasına izin verme|Kullanıcıların yeni SharePoint siteleri oluşturup oluşturamadığını belirtir.|Bu ayar kapalıysa, kullanıcılar grup oluşturarak gruba bağlı ekip siteleri oluşturmaya devam edebilir.||

## <a name="the-effects-of-microsoft-365-groups-setting-on-sharepoint"></a>SharePoint'te Microsoft 365 grupları ayarının etkileri

|Microsoft 365 grupları ayarı|Açıklama|SharePoint üzerindeki etkisi|Öneri|
|:---------------------------|:----------|:-------------------|:-------------|
|Adlandırma ilkeleri|Grup adı ön eklerini ve soneklerini ve grup oluşturma için engellenen sözcükleri belirtir|İlkeler, grup bağlantılı ekip siteleri oluşturan kullanıcılar için uygulanır, ancak diğer şablonlarla iletişim siteleri veya siteler için uygulanmaz.|Gerekirse iletişim siteleri için ayrı adlandırma kılavuzu oluşturun.|
|Grup konuk erişimi|Kuruluş dışındaki kişilerin gruplara eklenip eklenebileceğini belirtir.|SharePoint ve grup ayarları eşleşmiyorsa, gruptaki konukların siteye erişimi engellenebilir veya dış erişim grupta değil, sitede kullanılabilir olabilir.|Paylaşım ayarlarını değiştirirken, gruba bağlı ekip siteleri için hem Gruplar ayarlarını hem de SharePoint site ayarlarını denetleyin.<br><br>Bkz. [Sitedeki konuklarla işbirliği yapma](./collaborate-in-site.md)|
|Güvenlik grubuna göre grup oluşturma|Gruplar yalnızca belirli bir güvenlik grubunun üyeleri tarafından oluşturulabilir.|Güvenlik grubunun üyesi olmayan kullanıcılar, gruba bağlı bir ekip sitesi oluşturamaz.|Grup isteme işleminizde site isteğinde bulunma yönergelerinin bulunduğuna emin olun.|
|Grup süre sonu ilkesi|Etkin olarak kullanılmayan grupların otomatik olarak silineceği süreyi belirtir.|Grup silindiğinde, ilişkili SharePoint sitesi de silinir. Bekletme ilkeleri tarafından korunan içerik korunur.|Kullanılmayan grupların ve sitelerin yayılmasını önlemek için süre sonu ilkelerini kullanın.|

## <a name="related-topics"></a>İlgili konular

[İşbirliği idaresi planlama önerileri](collaboration-governance-overview.md#collaboration-governance-planning-recommendations)

[İşbirliği idare planınızı oluşturma](collaboration-governance-first.md)

[Kuruluşunuzun dışındaki kişilerle işbirliği](./collaborate-with-people-outside-your-organization.md)

[SharePoint'te site oluşturmayı yönetme](/sharepoint/manage-site-creation)