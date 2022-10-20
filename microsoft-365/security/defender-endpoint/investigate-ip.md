---
title: Uyarıyla ilişkilendirilmiş BIR IP adresini araştırma
description: Cihazlar ve dış IP adresleri arasındaki olası iletişimi incelemek için araştırma seçeneklerini kullanın.
keywords: araştırma, araştırma, IP adresi, uyarı, Uç Nokta için Microsoft Defender, dış IP
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
- tier2
ms.topic: conceptual
ms.date: 04/24/2018
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: e652be5793988d468d36a3c0a7dbd9e879739fe7
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68623024"
---
# <a name="investigate-an-ip-address-associated-with-a-microsoft-defender-for-endpoint-alert"></a>Uç Nokta için Microsoft Defender uyarısıyla ilişkili IP adresini araştırma

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

Cihazlarınız ile dış İnternet protokolü (IP) adresleri arasındaki olası iletişimi inceleyin.

Kuruluştaki komut ve denetim (C2) sunucuları gibi şüpheli veya bilinen bir kötü amaçlı IP adresiyle iletişim kuran tüm cihazları tanımlamak olası ihlal kapsamını, ilişkili dosyaları ve virüslü cihazları belirlemeye yardımcı olur.

IP adresi görünümünde aşağıdaki bölümlerden bilgi bulabilirsiniz:

- Dünya çapında IP
- DNS adlarını ters çevir
- Bu IP ile ilgili uyarılar
- Kuruluşta IP
- Prevalans

## <a name="ip-worldwide-and-reverse-dns-names"></a>IP Worldwide ve Reverse DNS adları

IP adresi ayrıntıları bölümünde, ASN ve Ters DNS adları gibi IP adresinin öznitelikleri gösterilir.

## <a name="alerts-related-to-this-ip"></a>Bu IP ile ilgili uyarılar

**Bu IP ile ilgili uyarılar bölümü, IP** ile ilişkilendirilmiş uyarıların listesini sağlar.

## <a name="ip-in-organization"></a>Kuruluşta IP

**Kuruluştaki IP bölümü, kuruluştaki** IP adresinin yaygınlığı hakkında ayrıntılı bilgi sağlar.

## <a name="prevalence"></a>Prevalans

**Yaygınlık** bölümü, bu IP adresine kaç cihazın bağlandığını ve IP'nin ilk ve son görüldüğü zamanları gösterir. Bu bölümün sonuçlarını zaman aralığına göre filtreleyebilirsiniz; varsayılan süre 30 gündür.

## <a name="most-recent-observed-devices-with-ip"></a>IP ile en son gözlemlenen cihazlar

**IP ile en son gözlemlenen cihazlar** bölümü, IP adresinde gözlemlenen olaylar ve ilişkili uyarılar hakkında kronolojik bir görünüm sağlar.

**Dış IP'yi araştırma:**

1. **Arama çubuğu** açılan menüsünden **IP'yi** seçin.
2. **Arama** alanına IP adresini girin.
3. Arama simgesine tıklayın veya **Enter tuşuna** basın.

IP adresiyle ilgili ayrıntılar görüntülenir: kayıt ayrıntıları (varsa), ters IP'ler (örneğin, etki alanları), kuruluştaki bu IP Adresi ile iletişim kuran cihazların yaygınlığı (seçilebilir zaman aralığında) ve kuruluştaki bu IP adresiyle iletişim kurarken gözlemlenen cihazlar.

> [!NOTE]
> Arama sonuçları yalnızca kuruluştaki cihazlarla iletişimde gözlemlenen IP adresleri için döndürülür.

Arama ölçütlerini tanımlamak için arama filtrelerini kullanın. Ayrıca, kuruluştaki IP adresiyle, iletişimle ilişkilendirilmiş dosyayla ve gözlemlenen son tarihle iletişim kurarak gözlemlenen tüm cihazların görüntülenen sonuçlarını filtrelemek için zaman çizelgesi arama kutusunu da kullanabilirsiniz.

Cihaz adlarından herhangi birine tıkladığınızda bu cihazın görünümüne gidebilirsiniz; burada bildirilen uyarıları, davranışları ve olayları araştırmaya devam edebilirsiniz.

## <a name="related-topics"></a>İlgili konular

- [Uç Nokta için Microsoft Defender Uyarıları kuyruğu görüntüleme ve düzenleme](alerts-queue.md)
- [Uç Nokta için Microsoft Defender uyarılarını yönetme](manage-alerts.md)
- [Uç Nokta için Microsoft Defender uyarılarını araştırma](investigate-alerts.md)
- [Uç Nokta için Microsoft Defender uyarısıyla ilişkili bir dosyayı araştırma](investigate-files.md)
- [Uç Nokta için Microsoft Defender Cihazlar listesindeki cihazları araştırma](investigate-machines.md)
- [Uç Nokta için Microsoft Defender uyarısıyla ilişkili bir etki alanını araştırma](investigate-domain.md)
- [Uç Nokta için Microsoft Defender'de kullanıcı hesabını araştırma](investigate-user.md)
