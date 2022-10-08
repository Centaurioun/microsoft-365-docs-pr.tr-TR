---
title: Microsoft 365'te Teams ile güvenli dosya ve belge paylaşımı ve işbirliği ayarlama
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection:
- highpri
- M365-collaboration
- m365solution-securecollab
- m365solution-overview
ms.custom:
- M365solutions
- seo-marvel-jun2020
f1.keywords: NOCSH
recommendations: false
description: Verilerinizi duyarlılığına göre korumak için Teams'de güvenli dosya işbirliği ve paylaşımı ayarlamak için en iyi yöntemleri öğrenin.
ms.openlocfilehash: ab3d57f45aed00ab2b9500a7cdb80b3adda76483
ms.sourcegitcommit: fce27da5140691b013a6f7c0ea9c88b4ea4b7c10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/23/2022
ms.locfileid: "67985992"
---
# <a name="set-up-secure-file-sharing-and-collaboration-with-microsoft-teams"></a>Microsoft Teams ile güvenli dosya paylaşımı ve işbirliği ayarlama

Aşırı paylaşımı engellerken dosyaları ve belgeleri doğru kişilerle kolayca paylaşabilmek, kuruluşun başarısı için önemlidir. Bu, gizli veya diğer hassas verileri yalnızca erişimi olması gereken kişilerle güvenli bir şekilde paylaşabilmektir. Projeye bağlı olarak bu, hassas verileri kuruluşunuzun dışındaki kişilerle paylaşmayı içerebilir.

Bu işbirliği çözümü kılavuzu, size yardımcı olacak iki bileşen içerir:

- Teams'i her proje için doğru koruma düzeyiyle dağıtma
- Her proje için uygun güvenlik ayarlarıyla dış paylaşımı yapılandırma

![Teams'i uygun korumayla dağıtın ve uygun güvenlik ayarlarıyla dış paylaşımı yapılandırın.](..\media\solutions-architecture-center\secure-collaboration-overview.png)

Çok yönlü ve kullanımı kolay dosya işbirliği araçları kullanılamıyorsa, kullanıcılar genellikle belgeleri e-postayla göndererek işbirliği yapacaktır. Bu yorucu ve hataya açık bir işbirliği yöntemidir ve bilgilerin uygunsuz paylaşılması riskini artırabilir. kişiler dosya paylaşımını çok zor bulursa BT tarafından yönetilmeyen tüketici ürünlerini kullanmaya geri dönebilir. Bu daha da büyük bir risk oluşturabilir.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWxMmL?autoplay=false]

Microsoft 365 ile Teams'i aşağıdakilere yardımcı olan çeşitli yapılandırmalarla dağıtabilirsiniz:

- Fikri mülkiyetinizi koruma
- Belgeler ve diğer dosyalarla kolay işbirliğine olanak sağlama
- Kullanıcı memnuniyetini artıran ve gölge BT riskini azaltan güvenlik ve kullanılabilirlik arasında denge oluşturma

Çoğu kuruluş, bilgilerin uygunsuz şekilde paylaşılması durumunda çeşitli duyarlılık dereceleri ve değişen iş etki dereceleriyle çeşitli bilgilere sahiptir. Belirli bir bilgi parçasının hassasiyetine bağlı olarak, aşağıdakilerle paylaşıma izin vermek isteyebilirsiniz:

- Herkes (kimliği doğrulanmamış)
- Kuruluşun içinde Kişiler
- Kuruluş içindeki belirli kişiler
- Kuruluşun içindeki ve dışındaki belirli kişiler

Pazarlama broşürleri gibi bilgiler, kuruluş dışında geniş çapta paylaşıma yöneliktir. Kafeterya menüleri gibi bilgiler dış paylaşım için tasarlanmıyor, ancak dışarıdan paylaşıldıklarında iş açısından hiçbir etkisi olmaz. Bu tür bilgilerin çok az korunması gerekir veya hiç korunmaz.

