---
title: Office 365 için Microsoft Defender için gelişmiş avcılık örneği
description: Gelişmiş avcılığı kullanarak e-posta tehditlerini aramaya başlama
keywords: gelişmiş avcılık, tehdit avcılığı, siber tehdit avcılığı, Microsoft 365 Defender, microsoft 365, m365, arama, sorgu, telemetri, özel algılamalar, şema, kusto
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 014802107d564fc24cf5e50a7513c390dcc943d5
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/31/2022
ms.locfileid: "67480072"
---
# <a name="advanced-hunting-example-for-microsoft-defender-for-office-365"></a>Office 365 için Microsoft Defender için gelişmiş avcılık örneği

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**
- Microsoft 365 Defender

Gelişmiş avcılığı kullanarak e-posta tehditlerini aramaya başlamak mı istiyorsunuz? Deneyebileceğiniz yöntem:

[Office 365 için Microsoft Defender makalesinin](/microsoft-365/security/office-365-security/defender-for-office-365) [Başlarken](/microsoft-365/security/office-365-security/defender-for-office-365#getting-started) bölümünde aşağıdakine benzer mantıksal erken yapılandırma öbekleri vardır:

1. Adında 'Anti' ile her şeyi yapılandırın.
   - Kötü amaçlı yazılımdan koruma
   - Kimlik avına karşı koruma
   - Antispam
2. Adında 'Güvenli' olan her şeyi ayarlayın.
   - Güvenli Bağlantılar
   - Güvenli Ekler
3. İş yüklerini savunma (ör. SharePoint Online, OneDrive ve Teams).
4. Sıfır saatlik otomatik temizleme ile koruyun.

1. Günde hemen atlayıp yapılandırmayı almak için bir [bağlantıyla](../office-365-security/protect-against-threats.md) birlikte.

**Başlarken'in** son adımı, ZAP olarak da bilinen **Sıfır Saat otomatik temizleme** ile kullanıcıları korumaktır. Şüpheli veya kötü amaçlı bir postayı(teslim sonrası) zap etme çabalarınızın başarılı olup olmadığını bilmek çok önemli olabilir.

Sorunları aramak için Kusto sorgu diline hızla gitmek, bu iki güvenlik merkezini birleştirmenin bir avantajıdır. Güvenlik ekipleri, **Av** **Gelişmiş Avcılığı**\> altında sonraki adımlarını [atarak](https://security.microsoft.com/advanced-hunting) ZAP eksiklerini izleyebilir.

1. Gelişmiş Avcılık sayfasında **Sorgu'ya** tıklayın.
1. Aşağıdaki sorguyu sorgu penceresine kopyalayın.
1. **Sorguyu çalıştır'ı** seçin.

```kusto
EmailPostDeliveryEvents 
| where Timestamp > ago(7d)
//List malicious emails that were not zapped successfullyconverge-2-endpoints-new.png
| where ActionType has "ZAP" and ActionResult == "Error"
| project ZapTime = Timestamp, ActionType, NetworkMessageId , RecipientEmailAddress 
//Get logon activity of recipients using RecipientEmailAddress and AccountUpn
| join kind=inner IdentityLogonEvents on $left.RecipientEmailAddress == $right.AccountUpn
| where Timestamp between ((ZapTime-24h) .. (ZapTime+24h))
//Show only pertinent info, such as account name, the app or service, protocol, the target device, and type of logon
| project ZapTime, ActionType, NetworkMessageId , RecipientEmailAddress, AccountUpn, 
LogonTime = Timestamp, AccountDisplayName, Application, Protocol, DeviceName, LogonType
```

:::image type="content" source="../../media/ah-query-example-new.png" alt-text="Sorgu panelinin en üstünde Sorgu'nun seçili olduğu Gelişmiş avcılık sayfası (Avcılık altında) ve son 7 gün içindeki ZAP eylemlerini yakalamak için bir Kusto sorgusu çalıştırma." lightbox="../../media/ah-query-example-new.png":::

Bu sorgudaki veriler, sorgunun altındaki sonuçlar panelinde görünür. Sonuçlar, özelleştirilebilir bir sonuç kümesinde 'DeviceName', 'AccountDisplayName' ve 'ZapTime' gibi bilgileri içerir. Sonuçlar, kayıtlarınız için de dışarı aktarılabilir. Sorgu yeniden ihtiyacınız olacaksa Farklı **Kaydet'i** >  seçin ve sorguyu sorgu, paylaşılan veya topluluk sorguları listenize ekleyin.

## <a name="related-information"></a>İlgili bilgiler
- [Gelişmiş avcılık en iyi yöntemleri](advanced-hunting-best-practices.md)
- [Genel Bakış - Gelişmiş avcılık](advanced-hunting-overview.md)
