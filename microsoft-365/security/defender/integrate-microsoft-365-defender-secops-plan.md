---
title: Adım 1. Microsoft 365 Defender işlemlerin hazır olma durumunu planlama
description: Microsoft 365 Defender güvenlik işlemlerinizle tümleştirirken Microsoft 365 Defender işlemlerin hazır olma durumunu planlamanın temelleri.
keywords: olaylar, uyarılar, araştırma, bağıntı, saldırı, cihazlar, kullanıcılar, kimlikler, kimlik, posta kutusu, e-posta, 365, Microsoft, m365, olay yanıtı, siber saldırı, secops, güvenlik işlemleri, soc
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
- M365-security-compliance
- m365solution-m365dsecops
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: e4cae3512e9f4d856dd97f04f3678ac113d0ecb6
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/31/2022
ms.locfileid: "67483156"
---
# <a name="step-1-plan-for-microsoft-365-defender-operations-readiness"></a>Adım 1. Microsoft 365 Defender işlemlerin hazır olma durumunu planlama

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- Microsoft 365 Defender

Güvenlik operasyonlarınızın geçerli vadesi ne olursa olsun, Güvenlik İşlemleri Merkezi (SOC) ile uyumlu olmanız önemlidir. Her kuruluşa uyan tek bir model olmasa da, diğerlerinden daha yaygın olan bazı yönler vardır.

Aşağıdaki bölümlerde SOC'nin temel işlevleri açıklanmaktadır.

## <a name="provide-situational-awareness-of-modern-threats"></a>Modern tehditler konusunda durumsal farkındalık sağlama

Bir SOC ekibi, karşı önlemler ve yanıtlar oluşturmak üzere kuruluşla birlikte çalışabilmeleri için yeni ve gelen tehditlere hazırlanır ve bu tehditleri avlar. SOC ekibinizin modern saldırı yöntemleri ve teknikleri konusunda yüksek düzeyde eğitilmiş ve tehdit aktörlerini anlayan personeli olmalıdır. [Siber Sonlandırma Zinciri](https://www.microsoft.com/security/blog/2016/11/28/disrupting-the-kill-chain/) veya [MITRE ATT&CK çerçevesi](https://attack.mitre.org/) gibi paylaşılan tehdit bilgileri ve çerçeveler, tehdit analistleri ve tehdit avcıları personelinizi güçlendirebilir.

## <a name="provide-first-second-and-potentially-third-level-responses-to-cyber-incidents-and-events"></a>Siber olaylara ve olaylara birinci, ikinci ve potansiyel olarak üçüncü düzey yanıtlar sağlayın

SOC, güvenlik olaylarına ve olaylarına karşı savunmanın ön hattıdır. Bir olay, tehdit, saldırı, ilke ihlali veya denetim bulma işlemi bir uyarıyı veya eylem çağrısını tetiklediğinde, SOC ekibi bu uyarıyı önceliklendirmek ve içermek ya da araştırma için ilerletmek için bir değerlendirme yapar. Bu nedenle, SOC ilk satır yanıtlayıcıları güvenlik olayları ve göstergeleri hakkında geniş bir teknik bilgiye sahip olmalıdır.

## <a name="centralize-monitoring-and-logging-of-your-organizations-security-sources"></a>Kuruluşunuzun güvenlik kaynaklarının izlenmesini ve günlüğe kaydedilmesini merkezileştirme

SOC ekibinin temel işlevi genellikle güvenlik duvarları, izinsiz giriş önleme sistemleri, veri kaybı önleme sistemleri, güvenlik açığı yönetim sistemleri ve kimlik sistemleri gibi tüm güvenlik cihazlarının doğru çalıştığından ve izlendiğinden emin olmaktır. SOC ekipleri, güvenlik bilgilerinin analizinin merkezi ve güvenli olduğundan emin olmak için kimlik, DevOps, bulut, uygulama, veri bilimi ve diğer iş ekipleri gibi daha geniş ağ işlemleriyle çalışacaktır. Ayrıca SOC ekibi, verilerin günlüklerini ayrıştırma ve normalleştirmeyi de içerebilecek, kullanılabilir ve okunabilir biçimlerde tutmakla sorumludur.

## <a name="establish-red-blue-and-purple-team-operational-readiness"></a>Kırmızı, Mavi ve Mor takım işletime hazır olma durumunu belirleme

Her SOC ekibi, bir siber olaya yanıt verirken hazırlığını test etmelidir. Test, BT, güvenlik ve iş düzeyindeki çeşitli kişilerle tablo üstü ve uygulama çalıştırmaları gibi eğitim alıştırmaları aracılığıyla yapılabilir. Bireysel eğitim alıştırma ekipleri, temsili roller temelinde oluşturulur ve bir savunmacı (Mavi Takım), bir saldırganın (Kırmızı Takım) rolünü oynar veya alıştırma sırasında ortaya çıkan güçlü ve zayıflıklar (Mor Takım) aracılığıyla hem Mavi hem de Kırmızı takımların yöntemlerini ve tekniklerini geliştirmek isteyen gözlemciler olarak görev alır.

## <a name="next-step"></a>Sonraki adım

[2. Adım. Sıfır Güven Framework kullanarak SOC tümleştirme hazırlığı değerlendirmesi gerçekleştirme](integrate-microsoft-365-defender-secops-readiness.md)