Geliştirme aşamasındayken aynı pazarlama broşürleri yalnızca kuruluş içinde paylaşılabilir. Bu durumda, Teams'deki varsayılan paylaşım ayarları yeterli olabilir.

Geliştirme aşamasında olan yeni bir ürün hakkındaki bilgiler, kuruluş içinde bile hassas olarak kabul edilebilir. Bu durumda daha yüksek bir koruma derecesi uygun olabilir. Örneğin, bu bilgilere erişimi belirli bir ekibin üyeleriyle kısıtlayabilirsiniz. Projeye bağlı olarak, kuruluşunuzun dışındaki satıcı veya iş ortağı kuruluş gibi kişilerle işbirliği yapmanız gerekebilir.

Kuruluşunuzun başarısı için kritik öneme sahip olan veya sıkı güvenlik veya uyumluluk gereksinimleri olan bilgiler daha da yüksek koruma düzeyleri gerektirebilir.

![Düşükten (yayımlanan broşür) yüksek (hassas iş verilerine) kadar risk ölçeği.](../media/solutions-architecture-center/SecureCollaboration-SensitivityAndBusinessImpactofSharing-fromVisio.png)

Yukarıda belirtilen tüm senaryolar için Microsoft Teams'deki ekipleri kullanarak bilgileri depolayabilir, paylaşabilir ve üzerinde işbirliği yapabilirsiniz.

Güvenli işbirliğini yapılandırmak için bu Microsoft 365 özelliklerini ve özelliklerini kullanırsınız.

|Ürün veya bileşen|Yetenek veya özellik|Lisanslama|
|---|---|---|
|Office 365 için Microsoft Defender|SPO, OneDrive ve Teams için Güvenli Ekler; Güvenli Belgeler; Teams için Güvenli Bağlantılar|Microsoft 365 E1, E3 ve E5|
|SharePoint|Site ve dosya paylaşım ilkeleri, Site paylaşım izinleri, Paylaşım bağlantıları, Erişim istekleri, Site konuk paylaşım ayarları|Microsoft 365 E1, E3 ve E5|
|Microsoft Teams|Konuk erişimi, özel ekipler, özel kanallar, paylaşılan kanallar|Microsoft 365 E1, E3 ve E5|
|Microsoft Purview|Duyarlılık etiketleri|Microsoft 365 E3 ve E5|

## <a name="collaboration-governance-framework-for-teams-and-microsoft-365"></a>Teams ve Microsoft 365 için işbirliği idare çerçevesi

Microsoft 365, işbirliği çözümünüzü yönetmek için birçok seçenek sunar. Kuruluşunuz için en iyi işbirliği çözümünü oluşturmak için bu dağıtım [içeriğini işbirliği idaresi içeriğiyle](collaboration-governance-overview.md) birlikte kullanmanızı öneririz.

### <a name="securing-teams-for-sensitive-and-highly-sensitive-data"></a>Hassas ve son derece hassas veriler için Teams'in güvenliğini sağlama

Farklı hassasiyetlere sahip bilgilere erişimi yönetmek [için Teams için üç farklı koruma katmanı](configure-teams-three-tiers-protection.md) geliştirdik. Gereksinimlerinizi veya işinizi daha iyi karşılamak için bu katmanlardan herhangi birini özelleştirebilirsiniz.

![Teams için üç koruma düzeyi grafiği.](../media/solutions-architecture-center/Teams-tiers-of-protection-1.png)

Temel *,* *hassas* ve *yüksek oranda hassas* olan bu katmanlar, aşağıdaki tabloda gösterildiği gibi fazla paylaşımı ve olası bilgi sızıntısını önlemeye yardımcı olan korumaları aşamalı olarak artırır.

