---
title: Microsoft Defender güncelleştirmeleri için aşamalı olarak geçiş işlemini yönetme
description: Aşamalı güncelleştirme işlemi ve denetimleri hakkında bilgi
keywords: güncelleştirme, güncelleştirme işlemi, denetimler, sürüm
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: bc9e6814dc599b6a3474a00cd51676bbe708716a
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/24/2021
ms.locfileid: "62998258"
---
# <a name="manage-the-gradual-rollout-process-for-microsoft-defender-updates"></a>Microsoft Defender güncelleştirmeleri için aşamalı olarak geçiş işlemini yönetme

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Aşağıdakiler için geçerlidir:**
- [Uç Nokta Planı 2 için Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)

kritik koruma özellikleri sağlamak ve saldırılardan korunmak için istemci bileşenlerinin güncel olduğundan emin olmak önemlidir.

Özellikler çeşitli bileşenler aracılığıyla sağlanır:

- [Uç Nokta Algılama & Yanıtı](overview-endpoint-detection-response.md)
- [Buluta teslim edilen korumayla](microsoft-defender-antivirus-windows.md) [yeni nesil koruma](cloud-protection-microsoft-defender-antivirus.md)
- [Saldırı Yüzeyini Azaltma](overview-attack-surface-reduction.md)

Güncelleştirmeler, aşamalı bir sürüm işlemi kullanılarak aylık olarak yayımlar. Bu işlem, erken hata algılamanın meydana gelen etkiyi yakalaması ve daha büyük bir rollamadan önce bu etkiyi hızlı bir şekilde ele almalarını sağlar.

> [!NOTE]
> Günlük güvenlik zekası güncelleştirmelerini denetleme hakkında daha fazla bilgi için bkz. Koruma [güncelleştirmelerini Microsoft Defender Virüsten Koruma zamanlama](manage-protection-update-schedule-microsoft-defender-antivirus.md). Güncelleştirmeler, bulut teslimi koruması uç noktada sağlanmaz bile olsa yeni nesil korumanın yeni tehditlere karşı savunmada olmasını sağlar.

## <a name="microsoft-gradual-rollout-model"></a>Microsoft aşamalı kademeli kademeli çıkış modeli

Aylık Defender güncelleştirmeleri için aşağıdaki aşamalı geçiş modeli takip edilecektir:

1. İlk sürüm Beta kanalı abonelerine sunulacaktır.
2. Doğrulama, geri bildirim ve düzeltmelerden sonra aşamalı olarak ve kısıtlandıktan sonra önce Kanal abonelerini önizlemek için aşamalı olarak kademeli olarak kademeli olarak geçiş işlemini başlatacağız.
3. Daha sonra, güncelleştirmeyi genel popülasyonın geri kalanına serbest bırakmak ve %10-100 arasında ölçeklendirme yapmak için devam edeceğiz.

Mühendislerimiz gereken etkiyi sürekli izlemektedir ve bir düzeltme oluşturmak için tüm sorunları büyülemektedir.

## <a name="how-to-customize-your-internal-deployment-process"></a>İç dağıtım işleminizi özelleştirme

Makineniz Windows Update'Windows Defender güncelleştirmeleri alıyorsa aşamalı olarak kademeli geçiş işlemi, bazı makinenizin Defender güncelleştirmelerini diğerlerine göre daha önce almasine neden olabilir. Aşağıdaki bölümde, güncelleştirme kanalı yapılandırmasından yararlanarak otomatik güncelleştirmelerin belirli cihaz gruplarına farklı aksına izin verecek bir stratejinin nasıl tanımlanacakları açıklanıyor.

> [!NOTE]
> Kendi aşamalı sürümünizi planken lütfen her zaman önizleme ve aşamalı kanallara abone olan farklı cihazlar seçmeyi unutmayın. Bu, hem organizasyon hem de Microsoft'a ortamınıza özgü sorunları önleme veya bulma ve düzeltme fırsatı sağlar.

Örneğin, Windows Server Update Services (WSUS) veya Microsoft Endpoint Configuration Manager (MECM) aracılığıyla güncelleştirme alan makinelerde, tüm Windows Defender Uç Nokta güncelleştirmeleri de dahil olmak üzere başka seçenekler de vardır.

