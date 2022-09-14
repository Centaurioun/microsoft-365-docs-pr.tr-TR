---
title: Tehdit analizindeki analist raporu bölümünü anlama.
ms.reviewer: ''
description: Tehdit analizi raporlarının rapor bölümü tehditler, risk azaltma, algılamalar, gelişmiş tehdit avcılığı sorguları ve daha fazlası hakkında nasıl bilgi sağlar?
keywords: analist raporu, tehdit analizi, algılamalar, gelişmiş tehdit avcılığı sorguları, azaltmalar,
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 1d47b966ccce5a22a2d61f18353cefa77c7a58c3
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67689305"
---
# <a name="the-analyst-report-in-threat-analytics"></a>Tehdit analizinde analist raporu

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**

- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Her [tehdit analizi raporu](threat-analytics.md) dinamik bölümler ve _analist raporu_ adlı kapsamlı bir yazılı bölüm içerir. Bu bölüme erişmek için izlenen tehditle ilgili raporu açın ve **Analist raporu** sekmesini seçin.

:::image type="content" source="images/ta-analyst-report-small.png" alt-text="Tehdit analizi raporunun analist raporu bölümü" lightbox="images/ta-analyst-report-small.png":::

_Tehdit analizi raporunun analist raporu bölümü_

## <a name="scan-the-analyst-report"></a>Analist raporunu tarama

Analist raporunun her bölümü eyleme dönüştürülebilir bilgiler sağlamak için tasarlanmıştır. Raporlar farklılık gösterse de, çoğu rapor aşağıdaki tabloda açıklanan bölümleri içerir.

<br>

****

