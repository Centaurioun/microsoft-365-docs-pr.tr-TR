---
title: Makine API'sini çıkarma
description: Uç Nokta için Microsoft Defender'dan bir cihazı çıkarmak için API kullanmayı öğrenin.
keywords: api'ler, graf api'leri, desteklenen API'ler, araştırma paketini toplama
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
ms.topic: article
ms.subservice: mde
ms.custom: api
search.appverid: met150
ms.openlocfilehash: 33cbe799c9263fa6d5d403eafb08447f264358ea
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2022
ms.locfileid: "68228020"
---
# <a name="offboard-machine-api"></a>Makine API'sini çıkarma

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API açıklaması

Uç Nokta için Defender'dan cihazı kullanıma alın.

## <a name="limitations"></a>Sınırlamalar

- Bu API için hız sınırlamaları dakikada 100 çağrı ve saatte 1500 çağrıdır.

  [!include[Machine actions note](../../includes/machineactionsnote.md)]

> [!NOTE]
> Bu API Windows 11, Windows 10, sürüm 1703 ve üzeri ya da Windows Server 2019 ve sonraki sürümlerde desteklenir.
>
> Bu API MacOS veya Linux cihazlarda desteklenmez.

## <a name="permissions"></a>İzinler

Bu API'yi çağırmak için aşağıdaki izinlerden biri gereklidir. İzinlerin nasıl seçileceği de dahil olmak üzere daha fazla bilgi edinmek için bkz [. Uç Nokta API'leri için Defender'ı kullanma](apis-intro.md)

İzin türü|Izni|İzin görünen adı
---|---|---
Uygulama|Machine.Offboard|'Offboard machine'
Temsilci (iş veya okul hesabı)|Machine.Offboard|'Offboard machine'

> [!NOTE]
> Kullanıcı kimlik bilgilerini kullanarak belirteç alırken:
>
> - Kullanıcının 'Genel Yönetici' AD rolüne ihtiyacı var
> - Kullanıcının cihaz grubu ayarlarına göre cihaza erişimi olmalıdır (Daha fazla bilgi için bkz [. Cihaz grupları oluşturma ve yönetme](machine-groups.md) )
>
> Cihaz grubu oluşturma, Uç Nokta Için Defender Plan 1 ve Plan 2'de desteklenir.  

## <a name="http-request"></a>HTTP isteği

```http
POST https://api.securitycenter.microsoft.com/api/machines/{id}/offboard
```

Makine kimliği, cihazı seçtiğinizde URL'de bulunabilir. Genellikle, URL'de bulunabilen 40 basamaklı alfasayısal bir sayıdır.

## <a name="request-headers"></a>İstek üst bilgileri

Name|Tür|Açıklama
---|---|---
Yetkilendirme|Dize|Taşıyıcı {token}. **Gerekli**.
İçerik Türü|Dize|application/json. **Gerekli**.

## <a name="request-body"></a>İstek gövdesi

İstek gövdesinde aşağıdaki parametreleri içeren bir JSON nesnesi sağlayın:

Parametre|Tür|Açıklama
---|---|---
Açıklama ekleme|Dize|Eylemle ilişkilendirilecek açıklama. **Gerekli**.

## <a name="response"></a>Yanıt

Başarılı olursa, bu yöntem yanıt gövdesinde 200 - Oluşturulan yanıt kodu ve [Makine Eylemi](machineaction.md) döndürür.

## <a name="example"></a>Örnek

### <a name="request"></a>Istek

burada isteğin bir örneği verilmiştir. JSON açıklaması eklenmediyse kod **400** ile hata oluşur.

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/offboard
```

```json
{
  "Comment": "Offboard machine by automation"
}
```
