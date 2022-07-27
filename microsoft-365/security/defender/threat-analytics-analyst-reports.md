---
title: Microsoft 365 Defender'de tehdit analizinin analist raporu bölümünü anlama
ms.reviewer: ''
description: Her tehdit analizi raporunun analist raporu bölümü hakkında bilgi edinin. Tehditler, risk azaltmalar, algılamalar, gelişmiş tehdit avcılığı sorguları ve daha fazlası hakkında nasıl bilgi sağladığını anlayın.
keywords: analist raporu, tehdit analizi, algılamalar, gelişmiş tehdit avcılığı sorguları, azaltmalar,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.openlocfilehash: 9f699be27f3ad0bee522a3e9d0f5550428aacc91
ms.sourcegitcommit: e8dd5cd434d17af7096d28d467a2b3b021cbb233
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2022
ms.locfileid: "67051502"
---
# <a name="understand-the-analyst-report-in-threat-analytics-in-microsoft-365-defender"></a>Microsoft 365 Defender'de tehdit analizinde analist raporunu anlama

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**

- Microsoft 365 Defender

[!INCLUDE [Prerelease](../includes/prerelease.md)]

Her [tehdit analizi raporu](threat-analytics.md) dinamik bölümler ve _analist raporu_ adlı kapsamlı bir yazılı bölüm içerir. Bu bölüme erişmek için izlenen tehditle ilgili raporu açın ve **Analist raporu** sekmesini seçin.

:::image type="content" source="../../media/threat-analytics/ta_analystreport_mtp.png" alt-text="Tehdit analizi raporunun analist raporu bölümü" lightbox="../../media/threat-analytics/ta_analystreport_mtp.png":::

_Tehdit analizi raporunun analist raporu bölümü_

## <a name="scan-the-analyst-report"></a>Analist raporunu tarama

Analist raporunun her bölümü eyleme dönüştürülebilir bilgiler sağlamak için tasarlanmıştır. Raporlar farklılık gösterse de, çoğu rapor aşağıdaki tabloda açıklanan bölümleri içerir.

