---
title: Uç Nokta için Microsoft Defender canlı yanıt sorunlarını giderme
description: Uç Nokta için Microsoft Defender'de canlı yanıt kullanırken ortaya çıkabilecek sorunları giderme
keywords: canlı yanıt, canlı, yanıt, kilitli, dosya sorunlarını giderme
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: troubleshooting
ms.subservice: mde
ms.openlocfilehash: fa266b94dd6f3a8972fd08ddb3a3d473fed4997e
ms.sourcegitcommit: d3ef9391f621e8f4ca70661184b3bb82c6cbda94
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/02/2022
ms.locfileid: "67580563"
---
# <a name="troubleshoot-microsoft-defender-for-endpoint-live-response-issues"></a>Uç Nokta için Microsoft Defender canlı yanıt sorunlarını giderme

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-pullalerts-abovefoldlink)

Bu sayfada canlı yanıt sorunlarını gidermek için ayrıntılı adımlar sağlanır.

## <a name="file-cannot-be-accessed-during-live-response-sessions"></a>Canlı yanıt oturumları sırasında dosyaya erişilemiyor

Canlı yanıt oturumu sırasında bir eylem gerçekleştirmeye çalışırken dosyaya erişilemediğini belirten bir hata iletisiyle karşılaşırsanız, sorunu çözmek için aşağıdaki adımları kullanmanız gerekir.

1. Aşağıdaki betik kodu parçacığını kopyalayın ve PS1 dosyası olarak kaydedin:

    ```powershell
    $copied_file_path=$args[0]
    $action=Copy-Item $copied_file_path -Destination $env:TEMP -PassThru -ErrorAction silentlyContinue

    if ($action){
         Write-Host "You copied the file specified in $copied_file_path to $env:TEMP Succesfully"
    }

    else{
        Write-Output "Error occoured while trying to copy a file, details:"
        Write-Output  $error[0].exception.message

    }
    ```

2. Betiği canlı yanıt kitaplığına ekleyin.
3. Betiği tek bir parametreyle çalıştırın: kopyalanacak dosyanın dosya yolu.
4. TEMP klasörünüze gidin.
5. Kopyalanan dosyada yapmak istediğiniz eylemi çalıştırın.

## <a name="slow-live-response-sessions-or-delays-during-initial-connections"></a>yavaş canlı yanıt oturumları veya ilk bağlantılar sırasındaki gecikmeler

Canlı yanıt, Windows'da WNS hizmetiyle Uç Nokta için Defender algılayıcı kaydı hizmetinden yararlanıyor. Canlı yanıtla ilgili bağlantı sorunlarınız varsa aşağıdaki ayrıntıları onaylayın:

1. WpnService (Windows Anında İletme Bildirimleri Sistem Hizmeti) devre dışı bırakılmamış.
2. WNS bulutuyla WpnService bağlantısı, grup ilkesi veya MDM ayarı aracılığıyla devre dışı bırakılmaz. ['Bildirimlerin ağ kullanımını kapat'](/windows/client-management/mdm/policy-csp-notifications) ayarı '1' olarak ayarlanmamalıdır.

WpnService hizmetinin davranışını ve gereksinimlerini tam olarak anlamak için aşağıdaki makalelere bakın:

- [Windows Anında İletme Bildirimi Hizmetleri'ne (WNS) genel bakış](/windows/uwp/design/shell/tiles-and-notifications/windows-push-notification-services--wns--overview)
- [WNS Trafiğini Desteklemek için Kurumsal Güvenlik Duvarı ve Ara Sunucu Yapılandırmaları](/windows/uwp/design/shell/tiles-and-notifications/firewall-allowlist-config)
- [Microsoft Anında İletme Bildirimleri Hizmeti (MPNS) Genel IP aralıkları](https://www.microsoft.com/download/details.aspx?id=44535)