|Rapor bölümü|Açıklama|
|---|---|
|Yönetici özeti|İlk görüldüğü zaman, motivasyonları, dikkate değer olaylar, ana hedefler ve farklı araçlar ve teknikler de dahil olmak üzere, tehdide genel bakış. Bu bilgileri, sektörünüz, coğrafi konumunuz ve ağınız bağlamında tehdidi nasıl önceliklendirebileceğinizi daha fazla değerlendirmek için kullanabilirsiniz.|
|Analysis|Bir saldırının ayrıntıları ve saldırganların yeni bir teknik veya saldırı yüzeyini nasıl kullanabileceği dahil olmak üzere tehditler hakkında teknik bilgiler|
|GÖZLEMLENEN MITRE ATT&CK teknikleri|Gözlemlenen teknikler [MITRE ATT&CK saldırı çerçevesiyle nasıl eşlenir?](https://attack.mitre.org/)|
|[Azaltıcı etken](#apply-additional-mitigations)|Tehdidi durdurabilecek veya tehdidin etkisini azaltmaya yardımcı olabilecek öneriler. Bu bölüm, tehdit analizi raporunun bir parçası olarak dinamik olarak izlenmemiş risk azaltmaları da içerir.|
|[Algılama ayrıntıları](#understand-how-each-threat-can-be-detected)|Microsoft güvenlik çözümleri tarafından sağlanan ve tehditle ilişkili etkinlikleri veya bileşenleri ortaya çıkarabilen belirli ve genel algılamalar.|
|[Gelişmiş avcılık örneği](#find-subtle-threat-artifacts-using-advanced-hunting)|Olası tehdit etkinliğini proaktif olarak tanımlamak için [gelişmiş tehdit avcılığı sorguları](advanced-hunting-overview.md). Sorguların çoğu, özellikle kötü amaçlı olabilecek bileşenleri veya kötü amaçlı olduğu dinamik olarak değerlendirilemeyen davranışları bulmak için ek algılamalar için sağlanır.|
|Başvurular|Raporun oluşturulması sırasında analistler tarafından başvuruda bulunan Microsoft ve üçüncü taraf yayınları. Tehdit analizi içeriği, Microsoft araştırmacıları tarafından doğrulanan verileri temel alır. Genel kullanıma açık, üçüncü taraf kaynaklardan gelen bilgiler bu şekilde net bir şekilde tanımlanır.|
|Günlüğü Değiştir|Raporun yayımlandığı zaman ve raporda önemli değişiklikler yapıldığında.|
|

## <a name="apply-additional-mitigations"></a>Ek risk azaltmaları uygulama

Tehdit analizi [, güvenlik güncelleştirmelerinin ve güvenli yapılandırmaların durumunu](threat-analytics.md#mitigations-review-list-of-mitigations-and-the-status-of-your-devices) dinamik olarak izler. Bu bilgiler, **Risk Azaltmalar** sekmesinde grafikler ve tablolar olarak kullanılabilir.

Analist raporu, izlenen bu risk azaltmalara ek olarak dinamik olarak _izlenmeyen_ risk azaltmaları da ele alır. Aşağıda dinamik olarak izlenmemiş bazı önemli risk azaltma örnekleri verilmiştir:

- _.lnk_ eklerine veya diğer şüpheli dosya türlerine sahip e-postaları engelleme
- Yerel yönetici parolalarını rastgele belirleme
- Son kullanıcıları kimlik avı e-postası ve diğer tehdit vektörleri hakkında eğitme
- Belirli [saldırı yüzeyi azaltma kurallarını](attack-surface-reduction.md) açma

Güvenlik duruşunuzu bir tehdide karşı değerlendirmek için **Risk Azaltmalar** sekmesini kullanabilirsiniz ancak bu öneriler güvenlik duruşunuzu iyileştirmeye yönelik ek adımlar atmanıza olanak sağlar. Analist raporundaki tüm risk azaltma kılavuzlarını dikkatle okuyun ve mümkün olduğunda uygulayın.

## <a name="understand-how-each-threat-can-be-detected"></a>Her tehdidin nasıl algılanabilir olduğunu anlama

Analist raporu ayrıca Microsoft Defender Virüsten Koruma ile _uç nokta algılama ve yanıt_ (EDR) özelliklerinden algılamalar sağlar.

### <a name="antivirus-detections"></a>Virüsten koruma algılamaları

Bu algılamalar [, Microsoft Defender Virüsten Koruma'nın](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) açık olduğu cihazlarda kullanılabilir. Bu algılamalar, Uç Nokta için Microsoft Defender eklenen cihazlarda gerçekleştiğinde, rapordaki grafikleri aydınlatan uyarılar da tetikler.

> [!NOTE]
> Analist raporu, izlenen tehdide özgü bileşenlere veya davranışlara ek olarak çok çeşitli tehditleri belirleyebilen **genel algılamaları** da listeler. Bu genel algılamalar grafiklere yansıtılamaz.

### <a name="endpoint-detection-and-response-edr-alerts"></a>Uç nokta algılama ve yanıt (EDR) uyarıları

[Uç Nokta için Microsoft Defender eklenen cihazlar](onboard-configure.md) için EDR uyarıları oluşturulur. Bu uyarılar genellikle Uç Nokta için Microsoft Defender algılayıcısı tarafından toplanan güvenlik sinyallerini ve güçlü sinyal kaynakları olarak hizmet veren diğer uç nokta özelliklerini (virüsten koruma, ağ koruması, kurcalama koruması gibi) kullanır.

Virüsten koruma algılamaları listesinde olduğu gibi, bazı EDR uyarıları da izlenen tehditle ilişkilendirilmeyebilecek şüpheli davranışlara genel olarak bayrak eklemek için tasarlanmıştır. Bu gibi durumlarda rapor, uyarıyı açıkça "genel" olarak tanımlar ve rapordaki grafiklerin hiçbirini etkilemez.

## <a name="find-subtle-threat-artifacts-using-advanced-hunting"></a>Gelişmiş tehdit avcılığı kullanarak küçük tehdit yapıtlarını bulma

Algılamalar izlenen tehdidi otomatik olarak tanımlamanıza ve durdurmanıza olanak sağlarken, birçok saldırı etkinliği ek inceleme gerektiren ince izler bırakır. Bazı saldırı etkinlikleri de normal olabilecek davranışlar sergiler, bu nedenle bunları dinamik olarak algılamak işlemsel kirlilik ve hatta hatalı pozitif sonuçlara neden olabilir.

[Gelişmiş avcılık](advanced-hunting-overview.md), tehdit etkinliğinin ince göstergelerini bulma işlemini basitleştiren Kusto Sorgu Dili dayalı bir sorgu arabirimi sağlar. Ayrıca bağlamsal bilgileri ortaya çıkmanızı ve göstergelerin bir tehdide bağlı olup olmadığını doğrulamanızı sağlar.

Analist raporlarındaki gelişmiş tehdit avcılığı sorguları Microsoft analistleri tarafından izlendi ve [gelişmiş tehdit avcılığı sorgu düzenleyicisinde](https://security.microsoft.com/advanced-hunting) çalıştırmaya hazır. Gelecekteki eşleşmeler için uyarıları tetikleyen [özel algılama kuralları](custom-detection-rules.md) oluşturmak için sorguları da kullanabilirsiniz.

## <a name="related-topics"></a>İlgili konular

- [Tehdit analizine genel bakış](threat-analytics.md)
- [Gelişmiş avcılık ile tehditleri proaktif olarak bulma](advanced-hunting-overview.md)
- [Özel algılama kuralları](custom-detection-rules.md)
