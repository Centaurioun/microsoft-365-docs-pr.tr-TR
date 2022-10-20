---
title: Forward proxy’lerin arkasında oluşan bağlantı olaylarını araştırın
description: Uç Nokta için Microsoft Defender'da, ara sunucu yerine gerçek bir hedefi ortaya çıkararak ağ koruması aracılığıyla gelişmiş HTTP düzeyinde izlemeyi kullanmayı öğrenin.
keywords: proxy, ağ koruması, iletme ara sunucusu, ağ olayları, denetim, engelleme, etki alanı adları, etki alanı
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
- tier2
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: ea3c49702d90b45edf49ab196086eadde072bf33
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68636552"
---
# <a name="investigate-connection-events-that-occur-behind-forward-proxies"></a>Forward proxy’lerin arkasında oluşan bağlantı olaylarını araştırın

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigatemachines-abovefoldlink)

Uç Nokta için Defender, ağ yığınının farklı düzeylerinden ağ bağlantısı izlemeyi destekler. Zor bir durum, ağın İnternet'e ağ geçidi olarak ileriye doğru ara sunucu kullanmasıdır.

Proxy, hedef uç noktaymış gibi davranır. Bu gibi durumlarda, basit ağ bağlantısı izleyicileri doğru olan ancak araştırma değeri daha düşük olan proxy ile bağlantıları denetler.

Uç Nokta için Defender, ağ koruması aracılığıyla gelişmiş HTTP düzeyinde izlemeyi destekler. Açıldığında, gerçek hedef etki alanı adlarını kullanıma sunan yeni bir olay türü ortaya çıkar.

## <a name="use-network-protection-to-monitor-network-connection-behind-a-firewall"></a>Güvenlik duvarının arkasındaki ağ bağlantısını izlemek için ağ korumasını kullanma

Ağ korumasından kaynaklanan diğer ağ olaylarından dolayı ileriye doğru ara sunucu arkasındaki ağ bağlantısını izlemek mümkündür. Bunları bir cihaz zaman çizelgesinde görmek için ağ korumasını açın (denetim modunda en azından).

Ağ koruması aşağıdaki modlar kullanılarak denetlenebilir:

- **Engelle**: Kullanıcıların veya uygulamaların tehlikeli etki alanlarına bağlanması engellenir. Bu etkinliği Microsoft 365 Defender görebilirsiniz.
- **Denetim**: Kullanıcıların veya uygulamaların tehlikeli etki alanlarına bağlanması engellenmez. Ancak, bu etkinliği Microsoft 365 Defender görmeye devam edebilirsiniz.


Ağ korumasını kapatırsanız, kullanıcıların veya uygulamaların tehlikeli etki alanlarına bağlanması engellenmez. Microsoft 365 Defender'da herhangi bir ağ etkinliği görmezsiniz.

Yapılandırmazsanız, ağ engelleme varsayılan olarak kapatılır.

Daha fazla bilgi için bkz [. Ağ korumasını etkinleştirme](enable-network-protection.md).

## <a name="investigation-impact"></a>Araştırma etkisi

Ağ koruması açık olduğunda, gerçek hedef adres görünürken cihazın zaman çizelgesinde IP adresinin proxy'yi temsil ettiğini görürsünüz.

:::image type="content" source="images/atp-proxy-investigation.png" alt-text="Cihazın zaman çizelgesindeki ağ olayları" lightbox="images/atp-proxy-investigation.png":::

Ağ koruma katmanı tarafından tetiklenen diğer olaylar artık bir ara sunucu arkasında bile gerçek etki alanı adlarını ortaya sürebilmek için kullanılabilir.

Olayın bilgileri:

:::image type="content" source="images/atp-proxy-investigation-event.png" alt-text="Tek bir ağ olayının URL'leri" lightbox="images/atp-proxy-investigation-event.png":::

## <a name="hunt-for-connection-events-using-advanced-hunting"></a>Gelişmiş avcılığı kullanarak bağlantı olaylarını avlama

Tüm yeni bağlantı etkinlikleri, gelişmiş avcılık yoluyla da avlanabilirsiniz. Bu olaylar bağlantı olayları olduğundan, bunları eylem türünün altındaki DeviceNetworkEvents tablosunun `ConnecionSuccess` altında bulabilirsiniz.

Bu basit sorguyu kullanmak size tüm ilgili olayları gösterir:

```console
DeviceNetworkEvents
| where ActionType == "ConnectionSuccess"
| take 10
```

:::image type="content" source="images/atp-proxy-investigation-ah.png" alt-text="Gelişmiş tehdit avcılığı sorgusu" lightbox="images/atp-proxy-investigation-ah.png":::

Ayrıca, proxy'nin kendisiyle bağlantıyla ilgili olayları filtreleyebilirsiniz.

Ara sunucu bağlantılarını filtrelemek için aşağıdaki sorguyu kullanın:

```console
DeviceNetworkEvents
| where ActionType == "ConnectionSuccess" and RemoteIP != "ProxyIP"
| take 10
```

## <a name="related-topics"></a>İlgili konular

- [GP ile ağ koruması uygulama - ilke CSP](/windows/client-management/mdm/policy-csp-defender#defender-enablenetworkprotection)