|-|Temel katman|Hassas katman|Son derece hassas katman|
|---|---|---|---|
|Genel veya özel ekip|İki durumdan biri|Özel|Özel|
|Kimliği doğrulanmamış paylaşım|Engellenen|Engellenen|Engellenen|
|Dosya paylaşımı|Izin verilen|Izin verilen|Yalnızca ekip sahipleri paylaşabilir.|
|Ekip üyeliği|Herkes herkese açık ekiplere katılabilir.<br>Özel takımlara katılmak için ekip sahibi onayı gerekir.|Katılmak için ekip sahibi onayı gerekir.|Katılmak için ekip sahibi onayı gerekir.|
|Belge şifrelemesi|||Duyarlılık etiketiyle kullanılabilir|
|Konuk paylaşımı|Izin verilen|İzin verilebilir veya engellenebilir|İzin verilebilir veya engellenebilir|
|Yönetilmeyen cihazlar|Kısıtlama yok|Yalnızca web erişimi|Engellenen|

Bu katmanların yapılandırılması şunları içerir:

- Teams'de konuk erişimi ve özel kanallar için ayarları yapılandırma
- Bir ekibin ilişkili SharePoint sitesinde iç ve konuk paylaşımı, erişim istekleri ve paylaşım bağlantıları için ayarları yapılandırma
- *Hassas* ve *son derece hassas* katmanlar için, ekipleri sınıflandırmak için duyarlılık etiketlerini yapılandırma ve yönetilmeyen cihazlardan konuk paylaşımını ve erişimini denetleme
- *Son derece hassas* katman için, uygulandığı belgeleri şifrelemek için bir duyarlılık etiketi yapılandırma

Temel katmanla başlayın ve ardından *kuruluşunuzdaki bilgilerin* korunmasına yardımcı olmak için hassas ve *yüksek düzeyde hassas* katmanları kullanan ekipler ekleyin. Başlamak için şu kaynaklara bakın:

- [Ekipleri temel koruma ile yapılandırma](configure-teams-baseline-protection.md)
- [Hassas veriler için koruma ile ekipleri yapılandırma](configure-teams-sensitive-protection.md)
- [Son derece hassas veriler için koruma ile ekipleri yapılandırma](configure-teams-highly-sensitive-protection.md)

Kuruluşunuzda bile paylaşıma karşı ek koruma gerektiren son derece hassas bir projeniz varsa, dosyaları yalnızca ekip üyelerinin okuyabilmesi için kendi duyarlılık etiketini kullanan bir ekip yapılandırabilirsiniz. Ayrıntılar için bkz. [Ekibi güvenlik yalıtımıyla yapılandırma](secure-teams-security-isolation.md) .

### <a name="sharing-with-people-outside-your-organization"></a>Kuruluşunuzun dışındaki kişilerle paylaşma

[Herhangi bir duyarlılık bilgilerini kuruluşunuzun dışındaki kişilerle paylaşmanız](collaborate-with-people-outside-your-organization.md) gerekebilir. Bu, tek bir belgeyi tek bir kişiyle paylaşmaktan büyük bir ortak kuruluşla veya dünyanın dört bir yanından serbest çalışanlarla büyük bir proje üzerinde işbirliği yapmaya kadar değişebilir. Microsoft 365'te, hassas bilgilerinizi korumaya yardımcı olmak için bu dış paylaşım aralığı kolayca ve uygun korumalarla yapılabilir.

Bu kaynaklar, ortamınızı kuruluşunuzun dışındaki kişilerle işbirliği yapmak üzere ayarlamaya başlamanıza yardımcı olur:

- Klasörlerin tek tek dosyalarını paylaşmak için [belgeler üzerinde işbirliği yapın](collaborate-on-documents.md).
- SharePoint sitesindeki konuklarla işbirliği yapmak için bir sitede [işbirliği yapın](collaborate-in-site.md).
- Ekipteki konuklarla işbirliği yapmak için [ekip olarak işbirliği yapın](collaborate-as-team.md).
- Paylaşılan bir kanalda kuruluş dışındaki kişilerle işbirliği yapmak için [kanaldaki dış katılımcılarla işbirliği](/microsoft-365/solutions/collaborate-teams-direct-connect) yapın.

