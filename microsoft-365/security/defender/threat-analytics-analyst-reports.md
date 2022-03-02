---
title: Microsoft 365 Defender'de tehdit analizinde analist raporu bölümünü Microsoft 365 Defender
ms.reviewer: ''
description: Her tehdit analizi raporunun analist raporu bölümü hakkında bilgi edinin. Tehdit, risk azaltma, algılama, gelişmiş arama sorguları ve daha fazlası hakkında nasıl bilgi sağladığını anlıyoruz.
keywords: analist raporu, tehdit analizi, algılamalar, gelişmiş arama sorguları, risk azaltmaları,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3821f0738984c856650e8a455c0d83563a148a2a
ms.sourcegitcommit: 6f3bc00a5cf25c48c61eb3835ac069e9f41dc4db
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/24/2022
ms.locfileid: "63010742"
---
# <a name="understand-the-analyst-report-in-threat-analytics-in-microsoft-365-defender"></a>Microsoft 365 Defender'de tehdit analizinde analist raporunu Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Aşağıdakiler için geçerlidir:**
- Microsoft 365 Defender

> Bu deneyimi Microsoft 365 Defender? Bunu bir [laboratuvar ortamında değerlendirin veya](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) [üretimde pilot projenizi çalıştırın](m365d-pilot.md?ocid=cx-evalpilot).
>

[!INCLUDE [Prerelease](../includes/prerelease.md)]

Her [tehdit analizi raporu](threat-analytics.md) dinamik bölümleri ve analist raporu adlı kapsamlı bir yazılı _bölümü içerir_. Bu bölüme erişmek için, izleme tehdidiyle ilgili raporu açın ve Analist raporu **sekmesini** seçin.

![Tehdit analizi raporunun analist raporu bölümünün görüntüsü.](../../media/threat-analytics/ta_analystreport_mtp.png)

_Tehdit analizi raporunun analist raporu bölümü_

## <a name="scan-the-analyst-report"></a>Analist raporunu tarama 
Analist raporunun her bölümü işlemde değiştirilebilir bilgiler sağlamak için tasarlanmıştır. Raporların çoğu farklılık gösterirken, çoğu rapor aşağıdaki tabloda açıklanan bölümleri içerir.

