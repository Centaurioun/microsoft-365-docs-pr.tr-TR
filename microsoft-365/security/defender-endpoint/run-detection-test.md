---
title: Uç Nokta için Microsoft Defender'a düzgün şekilde eklendiğini doğrulamak için bir cihazda algılama testi çalıştırma
description: Algılama testi betiğini Uç Nokta için Microsoft Defender hizmetine yakın zamanda eklenen bir cihazda çalıştırarak düzgün eklendiğini doğrulayın.
search.appverid: met150
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
ms.date: 09/13/2022
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365-initiative-defender-endpoint
ms.topic: article
ms.subservice: mde
ms.openlocfilehash: 37d02195cc3acf9dfbdcae55ceb9534b6d68d722
ms.sourcegitcommit: 0af064e8b6778060f1bd365378d69b16fc9949b5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/15/2022
ms.locfileid: "67727980"
---
# <a name="run-a-detection-test-on-a-newly-onboarded-microsoft-defender-for-endpoint-device"></a>Yeni eklenen bir Uç Nokta için Microsoft Defender cihazında algılama testi çalıştırma

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Şunlar için geçerlidir:**
- Windows 11
- Desteklenen Windows 10 sürümleri
- Windows Server 2012 R2
- Windows Server 2016
- Windows Server, sürüm 1803
- Windows Server 2019
- Windows Server 2022
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Yönetim için Uç Nokta için Microsoft Defender hizmetine bir cihaz eklediğinizde, buna cihaz ekleme de denir. Ekleme, cihazların sistem durumuyla ilgili sinyalleri hizmete bildirmesine olanak tanır.

Bir cihazın hizmete başarıyla eklendiğinden emin olmak veya doğrulamak, dağıtım sürecinin tamamında kritik bir adımdır. Beklenen tüm cihazların yönetildiğini garanti eder. 

## <a name="verify-microsoft-defender-for-endpoint-onboarding-of-a-device-using-a-powershell-detection-test"></a>PowerShell algılama testi kullanarak cihazın Uç Nokta için Microsoft Defender eklendiğini doğrulama

Uç Nokta için Defender hizmetine düzgün bir şekilde raporlandığını doğrulamak için yeni eklenen bir cihazda aşağıdaki PowerShell betiğini çalıştırın.

1. Cihazda yükseltilmiş bir komut satırı istemi açın ve betiği çalıştırın:

   1. **Başlangıç'a** gidin ve **cmd** yazın.

   1. **Komut İstemi'ne** sağ tıklayın ve **Yönetici olarak çalıştır'ı** seçin.

      :::image type="content" source="images/run-as-admin.png" alt-text="Yönetici olarak çalıştır'ı işaret eden Başlat menüsü" lightbox="images/run-as-admin.png":::
    
2. İstemde aşağıdaki komutu kopyalayıp çalıştırın:

   ```powershell
   powershell.exe -NoExit -ExecutionPolicy Bypass -WindowStyle Hidden $ErrorActionPreference = 'silentlycontinue';(New-Object System.Net.WebClient).DownloadFile('http://127.0.0.1/1.exe', 'C:\\test-MDATP-test\\invoice.exe');Start-Process 'C:\\test-MDATP-test\\invoice.exe'
   ```

Komut İstemi penceresi otomatik olarak kapatılır. Başarılı olursa, eklenen cihaz için portalda yaklaşık on dakika içinde yeni bir uyarı görünür.

## <a name="related-topics"></a>İlgili konular

- [Windows cihazlarını ekleme](configure-endpoints.md)
- [Sunucuları ekleme](configure-server-endpoints.md)
- [Uç Nokta için Microsoft Defender ekleme sorunlarını giderme](/microsoft-365/security/defender-endpoint/troubleshoot-onboarding)
