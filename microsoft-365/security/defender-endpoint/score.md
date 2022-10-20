---
title: Puan yöntemleri ve özellikleri
description: Kuruluşunuzun maruz kalma puanını, cihaz güvenli puanını ve cihaz grubuna göre maruz kalma puanını alır
keywords: api'ler, graf api'leri, desteklenen API'ler, puan, maruz kalma puanı, cihaz güvenli puanı, cihaz grubuna göre maruz kalma puanı
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: siosulli
author: siosulli
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier3
ms.topic: conceptual
ms.subservice: mde
ms.custom: api
search.appverid: met150
ms.openlocfilehash: 4375b5b2d76ea9b3d94b8b372d7213fa8c4c7d2d
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68644361"
---
# <a name="score-resource-type"></a>Kaynak türünü puanla

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a>Yöntemler

Yöntem|Dönüş Türü|Açıklama
:---|:---|:---
[Hassaslık puanı al](get-exposure-score.md)|[Puan](score.md)|Kurumsal maruz kalma puanını alın.
[Cihaz güvenlik puanı al](get-device-secure-score.md)|[Puan](score.md)|Kuruluş cihazının güvenli puanını alın.
[Cihaz grubuna göre pozlama puanını listeleme](get-machine-group-exposure-score.md)|[Puan](score.md)|Cihaz grubuna göre puanları listeleyin.

> [!NOTE]
> Cihaz grubu oluşturma, Uç Nokta Için Defender Plan 1 ve Plan 2'de desteklenir.  

## <a name="properties"></a>Özellikler

Özellik|Tür|Açıklama
:---|:---|:---
Puan|Çift|Geçerli puan.
Saat|Datetime|Bu API için çağrının yapıldığı tarih ve saat.
RbacGroupName|Dize|Cihaz grubu adı.
RbacGroupId|Dize|Cihaz grubu kimliği.
