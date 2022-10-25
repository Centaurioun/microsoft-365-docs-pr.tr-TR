---
title: Adım 2. İlk olayınızı düzeltme
description: Microsoft 365 Defender'daki ilk olayınızı düzeltmeye başlama.
keywords: olaylar, uyarılar, saldırı hikayesi, araştırma, bağıntı, saldırı, makineler, cihazlar, kullanıcılar, kimlikler, kimlik, posta kutusu, e-posta, 365, Microsoft, m365, olay yanıtı, siber saldırı
search.product: eADQiWindows 10XVcnh
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- m365solution-firstincident
- highpri
- tier1
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 7094a4445422e6fb68f797c7011f0e420df0a765
ms.sourcegitcommit: e7dbe3b0d97cd8c64b5ae15f990d5e4b1dc9c464
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2022
ms.locfileid: "68687682"
---
# <a name="step-2-remediate-your-first-incident"></a>Adım 2. İlk olayınızı düzeltme

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- Microsoft 365 Defender

Microsoft 365 Defender yalnızca algılama ve analiz özellikleri sağlamakla kalmaz, aynı zamanda kötü amaçlı yazılımların kapsanması ve silinmesini de sağlar. Kapsama, saldırının etkisini azaltmaya yönelik adımlar içerirken, silme işlemi saldırgan etkinliğinin tüm izlemelerinin ağdan kaldırılmasını sağlar. Microsoft 365 Defender, etkilenen cihazların işletim sistemine ve saldırı türüne bağlı olarak [otomatik olarak düzeltilecek](m365d-autoir.md) şekilde yapılandırılabilir çeşitli düzeltme eylemleri sunar.

Microsoft 365 Defender analistlerin el ile başlatabileceği çeşitli düzeltme eylemleri sunar. Eylemler iki kategoriye ayrılır: Cihazlarda eylemler ve dosyalardaki eylemler. Bazı eylemler tehdidi hemen durdurmak için kullanılırken, diğer eylemler daha fazla adli analize yardımcı olabilir.

## <a name="actions-on-devices"></a>Cihazlardaki eylemler