| Rapor bölümü | Açıklama |
|--|--|
| Yönetici özeti | Tehditlere, ilk ne zaman görüldüklerine, motivasyonlarına, önemli etkinliklere, önemli hedeflere ve farklı araçlara ve tekniklere genel bakış. Bu bilgileri kullanarak sektör, coğrafi konum ve ağ bağlamında tehdit önceliklerini nasıl önceliklendireceklerini daha ayrıntılı değerlendirebilirsiniz. |
| Çözümleme | Saldırının ayrıntıları ve saldırganların yeni bir teknik veya saldırı yüzeyinden nasıl yararlanabilmesi gibi tehditlerle ilgili teknik bilgiler | 
| CK tekniklerini&MITRE ATT ve | [CK saldırı çerçevesi için MITRE ATT&gözlemlenen teknikler nasıl eşlenir](https://attack.mitre.org/) | 
| [Azaltmalar](#apply-additional-mitigations) | Öneriler tehdit etkisini durduran veya azaltmaya yardımcı olan yeni bir etki. Bu bölüm aynı zamanda tehdit analizi raporunun bir parçası olarak dinamik olarak izlen etmeyen risk azaltmaları da içerir. |
| [Algılama ayrıntıları](#understand-how-each-threat-can-be-detected) | Microsoft güvenlik çözümleri tarafından sağlanan ve tehditle ilişkili etkinliği veya bileşenleri ortaya çıkaran özel ve genel algılamalar. | 
| [Gelişmiş av](#find-subtle-threat-artifacts-using-advanced-hunting) | [Olası tehdit etkinliğini önceden](advanced-hunting-overview.md) belirlemek için gelişmiş arama sorguları. Çoğu sorgu, özellikle kötü amaçlı olabilecek bileşenleri veya kötü amaçlı olarak değerlendirilamayabilecek davranışları bulmak için ek algılamalara sağlanmıştır. | 
| Başvurular | Rapor oluşturma sırasında analistler tarafından başvurulan Microsoft ve üçüncü taraf yayınları. Tehdit analizi içeriği, Microsoft araştırmacısı tarafından doğrulanmış verilere dayalıdır. Genel kullanıma açık üçüncü taraf kaynaklarından gelen bilgiler bu şekilde açıkça tanımlanır. | 
| Günlüğü Değiştir | Raporun yayım zamanı ve raporda önemli değişiklikler yapıldı. |

## <a name="apply-additional-mitigations"></a>Ek azaltmalar uygulama
Tehdit analizleri güvenlik güncelleştirmelerinin [durumunu dinamik olarak izler ve güvenli yapılandırmaları izler](threat-analytics.md#mitigations-review-list-of-mitigations-and-the-status-of-your-devices). Bu bilgiler Risk Azaltmalar sekmesinde grafik ve **tablo olarak** kullanılabilir.

Bu izlenen risk azaltmalara ek olarak, analist raporu dinamik olarak izlen raporda yer alan risk _azaltmaları da_ tartış eder. Aşağıda, dinamik olarak izlen etmeyen önemli risk azaltmalara bazı örnekler verilmiştir:

- _.lnk ekleri veya diğer_ şüpheli dosya türleri içeren e-postaları engelleme
- Yerel yönetici parolalarını rastgele seçin
- Son kullanıcıları kimlik avı e-postaları ve diğer tehdit vektörleri hakkında eğitin
- Belirli saldırı [yüzeyini azaltma kurallarını açma](/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction)

Risk azaltmalar sekmesini **kullanarak bir** tehditle karşı karşıya güvenliğinizi değerlendirebilirsiniz, ancak bu öneriler, güvenlik görünümlerinizi geliştirme yönünde ek adımlar atmanıza yardımcı olur. Analist raporuna yönelik tüm risk azaltma kılavuzlarını dikkatle okuyun ve mümkün olduğunca kullanın.

## <a name="understand-how-each-threat-can-be-detected"></a>Her bir tehdidin nasıl algı edilemediklerini anlama
Analist raporu aynı zamanda teknik özellikler ve Microsoft Defender Virüsten Koruma özellikleri _uç noktada algılama ve yanıtlama_ EDR sağlar.

### <a name="antivirus-detections"></a>Virüsten koruma algılamaları
Bu algılamalar açık [olan Microsoft Defender Virüsten Koruma kullanılabilir](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10). Bu algılamalar, Uç Nokta için Microsoft Defender'a ekli cihazlarda oluştuğunda, raporki grafikleri aydınlatan uyarıları da tetikler.

>[!NOTE]
>Analist raporu ayrıca, **izleme tehdidine** özgü bileşenlere veya davranışlara ek olarak çok çeşitli tehditleri tanımlayan genel algılamaları da listeler. Bu genel algılamalar grafiklere yansımaz.

### <a name="endpoint-detection-and-response-edr-alerts"></a>Uç nokta algılama ve yanıt (EDR) uyarıları
EDR için [Microsoft Defender'a ekli cihazlar için uyarı uyarısı yükseltildi](/windows/security/threat-protection/microsoft-defender-atp/onboard-configure). Bu uyarılar genellikle, Uç nokta algılayıcısı için Microsoft Defender tarafından toplanan güvenlik sinyallerine ve virüsten koruma, ağ koruması, müdahale koruması gibi güçlü sinyal kaynakları olarak diğer uç nokta özelliklerine uyar.

Virüsten koruma algılama listesi gibi, EDR uyarılarının bazıları da izleme tehdidiyle ilişkili olmayan şüpheli davranışlara genel olarak bayrak eklemeye yönelik tasarlanmıştır. Böyle durumlarda rapor, uyarıyı "genel" olarak açıkça tanımlayacak ve raporki grafikleri etkilemeyecek.

### <a name="email-related-detections-and-mitigations"></a>E-postayla ilgili algılamalar ve risk azaltmalar
Office 365 için Microsoft Defender'dan gelen e-postayla ilgili algılamalar ve risk azaltmalar, analist raporlarına, ayrıca Uç Nokta için Microsoft Defender'da bulunan uç nokta verilerine ek olarak yer alır. 

Engellenmiş e-posta deneme bilgileri, saldırı etkili bir şekilde teslimat öncesinde engellenmiş veya gereksiz posta klasörüne teslim edilene kadar analist raporunda ele alınan tehdidin hedefi olup olmadığı hakkında size öngörüler sağlar.

## <a name="find-subtle-threat-artifacts-using-advanced-hunting"></a>Gelişmiş avı kullanarak küçük tehdit yapıtlarını bulun
Algılamalar, izleme tehditlerini otomatik olarak tanımlamanıza ve durdurmanıza olanak tanısa da, birçok saldırı özelliği ek denetim gerektiren hafif izlemeler bırakır. Bazı saldırı etkinlikleri de normal olan davranışları sergilemektedir, bu nedenle bunları dinamik olarak algılamak işlem gürültüsüne, hatta hatalı pozitif sonuçlara neden olabilir.

[Gelişmiş av](advanced-hunting-overview.md) , Tehdit etkinliğinin hafif göstergelerini bulmayı basitleştiren, Kusto Sorgu Dili'ne dayalı bir sorgu arabirimi sağlar. Ayrıca bağlamsal bilgileri ortaya çıkararak göstergelerin bir tehditle bağlantılı olup olmadığını doğrulamanız için de olanak sağlar.

Analist raporlarında yer alan gelişmiş arama sorguları Microsoft analistleri tarafından yoklandı ve gelişmiş arama sorgusu [düzenleyicisinde çalıştırmaya hazır](https://security.microsoft.com/advanced-hunting). Gelecekteki eşleşmelerde uyarıları tetikleyen [özel algılama kuralları](custom-detection-rules.md) oluşturmak için sorguları da kullanabilirsiniz.


>[!NOTE]
> Tehdit analizi, Uç Nokta için [Microsoft Defender'da da kullanılabilir](/windows/security/threat-protection/microsoft-defender-atp/threat-analytics). Ancak, tehdit çözümlemesinde var olan Microsoft Defender for Office Uç Nokta için Microsoft Defender ile Microsoft 365 Defender tümleştirmesi olmaz.


## <a name="related-topics"></a>İlgili konular
- [Tehdit analizine genel bakış](threat-analytics.md)
- [Gelişmiş avla tehditlere karşı önceden bulma](advanced-hunting-overview.md) 
- [Özel algılama kuralları](custom-detection-rules.md)