---
title: Makine Etiketleri API'sini Ekleme veya Kaldırma
description: Uç Nokta için Microsoft Defender'da makine etiketi eklemek veya kaldırmak için Makine etiketleri ekleme veya kaldırma API'sini kullanmayı öğrenin.
keywords: api'ler, graf api'leri, desteklenen API'ler, etiketler, makine etiketleri
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
ms.technology: m365d
ms.custom: api
ms.openlocfilehash: f5a4a232e7752ae990c1f32ca69653c45baecb8b
ms.sourcegitcommit: 217108c59be41b01963a393b4f16d137636fe6a8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/12/2022
ms.locfileid: "67328111"
---
# <a name="add-or-remove-machine-tags-api"></a>Makine Etiketleri API'sini Ekleme veya Kaldırma

**Şunlar için geçerlidir:**

- [Uç Nokta için Microsoft Defender Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API açıklaması

Belirli bir [Makineye](machine.md) etiket ekler veya kaldırır.

## <a name="limitations"></a>Sınırlamalar

1. Yapılandırdığınız saklama süresine göre son görülen makinelere posta gönderebilirsiniz.

2. Bu API için hız sınırlamaları dakikada 100 çağrı ve saatte 1500 çağrıdır.

## <a name="permissions"></a>İzinler

Bu API'yi çağırmak için aşağıdaki izinlerden biri gereklidir. İzinlerin nasıl seçileceği de dahil olmak üzere daha fazla bilgi edinmek için bkz [. Uç Nokta API'leri için Defender'ı kullanma](apis-intro.md)

İzin türü|Izni|İzin görünen adı
:---|:---|:---
Uygulama|Machine.ReadWrite.All|'Tüm makine bilgilerini okuma ve yazma'
Temsilci (iş veya okul hesabı)|Machine.ReadWrite|'Makine bilgilerini okuma ve yazma'

> [!NOTE]
> Kullanıcı kimlik bilgilerini kullanarak belirteç alırken:
>
> - Kullanıcının en az şu rol iznine sahip olması gerekir: 'Güvenlik ayarını yönet'. Daha fazla bilgi için (Daha fazla bilgi için bkz. [Rolleri oluşturma ve yönetme](user-roles.md) )
> - Kullanıcının makine grubu ayarlarına göre makineye erişimi olmalıdır (Daha fazla bilgi için bkz [. Makine gruplarını oluşturma ve yönetme](machine-groups.md) )

## <a name="http-request"></a>HTTP isteği

```http
POST https://api.securitycenter.microsoft.com/api/machines/{id}/tags
```

## <a name="request-headers"></a>İstek üst bilgileri

Name|Tür|Açıklama
:---|:---|:---
Yetkilendirme|Dize|Taşıyıcı {token}. **Gerekli**.
İçerik Türü|Dize|application/json. **Gerekli**.

## <a name="request-body"></a>İstek gövdesi

İstek gövdesinde aşağıdaki parametreleri içeren bir JSON nesnesi sağlayın:

Parametre|Tür|Açıklama
:---|:---|:---
Değer|Dize|Etiket adı. **Gerekli**.
Eylem|Enum|Ekle veya Kaldır'ı seçin. İzin verilen değerler şunlardır: 'Ekle' veya 'Kaldır'. **Gerekli**.

## <a name="response"></a>Yanıt

Başarılı olursa, bu yöntem 200 - Tamam yanıt kodunu ve yanıt gövdesindeki güncelleştirilmiş Makine'yi döndürür.

## <a name="example"></a>Örnek

### <a name="request"></a>Istek

Makine etiketi ekleyen bir istek örneği aşağıda verilmiştir.

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/tags
```

```json
{
  "Value" : "test Tag 2",
  "Action": "Add"
}
```

- Makine etiketini kaldırmak için eylem'i istek gövdesinde 'Ekle' yerine 'Kaldır' olarak ayarlayın.
