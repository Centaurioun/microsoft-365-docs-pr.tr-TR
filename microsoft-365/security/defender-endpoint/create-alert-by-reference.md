---
title: Olay API'sinden uyarı oluşturma
description: Uç Nokta için Microsoft Defender'da Olay'ın üzerinde yeni bir Uyarı oluşturmak için Uyarı oluşturma API'sini kullanmayı öğrenin.
keywords: api'ler, graf api'si, desteklenen API'ler, alma, uyarı, bilgi, kimlik
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
ms.custom: api
search.appverid: met150
ms.openlocfilehash: 817bfec55a38cef0404c392bce9765d1aef14686
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68623156"
---
# <a name="create-alert-api"></a>Uyarı API'si oluşturma

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API açıklaması

**Olay'ın** üzerinde yeni [Uyarı](alerts.md) oluşturur.

- Uyarı oluşturmak için **Uç Nokta için Microsoft Defender Olay** gereklidir.
- İstekteki Olaydan üç parametre sağlamanız gerekir: **Olay Zamanı**, **Makine Kimliği** ve **Rapor Kimliği**. Aşağıdaki örniğe bakın.
- Gelişmiş Tehdit Avcılığı API'sinde veya Portalda bulunan bir olayı kullanabilirsiniz.
- Aynı Cihazda aynı Başlığa sahip açık bir uyarı varsa, oluşturulan yeni uyarı bu uyarıyla birleştirilir.
- API aracılığıyla oluşturulan uyarılarda otomatik araştırma otomatik olarak başlar.

## <a name="limitations"></a>Sınırlamalar

1. Bu API için hız sınırlamaları dakikada 15 çağrıdır.

## <a name="permissions"></a>İzinler

Bu API'yi çağırmak için aşağıdaki izinlerden biri gereklidir. İzinlerin nasıl seçileceği de dahil olmak üzere daha fazla bilgi edinmek için bkz[. Uç Nokta için Microsoft Defender API'leri kullanma](apis-intro.md)

İzin türü | Izni | İzin görünen adı
:---|:---|:---
Uygulama | Alert.ReadWrite.All | 'Tüm uyarıları okuma ve yazma'
Temsilci (iş veya okul hesabı) | Alert.ReadWrite | 'Uyarıları okuma ve yazma'

> [!NOTE]
> Kullanıcı kimlik bilgilerini kullanarak belirteç alırken:
>
> - Kullanıcının en az şu rol iznine sahip olması gerekir: 'Uyarılar araştırması' (Daha fazla bilgi için bkz. [Rolleri oluşturma ve yönetme](user-roles.md) )
> - Kullanıcının, cihaz grubu ayarlarına göre uyarıyla ilişkilendirilmiş cihaza erişimi olmalıdır (Daha fazla bilgi için bkz. [Cihaz grupları oluşturma ve yönetme](machine-groups.md)
>
> Cihaz Grubu oluşturma hem Uç Nokta için Defender Plan 1 hem de Plan 2'de desteklenir

## <a name="http-request"></a>HTTP isteği

```http
POST https://api.securitycenter.microsoft.com/api/alerts/CreateAlertByReference
```

## <a name="request-headers"></a>İstek üst bilgileri

Name|Tür|Açıklama
:---|:---|:---
Yetkilendirme | Dize | Taşıyıcı {token}. **Gerekli**.
İçerik Türü | Dize | application/json. **Gerekli**.

## <a name="request-body"></a>İstek gövdesi

İstek gövdesinde aşağıdaki değerleri sağlayın (tümü gereklidir):

Özellik | Tür | Açıklama
:---|:---|:---
eventTime | DateTime(UTC) | Olayın, gelişmiş avcılıktan elde edilen dize olarak kesin zamanı. Örneğin **Gerekli**```2018-08-03T16:45:21.7115183Z```.
reportId | Dize | Gelişmiş avlanmadan elde edilen olayın reportId değeri. **Gerekli**.
machineId | Dize | Olayın tanımlandığı cihazın kimliği. **Gerekli**.
Önem | Dize | Uyarının önem derecesi. Özellik değerleri şunlardır: 'Low', 'Medium' ve 'High'. **Gerekli**.
Başlık | Dize | Uyarının başlığı. **Gerekli**.
Açıklama | Dize | Uyarının açıklaması. **Gerekli**.
recommendedAction| Dize | Güvenlik görevlisinin uyarıyı analiz ederken bu eylemi gerçekleştirmesi gerekir. **Gerekli**.
Kategori| Dize | Uyarı kategorisi. Özellik değerleri şunlardır: "General", "CommandAndControl", "Collection", "CredentialAccess", "DefenseEvasion", "Discovery", "Exfiltrasyon", "Exploit", "Execution", "InitialAccess", "LateralMovement", "Malware", "Persistence", "PrivilegeEscalation", "Ransomware", "SuspiciousActivity" **Required**.

## <a name="response"></a>Yanıt

Başarılı olursa, bu yöntem 200 Tamam döndürür ve yanıt gövdesinde yeni bir [uyarı](alerts.md) nesnesi döndürür. Belirtilen özelliklere (_reportId_, _eventTime_ ve _machineId_) sahip olay bulunamadıysa - 404 Bulunamadı.

## <a name="example"></a>Örnek

### <a name="request"></a>Istek

burada isteğin bir örneği verilmiş.

```http
POST https://api.securitycenter.microsoft.com/api/alerts/CreateAlertByReference
```

```json
{
    "machineId": "1e5bc9d7e413ddd7902c2932e418702b84d0cc07",
    "severity": "Low",
    "title": "example",
    "description": "example alert",
    "recommendedAction": "nothing",
    "eventTime": "2018-08-03T16:45:21.7115183Z",
    "reportId": "20776",
    "category": "Exploit"
}
```
