---
title: Virüsten koruma tarama API'si çalıştırma
description: Bir cihazda virüsten koruma taraması çalıştırmayla ilgili çağrılar oluşturmak için bu API'yi kullanın.
keywords: api'ler, graph API'leri, desteklenen API'ler, cihazı yalıtımdan kaldırma
ms.prod: m365-security
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
ms.technology: mde
ms.custom: api
ms.openlocfilehash: 0f72d2d6db4bae754b0cd70d444e2781654a4b40
ms.sourcegitcommit: d09eb780dc41a01796eb8137fbe9267231af6746
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/19/2022
ms.locfileid: "67387102"
---
# <a name="run-antivirus-scan-api"></a>Virüsten koruma tarama API'si çalıştırma

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:** 
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API açıklaması

Cihazda Microsoft Defender Virüsten Koruma taraması başlatın.

## <a name="limitations"></a>Sınırlamalar

1. Bu API için hız sınırlamaları dakikada 100 çağrı ve saatte 1500 çağrıdır.

[!include[Device actions note](../../includes/machineactionsnote.md)]

> [!IMPORTANT]
>
> - Bu eylem Windows 10, sürüm 1709 veya üzeri ve Windows 11 cihazlarda kullanılabilir.
> - Microsoft Defender Virüsten Koruma taraması, Microsoft Defender Virüsten Koruma'nın etkin virüsten koruma çözümü olup olmadığına bakılmaksızın diğer virüsten koruma çözümleriyle birlikte çalıştırılabilir. Microsoft Defender Virüsten Koruma Pasif modda olabilir. Daha fazla bilgi için bkz. [Microsoft Defender Virüsten Koruma uyumluluğu](/microsoft-365/security/defender-endpoint/microsoft-defender-antivirus-compatibility).

## <a name="permissions"></a>İzinler

Bu API'yi çağırmak için aşağıdaki izinlerden biri gereklidir. İzinlerin nasıl seçileceği de dahil olmak üzere daha fazla bilgi edinmek için bkz[. Uç Nokta için Microsoft Defender API'leri kullanma](apis-intro.md)

İzin türü|Izni|İzin görünen adı
:---|:---|:---
Uygulama|Machine.Scan|'Tarama makinesi'
Temsilci (iş veya okul hesabı)|Machine.Scan|'Tarama makinesi'

> [!NOTE]
> Kullanıcı kimlik bilgilerini kullanarak belirteç alırken:
>
> - Kullanıcının en az şu rol iznine sahip olması gerekir: 'Etkin düzeltme eylemleri' (Daha fazla bilgi için bkz [. Rolleri oluşturma ve yönetme](user-roles.md) )
> - Kullanıcının cihaz grubu ayarlarına göre cihaza erişimi olmalıdır (Daha fazla bilgi için bkz [. Cihaz grupları oluşturma ve yönetme](machine-groups.md) )

## <a name="http-request"></a>HTTP isteği

```http
POST https://api.securitycenter.microsoft.com/api/machines/{id}/runAntiVirusScan
```

## <a name="request-headers"></a>İstek üst bilgileri

Name|Tür|Açıklama
:---|:---|:---
Yetkilendirme|Dize|Taşıyıcı {token}. **Gerekli**.
İçerik Türü|Dize|application/json

## <a name="request-body"></a>İstek gövdesi

İstek gövdesinde aşağıdaki parametreleri içeren bir JSON nesnesi sağlayın:

Parametre|Tür|Açıklama
:---|:---|:---
Açıklama ekleme|Dize|Eylemle ilişkilendirilecek açıklama. **Gerekli**.
ScanType|Dize|Tarama'nın türünü tanımlar. **Gerekli**.

**ScanType** gerçekleştirilecek tarama türünü denetler ve aşağıdakilerden biri olabilir:

- **Hızlı**: Cihazda hızlı tarama gerçekleştirme
- **Tam**: Cihazda tam tarama gerçekleştirme

## <a name="response"></a>Yanıt

Başarılı olursa, bu yöntem yanıt gövdesinde 201, Oluşturuldu yanıt kodu ve _MachineAction_ nesnesi döndürür.

Aynı cihaz için virüsten koruma taraması çalıştırmak için birden çok API çağrısı gönderirseniz, "bekleyen makine eylemi" veya "Eylem zaten sürüyor" iletisiyle HTTP 400 döndürür.

## <a name="example"></a>Örnek

### <a name="request"></a>Istek

burada isteğin bir örneği verilmiştir.

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/runAntiVirusScan 
```

```json
{
  "Comment": "Check machine for viruses due to alert 3212",
  "ScanType": "Full"
}
```
