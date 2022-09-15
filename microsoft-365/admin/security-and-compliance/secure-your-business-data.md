---
title: İşletmenizin güvenliğini sağlamanın en iyi 10 yolu
f1.keywords:
- CSH
ms.author: deniseb
author: denisebmsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.date: 09/14/2022
ms.collection:
- highpri
- Adm_O365
- Adm_TOC
ms.custom:
- VSBFY23
- MSStore_Link
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
- admindeeplinkMAC
- admindeeplinkDEFENDER
- adminvideo
- admindeeplinkEXCHANGE
- business_assist
search.appverid:
- BCS160
- MET150
- MOE150
description: İşletmenizi fidye yazılımlarından, kimlik avından ve kötü amaçlı URL'lerden veya eklerden korumaya yönelik en iyi yöntemler.
ms.openlocfilehash: da1fba7bddabba0ccd95429dc36f06bfb302db48
ms.sourcegitcommit: b1ed6470645455c2f1fcf467450debc622c40147
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/15/2022
ms.locfileid: "67711487"
---
# <a name="top-10-ways-to-secure-your-business---best-practices-to-follow"></a>İşletmenizin güvenliğini sağlamanın en iyi 10 yolu - İzleyebileceğiniz en iyi yöntemler

**Uygulandığı öğe**

- Microsoft 365 Küçük İşletme
- Microsoft 365 Business Standard
- Microsoft 365 Business Premium

> [!NOTE]
> Bu makale, 300'e kadar kullanıcısı olan küçük ve orta ölçekli işletmeler için tasarlanmıştır. Kurumsal bir kuruluşsanız bkz. [Microsoft 365 kiracınız için fidye yazılımı koruması dağıtma](../../solutions/ransomware-protection-microsoft-365.md).

