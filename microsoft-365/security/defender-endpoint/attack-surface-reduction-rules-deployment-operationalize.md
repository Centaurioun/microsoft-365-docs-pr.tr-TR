---
title: Saldırı yüzeyini azaltma (ASR) kurallarını kullanıma hazır hale getirme
description: Saldırı yüzeyi azaltma kuralları dağıtımınızı kullanıma hazır hale getirmek için rehberlik sağlar.
keywords: Saldırı yüzeyi azaltma (ASR) kuralları dağıtımı, Microsoft ASR, defender ASR kurallarını yönetme, ASR kurallarını izleme, ASR kuralları gelişmiş avcılık, ASR kuralları raporu, ASR kuralları hatalı pozitif sonuçları, ASR'yi yapılandırma, konak izinsiz girişi önleme sistemi, koruma kuralları, kötüye kullanım önleme kuralları, kötüye kullanım önleme kuralları, bulaşma önleme kuralları, Uç Nokta için Microsoft Defender, ASR kurallarını yapılandırma
search.product: eADQiWindows 10XVcnh
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.service: microsoft-365-security
ms.subservice: mde
ms.localizationpriority: medium
audience: ITPro
author: jweston-1
ms.author: v-jweston
ms.reviewer: oogunrinde, sugamar
manager: dansimp
ms.custom: asr
ms.topic: conceptual
ms.collection:
- m365-security
- m365solution-asr-rules
- highpri
- tier1
ms.date: 1/18/2022
search.appverid: met150
ms.openlocfilehash: 98aa168624b4093923ed6afa476e3385248ce3c2
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68624653"
---
# <a name="operationalize-attack-surface-reduction-asr-rules"></a>Saldırı yüzeyini azaltma (ASR) kurallarını kullanıma hazır hale getirme

Saldırı yüzeyi azaltma (ASR) kurallarını tam olarak dağıttıktan sonra, ASR ile ilgili etkinlikleri izlemek ve yanıtlamak için gerekli işlemlerin olması çok önemlidir. Etkinlikler şunlardır: 

## <a name="managing-asr-rules-false-positives"></a>ASR kurallarını yönetme hatalı pozitifler

Herhangi bir tehdit koruması çözümünde hatalı pozitifler/negatifler oluşabilir. Hatalı pozitifler, varlığın (dosya veya işlem gibi) algılandığı ve kötü amaçlı olarak tanımlandığı durumlardır, ancak varlık aslında bir tehdit değildir. Buna karşılık, hatalı negatif, tehdit olarak algılanan ancak kötü amaçlı olan bir varlıktır. Hatalı pozitifler ve hatalı negatifler hakkında daha fazla bilgi için bkz. [Uç Nokta için Microsoft Defender](defender-endpoint-false-positives-negatives.md)

## <a name="keeping-up-with-asr-rules-reports"></a>ASR kuralları raporlarını takip etme

Raporların tutarlı ve düzenli olarak gözden geçirilmesi, ASR kuralları dağıtımınızı korumanın ve yeni ortaya çıkan tehditleri yakından izlemenin önemli bir yönüdür. Kuruluşunuzun ASR kuralları tarafından bildirilen olaylarla güncel kalmasını sağlayacak bir tempoda ASR kuralları olaylarının zamanlanmış gözden geçirmeleri olmalıdır. Kuruluşunuzun boyutuna bağlı olarak incelemeler günlük, saatlik veya sürekli izleme olabilir.

## <a name="asr-rules-advanced-hunting"></a>ASR kuralları Gelişmiş Avcılık

