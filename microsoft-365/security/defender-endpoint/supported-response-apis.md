---
title: Desteklenen Uç Nokta için Microsoft Defender yanıt API'leri
description: Yanıtla ilgili belirli Uç Nokta için Microsoft Defender API çağrıları hakkında bilgi edinin.
keywords: yanıt api'leri, graf api'leri, desteklenen API'ler, aktör, uyarılar, cihaz, kullanıcı, etki alanı, ip, dosya
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.topic: conceptual
ms.openlocfilehash: 8dd36e06b90726a01168ccd3ebf12886c127b101
ms.sourcegitcommit: e8dd5cd434d17af7096d28d467a2b3b021cbb233
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2022
ms.locfileid: "67050974"
---
# <a name="supported-microsoft-defender-for-endpoint-query-apis"></a>Desteklenen Uç Nokta için Microsoft Defender sorgu API'leri

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)

> [!TIP]
> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-supported-response-apis-abovefoldlink)

Çalıştırabileceğiniz yanıtla ilgili desteklenen API çağrıları ve gerekli istek üst bilgileri ve çağrılardan beklenen yanıt gibi ayrıntılar hakkında bilgi edinin.

## <a name="in-this-section"></a>Bu bölümde

<br>

****

|Konu|Açıklama|
|---|---|
|Soruşturma paketini toplayın|Bir cihazdan araştırma paketi toplamak için bu API'yi çalıştırın.|
|Cihazı yalıtma|Bir cihazı ağdan yalıtmak için bu API'yi çalıştırın.|
|Tek çözümsüz cihaz|Cihazı yalıtımdan kaldırma.|
|Kod yürütmeyi kısıtlama|Kötü amaçlı işlemleri durdurarak bir saldırıyı içermek için bu API'yi çalıştırın. Ayrıca bir cihazı kilitleyebilir ve kötü amaçlı olabilecek programların sonraki denemelerinin çalışmasını engelleyebilirsiniz.|
|Kod yürütmenin yanıtlarını kaldırma|Güvenliği aşılmış cihazın düzeltildiğini doğruladıktan sonra uygulama ilkesinin kısıtlamasını tersine çevirmek için bunu çalıştırın.|
|Antivirüs taraması başlat|Güvenliği aşılmış bir cihazda bulunabilecek kötü amaçlı yazılımları tanımlamaya ve düzeltmeye yardımcı olmak için uzaktan bir virüsten koruma taraması başlatın.|
|Dur ve dosyayı karantinaya al|İşlemleri çalıştırmayı durdurmak, dosyaları karantinaya almak ve kayıt defteri anahtarları gibi kalıcılığı silmek için bu çağrıyı çalıştırın.|
|İstek örneği|Belirli bir cihazdan dosya örneği istemek için bu çağrıyı çalıştırın. Dosya cihazdan toplanır ve güvenli bir depolama alanına yüklenir.|
|Blok dosyası|Kötü amaçlı olabilecek dosyaları veya şüpheli kötü amaçlı yazılımları yasaklayarak kuruluşunuzda bir saldırının daha fazla yayılmasını önlemek için bu API'yi çalıştırın.|
|Dosyanın engellemesini kaldırma|Microsoft Defender Virüsten Koruma kullanarak kuruluşta bir dosyanın çalıştırılmasına izin verin.|
|Paket SAS URI'si alma|Araştırma paketini indirmeye izin veren bir URI almak için bu API'yi çalıştırın.|
|MachineAction nesnesini alma|MachineAction nesnesini almak için bu API'yi çalıştırın.|
|MachineActions koleksiyonunu alma|MachineAction koleksiyonunu almak için bunu çalıştırın.|
|FileActions koleksiyonunu alma|FileActions koleksiyonunu almak için bu API'yi çalıştırın.|
|Get FileMachineAction nesnesi|FileMachineAction nesnesini almak için bu API'yi çalıştırın.|
|FileMachineActions koleksiyonunu alma|FileMachineAction koleksiyonunu almak için bu API'yi çalıştırın.|
|
