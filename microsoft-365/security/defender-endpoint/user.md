---
title: Kullanıcı kaynak türü
description: Kullanıcılarla ilgili son Uç Nokta için Microsoft Defender uyarılarını alın.
keywords: api'ler, graf api'leri, desteklenen API'ler, alma, uyarılar, son kullanılanlar
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.subservice: mde
ms.custom: api
search.appverid: met150
ms.openlocfilehash: 9b0c452ff63196498b41764f8b870cfafc441dff
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67684223"
---
# <a name="user-resource-type"></a>Kullanıcı kaynak türü

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

Yöntem|Dönüş Türü|Açıklama
---|---|---
[Kullanıcıyla ilgili uyarıları listeleme](get-user-related-alerts.md)|[uyarı](alerts.md) koleksiyonu|Bir [kullanıcıyla](user.md) ilişkili tüm uyarıları listeleyin.
[Kullanıcıyla ilgili cihazları listeleme](get-user-related-machines.md)|[makine](machine.md) koleksiyonu|[Bir kullanıcı](user.md) tarafından oturum açmış olan tüm cihazları listeleyin.