[Microsoft 365 Defender](https://security.microsoft.com) en güçlü özelliklerinden biri gelişmiş avcılıktır. Gelişmiş avcılık hakkında bilginiz yoksa bkz. Gelişmiş [avcılık ile tehditleri proaktif olarak avlama](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview).

> :::image type="content" source="images/asr-defender365-advanced-hunting2.png" alt-text="Microsoft 365 Defender portalındaki Gelişmiş Avcılık sayfası. Uç Nokta için Microsoft Defender (MDE) ASR kuralları, ASR kuralları gelişmiş avcılık, asr kuralları raporları, asr kuralları hatalı pozitifler," lightbox="images/asr-defender365-advanced-hunting2.png":::

Gelişmiş avcılık, ATP Uç Nokta Algılama ve Yanıt (EDR) Microsoft Defender tüm makinelerinizden topladığı yakalanan (ham) verilerin 30 gününe kadar araştırmanıza olanak tanıyan sorgu tabanlı (Kusto Sorgu Dili) bir tehdit avcılığı aracıdır. Gelişmiş avcılık sayesinde, ilginç göstergeleri ve varlıkları bulmak için olayları proaktif olarak inceleyebilirsiniz. Verilere esnek erişim, hem bilinen hem de olası tehditler için kısıtlanmamış avlanmayı kolaylaştırır.

Gelişmiş avcılık sayesinde ASR kural bilgilerini ayıklamak, raporlar oluşturmak ve belirli bir ASR kural denetimi veya engelleme olayının bağlamı hakkında ayrıntılı bilgi almak mümkündür.

 ASR kuralları olaylarını, Microsoft 365 Defender portalının gelişmiş avcılık bölümündeki DeviceEvents tablosundan sorgulayabilirsiniz. Örneğin, aşağıdaki gibi basit bir sorgu, son 30 gün içinde veri kaynağı olarak ASR kuralları olan tüm olayları raporlayabilir ve bunları ActionType sayısına göre özetler ve bu durumda ASR kuralının gerçek kod adı olur.

Ilerleyen tehdit avcılığı portalında gösterilen ASR olayları saatte bir görülen benzersiz süreçlere kısıtlanıyor. ASR olayının saati, olayın bu saat içinde ilk kez görülmesidir.

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/asr-defender365-advanced-hunting3.png" alt-text="Microsoft 365 Defender portalındaki Gelişmiş tehdit avcılığı sorgusu komut satırı" lightbox="images/asr-defender365-advanced-hunting3.png":::

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/asr-defender365-advanced-hunting4.png" alt-text="Gelişmiş tehdit avcılığı sorgusu, Microsoft 365 Defender portalında sonuçlanıyor" lightbox="images/asr-defender365-advanced-hunting4.png":::

Yukarıdakiler AsrLsassCredentialTheft için 187 olayın kaydedildiğini göstermektedir:

- Engellenenler için 102
- Denetim için 85
- AsrOfficeChildProcess için 2 olay (Denetlenen için 1 ve Blok için 1)
- AsrPsexecWmiChildProcessAudited için 8 olay

AsrOfficeChildProcess kuralına odaklanmak ve ilgili gerçek dosya ve işlemlerin ayrıntılarını almak istiyorsanız, ActionType filtresini değiştirin ve özet satırını istenen alanların bir projeksiyonuyla değiştirin (bu durumda Bunlar DeviceName, FileName, FolderPath vb.).

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/asr-defender365-advanced-hunting4b.png" alt-text="Microsoft 365 Defender portalında Gelişmiş tehdit avcılığı sorgusu odaklı örnek" lightbox="images/asr-defender365-advanced-hunting4b.png":::

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/asr-defender365-advanced-hunting5b.png" alt-text="Gelişmiş tehdit avcılığı sorgusuna odaklanan sonuçlar Microsoft 365 Defender portalında" lightbox="images/asr-defender365-advanced-hunting5b.png":::

Gelişmiş avcılık özelliğinin gerçek avantajı, sorguları istediğiniz gibi şekillendirebilmenizdir. Sorgunuzu şekillendirerek, tek bir makinede bir şeyi saptamak veya ortamınızın tamamından içgörüler ayıklamak istemeniz fark etmeksizin neler olduğunu tam olarak görebilirsiniz.

Avlanma seçenekleri hakkında daha fazla bilgi için bkz. [Saldırı yüzeyini azaltma kurallarını kaldırma - Bölüm 3](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/demystifying-attack-surface-reduction-rules-part-3/ba-p/1360968).

## <a name="topics-in-this-deployment-collection"></a>Bu dağıtım koleksiyonundaki konular

[Saldırı yüzeyini azaltma (ASR) kuralları dağıtımına genel bakış](attack-surface-reduction-rules-deployment.md)

[Saldırı yüzeyini azaltma (ASR) kuralları dağıtım planı](attack-surface-reduction-rules-deployment-plan.md)

[Saldırı yüzeyini azaltma (ASR) kuralları testi](attack-surface-reduction-rules-deployment-test.md)

[Saldırı yüzeyini azaltma (ASR) kurallarını etkinleştirme](attack-surface-reduction-rules-deployment-implement.md)

[Saldırı yüzeyini azaltma (ASR) kuralları başvurusu](attack-surface-reduction-rules-reference.md)
