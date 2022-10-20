---
title: Araştırma API'lerini başlatma
description: Bir cihazda araştırma başlatmak için bu API'yi kullanın.
keywords: api'ler, graf API'leri, desteklenen API'ler, araştırma
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
ms.openlocfilehash: 956a443778db52a40d85974dace4bc12ebba7224
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68636530"
---
# <a name="start-investigation-api"></a>Araştırma API'lerini başlatma

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API açıklaması

Cihazda otomatik araştırma başlatın.

Daha fazla bilgi için bkz. [Otomatik araştırmalara genel bakış](automated-investigations.md) .

## <a name="limitations"></a>Sınırlamalar

1. Bu API için hız sınırlamaları saatte 50 çağrıdır.

## <a name="requirements-for-air"></a>AIR gereksinimleri

Kuruluşunuzda Uç Nokta için Defender olmalıdır (bkz. [Uç Nokta için Microsoft Defender için en düşük gereksinimler](minimum-requirements.md).

Şu anda AIR yalnızca aşağıdaki işletim sistemi sürümlerini destekler:

- Windows Server 2019
- Windows Server 2022
- Windows 10, sürüm 1709 ([KB4493441](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441) ile İs Derlemesi 16299.1085) veya üzeri
- Windows 10, sürüm 1803 ([KB4493464](https://support.microsoft.com/help/4493464/windows-10-update-kb4493464) ile İs Derlemesi 17134.704) veya üzeri
- Windows 10, sürüm [1803](/windows/release-information/status-windows-10-1809-and-windows-server-2019) veya üzeri
- Windows 11

## <a name="permissions"></a>İzinler

Bu API'yi çağırmak için aşağıdaki izinlerden biri gereklidir. İzinlerin nasıl seçileceği de dahil olmak üzere daha fazla bilgi edinmek için bkz[. Uç Nokta için Microsoft Defender API'leri kullanma](apis-intro.md)

İzin türü|Izni|İzin görünen adı
:---|:---|:---
Uygulama|Alert.ReadWrite.All|'Tüm uyarıları okuma ve yazma'
Temsilci (iş veya okul hesabı)|Alert.ReadWrite|'Uyarıları okuma ve yazma'

> [!NOTE]
> Kullanıcı kimlik bilgilerini kullanarak belirteç alırken:
>
> - Kullanıcının en az şu rol iznine sahip olması gerekir: 'Etkin düzeltme eylemleri' (Daha fazla bilgi için bkz [. Rolleri oluşturma ve yönetme](user-roles.md) )
> - Kullanıcının cihaz grubu ayarlarına göre cihaza erişimi olmalıdır (Daha fazla bilgi için bkz [. Cihaz grupları oluşturma ve yönetme](machine-groups.md) )
>
> Cihaz grubu oluşturma, Uç Nokta Için Defender Plan 1 ve Plan 2'de desteklenir. 

## <a name="http-request"></a>HTTP isteği

```http
POST https://api.security.microsoft.com/api/machines/{id}/startInvestigation
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
Açıklama ekleme|Dize|Eylemle ilişkilendirilecek açıklama. **Gerekli**.

## <a name="response"></a>Yanıt

Başarılı olursa, bu yöntem 201 - Yanıt gövdesinde oluşturulan yanıt kodu ve [Araştırma](investigation.md) döndürür.

## <a name="example"></a>Örnek

### <a name="request"></a>Istek

burada isteğin bir örneği verilmiştir.

```https
POST https://api.security.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/startInvestigation
```

```json
{
  "Comment": "Test investigation"
}
```