Paylaşılmakta olan bilgilerin duyarlılığına bağlı olarak, fazla paylaşımı önlemeye yardımcı olacak korumalar ekleyebilirsiniz. Bu kaynaklar, kuruluşunuz için ihtiyacınız olan korumaları ayarlamanıza yardımcı olur:

- [Kimliği doğrulanmamış kullanıcılarla dosya ve klasör paylaşmaya yönelik en iyi yöntemler](best-practices-anonymous-sharing.md)
- [Kuruluşunuzun dışındaki kişilerle paylaşım yaparken dosyaların yanlışlıkla açığa çıkmalarını sınırlayın](share-limit-accidental-exposure.md)
- [Güvenli bir konuk paylaşım ortamı oluşturma](create-secure-guest-sharing-environment.md)

İş ortağı bir kuruluşla ilgili önemli bir projeniz varsa, kuruluşunuzun dışında işbirliği yapmanız gereken kişileri yönetmek için [paylaşılan kanalları](/microsoft-365/solutions/collaborate-teams-direct-connect) veya [Azure Yetkilendirme Yönetimi'ni](b2b-extranet.md) kullanabilirsiniz.

## <a name="training-for-administrators"></a>Yöneticiler için eğitim

Microsoft Learn'deki bu eğitim modülleri Teams ve SharePoint'teki işbirliği, idare ve kimlik özelliklerini öğrenmenize yardımcı olabilir.

### <a name="teams"></a>Teams

|Eğitim:|Microsoft Teams ile ekip işbirliğini yönetme|
|---|---|
|![Teams işbirliği eğitim simgesi.](../media/manage-team-collaboration-with-microsoft-teams.svg)|Microsoft Teams ile ekip işbirliğini yönetme, Microsoft 365'te ekip işbirliğinin merkezi olan Microsoft Teams'in özelliklerini ve özelliklerini size tanıtır. Teams'i kullanarak hem şirket içinde hem de şirket dışında, masaüstlerinden tabletlere ve telefonlara kadar çok çeşitli cihazlarda ekip çalışmasını ve iletişimi kolaylaştırırken Office 365 uygulamalarının tüm zengin işlevselliğinden nasıl yararlanabileceğinizi öğreneceksiniz. Teams'in uygulamalar ve cihazlar arasında işbirliği için nasıl kapsamlı ve esnek bir ortam sağladığını anlayacaksınız. Bu öğrenme yolu, Microsoft 365 Sertifikalı: Teams Yönetici İş Ortağı sertifikasına hazırlanmanıza yardımcı olabilir.<p>2 sa 17 dk - Öğrenme Yolu - 5 Modül|

> [!div class="nextstepaction"]
> [Başlangıç >](/training/modules/m365-teams-collab-prepare-deployment/introduction/)

### <a name="sharepoint"></a>SharePoint

|Eğitim:|Microsoft 365'te SharePoint ile işbirliği yapma|
|---|---|
|![SharePoint eğitim simgesi.](../media/collaborate-with-sharepoint-in-microsoft-365.svg)|Microsoft SharePoint ile paylaşılan içeriği yönetme, SharePoint'in özelliklerini ve özelliklerini ve Microsoft 365 ile nasıl çalıştığını gösterir. Merkez siteleri, bilgi koruma, raporlama ve izleme gibi farklı Türlerdeki SharePoint siteleri hakkında bilgi edineceksiniz. Ayrıca, işbirliğini iyileştirmek için SharePoint dosya ve klasör paylaşımını kullanmayı, dosyaları harici olarak paylaşmayı ve SharePoint yönetim merkezinde SharePoint sitelerini yönetmeyi de öğreneceksiniz. Bu öğrenme yolu, Microsoft 365 Sertifikalı: Ekip Çalışması Yöneticisi İş Ortağı sertifikasına hazırlanmanıza yardımcı olabilir.<p>1 sa 14 dk - Öğrenme Yolu - 4 Modül|

> [!div class="nextstepaction"]
> [Başlangıç >](/training/modules/m365-teams-sharepoint-plan-sharepoint/introduction/)

### <a name="information-protection"></a>Bilgi koruması

|Eğitim:|Microsoft 365 ile kurumsal bilgileri koruma|
|---|---|
|![Teams bilgi koruma eğitimi simgesi.](../media/protect-enterprise-information-microsoft-365.svg)|Kuruluşunuzun bilgilerini korumak ve güvenliğini sağlamak her zamankinden daha zordur. Microsoft 365 ile kurumsal bilgileri koruma öğrenme yolu, hassas bilgilerinizi yanlışlıkla aşırı paylaşıma veya kötüye kullanmaya karşı korumayı, verileri bulmayı ve sınıflandırmayı, duyarlılık etiketleriyle korumayı ve kaybına karşı korumak için hassas bilgilerinizi izleme ve analiz etme konularını açıklar. Bu öğrenme yolu, Microsoft 365 Sertifikalı: Güvenlik Yöneticisi İş Ortağı ve Microsoft 365 Sertifikalı: Kurumsal Yönetim Uzmanı sertifikaları için hazırlanmanıza yardımcı olabilir.<p>1 sa - Öğrenme Yolu - 5 Modül|

> [!div class="nextstepaction"]
> [Başlangıç >](/training/modules/m365-security-info-overview/introduction/)

### <a name="identity-and-access"></a>Kimlik ve erişim

|Eğitim:|Azure Active Directory ile kimliği ve erişimi koruma|
|---|---|
|![Kimlik ve erişim eğitimi simgesi.](../media/protect-identity-and-access-with-microsoft-365.svg)|Kimlik ve Erişim öğrenme yolu, en son kimlik ve erişim teknolojilerini, kimlik doğrulamasını güçlendirmeye yönelik araçları ve kuruluşunuzdaki kimlik korumasına yönelik yönergeleri kapsar. Microsoft erişim ve kimlik teknolojileri, ister şirket içinde ister bulutta olsun kuruluşunuzun kimliğinin güvenliğini sağlamanızı ve kullanıcılarınızın herhangi bir konumdan güvenli bir şekilde çalışmasını sağlamanızı sağlar. Bu öğrenme yolu, Microsoft 365 Sertifikalı: Güvenlik Yöneticisi İş Ortağı ve Microsoft 365 Sertifikalı: Kurumsal Yönetim Uzmanı sertifikaları için hazırlanmanıza yardımcı olabilir.<p>2 sa 52 dk - Öğrenme Yolu - 6 Modül|

> [!div class="nextstepaction"]
> [Başlangıç >](/training/modules/m365-identity-overview/introduction/)

## <a name="training-for-end-users"></a>Son kullanıcılar için eğitim

Bu eğitim modülleri, kullanıcılarınızın Microsoft 365'te işbirliği için Teams, gruplar ve SharePoint kullanmalarına yardımcı olabilir.

|Teams|SharePoint|
|---|---|
|![Ekip eğitimi simgenizi ayarlayın ve özelleştirin.](../media/set-up-customize-team-training.png)<br>**[Ekibinizi ayarlama ve özelleştirme](https://support.microsoft.com/office/702a2977-e662-4038-bef5-bdf8ee47b17b)**|![SharePoint eğitim paylaşma ve eşitleme simgesi](../media/sharepoint-share-sync-training.png)<br>**[Paylaşma ve eşitleme](https://support.microsoft.com/office/98cb2ff2-c27e-42ea-b055-c2d895f8a5de)**|
|![Ekipler dosya yükleme ve bulma eğitim simgesi.](../media/smc-teams-upload-find-files-training.png)<br>**[Dosyaları karşıya yükleme ve bulma](https://support.microsoft.com/office/57b669db-678e-424e-b0a0-15d19215cb12)**||
|![Ekiplerde ve kanallarda işbirliği yapma simgesi.](../media/teams-collaborate-channels-training.png)<br>**[Ekiplerde ve kanallarda işbirliği yapma](https://support.microsoft.com/office/c3d63c10-77d5-4204-a566-53ddcf723b46)**||

## <a name="illustrations"></a>Çizim

Bu çizimler, grupların ve ekiplerin Microsoft 365'teki diğer hizmetlerle nasıl etkileşim kuracağını ve kuruluşunuzda bu hizmetleri yönetmenize yardımcı olacak idare ve uyumluluk özelliklerinin neler olduğunu anlamanıza yardımcı olur.

### <a name="groups-in-microsoft-365-for-it-architects"></a>BT Mimarları için Microsoft 365'teki gruplar

BT mimarlarının Microsoft 365'teki gruplar hakkında bilmesi gerekenler

|**Öğe**|**Açıklama**|
|---|---|
|[![Gruplar için başparmak görüntüsü bilgi grafiği.](../downloads/msft-m365-groups-architecture-thumb.png)](https://download.microsoft.com/download/6/3/0/6309218f-a169-4f2d-af4c-2fe49e30ba17/msft-m365-groups.pdf) <br/> [PDF](https://download.microsoft.com/download/6/3/0/6309218f-a169-4f2d-af4c-2fe49e30ba17/msft-m365-groups.pdf) \| [Visio](https://download.microsoft.com/download/6/3/0/6309218f-a169-4f2d-af4c-2fe49e30ba17/msft-m365-groups.vsdx) <br> Mayıs 2022'de güncelleştirildi|Bu çizimler, farklı grup türlerini, bunların nasıl oluşturulup yönetildiğini ve birkaç idare önerisini ayrıntılarıyla açıklar.|

### <a name="microsoft-teams-and-related-productivity-services-in-microsoft-365-for-it-architects"></a>BT mimarları için Microsoft 365'te Microsoft Teams ve ilgili üretkenlik hizmetleri

Microsoft Teams ile önde gelen Microsoft 365'teki üretkenlik hizmetlerinin mantıksal mimarisi.

|**Öğe**|**Açıklama**|
|---|---|
|[![Teams mantıksal mimari posteri için başparmak resmi.](../downloads/msft-teams-logical-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-teams-logical-architecture.pdf) <br/> [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-teams-logical-architecture.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-teams-logical-architecture.vsdx)  <br>Nisan 2019 güncelleştirildi|Microsoft, veri idaresi, güvenlik ve uyumluluk özellikleriyle işbirliği deneyimleri sağlamak için birlikte çalışan bir üretkenlik hizmetleri paketi sağlar. <p>Bu çizim serisi, Microsoft Teams ile önde gelen kurumsal mimarlar için üretkenlik hizmetlerinin mantıksal mimarisine yönelik bir görünüm sağlar.|

## <a name="deploy-the-secure-collaboration-solution"></a>Güvenli işbirliği çözümünü dağıtma

Bu çözümü dağıtmaya hazır olduğunuzda şu adımlarla devam edin:

1. [Teams için üç farklı koruma katmanını](configure-teams-three-tiers-protection.md) yapılandırın.
2. [Herhangi bir duyarlılık bilgilerini kuruluşunuzun dışındaki kişilerle paylaşmak](collaborate-with-people-outside-your-organization.md) için ayarları yapılandırın.

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft 365 güvenlik belgeleri](../security/index.yml)

[Microsoft Purview belgeleri](../compliance/index.yml)

[Microsoft Teams'e hoş geldiniz](/MicrosoftTeams/Teams-overview)
