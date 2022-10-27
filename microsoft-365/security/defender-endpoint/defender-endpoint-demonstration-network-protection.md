---
title: ağ koruması tanıtımlarını Uç Nokta için Microsoft Defender
description: Ağ korumasının, çalışanların İnternet'te kimlik avı dolandırıcılığı, açıklardan yararlanma ve diğer kötü amaçlı içeriğe ev sahipliği yapabilen tehlikeli etki alanlarına erişmek için herhangi bir uygulamayı kullanmasını nasıl önlediğini gösterir.
keywords: ağ koruması, kimlik avı dolandırıcılığına karşı koruma, açıklardan yararlanmaya karşı koruma, kötü amaçlı içeriğe karşı koruma, tanıtım
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.mktglfcycl: evaluation
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier2
- demo
ms.topic: article
ms.subservice: mde
ms.date: 10/21/2022
ms.openlocfilehash: 41a1a023fbfdc71ceec060dda84349ff6776175d
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2022
ms.locfileid: "68732767"
---
# <a name="network-protection-demonstrations"></a>Ağ koruma tanıtımları

Ağ Koruması, cihazlarınızın saldırı yüzeyini İnternet tabanlı olaylardan azaltmaya yardımcı olur. Çalışanların, İnternet'te kimlik avı dolandırıcılığı, açıklardan yararlanma ve diğer kötü amaçlı içeriğe ev sahipliği yapabilen tehlikeli etki alanlarına erişmek için herhangi bir uygulama kullanmasını engeller.

## <a name="scenario-requirements-and-setup"></a>Senaryo gereksinimleri ve kurulumu

- Windows 10 1709 derleme 16273, Windows 11
- Microsoft Defender Virüsten Koruma

## <a name="powershell-command"></a>PowerShell komutu

```powershell
Set-MpPreference -EnableNetworkProtection Enabled
```

## <a name="rule-states"></a>Kural durumları

|Durum | Mod| Sayısal değer |
|:---|:---|:---|
| Devre dışı | = Kapalı | 0 |
| Etkin | = Blok modu | 1 |
| Denetim | = Denetim modu | 2 |

## <a name="verify-configuration"></a>Yapılandırmayı doğrulama

```powershell
Get-MpPreference
```

## <a name="scenario"></a>Senaryo

1. PowerShell komutunu kullanarak Ağ Koruması'nı açın:

   ```powershell
   Set-MpPreference -EnableNetworkProtection Enabled
   ```

2. Seçtiğiniz tarayıcıyı (Microsoft Edge*'i değil) kullanarak [Ağ Koruması web sitesi testine](https://smartscreentestratings2.net/) gidin. Microsoft Edge'de bu güvenlik açığından (SmartScreen) korunmak için başka güvenlik önlemleri vardır.

## <a name="expected-results"></a>Beklenen sonuçlar

Web sitesine gezinti engellenmelidir ve **Bağlantı engellendi** bildirimi görmeniz gerekir.

## <a name="clean-up"></a>Temizleme

```powershell
Set-MpPreference -EnableNetworkProtection Disabled
```

## <a name="see-also"></a>Ayrıca bkz.

[Ağ Koruması](network-protection.md)

[Uç Nokta için Microsoft Defender - tanıtım senaryoları](defender-endpoint-demonstrations.md)