İş için Microsoft 365 planları, antiphishing, antispam ve kötü amaçlı yazılım koruması gibi güvenlik özelliklerini içerir. Microsoft 365 İş Ekstra cihaz güvenliği, gelişmiş tehdit koruması ve bilgi koruması gibi daha da fazla özellik içerir. Bu makalede işletmenizin güvenliğini sağlama açıklanır ve [microsoft 365 İş planlarının özellikleri karşılaştırılmaktadır](#comparing-microsoft-365-for-business-plans).

:::image type="content" source="../../media/top-10-ways-secure-data.png" alt-text="İş verilerinin güvenliğini sağlamanın en iyi 10 yolunu listeleyen diyagram.":::

| Adım | Görev | Açıklama |
|:--:|:---|:---|
| 1 | **[Çok faktörlü kimlik doğrulamasını kullanın](multi-factor-authentication-microsoft-365.md)**. | İki aşamalı doğrulama olarak da bilinen [çok faktörlü kimlik doğrulaması](multi-factor-authentication-microsoft-365.md) (MFA), kullanıcıların Microsoft 365'te oturum açmak için telefonlarında bir kod veya kimlik doğrulama uygulaması kullanmasını gerektirir ve iş verilerinizi korumanın kritik bir ilk adımıdır. MFA'nın kullanılması, korsanların parolanızı biliyorsa devralmalarını engelleyebilir.<br/><br/>Bkz [. güvenlik varsayılanları ve MFA](../../business-premium/m365bp-conditional-access.md). |
| 2 | **[Yönetici hesaplarınızı koruyun](../../business-premium/m365bp-protect-admin-accounts.md)**. | Yönetici hesaplarının (yönetici olarak da adlandırılır) yükseltilmiş ayrıcalıkları vardır ve bu da bu hesapların siber saldırılara karşı daha hassas olmasını sağlar. İşletmeniz için doğru sayıda yönetici ve kullanıcı hesabı ayarlamanız ve yönetmeniz gerekir. Ayrıca, kullanıcılara ve uygulamalara yalnızca işlerini gerçekleştirmek için ihtiyaç duydukları veri ve işlemlere erişim verilmesi gerektiği anlamına gelen en az ayrıcalıklı bilgi güvenliği ilkesine de bağlı kalmalısınız. <br/><br/>Bkz. [Yönetici hesaplarınızı koruma](../../business-premium/m365bp-protect-admin-accounts.md). |
| 3 | **[Önceden ayarlanmış güvenlik ilkelerini kullanın](../../business-premium/m365bp-increase-protection.md)**. | Aboneliğiniz istenmeyen posta önleme, kötü amaçlı yazılımdan koruma ve kimlik avı koruması için önerilen ayarları kullanan [önceden ayarlanmış güvenlik ilkeleri](../../security/office-365-security/preset-security-policies.md) içerir. <br/><br/>Bkz [. Kötü amaçlı yazılımlara ve diğer siber tehditlere karşı koruma](../../business-premium/m365bp-increase-protection.md). |
| 4 | **[Tüm cihazları koruyun](../../business-premium/m365bp-devices-overview.md)**. | Her cihaz ağınıza yönelik olası bir saldırı yoludur ve kişisel olarak sahip olunan ancak iş için kullanılan cihazlar bile düzgün bir şekilde yapılandırılmalıdır. <br/><br/>Aşağıdaki makalelere bakın: <br/>- [Kullanıcıların cihazlarında MFA ayarlamasına yardımcı olun](https://support.microsoft.com/office/set-up-your-microsoft-365-sign-in-for-multi-factor-authentication-ace1d096-61e5-449b-a875-58eb3d74de14)<br/>- [Yönetilmeyen Windows ve Mac bilgisayarlarını koruma](../../business-premium/m365bp-protect-pcs-macs.md) <br/>- [Yönetilen cihazları ayarlama](../../business-premium/m365bp-managed-devices-setup.md) (Microsoft 365 İş Ekstra veya İş için Microsoft Defender gerektirir) |
| 5 | **[Herkesi e-posta en iyi yöntemleriyle eğitin](../../business-premium/m365bp-avoid-phishing-and-attacks.md)**. | Email zararsız iletişim olarak gizlenmiş kötü amaçlı saldırılar içerebilir. Email sistemler özellikle savunmasızdır, çünkü e-posta kuruluştaki herkes tarafından işlenir ve güvenlik, insanların bu iletişimlerle tutarlı bir şekilde iyi kararlar almalarına dayanır. İstenmeyen veya gereksiz postalar, kimlik avı girişimleri, kimlik sahtekarlığı ve e-postalarında kötü amaçlı yazılımlara karşı neleri izleyeceğini öğrenmek için herkesi eğitin. <br/><br/>Bkz [. Kendinizi kimlik avına ve diğer saldırılara karşı koruma](../../business-premium/m365bp-avoid-phishing-and-attacks.md). |
| 6 | **[İşbirliği ve paylaşım için Microsoft Teams'i kullanın](../../business-premium/m365bp-collaborate-share-securely.md)**. | Güvenli bir şekilde işbirliği yapma ve paylaşmanın en iyi yolu Microsoft Teams'i kullanmaktır. Microsoft Teams ile tüm dosyalarınız ve iletişimleriniz korumalı bir ortamdadır ve bunun dışında güvenli olmayan yollarla depolanmaz.<br/><br/> Aşağıdaki makalelere bakın: <br/>- [İşbirliği için Microsoft Teams'i kullanma](../../business-premium/create-teams-for-collaboration.md) <br/>- [Microsoft Teams ile toplantı ayarlama](../../business-premium/set-up-meetings.md) <br/>- [Dosyaları ve videoları güvenli bir ortamda paylaşma](../../business-premium/share-files-and-videos.md) |
| 7 | **[SharePoint ve OneDrive dosya ve klasörleri için paylaşım ayarlarını yapın](../../business-premium/m365bp-increase-protection.md)**. | SharePoint ve OneDrive için varsayılan paylaşım düzeyleriniz, kullanmanız gerekenden daha izinli bir düzeye ayarlanmış olabilir. İşletmenizi daha iyi korumak için varsayılan ayarları gözden geçirmenizi ve gerekirse değiştirmenizi öneririz. Kişilere yalnızca işlerini yapmak için ihtiyaç duydukları erişimi verin. <br/><br/>Bkz. [SharePoint ve OneDrive dosya ve klasörleri için paylaşım ayarlarını ayarlama](../../business-premium/m365bp-increase-protection.md#set-sharing-settings-for-sharepoint-and-onedrive-files-and-folders). |
| 8 | **[Cihazlarda Microsoft 365 Uygulamaları kullanın](https://support.microsoft.com/topic/train-your-users-on-office-and-microsoft-365-7cba3c97-7f19-46ed-a1c6-763971a26c27)**. | Outlook ve Microsoft 365 Uygulamaları (Office uygulamaları olarak da adlandırılır), kişilerin cihazlar arasında üretken ve daha güvenli bir şekilde çalışmasını sağlar. Bir uygulamanın web sürümünü veya masaüstü sürümünü kullanıyor olun, belgeyi bir cihazda başlatabilir ve daha sonra başka bir cihazdan alabilirsiniz. Dosyaları e-posta eki olarak göndermek yerine, SharePoint veya OneDrive'da depolanan belgelerin bağlantılarını paylaşabilirsiniz. <br/><br/>Aşağıdaki makalelere bakın: <br/>- [Office uygulamalarını tüm cihazlara yükleyin](../../business-premium/m365bp-install-office-apps.md).<br/>- [Kullanıcılarınızı Office ve Microsoft 365'te eğitin](https://support.microsoft.com/topic/train-your-users-on-office-and-microsoft-365-7cba3c97-7f19-46ed-a1c6-763971a26c27) |
| 9 | **[İşletmeniz için takvim paylaşımını yönetin](../../business-premium/m365bp-increase-protection.md#manage-calendar-sharing)**. | Kuruluşunuzdaki kişilerin daha iyi işbirliği için takvimlerini uygun şekilde paylaşmalarına yardımcı olabilirsiniz. Paylaşabilecekleri ayrıntı düzeyini yönetebilirsiniz. Örneğin, paylaşılan ayrıntıları yalnızca serbest/meşgul zamanlarıyla sınırlandırabilirsiniz. <br/><br/>Bkz. [Takvim paylaşımını yönetme](../../business-premium/m365bp-increase-protection.md#manage-calendar-sharing). |
| 10 | **[Ortamınızı koruyun](../../business-premium/m365bp-maintain-environment.md)**. | İş için Microsoft 365'in ilk kurulumu ve yapılandırması tamamlandıktan sonra kuruluşunuzun bir bakım ve operasyon planına ihtiyacı vardır. Çalışanlar gelip gittikçe kullanıcıları eklemeniz veya kaldırmanız, parolaları sıfırlamanız ve hatta cihazları fabrika ayarlarına sıfırlamanız gerekir. Ayrıca, kişilerin yalnızca işlerini yapmak için ihtiyaç duydukları erişime sahip olduğundan emin olmak istersiniz. <br/><br/>Bkz [. Ortamınızı koruma](../../business-premium/m365bp-maintain-environment.md). |

## <a name="comparing-microsoft-365-for-business-plans"></a>İş için Microsoft 365 planlarını karşılaştırma

İş için Microsoft 365 planları güvenli e-posta, işbirliği ve dosya depolama için Microsoft Exchange, Microsoft Teams, SharePoint ve OneDrive'ı içerir. Bu planlar temel antiphishing, antimalware ve antispam koruması da içerir. Microsoft 365 İş Ekstra ile cihaz yönetimi, gelişmiş tehdit koruması ve bilgi koruması gibi daha fazla özelliğe sahip olursunuz. 

Aşağıdaki tabloda İş için Microsoft 365 planlarındaki özellikler karşılaştırilmektedir. 

| Yeteneği | [Microsoft 365 Küçük İşletme](../setup/setup-business-basic.md) | [Microsoft 365 Business Standard](../setup/setup-business-standard.md) | [Microsoft 365 Business Premium](../../business-premium/index.md) |
|:---|:--:|:--:|:--:|
| **Office uygulamalarının Outlook ve Web/mobil sürümleri** <br/>Word, Excel ve PowerPoint | ![Dahil.](../../media/d238e041-6854-4a78-9141-049224df0795.png) | ![Dahil.](../../media/d238e041-6854-4a78-9141-049224df0795.png) |![Dahil.](../../media/d238e041-6854-4a78-9141-049224df0795.png) |
| **Office uygulamalarının masaüstü sürümleri**<br/>Word, Excel, PowerPoint, Publisher ve Access <sup>[[Bkz. not 1](#fn1)]</sup> |  | ![Dahil.](../../media/d238e041-6854-4a78-9141-049224df0795.png) | ![Dahil.](../../media/d238e041-6854-4a78-9141-049224df0795.png) |
| **Güvenli iletişim, işbirliği ve dosya depolama**<br/>Microsoft Teams, Exchange, OneDrive ve SharePoint | ![Dahil.](../../media/d238e041-6854-4a78-9141-049224df0795.png) | ![Dahil.](../../media/d238e041-6854-4a78-9141-049224df0795.png) | ![Dahil.](../../media/d238e041-6854-4a78-9141-049224df0795.png) |
| E-posta **için antispam, antiphishing ve kötü amaçlı yazılımdan koruma** <br/>[Exchange Online Protection](../../security/office-365-security/exchange-online-protection-overview.md) | ![Dahil.](../../media/d238e041-6854-4a78-9141-049224df0795.png) | ![Dahil.](../../media/d238e041-6854-4a78-9141-049224df0795.png) | ![Dahil.](../../media/d238e041-6854-4a78-9141-049224df0795.png) |
| **Mobil cihaz yönetimi** ve mobil uygulama yönetimi <br/>[Microsoft Intune](/mem/intune/fundamentals/what-is-intune) | Bkz. not <sup>[[2](#fn2)]</sup> | Bkz. not <sup>[[2](#fn2)]</sup> | ![Dahil.](../../media/d238e041-6854-4a78-9141-049224df0795.png) |
| Yeni nesil koruma, güvenlik duvarı, saldırı yüzeyini azaltma, otomatik araştırma ve yanıt ve daha fazlası ile **gelişmiş cihaz güvenliği** <br/>[İş için Defender](../../security/defender-business/mdb-overview.md) | Nota bakın <sup>[[3](#fn3)]</sup>  | Nota bakın <sup>[[3](#fn3)]</sup> | ![Dahil.](../../media/d238e041-6854-4a78-9141-049224df0795.png) |
| Gelişmiş kimlik avı önleme, Güvenli Bağlantılar, Güvenli Ekler ve gerçek zamanlı algılamalar ile **e-posta ve belgeler için gelişmiş koruma**<br/>[Office 365 için Microsoft Defender Plan 1](../../security/office-365-security/defender-for-office-365.md) | Bkz. not <sup>[[4](#fn4)]</sup> | Bkz. not <sup>[[4](#fn4)]</sup> | ![Dahil.](../../media/d238e041-6854-4a78-9141-049224df0795.png) | 
| Hassas bilgileri keşfetmeye, sınıflandırmaya, korumaya ve yönetmeye yönelik bilgi **koruma** özellikleri <br/>[Azure Information Protection](/azure/information-protection/what-is-information-protection)  | | | ![Dahil.](../../media/d238e041-6854-4a78-9141-049224df0795.png) |

(<a id="fn1">1</a>) Microsoft Publisher ve Microsoft Access yalnızca Windows dizüstü ve masaüstü bilgisayarlarda çalışır.

(<a id="fn2">2</a>) Microsoft Intune, Microsoft 365 İş Ekstra gibi belirli Microsoft 365 planlarıyla birlikte sağlanır. Temel Mobilite ve Güvenlik özellikleri Microsoft 365 İş Temel ve Standard'a dahildir. [Temel Mobilite ve Güvenlik veya Intune arasında seçim yapın](../basic-mobility-security/choose-between-basic-mobility-and-security-and-intune.md).

(<a id="fn3">3</a>) İş için Defender Microsoft 365 İş Ekstra dahildir. İş için Defender, Microsoft 365 İş Temel veya Standart'a da eklenebilir. Bkz. [İş için Defender'ı edinme](/microsoft-365/security/defender-business/get-defender-business).

(<a id="fn4">4</a>) Office 365 için Defender Plan 1 Microsoft 365 İş Ekstra dahil edilir. Office 365 için Defender Plan 1, Microsoft 365 İş Temel veya Standart'a da eklenebilir. Bkz. [Plan 1 ve Plan 2](../../security/office-365-security/overview.md#microsoft-defender-for-office-365-plan-1-vs-plan-2-cheat-sheet) Office 365 için Defender.

> [!TIP]
> Her planın neler içerdiği hakkında daha fazla bilgi için bkz. [Microsoft 365 ve Microsoft Teams ile üretkenliği yeniden](https://www.microsoft.com/en-us/microsoft-365/business/compare-all-microsoft-365-business-products-b?ef_id=8c2a86ec9ea514a008c6e419e036519c:G:s&OCID=AIDcmmwf9kwzdj_SEM_8c2a86ec9ea514a008c6e419e036519c:G:s&lnkd=Bing_O365SMB_Brand&msclkid=8c2a86ec9ea514a008c6e419e036519c) planlama.


## <a name="see-also"></a>Ayrıca bkz.

- [İş için Defender nedir?](../../security/defender-business/mdb-overview.md)
- [Microsoft 365 İş Ekstra— küçük işletmeler için siber güvenlik](/microsoft-365/business-premium/)
- [Küçük ve orta ölçekli işletmeler için Microsoft 365 planlarındaki güvenlik özelliklerini karşılaştırma](../../security/defender-business/compare-mdb-m365-plans.md) (İş için Defender ve Microsoft 365 İş Ekstra hakkında daha fazla ayrıntı için)
- [Microsoft uç nokta güvenlik planlarını karşılaştırma](../../security/defender-endpoint/defender-endpoint-plan-1-2.md) (cihazların güvenliğini sağlamak ve yönetmek için)

