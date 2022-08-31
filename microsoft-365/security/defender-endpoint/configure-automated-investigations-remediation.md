---
title: Otomatik araştırma ve düzeltme özelliklerini yapılandırma
description: Uç Nokta için Microsoft Defender'de otomatik araştırma ve düzeltme özelliklerinizi ayarlayın.
keywords: yapılandırma, kurulum, otomatik, araştırma, algılama, uyarılar, düzeltme, yanıt
ms.service: microsoft-365-security
ms.subservice: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: dansimp
ms.author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: how-to
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.openlocfilehash: 09d9860119a7c4aeb8949357b277fb395e09a9c2
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/31/2022
ms.locfileid: "67481910"
---
# <a name="configure-automated-investigation-and-remediation-capabilities-in-microsoft-defender-for-endpoint"></a>Uç Nokta için Microsoft Defender'de otomatik araştırma ve düzeltme özelliklerini yapılandırma

**Şunlar için geçerlidir:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [İş için Microsoft Defender](../defender-business/mdb-overview.md)

> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

[KuruluşunuzDa Uç Nokta için Defender](/windows/security/threat-protection/) (veya [İş için Defender](../defender-business/mdb-overview.md)) kullanılıyorsa[, otomatik araştırma ve düzeltme özellikleri](/microsoft-365/security/defender-endpoint/automated-investigations) güvenlik operasyonları ekibinizin zaman ve çabasını kaydedebilir. [Bu blog gönderisinde](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/enhance-your-soc-with-microsoft-defender-atp-automatic/ba-p/848946) açıklandığı gibi, bu özellikler bir güvenlik analistinin tehditleri araştırmak ve düzeltmek için uyguladığı ideal adımları taklit eder. [Otomatik araştırma ve düzeltme hakkında daha fazla bilgi edinin](/microsoft-365/security/defender-endpoint/automated-investigations).

Otomatik araştırma ve düzeltmeyi yapılandırmak için:

1. [Özellikleri açın](#turn-on-automated-investigation-and-remediation); Ve
2. [Cihaz gruplarını ayarlayın](#set-up-device-groups).

## <a name="turn-on-automated-investigation-and-remediation"></a>Otomatik araştırmayı ve düzeltmeyi açma

1. Genel yönetici veya güvenlik yöneticisi olarak Microsoft 365 Defender portalına ([https://security.microsoft.com](https://security.microsoft.com)) gidin ve oturum açın.

2. Gezinti bölmesinde **Ayarlar'ı** seçin.

3. **Uç noktalar'ı** ve ardından **Gelişmiş özellikler'i** seçin.

4. **Hem Otomatik Araştırma'ya** hem de **Uyarıları otomatik olarak çözümle'ye gidin**.

## <a name="set-up-device-groups"></a>Cihaz gruplarını ayarlayın

> [!NOTE]
> Bu yordam İş için Defender için geçerli değildir.

1. Microsoft 365 Defender portalında ([https://security.microsoft.com](https://security.microsoft.com)), **Ayarlar** sayfasındaki **İzinler'in** altında **Cihaz grupları'nı** seçin.

2. **+ Cihaz grubu ekle'yi** seçin.

3. Aşağıdaki gibi en az bir cihaz grubu oluşturun:

   - Cihaz grubu için bir ad ve açıklama belirtin.
   - **Otomasyon düzeyi listesinde** **Tam - tehditleri otomatik olarak düzeltme** gibi bir düzey seçin. Otomasyon düzeyi, düzeltme eylemlerinin otomatik olarak mı yoksa yalnızca onay üzerine mi gerçekleştirileceğini belirler. Daha fazla bilgi edinmek için bkz. [Otomatik araştırma ve düzeltmede otomasyon düzeyleri](automation-levels.md).
   - **Üyeler** bölümünde, cihazları tanımlamak ve dahil etmek için bir veya daha fazla koşul kullanın.
   - **Kullanıcı erişimi** sekmesinde, oluşturduğunuz cihaz grubuna erişimi olması gereken [Azure Active Directory gruplarını](/azure/active-directory/fundamentals/active-directory-manage-groups?context=azure/active-directory/users-groups-roles/context/ugr-context) seçin.

4. Cihaz grubunuzu ayarlamayı bitirdiğinizde **Bitti'yi** seçin.

## <a name="next-steps"></a>Sonraki adımlar

- [Bekleyen ve tamamlanan düzeltme eylemlerini görüntülemek için İşlem Merkezi'ni ziyaret edin](/microsoft-365/security/defender-endpoint/auto-investigation-action-center#the-action-center)
- [Bekleyen eylemleri gözden geçirme ve onaylama](/microsoft-365/security/defender-endpoint/manage-auto-investigation)

## <a name="see-also"></a>Ayrıca bkz.

- [Uç Nokta için Microsoft Defender'da yanlış pozitifleri/negatifleri ele alın](defender-endpoint-false-positives-negatives.md)