| Rapor bölümü | Açıklama |
|--|--|
| Yönetici özeti | İlk görüldüğü zaman, motivasyonları, dikkate değer olaylar, ana hedefler ve farklı araçlar ve teknikler de dahil olmak üzere, tehdide genel bakış. Bu bilgileri, sektörünüz, coğrafi konumunuz ve ağınız bağlamında tehdidi nasıl önceliklendirebileceğinizi daha fazla değerlendirmek için kullanabilirsiniz. |
| Analysis | Bir saldırının ayrıntıları ve saldırganların yeni bir teknik veya saldırı yüzeyini nasıl kullanabileceği dahil olmak üzere tehditler hakkında teknik bilgiler |
| GÖZLEMLENEN MITRE ATT&CK teknikleri | Gözlemlenen teknikler [MITRE ATT&CK saldırı çerçevesiyle nasıl eşlenir?](https://attack.mitre.org/) |
| [Azaltıcı etken](#apply-additional-mitigations) | Tehdidi durdurabilecek veya tehdidin etkisini azaltmaya yardımcı olabilecek öneriler. Bu bölüm, tehdit analizi raporunun bir parçası olarak dinamik olarak izlenmemiş risk azaltmaları da içerir. |
| [Algılama ayrıntıları](#understand-how-each-threat-can-be-detected) | Microsoft güvenlik çözümleri tarafından sağlanan ve tehditle ilişkili etkinlikleri veya bileşenleri ortaya çıkarabilen belirli ve genel algılamalar. |
| [Gelişmiş avcılık örneği](#find-subtle-threat-artifacts-using-advanced-hunting) | Olası tehdit etkinliğini proaktif olarak tanımlamak için [gelişmiş tehdit avcılığı sorguları](advanced-hunting-overview.md). Sorguların çoğu, özellikle kötü amaçlı olabilecek bileşenleri veya kötü amaçlı olduğu dinamik olarak değerlendirilemeyen davranışları bulmak için ek algılamalar için sağlanır. |
| Başvurular | Raporun oluşturulması sırasında analistler tarafından başvuruda bulunan Microsoft ve üçüncü taraf yayınları. Tehdit analizi içeriği, Microsoft araştırmacıları tarafından doğrulanan verileri temel alır. Genel kullanıma açık, üçüncü taraf kaynaklardan gelen bilgiler bu şekilde net bir şekilde tanımlanır. |
| Günlüğü Değiştir | Raporun yayımlandığı zaman ve raporda önemli değişiklikler yapıldığında. |

## <a name="apply-additional-mitigations"></a>Ek risk azaltmaları uygulama

Tehdit analizi [, güvenlik güncelleştirmelerinin ve güvenli yapılandırmaların durumunu](threat-analytics.md#exposure-and-mitigations-review-list-of-mitigations-and-the-status-of-your-devices) dinamik olarak izler. Bu bilgiler, **Pozlama & azaltmalar** sekmesinde grafikler ve tablolar olarak kullanılabilir.

Analist raporu, izlenen bu risk azaltmalara ek olarak dinamik olarak _izlenmeyen_ risk azaltmaları da ele alır. Aşağıda dinamik olarak izlenmemiş bazı önemli risk azaltma örnekleri verilmiştir:

- _.lnk_ eklerine veya diğer şüpheli dosya türlerine sahip e-postaları engelleme
- Yerel yönetici parolalarını rastgele belirleme
- Son kullanıcıları kimlik avı e-postası ve diğer tehdit vektörleri hakkında eğitme
- Belirli [saldırı yüzeyi azaltma kurallarını](/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction) açma

Güvenlik duruşunuzu bir tehdide karşı değerlendirmek için **Pozlama & risk azaltmalar** sekmesini kullanabilirsiniz ancak bu öneriler güvenlik duruşunuzu iyileştirmeye yönelik ek adımlar atmanıza olanak sağlar. Analist raporundaki tüm risk azaltma kılavuzlarını dikkatle okuyun ve mümkün olduğunda uygulayın.

## <a name="understand-how-each-threat-can-be-detected"></a>Her tehdidin nasıl algılanabilir olduğunu anlama

Analist raporu ayrıca Microsoft Defender Virüsten Koruma ile _uç nokta algılama ve yanıt_ (EDR) özelliklerinden algılamalar sağlar.

### <a name="antivirus-detections"></a>Virüsten koruma algılamaları

Bu algılamalar [, Microsoft Defender Virüsten Koruma'nın](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) açık olduğu cihazlarda kullanılabilir. Bu algılamalar, Uç Nokta için Microsoft Defender eklenen cihazlarda gerçekleştiğinde, rapordaki grafikleri aydınlatan uyarılar da tetikler.

>[!NOTE]
>Analist raporu, izlenen tehdide özgü bileşenlere veya davranışlara ek olarak çok çeşitli tehditleri belirleyebilen **genel algılamaları** da listeler. Bu genel algılamalar grafiklere yansıtılamaz.

### <a name="endpoint-detection-and-response-edr-alerts"></a>Uç nokta algılama ve yanıt (EDR) uyarıları

[Uç Nokta için Microsoft Defender eklenen cihazlar](/windows/security/threat-protection/microsoft-defender-atp/onboard-configure) için EDR uyarıları oluşturulur. Bu uyarılar genellikle Uç Nokta için Microsoft Defender algılayıcısı tarafından toplanan güvenlik sinyallerini ve güçlü sinyal kaynakları olarak görev yapan virüsten koruma, ağ koruması, kurcalama koruması gibi diğer uç nokta özelliklerini kullanır.

Virüsten koruma algılamaları listesinde olduğu gibi, bazı EDR uyarıları da izlenen tehditle ilişkilendirilmeyebilecek şüpheli davranışlara genel olarak bayrak eklemek için tasarlanmıştır. Bu gibi durumlarda rapor, uyarıyı açıkça "genel" olarak tanımlar ve rapordaki grafiklerin hiçbirini etkilemez.

### <a name="email-related-detections-and-mitigations"></a>Email ile ilgili algılamalar ve risk azaltmalar

Office 365 için Microsoft Defender Email ilgili algılamalar ve risk azaltmaları, Uç Nokta için Microsoft Defender'de zaten mevcut olan uç nokta verilerine ek olarak analist raporlarına da eklenir.

Engellenen e-posta girişimi bilgileri, saldırı teslim edilmeden önce etkin bir şekilde engellenmiş veya gereksiz posta klasörüne teslim edilmiş olsa bile kuruluşunuzun analist raporunda ele alınan tehdidin hedefi olup olmadığına ilişkin içgörüler sağlar.

## <a name="find-subtle-threat-artifacts-using-advanced-hunting"></a>Gelişmiş tehdit avcılığı kullanarak küçük tehdit yapıtlarını bulma

Algılamalar izlenen tehdidi otomatik olarak tanımlamanıza ve durdurmanıza olanak sağlarken, birçok saldırı etkinliği ek inceleme gerektiren ince izler bırakır. Bazı saldırı etkinlikleri de normal olabilecek davranışlar sergiler, bu nedenle bunları dinamik olarak algılamak işlemsel kirlilik ve hatta hatalı pozitif sonuçlara neden olabilir.

[Gelişmiş avcılık](advanced-hunting-overview.md), tehdit etkinliğinin ince göstergelerini bulma işlemini basitleştiren Kusto Sorgu Dili dayalı bir sorgu arabirimi sağlar. Ayrıca bağlamsal bilgileri ortaya çıkmanızı ve göstergelerin bir tehdide bağlı olup olmadığını doğrulamanızı sağlar.

Analist raporlarındaki gelişmiş tehdit avcılığı sorguları Microsoft analistleri tarafından izlendi ve [gelişmiş tehdit avcılığı sorgu düzenleyicisinde](https://security.microsoft.com/advanced-hunting) çalıştırmaya hazır. Gelecekteki eşleşmeler için uyarıları tetikleyen [özel algılama kuralları](custom-detection-rules.md) oluşturmak için sorguları da kullanabilirsiniz.

>[!NOTE]
> Tehdit analizi [Uç Nokta için Microsoft Defender'de](/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) de kullanılabilir. Ancak, Office için Microsoft Defender ile Uç Nokta için Microsoft Defender arasında veri tümleştirmesine sahip değildir.

## <a name="related-topics"></a>İlgili konular

- [Tehdit analizine genel bakış](threat-analytics.md)
- [Gelişmiş avcılık ile tehditleri proaktif olarak bulma](advanced-hunting-overview.md)
- [Özel algılama kuralları](custom-detection-rules.md)
