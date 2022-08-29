---
title: Cihazları etiket API'lerine göre bulma
description: specifc etiketi içeren tüm cihazları bulma
keywords: api'ler, desteklenen API'ler, get, device, find, find device, by tag
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
ms.openlocfilehash: f7926003a11c5aa27da5bbf4913feb54504a60d1
ms.sourcegitcommit: 217108c59be41b01963a393b4f16d137636fe6a8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/12/2022
ms.locfileid: "67327827"
---
# <a name="find-devices-by-tag-api"></a>Cihazları etiket API'lerine göre bulma

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:** 
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API açıklaması

[Etikete](machine-tags.md) Göre [Makineleri](machine.md) Bul.

`startswith` sorgu desteklenir.

## <a name="limitations"></a>Sınırlamalar

1. Bu API için hız sınırlamaları dakikada 100 çağrı ve saatte 1500 çağrıdır.

## <a name="permissions"></a>İzinler

Bu API'yi çağırmak için aşağıdaki izinlerden biri gereklidir. İzinlerin nasıl seçileceği de dahil olmak üzere daha fazla bilgi edinmek için bkz[. Uç Nokta için Microsoft Defender API'leri kullanma](apis-intro.md)

İzin türü|Izni|İzin görünen adı
:---|:---|:---
Uygulama|Machine.Read.All|'Tüm makine profillerini oku'
Uygulama|Machine.ReadWrite.All|'Tüm makine bilgilerini okuma ve yazma'
Temsilci (iş veya okul hesabı)|Machine.Read|'Makine bilgilerini oku'
Temsilci (iş veya okul hesabı)|Machine.ReadWrite|'Makine bilgilerini okuma ve yazma'

> [!NOTE]
> Kullanıcı kimlik bilgilerini kullanarak belirteç alırken:
>
> - Yanıt yalnızca kullanıcının cihaz grubu ayarlarına göre erişimi olan cihazları içerir (Daha fazla bilgi için bkz [. Cihaz grupları oluşturma ve yönetme](machine-groups.md) )
> - Kullanıcının en az şu rol iznine sahip olması gerekir: 'Verileri Görüntüle' (Daha fazla bilgi için bkz [. Rolleri oluşturma ve yönetme](user-roles.md) )
> - Yanıt yalnızca kullanıcının cihaz grubu ayarlarına göre erişimi olan cihazları içerir (Daha fazla bilgi için bkz [. Cihaz grupları oluşturma ve yönetme](machine-groups.md) )

## <a name="http-request"></a>HTTP isteği

```http
GET /api/machines/findbytag?tag={tag}&useStartsWithFilter={true/false}
```

## <a name="request-headers"></a>İstek üst bilgileri

Name|Tür|Açıklama
:---|:---|:---
Yetkilendirme|Dize|Taşıyıcı {token}. **Gerekli**.

## <a name="request-uri-parameters"></a>İstek URI parametreleri

Name|Tür|Açıklama
:---|:---|:---
Etiket|Dize|Etiket adı. **Gerekli**.
useStartsWithFilter|Boole|True olarak ayarlandığında, arama, sorguda verilen etiketle başlayan etiket adına sahip tüm cihazları bulur. Varsayılan değer false'tur. **İsteğe bağlı**.

## <a name="request-body"></a>İstek gövdesi

Boş

## <a name="response"></a>Yanıt

Başarılı olursa - Yanıt gövdesindeki makinelerin listesiyle 200 Tamam.

## <a name="example"></a>Örnek

### <a name="request"></a>Istek

burada isteğin bir örneği verilmiştir.

```http
GET https://api.securitycenter.microsoft.com/api/machines/findbytag?tag=testTag&useStartsWithFilter=true
```
