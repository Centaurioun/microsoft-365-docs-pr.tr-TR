---
title: Microsoft Defender Tehdit Analizi (Defender TI) Analist İçgörüleri
description: Bu genel bakış makalesinde Microsoft Defender Tehdit Analizi (Defender TI) analist içgörüleri özelliği hakkında bilgi edinin.
author: alexroland24
ms.author: aroland
manager: dolmont
ms.service: threat-intelligence
ms.topic: overview
ms.date: 08/02/2022
ms.custom: template-overview
ms.openlocfilehash: c9c4ca37ba75694d905c8f737a6fceb93e30a757
ms.sourcegitcommit: c29af68260ba8676083674b3c70209bff2c2e362
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/16/2022
ms.locfileid: "67735590"
---
# <a name="analyst-insights"></a>Çözümleyici içgörüleri

Microsoft Defender Tehdit Analizi'de (Defender TI) Analist İçgörüleri bölümü, bir araştırmanın sonraki adımını belirlemeye yardımcı olabilecek yapıt hakkında hızlı içgörüler sağlar. Bu bölümde yapıt için geçerli olan içgörülerin yanı sıra ek görünürlük için geçerli olmayan içgörüler listelenecektir. Aşağıdaki örnekte, IP Adresinin yönlendirilebilir olduğunu, bir web sunucusu barındırdığını ve son beş gün içinde açık bir bağlantı noktasına sahip olduğunu hızla belirleyebiliriz. Ayrıca, sistem tetiklenmeyen kurallar görüntüler ve bu da bir araştırma başlatırken aynı derecede yararlı olabilir.

![Analyst Insights Edge Ekran Görüntüsü](media/analystInsightsEdgeScreenshot.png)

## <a name="analyst-insight-types-and-questions-they-can-address"></a>Çözümleyici içgörü türleri ve ilgilenebilecekleri sorular

| Analist içgörü türleri                      | Yanıtlayabilecekleri sorular                                                                                                |
|--------------------------------------------|---------------------------------------------------------------------------------------------------------------------------|
| Engellenenler listesi                                | Etki alanı, ana bilgisayar veya IP adresi ne zaman engellendi?                                                                  |
|                                            | Defender TI etki alanını, konağı veya IP'yi kaç kez engelledi?                                                            |
| Kayıtlı & Güncelleştirildi                       | Etki alanı kaç gün, ay, yıl önce kaydedildi?                                                               |
|                                            | WHOIS Kaydı etki alanı ne zaman güncelleştirildi?                                                                                 |
| Alt etki alanı IP sayısı                         | Etki alanının alt etki alanlarıyla kaç farklı IP ilişkilendirilir?                                                  |
| Yeni alt etki alanı gözlemleri                 | Microsoft söz konusu etki alanı için en son ne zaman yeni bir alt etki alanı gözlemledi?                                     |
| Kayıtlı & Çözümleme | Sorgulanan etki alanı var mı?                                                                                            |
|                                            | Etki alanı bir IP adresine çözümlensin mi?                                                                                 |
| WHOIS kaydını paylaşan Etki Alanı Sayısı | Diğer hangi etki alanları aynı WHOIS kaydını paylaşır?                                                                           |
| Ad Sunucusu'nu paylaşan etki alanı sayısı  | Başka hangi etki alanları aynı ad sunucusu kaydını paylaşır?                                                                     |
| RiskIQ tarafından gezinildi                          | Bu konak veya etki alanı en son ne zaman Microsoft tarafından gezinildi?                                                                   |
| Uluslararası Etki Alanı                       | Etki alanı uluslararası bir etki alanı adı (IDN) için sorgulandı mı?                                                             |
| Üçüncü Taraf Tarafından Engellenenler Listesi                 | Bu gösterge üçüncü taraf tarafından engellenmiş mi?                                                                           |
| Tor Çıkış Düğümü Durumu                       | Soğan Yönlendirici Ağı (Tor) ile ilişkili sorularda IP adresi var mı?                                            |
| Açık Bağlantı Noktaları Algılandı                        | Microsoft bu IP adresini en son ne zaman taradı?                                                                        |
| Proxy Durumu                               | Bu göstergenin proxy durumu nedir?                                                                               |
| Konak Son Gözlemlenen                         | Söz konusu IP adresi İnternet'e erişilebilir mi?                                                                        |
| Web Sunucusu barındırıyor                         | IP adresinin, uygun web sunucusu için adını çözümlemek için kaynaklarını kullanan bir DNS sunucusu var mı? |

## <a name="next-steps"></a>Sonraki adımlar

Daha fazla bilgi için bkz.:

- [İtibar puanlaması](reputation-scoring.md)
- [Etiketleri kullanma](using-tags.md)