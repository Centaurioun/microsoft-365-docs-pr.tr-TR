---
title: dosyaları Uç Nokta için Microsoft Defender'de gönderme
description: Şüpheli e-postaları, URL'leri, e-posta eklerini ve dosyaları tarama için Microsoft'a göndermek için Microsoft 365 Defender'daki birleşik gönderimler özelliğini kullanmayı öğrenin.
keywords: virüsten koruma, istenmeyen posta, kimlik avı, dosya, uyarı, Uç Nokta için Microsoft Defender, hatalı pozitif, hatalı negatif, engellenen dosya, engellenen URL, gönderme, gönderme, rapor
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.date: 06/15/2021
ms.service: microsoft-365-security
ms.subservice: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
manager: dansimp
localization_priority: Normal
audience: ITPro
ms.topic: how-to
ms.collection:
- m365-security
- tier2
ms.custom: FPFN
ms.openlocfilehash: 89da86f56b391179b27ccff9146de211062ccbfc
ms.sourcegitcommit: b9282493c371d59c2e583b9803825096499b5e2c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68145853"
---
# <a name="submit-files-in-microsoft-defender-for-endpoint"></a>dosyaları Uç Nokta için Microsoft Defender'de gönderme

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Uygulandığı öğe**

- [Uç Nokta için Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2146806)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-usewdatp-abovefoldlink).

Uç Nokta için Microsoft Defender'da yöneticiler, dosyaları ve dosya karmalarını (SHD) gözden geçirebilmek üzere Microsoft'a göndermek için birleşik gönderimler özelliğini kullanabilir. Birleşik gönderim deneyimi, e-postaları, URL'leri, e-posta eklerini ve dosyaları kullanımı kolay tek bir gönderim deneyiminde göndermek için kullanabileceğiniz tek bir mağazadır. Yöneticiler şüpheli dosyaları göndermek için Microsoft 365 Defender portalını veya Uç Nokta için Microsoft Defender Uyarı sayfasını kullanabilir.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Başlamadan önce bilmeniz gerekenler

- Yeni birleşik gönderim deneyimi yalnızca Microsoft 365 Defender, Uç Nokta için Microsoft Defender Plan 2 veya Office Plan 2 için Microsoft Defender içeren aboneliklerde kullanılabilir.

- Microsoft'a dosya göndermek için aşağıdaki rol gruplarından birinin üyesi olmanız gerekir:

  - [Microsoft 365 Defender portalında](../office-365-security/permissions-microsoft-365-security-center.md) **Kuruluş Yönetimi**, **Güvenlik Yöneticisi** veya **Güvenlik Okuyucusu**.

- Microsoft'a istenmeyen posta, kimlik avı, URL'ler ve e-posta eklerini nasıl gönderebileceğiniz hakkında daha fazla bilgi için bkz. [İletileri ve dosyaları Microsoft'a bildirme](../office-365-security/report-junk-email-messages-to-microsoft.md).

## <a name="report-items-to-microsoft-from-the-portal"></a>Öğeleri portaldan Microsoft'a bildirme

Kötü amaçlı yazılım olabileceğinden şüphelendiğiniz veya yanlış algılandığından (hatalı pozitif) şüphelendiğiniz bir dosyanız varsa, konumundaki Microsoft 365 Defender portalını kullanarak analiz için dosyayı Microsoft'a https://security.microsoft.com/gönderebilirsiniz.

### <a name="submit-a-file-or-file-hash"></a>Dosya veya dosya karması gönderme

1. adresinden Microsoft 365 Defender <https://security.microsoft.com/>açın, **Eylemler & gönderimler'e** tıklayın, **Gönderiler'e** tıklayın, **Dosyalar** sekmesine gidin ve **yeni gönderim ekle'yi** seçin.

    > [!div class="mx-imgBorder"]
    > ![Yeni gönderim ekleme](../../media/unified-admin-submission-new.png)

2. **Dosya** veya **Dosya karmasını** göndermek **üzere görünen Öğeleri gözden geçirmek için Microsoft'a gönder** açılır penceresini kullanın.

3. **Gönderim türünü seçin** kutusunda, açılan **listeden Dosya** veya **Dosya karması'nı** seçin.

4. Dosya gönderirken **Dosyalara gözat'a** tıklayın. Açılan iletişim kutusunda dosyayı bulun ve seçin ve **aç'a** tıklayın. **Dosya karması** gönderimleri için dosya karması'nı kopyalamanız veya yazmanız gerekecektir.

5. **Bu dosya olarak kategorilere ayrılmış olmalıdır** bölümünde **Kötü amaçlı yazılım** (hatalı negatif) veya **İstenmeyen yazılım** ya da **Temizle** (hatalı pozitif) seçeneğini belirleyin.

6. Ardından **önceliği seçin**. **Dosya karması** gönderimleri için **Düşük - toplu dosya veya dosya karması gönderiminin** tek seçenek olduğunu ve otomatik olarak seçildiğini unutmayın.

    > [!div class="mx-imgBorder"]
    > ![Öğeleri gözden geçirmek üzere Microsoft'a gönderme](../../media/unified-admin-submission-file.png)

7. **Gönder'e** tıklayın.

   Gönderiminizin ayrıntılarını görüntülemek istiyorsanız **Gönderimler adı** listesinden gönderiminizi seçerek **Sonuç ayrıntıları** açılır öğesini açın.

## <a name="report-items-to-microsoft-from-the-alerts-page"></a>Uyarılar sayfasından Öğeleri Microsoft'a bildirme

Ayrıca, **doğrudan Uyarılar** sayfasındaki uyarı listesinden bir dosya veya dosya karması da gönderebilirsiniz.

1. konumundaki Microsoft 365 Defender <https://security.microsoft.com/>açın **, Uyarılar & Olaylar'a** tıklayın ve ardından **Uyarılar'a** tıklayarak uyarı listesini görüntüleyin.

2. Raporlamak istediğiniz uyarıyı seçin. Uyarının içinde iç içe yerleştirilmiş bir dosya gönderdiğinizi unutmayın.

3. Ek seçenekleri görmek için **Uyarıyı yönet'in** yanındaki üç noktaya tıklayın. **Öğeleri gözden geçirmek üzere Microsoft'a gönder'i** seçin.

    > [!div class="mx-imgBorder"]
    > ![Uyarılar kuyruğundan öğe gönderme](../../media/unified-admin-submission-alerts-queue.png)

4. Açılan sonraki açılır listede gönderim türünü seçin.

    > [!div class="mx-imgBorder"]
    > ![Gerekli alanları tamamlama](../../media/unified-admin-submission-alert-queue-flyout.png)

    Gönderim türü olarak **Dosya'yı** seçerseniz dosyayı karşıya yükleyin, gönderiminizi kategorilere ayırın ve önceliğini seçin.

    Gönderim türü olarak **Dosya Karması'nı** seçerseniz, açılan listeden kullanılabilen dosya karmalarını seçin. Birden çok dosya karması seçebilirsiniz.

5. **Gönder'e** tıklayın.

## <a name="related-information"></a>İlgili bilgiler

- [Microsoft 365 Defender'da Uç Nokta için Microsoft Defender](../defender/microsoft-365-security-center-mde.md)
- [Hatalı pozitifleri/negatifleri ele al](defender-endpoint-false-positives-negatives.md)
- [Uç Nokta için Microsoft Defender'de uyarı kuyruğu görüntüleme ve düzenleme](alerts-queue.md)
