---
title: 'Microsoft Defender Tehdit Analizi (Defender TI): Altyapı Zincirleme'
description: Bu kavram makalesinde altyapı zinciri hakkında bilgi edinin ve Microsoft Defender Tehdit Analizi (Defender TI) kullanarak tehdit altyapısı analizi gerçekleştirmek için bu işlemi nasıl uygulayabileceğinizi öğrenin.
author: alexroland24
ms.author: aroland
manager: dolmont
ms.service: threat-intelligence
ms.topic: conceptual
ms.date: 08/02/2022
ms.custom: template-concept
ms.openlocfilehash: 2f2187b2b49e41bf9751be46fab771f66b601995
ms.sourcegitcommit: c29af68260ba8676083674b3c70209bff2c2e362
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/16/2022
ms.locfileid: "67737158"
---
# <a name="infrastructure-chaining"></a>Altyapı Zincirleme

Altyapı zinciri, araştırma oluşturmak için yüksek oranda bağlı veri kümeleri arasındaki ilişkilerden yararlanıyor. Bu işlem, tehdit altyapısı analizinin temelini oluşturur ve kuruluşların yeni bağlantıları ortaya çıkarmasına, benzer saldırı etkinliklerini gruplandırmasına ve olay yanıtı sırasında varsayımları doğrulamasına olanak tanır.

![Altyapı zincirleme](media/infrastructureChaining.png)

## <a name="prerequisites"></a>Önkoşullar

1. [Microsoft Defender Tehdit Analizi (Defender TI) veri kümelerine genel bakış makalesini](data-sets.md) gözden geçirin
2. [Microsoft Defender Tehdit Analizi (Defender TI) arama ve özetleme makalesini](searching-and-pivoting.md) gözden geçirin

## <a name="all-you-need-is-a-starting-point"></a>Tek ihtiyacınız olan bir başlangıç noktası...

Saldırı kampanyalarında pasif işletim sistemi parmak izi gibi karmaşık taktiklere basit coğrafi filtreleme gibi çok çeşitli gizleme teknikleri uygulandığını görüyoruz. Bu, kendi izlerinde belirli bir noktaya araştırmayı durdurabilir. Yukarıdaki ekran görüntüsünde altyapı zincirleme kavramı vurgulanır. Veri zenginleştirme özelliğimizle, bir IP adresine (muhtemelen C2) bağlanmaya çalışan bir kötü amaçlı yazılım parçasıyla başlayabiliriz. Bu IP adresi, etki alanı adı gibi ortak bir ada sahip bir SSL sertifikası barındırmış olabilir. Bu etki alanı, kodda benzersiz izleyici içeren bir sayfaya bağlanabilir. Örneğin NewRelicID veya başka bir yerde gözlemlediğimiz başka bir analiz kimliği. Ya da etki alanı tarihsel olarak araştırmamıza ışık talan eden başka bir altyapıya bağlanmış olabilir. Asıl önemli nokta, bağlam dışına alınan bir veri noktasının özellikle yararlı olmayabileceğidir, ancak diğer tüm teknik verilere doğal bağlantıyı gözlemlediğimizde, bir hikaye birleştirmeye başlayabiliriz.

## <a name="an-adversarys-outside-in-perspective"></a>Saldırganların dışarıdan bakış açısı

Bir saldırganın dışarıdan bakış açısı, güvenlik duvarınızın dışında çalışan sürekli olarak genişleyen web ve mobil iletişim durumunuzdan yararlanmalarını sağlar.

Gerçek bir kullanıcı olarak web ve mobil özelliklere yaklaşmak ve bunlarla etkileşime geçmek, Microsoft'un gezinme, tarama ve makine öğrenmesi teknolojisinin kullanıcı oturumu verilerini toplayarak, kimlik avı, kötü amaçlı yazılım, sahte uygulamalar, istenmeyen içerik ve etki alanı ihlalini büyük ölçekte algılayarak saldırganların kaçınma tekniklerini etkisiz hale getirilmesini sağlar. Bu, saldırganların altyapısıyla ilişkili [tehdit bilgileri](index.md), [sistem etiketleri](using-tags.md), [analist içgörüleri](analyst-insights.md) ve [itibar puanları](reputation-scoring.md) biçiminde eyleme dönüştürülebilir, olay tabanlı tehdit uyarıları ve iş akışları sunmaya yardımcı olur.

Daha fazla tehdit verisi kullanıma sunuldukça analistlerin veri kümelerini ve buna karşılık gelen tehditleri anlaması için daha fazla araç, eğitim ve çaba gerekir. Microsoft Defender Tehdit Analizi (Defender TI), birden çok veri kaynağına tek bir görünüm sağlayarak bu çabaları birleştirir.

## <a name="next-steps"></a>Sonraki adımlar
Daha fazla bilgi için bkz [. Öğretici: Tehdit bilgilerini ve altyapı zincirini toplama](gathering-threat-intelligence-and-infrastructure-chaining.md).