- **Cihazı yalıtma** - Bu etkinlik, kötü amaçlı yazılımların yayılmasını en aza indirmek ve analistlerin kötü amaçlı bir aktör saldırıyı sürdüremeden analize devam etmelerini sağlamak için tüm ağ trafiğini (İnternet ve şirket içi) hemen engeller. İzin verilen tek bağlantı, Kimlik için Microsoft Defender cihazı izlemeye devam edebilmesi için Kimlik için Microsoft Defender hizmet bulutudur. 
- **Uygulama yürütmeyi kısıtlama** - Bir uygulamanın çalışmasını kısıtlamak için, yalnızca Microsoft tarafından verilen bir sertifika tarafından imzalanan dosyaların çalıştırılmasına izin veren bir kod bütünlüğü ilkesi uygulanır. Bu kısıtlama yöntemi, saldırganın güvenliği aşılmış cihazları denetlemesini ve daha fazla kötü amaçlı etkinlik gerçekleştirmesini önlemeye yardımcı olabilir.
- **Virüsten Koruma taraması çalıştırma** - Microsoft Defender Virüsten Koruma taraması, Defender Virüsten Koruma'nın etkin virüsten koruma çözümü olup olmadığına bakılmaksızın diğer virüsten koruma çözümleriyle birlikte çalıştırılabilir. Birincil uç nokta koruma çözümü başka bir virüsten koruma satıcısı ürünüyse Defender Virüsten Koruma'yı Pasif modda çalıştırabilirsiniz.
- **Otomatik araştırma başlatma** - Cihazda yeni bir genel amaçlı otomatik araştırma başlatabilirsiniz. Bir araştırma çalışırken, cihazdan oluşturulan diğer tüm uyarılar, araştırma tamamlanana kadar devam eden bir otomatik araştırmaya eklenir. Ayrıca, aynı tehdit diğer cihazlarda görülürse, bu cihazlar araştırmaya eklenir.
- **Canlı yanıt başlatma** - Canlı yanıt, uzak kabuk bağlantısı kullanarak bir cihaza anında erişim sağlayan bir özelliktir. Bu sayede ayrıntılı araştırma çalışmaları yapabilir ve belirlenen tehditleri anında gerçek zamanlı olarak içermek için anında yanıt eylemleri gerçekleştirebilirsiniz. Canlı yanıt, adli veri toplamanıza, betik çalıştırmanıza, analiz için şüpheli varlıklar göndermenize, tehditleri düzeltmenize ve yeni ortaya çıkan tehditleri proaktif olarak avlamanıza olanak tanıyarak araştırmalarını geliştirmek için tasarlanmıştır.
- **Araştırma paketini toplama** - Araştırma veya yanıt sürecinin bir parçası olarak bir cihazdan araştırma paketi toplayabilirsiniz. Araştırma paketini toplayarak cihazın geçerli durumunu belirleyebilir ve saldırgan tarafından kullanılan araç ve teknikleri daha iyi anlayabilirsiniz. 
- **Defender Uzmanlarına Sorun** (cihazlarda ve dosyalarda hem Eylemler'de kullanılabilir) - Tehlikeye girmiş olabilecek cihazlar veya zaten güvenliği aşılmış cihazlar hakkında daha fazla içgörü için Microsoft Defender uzmanına başvurabilirsiniz. Microsoft Defender uzmanları, zamanında ve doğru bir yanıt için doğrudan Microsoft 365 Defender içinden devreye eklenebilir.

> [!NOTE]
> Saldırı hikayesinin içindeki grafikten doğrudan cihazlarda eylem gerçekleştirebilirsiniz.

## <a name="actions-on-files"></a>Dosyalardaki eylemler

- **Dosyayı durdurma ve karantinaya alma** - Bu eylem, çalışan işlemleri durdurmayı, dosyaları quarantining'i ve herhangi bir kayıt defteri anahtarı gibi kalıcı verileri silmeyi içerir. Bu eylem, dosyanın son 30 gün içinde gözlemlendiği Windows 11 veya Windows 10, sürüm 1703 veya üzeri olan cihazlarda geçerli olur. 
- **Dosyayı engellemek veya dosyaya izin vermek için göstergeler ekleme** - Kötü amaçlı olabilecek dosyaları veya şüpheli kötü amaçlı yazılımları yasaklayarak kuruluşunuzda bir saldırının daha fazla yayılmasını engelleyin. Bu işlem, dosyanın kuruluşunuzdaki cihazlarda okunmasını, yazılmasını veya yürütülmesini engeller.
- **Dosya indirme veya toplama** – Bu eylem, analistlerin kuruluş tarafından daha fazla analiz için parola korumalı .zip arşiv dosyasındaki bir dosyayı indirmesine olanak tanır.
- **Derin analiz** : Bu eylem, güvenli, tam olarak izlemeli bir bulut ortamında bir dosya yürütür. Derin analiz sonuçları dosyanın etkinliklerini, gözlemlenen davranışlarını ve bırakılan dosyalar, kayıt defteri değişiklikleri ve IP adresleriyle iletişim gibi ilişkili yapıtları gösterir. 

Olayları [algılama, önceliklendirme ve analiz etme](first-incident-analyze.md#analyze-your-first-incident) başlığı altındaki örnekten devam eden analist, bu olayı şu eylemlerle düzeltebilir:

1. Kullanıcı hesabı parolasını hemen sıfırlayın
2. Derin analiz tamamlanana kadar cihazı Microsoft 365 Defender içinde yalıtma
3. Kötü amaçlı dosyanın SharePoint'ten karantinaya alındığından emin olun
4. Kötü amaçlı yazılımdan hangi uç noktaların etkilendiğini denetleyin
5. Sistemleri yeniden derleme
6. Diğer kullanıcılar için benzer Microsoft Defender for Cloud Apps uyarıları olup olmadığını denetleyin
7. Tor IP adresini engellemek için Uç Nokta için Microsoft Defender'de özel bir gösterge oluşturma
8. Aşağıdaki görüntüde gösterilenler gibi bu tür uyarılar için Microsoft Defender for Cloud Apps bir idare eylemi oluşturun:

   :::image type="content" source="../../media/first-incident-remediate/first-incident-mcas-governance.png" alt-text="Microsoft Defender for Cloud Apps portalındaki idare eylemleri" lightbox="../../media/first-incident-remediate/first-incident-mcas-governance.png":::

Düzeltme eylemlerinin çoğu Microsoft 365 Defender uygulanabilir ve izlenebilir.

## <a name="using-playbooks"></a>Playbook'ları kullanma

Ayrıca, playbook'lar kullanılarak otomatik düzeltme oluşturulabilir. Şu anda Microsoft, [GitHub'da](https://github.com/microsoft/Microsoft-Cloud-App-Security/tree/master/Playbooks) aşağıdaki senaryolar için playbook'lar sağlayan Playbook şablonlarına sahiptir:

- Kullanıcı doğrulaması istendikten sonra hassas dosya paylaşımını kaldırma
- Seyrek görülen ülke uyarılarını otomatik olarak önceliklendirme
- Hesabı devre dışı bırakmadan önce yönetici eylemi isteme
- Kötü amaçlı gelen kutusu kurallarını devre dışı bırakma

Playbook'lar, belirli ölçütler tetiklendikten sonra belirli etkinlikleri otomatikleştirmek üzere özel robotik süreç otomasyonu akışları oluşturmak için Power Automate'i kullanır. Kuruluşlar mevcut şablonlardan veya sıfırdan playbook'lar oluşturabilir. 

İşte bir örnek.
 
:::image type="content" source="../../media/first-incident-remediate/first-incident-power-automate.png" alt-text="Power Automate özel robotik süreç otomasyon akışı" lightbox="../../media/first-incident-remediate/first-incident-power-automate.png"::: 
 
Playbook'lar [, çözümlenen olaylardan düzeltme eylemleri oluşturmak için olay sonrası gözden geçirme](first-incident-post.md) sırasında da oluşturulabilir. 

## <a name="next-step"></a>Sonraki adım

Bir [olayın olay sonrası gözden geçirmesini nasıl gerçekleştireceğinizi](first-incident-post.md) öğrenin.

## <a name="see-also"></a>Ayrıca bkz.

- [Olaylara genel bakış](incidents-overview.md)
- [Olayları araştırın](investigate-incidents.md)
- [Olayları yönetin](manage-incidents.md)
