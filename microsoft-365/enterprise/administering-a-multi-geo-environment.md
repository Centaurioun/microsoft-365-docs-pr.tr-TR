---
title: Çok Coğrafi Özellikli Bir Ortamda Hizmet Davranışı
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
f1.keywords:
- NOCSH
ms.custom:
- seo-marvel-apr2020
- admindeeplinkSPO
ms.collection:
- Strat_SP_gtc
- SPO_Content
ms.localizationpriority: medium
description: Yöneticiler, SharePoint ve OneDrive hizmetlerini çok coğrafi bir ortamda yönetme hakkında bilgi edinebilir.
ms.openlocfilehash: ae6673488e552e1da9acd14526194734d194c305
ms.sourcegitcommit: 0c72639cc3dc74667a6b14343d303f318e70d457
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/01/2022
ms.locfileid: "68803627"
---
# <a name="service-behavior-a-multi-geo-enabled-environment"></a>Multi-Geo özellikli bir ortamın hizmet davranışı

Burada, Microsoft 365 hizmetlerinin Multi-Geo ortamında nasıl çalıştığına göz atabilirsiniz.

## <a name="administrator-experience"></a>Yönetici deneyimi

SharePoint yönetim merkezinde, sol gezinti bölmesinde [**coğrafi konumlarınızı**](https://go.microsoft.com/fwlink/?linkid=2185076) görüntüleyip yönetebileceğiniz bir coğrafi konum haritası içeren bir Coğrafi konumlar sekmesi bulunur. _Kiracınızın_ coğrafi konumlarını eklemek veya silmek için bu sayfayı kullanın.

## <a name="audit-log-search"></a>Denetim günlüğü araması

Tüm _Uydu Coğrafya_ konumlarınız için birleşik [bir Denetim günlüğü](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c), Microsoft 365 denetim günlüğü arama sayfasından sağlanır. Coğrafi konumlardaki tüm denetim günlüğü girişlerini görebilirsiniz, örneğin NAM & EUR kullanıcılarının etkinlikleri tek kuruluş görünümünde gösterilir ve ardından belirli kullanıcının etkinliklerini görmek için mevcut filtreleri uygulayabilirsiniz.

> [!NOTE]
> Exchange yöneticisi denetim olayları yalnızca varsayılan konum için kullanılabilir.

## <a name="bcs-secure-store-apps"></a>BCS, Güvenli Depolama, Uygulamalar

BCS, Güvenli Depolama ve Uygulamaların her uydu konumunda ayrı örnekleri vardır, bu nedenle SharePoint Online yöneticisi bu hizmetleri her uydu konumundan ayrı olarak yönetmeli ve yapılandırmalıdır.

## <a name="compliance-admin-center"></a>Uyumluluk yönetim merkezi

Multi-Geo _Kiracısı_ için tek bir merkezi Microsoft Purview uyumluluk portalı vardır: [Microsoft Purview yönetim merkezi](https://compliance.microsoft.com/).

## <a name="ediscovery"></a>Ediscovery

Varsayılan olarak, bir Multi-Geo _Kiracısının_ eBulma Yöneticisi veya Yöneticisi eBulma'yı yalnızca bu _Kiracının_ _Birincil Sağlanan Coğrafyasında_ gerçekleştirebilecektir. Office 365 genel yöneticisi, başkalarının eBulma gerçekleştirmesine izin vermek için eBulma Yöneticisi izinleri atamalı ve eBulma'yı uydu konumu olarak yürütmek için bölgeyi belirtmek üzere ilgili Uyumluluk Güvenlik Filtrelerinde bir "Bölge" parametresi atamalıdır, aksi takdirde uydu konumu için eBulma gerçekleştirilmeyecektir. Bir Bölge için Uyumluluk Güvenlik Filtresi'ni yapılandırmak için bkz. [Multi-Geo eBulma Office 365 yapılandırma](multi-geo-ediscovery-configuration.md).

## <a name="exchange-online-mailboxes"></a>posta kutularını Exchange Online

PdL'leri değiştirilirse kullanıcıların Exchange Online posta kutuları otomatik olarak taşınır. Yeni bir posta kutusu oluşturulduğunda, kullanıcının PDL'sine veya kullanıcının PDL'sine değer ayarlanmamışsa merkezi konuma sağlanır.

## <a name="information-protection-ip-data-loss-prevention-dlp-policy"></a>Information Protection (IP) Veri Kaybı Önleme (DLP) ilkesi

OneDrive İş, SharePoint Online ve Exchange Online için IP DLP ilkelerinizi Güvenlik ve Uyumluluk merkezinde _, kiracının_ tamamına veya geçerli kullanıcılara gereken kapsam belirleme ilkelerini ayarlayabilirsiniz. Örneğin: Uydu konumundaki bir kullanıcı için ilke seçmek istiyorsanız, ilkeyi belirli bir OneDrive İş uygulamak için öğesini seçin ve kullanıcının OneDrive İş URL'sini girin. DLP ilkeleri oluşturma konusunda genel yönergeler için bkz. [Veri kaybı önleme ilkelerine genel bakış](https://support.office.com/article/1966b2a7-d1e2-4d92-ab61-42efbb137f5e) .

DLP ilkeleri her coğrafi konuma uygulanabilirliklerine göre otomatik olarak eşitlenir.

Coğrafi konumdaki tüm kullanıcılara Information Protection ve Microsoft Purview Veri Kaybı Önleme ilkeleri uygulamak kullanıcı arabiriminde kullanılabilir bir seçenek değildir; bunun yerine ilke için geçerli hesapları seçmeniz veya ilkeyi tüm hesaplara genel olarak uygulamanız gerekir.

## <a name="microsoft-power-apps"></a>Microsoft Power Apps

Uydu konumu için oluşturulan Power Apps _, Kiracının_ merkezi konumunda bulunan bitiş noktasını kullanır. Microsoft Power Apps bir Multi-Geo hizmeti değildir. 

## <a name="microsoft-power-automate"></a>Microsoft Power Automate

Uydu konumu için oluşturulan akışlar _, Kiracı_ için varsayılan coğrafi konumda bulunan bitiş noktasını kullanır.  Microsoft Power Automate bir Multi-Geo hizmeti değildir. 

## <a name="sharepoint-online-storage-quota"></a>SharePoint Online depolama kotası

Varsayılan olarak, çok coğrafi ortamın tüm coğrafi konumları kullanılabilir _Kiracı_ depolama kotasını paylaşır.  Ayrıca, belirli bir coğrafi konum için belirli bir kota ayırarak depolama kotasını yönetebilirsiniz. Daha fazla bilgi için bkz. [Çok coğrafili ortamlarda SharePoint depolama kotaları](sharepoint-multi-geo-storage-quota.md).

## <a name="sharing"></a>Paylaşım

Yöneticiler konumlarının her biri için paylaşım ilkeleri ayarlayabilir ve yönetebilir. Her coğrafi konumdaki OneDrive İş ve SharePoint Online siteleri yalnızca ilgili coğrafi olarak özel paylaşım ayarlarına uygun olacaktır. (Örneğin, merkezi konumunuz için [dış paylaşıma](https://support.office.com/article/C8A462EB-0723-4B0B-8D0A-70FEAFE4BE85) izin verebilirim, ancak uydu konumunuz veya tam tersi için izin vermezsiniz.) Paylaşım ayarlarının coğrafi konumlar arasında paylaşım sınırlamalarının yapılandırılmasına izin vermediğini unutmayın.

## <a name="microsoft-stream"></a>Microsoft Stream

1:1 sohbetinde Microsoft Stream yüklenen videolar, karşıya yüklenen kişinin OneDrive İş depolanır. Toplantı kayıtları, toplantıyı kaydeden her katılımcının OneDrive İş depolanır.

## <a name="taxonomy"></a>Taksonomi

Coğrafi konumlar genelinde kurumsal olarak yönetilen meta veriler için birleştirilmiş [taksonomiyi](/sharepoint/managed-metadata) destekliyoruz ve ana veriler şirketiniz için merkezi konumda barındırılıyor. Genel taksonominizi merkezi konumdan yönetmenizi ve uydu konumunun Taksonomisine yalnızca konuma özgü terimler eklemenizi öneririz. Genel taksonomi terimleri uydu konumları ile eşitlenir.

Daha fazla ayrıntı ve geliştirici yönergeleri için bkz [. Multi-Geo kiracısında meta verileri yönetme](/sharepoint/dev/solution-guidance/multigeo-managedmetadata) .

## <a name="user-profile-application"></a>Kullanıcı Profili Uygulaması

Her coğrafi konumda bir [kullanıcı profili uygulaması](/sharepoint/manage-user-profiles) vardır. Her kullanıcının profil bilgileri kendi coğrafi konumunda barındırılır ve bu coğrafi konumun yöneticisi tarafından kullanılabilir.

Özel profil özellikleriniz varsa, coğrafyalar arasında aynı profil şemasını kullanmanızı ve özel profil özelliklerinizi tüm coğrafi konumlarda veya gerektiğinde doldurmanızı öneririz. Kullanıcı profili verilerini program aracılığıyla doldurma hakkında rehberlik için lütfen [Toplu Kullanıcı Profili Güncelleştirme API'sine](/sharepoint/dev/solution-guidance/bulk-user-profile-update-api-for-sharepoint-online) bakın.

Ek ayrıntılar ve geliştirici yönergeleri için bkz. [Multi-Geo kiracısında kullanıcı profilleriyle çalışma](/sharepoint/dev/solution-guidance/multigeo-userprofileexperience) .

## <a name="yammer"></a>Yammer

Yammer bir Multi-Geo iş yükü değildir. Yammer'da depolanan Yammer iş parçacıkları _Kiracının_ merkezi konumuna yerleştirilir. Yammer, Yammer dosyalarını SharePoint'in içinde depolayacak bir dosya depolama değişikliği dağıtıyor. SharePoint'te depolanan Yammer dosyaları, Yammer grubuyla ilişkilendirilmiş SharePoint sitesine yerleştirilir. SharePoint grup siteleri, [SharePoint Siteleri ve Grupları'nda](multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md#sharepoint-sites-and-groups) açıklandığı gibi PDL mantığını temel alır.