- Daha fazla bilgi için WSUS, MECM gibi bir çözümü kullanarak güncelleştirmelerin dağıtımını ve uygulamasını yönetme konusunda daha fazla bilgi için Microsoft Defender Virüsten Koruma [temelleri yönetme - ve temelleri uygulama - Windows okuyun](manage-updates-baselines-microsoft-defender-antivirus.md#product-updates).

## <a name="update-channels-for-monthly-updates"></a>Aylık güncelleştirmeler için kanalları güncelleştirme

Makinenin aylık altyapı ve platform güncelleştirmelerini aldığı tempoyu tanımlamak için bir makineyi güncelleştirme kanalına atabilirsiniz.

Güncelleştirmeleri yapılandırma hakkında daha fazla bilgi için bkz [. Microsoft Defender güncelleştirmeleri için özel bir aşamalı kademeli uygulama işlemi oluşturma](configure-updates.md).

Aşağıdaki güncelleştirme kanalları kullanılabilir:

<br>

****

|Kanal adı|Açıklama|Uygulama|
|---|---|---|
|Beta Kanalı - Prerelease|Güncelleştirmeleri diğer kişiden önce test edin|Bu kanal olarak ayarlanmış cihazlar, yeni aylık güncelleştirmeleri ilk alan olacaktır. Sorunları Microsoft'a belirlemek ve raporlamaya katılmak için Beta Kanal'ı seçin. Windows Insider Programı'nın cihazları varsayılan olarak bu kanala abonedir. Yalnızca test ortamlarında kullanım için.|
|Güncel Kanal (Önizleme)|Aşamalı sürüm sırasında güncel **Kanal güncelleştirmelerini** daha önce alın|Bu kanala ayarlanmış cihazlara, aşamalı sürüm döngüsünde en erken güncelleştirmeler sunulacaktır. Üretim öncesi/doğrulama ortamları için önerilir.|
|Güncel Kanal (Aşamalı)|Güncel Kanal güncelleştirmelerini daha sonra aşamalı sürüm sırasında alın|Cihazlara aşamalı sürüm döngüsünde daha sonra güncelleştirmeler sunulacaktır. Cihaz popülasyonu içinde küçük, temsili bir bölüme (~%10) uygulama önerilir.|
|Güncel Kanal (Geniş)|Aşamalı sürüm sonunda güncelleştirmeleri alın|Ancak aşamalı sürüm döngüsü tamamlandıktan sonra cihazlara güncelleştirmeler sunulacaktır. Üretim nüfuslu geniş bir cihaz kümesine (~%10-100) uygulama önerilir.|
|Kritik: Gecikme Süresi|Defender güncelleştirmelerini geciktirme|Cihazlara 48 saatlik bir gecikme süresiyle güncelleştirmeler sunulacaktır. Yalnızca sınırlı güncelleştirmeler alan veri merkezi makineleri için en iyi. Yalnızca kritik ortamlar için önerilir.|
|(default)||Bu ilkeyi devre dışı bırakır veya yapılandırmazsanız, cihaz Güncel Kanal'da (Varsayılan) kalır: Aşamalı sürüm döngüsü sırasında otomatik olarak güncel kalın. Çoğu cihaz için uygundur.|
|

### <a name="update-channels-for-daily-updates"></a>Günlük güncelleştirmeler için kanalları güncelleştirme

Ayrıca, bir makinenin günlük güncelleştirmeleri aldığı tempoyu tanımlamak için bir kanala da atabilirsiniz. Aylık işlemden farklı olarak, beta kanalı olmadığını ve bu aşamalı sürüm döngüsünün günde birden çok kez tekrarlal olduğunu unutmayın.

<br>

****

|Kanal adı|Açıklama|Uygulama|
|---|---|---|
|Güncel Kanal (Aşamalı)|Güncel Kanal güncelleştirmelerini daha sonra aşamalı sürüm sırasında alın|Cihazlara aşamalı sürüm döngüsünde daha sonra güncelleştirmeler sunulacaktır. Cihaz popülasyonu içinde küçük, temsili bir bölüme (~%10) uygulama önerilir.|
|Güncel Kanal (Geniş)|Aşamalı sürüm sonunda güncelleştirmeleri alın|Aşamalı sürüm döngüsünde cihazlara güncelleştirmeler sunulacaktır. Yalnızca sınırlı güncelleştirmeler alan veri merkezi makineleri için en iyi. Not: Bu ayar tüm Defender güncelleştirmeleri için geçerlidir.|
|(default)||Bu ilkeyi devre dışı bırakır veya yapılandırmazsanız, cihaz Güncel Kanal'da (Varsayılan) kalır: Aşamalı sürüm döngüsü sırasında otomatik olarak güncel kalın. Çoğu cihaz için uygun|
|

> [!NOTE]
> Zaman gecikmesi yerine en yeni imzaya güncellemeye zorlamak isterseniz, önce bu ilkeyi kaldırmanız gerekir.

## <a name="update-guidance"></a>Güncelleştirme kılavuzu

Çoğu durumda, Windows Update'i kullanırken önerilen yapılandırma, uç noktaların geldiğinde aylık Defender güncelleştirmelerini almalarına ve uygulamalarına izin vermektir. Bu, aralarındaki koruma ve ortaya olabilecek değişikliklerle ilişkili olası etki arasındaki en iyi dengeyi sağlar.

Otomatik Defender güncelleştirmelerinin daha fazla denetlenen aşamalı dağıtımına gerek olan ortamlarda, dağıtım gruplarında bir yaklaşımı göz önünde bulundurmalısınız:

1. Insider programına Windows veya Beta Kanalına bir cihaz grubu attayabilirsiniz.
2. Yeni güncelleştirmeleri erkenden almak için, Kanalı Önizleme Kanalını (genellikle doğrulama ortamları) kabul ediyor bir pilot grup atama.
3. Aşamalı kanaldan aşamalı olarak geçiş sırasında güncelleştirmeleri alacak bir makine grubu atatabilirsiniz. Normalde, popülasyonu temsili %10'olacak.
4. Aşamalı sürüm döngüsü tamamlandıktan sonra güncelleştirmeleri alan bir makine grubu atama. Bunlar genellikle önemli üretim sistemleridir.

Diğer cihazlar için varsayılan ayar, Microsoft aşamalı olarak uygulama işlemi sırasında edinilen yeni güncelleştirmeleri almaktır ve başka yapılandırma gerekmez.

Bu modeli benimseme:

- Erken sürümler üretim ortamına ulaşmadan önce test olanak sağlar
- Üretim ortamının düzenli güncelleştirmeleri hala aldığından ve kritik tehditlere karşı koruma sağlamakta olduğundan emin olun.

## <a name="management-tools"></a>Yönetim araçları

Aylık güncelleştirmeler için kendi özel aşamalı kademeli kademeli uygulama işleminizi oluşturmak için aşağıdaki araçları kullanabilirsiniz:

- Grup ilkesi
- Microsoft Endpoint Manager
- PowerShell

Bu araçların kullanımı hakkında ayrıntılı bilgi için bkz [. Microsoft Defender güncelleştirmeleri için özel bir aşamalı kademeli kademeli uygulama işlemi oluşturma](configure-updates.md).