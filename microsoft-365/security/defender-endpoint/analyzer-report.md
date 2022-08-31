---
title: İstemci çözümleyicisi HTML raporunu anlama
description: Uç Nokta için Microsoft Defender İstemci Çözümleyicisi HTML raporunu analiz etmeyi öğrenin
keywords: istemci çözümleyici raporu, html raporu, istemci çözümleyicisi
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-security-compliance
ms.topic: conceptual
ms.subservice: mde
ms.openlocfilehash: b1b83200b9fd0f67d832b4dbb41352bebfa418bd
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/31/2022
ms.locfileid: "67470795"
---
# <a name="understand-the-client-analyzer-html-report"></a>İstemci çözümleyicisi HTML raporunu anlama

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)

İstemci çözümleyicisi HTML biçiminde bir rapor oluşturur. Sorunları giderebilmeniz için olası algılayıcı sorunlarını belirlemek için raporu nasıl gözden geçireceğinizi öğrenin.

Raporu anlamak için aşağıdaki örneği kullanın.

 Süresi dolmuş Kuruluş Kimliği'ne eklenen ve gerekli Uç Nokta için Microsoft Defender URL'lerinden birine ulaşamayan bir makinedeki çözümleyiciden örnek çıktı:

:::image type="content" source="images/147cbcf0f7b6f0ff65d200bf3e4674cb.png" alt-text="MDE İstemci Çözümleyicisi Sonuçları sayfası" lightbox="images/147cbcf0f7b6f0ff65d200bf3e4674cb.png":::

- En üstte, betik sürümü ve betik çalışma zamanı başvuru için listelenir
- **Cihaz Bilgileri** bölümü, çözümleyicinin üzerinde çalıştığı cihazı benzersiz olarak tanımlamak için temel işletim sistemi ve cihaz tanımlayıcıları sağlar.
- **Endpoint Security Details**, Microsoft Defender Virüsten Koruma ve algılayıcı işlemi de dahil olmak üzere Uç Nokta için Microsoft Defender ile ilgili işlemler hakkında genel bilgiler sağlar. Önemli işlemler beklendiği gibi çevrimiçi değilse renk kırmızıya dönüşür.
  
-   **Endpoint Security Details**, Microsoft Defender Virüsten Koruma ve algılayıcı işlemi de dahil olmak üzere Uç Nokta için Microsoft Defender ile ilgili işlemler hakkında genel bilgiler sağlar. Önemli işlemler beklendiği gibi çevrimiçi değilse renk kırmızıya dönüşür.

    :::image type="content" source="images/85f56004dc6bd1679c3d2c063e36cb80.png" alt-text="Sonuçları Denetle Özeti sayfası" lightbox="images/85f56004dc6bd1679c3d2c063e36cb80.png":::

-   **Sonuçları Denetle Özeti** bölümünde çözümleyici tarafından algılanan hata, uyarı veya bilgilendirici olaylar için toplu bir sayı elde edersiniz.

-   **Ayrıntılı Sonuçlar** bölümünde, sonuçların ve çözümleyici tarafından yapılan gözlemlere göre kılavuzun yer aldığı bir liste (önem derecesine göre sıralanmış) görürsünüz.

## <a name="open-a-support-ticket-to-microsoft-and-include-the-analyzer-results"></a>Microsoft'a bir destek bileti açın ve Çözümleyici sonuçlarını ekleyin

[Destek bileti açarken](contact-support.md#open-a-service-request) çözümleyici sonuç dosyalarını eklemek için **Ekler** bölümünü kullandığınızdan ve dosyayı eklediğinizden `MDEClientAnalyzerResult.zip` emin olun:

:::image type="content" source="images/508c189656c3deb3b239daf811e33741.png" alt-text="Ek istemi" lightbox="images/508c189656c3deb3b239daf811e33741.png":::

> [!NOTE]
> Dosya boyutu 25 MB'tan büyükse, servis talebinize atanan destek mühendisi analiz için büyük dosyaları karşıya yüklemek için ayrılmış bir güvenli çalışma alanı sağlar.
