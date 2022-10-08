---
title: İş ortağı fırsatlarını ve senaryolarını Uç Nokta için Microsoft Defender
ms.reviewer: ''
description: Uç Nokta için Microsoft Defender ile uzantılar ve tümleştirmeler oluşturmak için mevcut güvenlik tekliflerini açık çerçevenin ve zengin API'lerin üzerine nasıl genişletebileceğinizi öğrenin
keywords: API, iş ortağı, genişletme, açık çerçeve, API'ler, uzantılar, tümleştirmeler, algılama, yönetim, yanıt, güvenlik açıkları, zeka
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier3
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 1b7b36848a61fce8fe702855cbce4f9cf815fd55
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2022
ms.locfileid: "68221862"
---
# <a name="microsoft-defender-for-endpoint-partner-opportunities-and-scenarios"></a>İş ortağı fırsatlarını ve senaryolarını Uç Nokta için Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)


İş ortakları, uç nokta için Defender ile uzantılar ve tümleştirmeler oluşturmak için mevcut güvenlik tekliflerini açık çerçevenin ve zengin ve eksiksiz API'lerin üzerine kolayca genişletebilir. 

API'ler algılama, yönetim, yanıt, güvenlik açıkları ve akıllı kullanım örnekleri gibi işlevsel alanlara yayılmaktadır. Kullanım örneğine ve gereksinime bağlı olarak, iş ortakları Uç Nokta için Defender'dan veri akışı yapabilir veya sorgulayabilir. 


## <a name="scenario-1-external-alert-correlation-and-automated-investigation-and-remediation"></a>Senaryo 1: Dış uyarı bağıntısı ve Otomatik araştırma ve düzeltme
Uç Nokta için Defender, olay yanıtlarını büyük ölçekte yönlendirmek için benzersiz otomatik araştırma ve düzeltme özellikleri sunar. 

Otomatik araştırma ve yanıt özelliğinin ağ güvenlik ürünleri veya diğer uç nokta güvenlik ürünleri gibi diğer çözümlerle tümleştirilmesi, uyarıların ele alınmasına yardımcı olur. Tümleştirme ayrıca ağ ve cihaz sinyali bağıntısını çevreleyen karmaşıklıkları en aza indirerek cihazlardaki araştırma ve tehdit düzeltme eylemlerini etkili bir şekilde akışa alır.

Uç Nokta için Defender aşağıdaki formlarda bu senaryo için destek ekler:

- Dış uyarılar Uç Nokta için Defender'a gönderilebilir ve Uç Nokta için Defender'dan ek cihaz tabanlı uyarılar ile yan yana sunulabilir. Bu görünüm, uyarının tam bağlamını sağlar. Gerçek süreç ve saldırının tam hikayesi.

- Bir uyarı oluşturulduktan sonra sinyal, kuruluştaki tüm Uç Nokta için Defender korumalı uç noktaları arasında paylaşılır. Uç Nokta için Defender, uyarıyı ele almak için anında otomatik veya operatör destekli yanıt alır.

## <a name="scenario-2-security-orchestration-and-automation-response-soar-integration"></a>Senaryo 2: Güvenlik düzenleme ve otomasyon yanıtı (SOAR) tümleştirmesi
Düzenleme çözümleri playbook'lar oluşturmanıza ve Uç Nokta için Defender API'lerinin cihaz verilerini sorgulama, cihaz yalıtımını tetikleme, engelleme/izin verme, uyarıyı ve diğer sorunları çözme gibi yanıtları düzenlemek için kullanıma verdiği zengin veri modelini ve eylemleri tümleştirmeye yardımcı olabilir.

## <a name="scenario-3-indicators-matching"></a>Senaryo 3: Gösterge eşleştirme 
Risk (ICS) eşleştirmesinin göstergesi, her uç nokta koruma çözümünde önemli bir özelliktir. Bu özellik Uç Nokta için Defender'da kullanılabilir ve varlıkların önlenmesi, algılanması ve dışlanması için göstergelerin listesini ayarlama olanağı sağlar. Eylemin ne zaman uygulanacağının yanı sıra gerçekleştirilecek eylemin süresini de tanımlayabilirsiniz.

Yukarıdaki senaryolar, platformun genişletilebilirliğine örnek olarak hizmet eder. Örneklerle sınırlı değildir ve diğer senaryoları keşfetmek ve keşfetmek için açık çerçeveden yararlanmanızı kesinlikle öneririz.

Çözümünüzü Uç Nokta için Defender'da tümleştirmek için [Uç Nokta için Microsoft Defender iş ortağı olma'daki](get-started-partner-integration.md) adımları izleyin.

## <a name="related-topic"></a>İlgili konu
- [Yönetim ve API'lere genel bakış](management-apis.md)
