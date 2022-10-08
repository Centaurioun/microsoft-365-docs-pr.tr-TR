---
title: Microsoft Güvenlik Tarayıcısı İndirme
ms.reviewer: ''
description: Windows bilgisayarlarından kötü amaçlı yazılımları bulmak ve kaldırmak için Microsoft Güvenlik Tarayıcısı aracını edinin.
keywords: güvenlik, kötü amaçlı yazılım
ms.service: microsoft-365-security
ms.mktglfcycl: secure
ms.sitesec: library
ms.localizationpriority: medium
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier2
ms.topic: article
search.appverid: met150
ms.openlocfilehash: 6d733c7b27528a25097bd8aa666f14a60989cbfc
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2022
ms.locfileid: "68221048"
---
# <a name="microsoft-safety-scanner-download"></a>Microsoft Güvenlik Tarayıcısı İndirme

Microsoft Güvenlik Tarayıcısı, Windows bilgisayarlarından kötü amaçlı yazılımları bulmak ve kaldırmak için tasarlanmış bir tarama aracıdır. Kötü amaçlı yazılımları bulmak ve tanımlanan tehditler tarafından yapılan değişiklikleri tersine çevirmeye çalışmak için indirmeniz ve tarama yapmanız yeterlidir.

- **[İndirme Microsoft Güvenlik Tarayıcısı (32 bit)](https://go.microsoft.com/fwlink/?LinkId=212733)**

- **[Microsoft Güvenlik Tarayıcısı indirme (64 bit)](https://go.microsoft.com/fwlink/?LinkId=212732)**

> [!NOTE]
> Kasım 2019'dan itibaren Güvenlik Tarayıcısı sha-2 özel olarak imzalanacak. Güvenlik Tarayıcısı'nın çalıştırılabilmesi için cihazlarınızın SHA-2'yi destekleyecek şekilde güncelleştirilmesi gerekir. Daha fazla bilgi edinmek için bkz. [Windows ve WSUS için 2019 SHA-2 Kod İmzalama Desteği gereksinimi](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus).

## <a name="important-information"></a>Önemli bilgiler

- Microsoft Güvenlik Tarayıcısı güvenlik bilgileri güncelleştirme sürümü[, bu web sayfasında](https://www.microsoft.com/wdsi/definitions) açıklanan sürümle eşleşir.

- Güvenlik Tarayıcısı yalnızca el ile tetiklendiğinde tarar ve indirildikten 10 gün sonra kullanılabilir. Her taramadan önce her zaman bu aracın en son sürümünü indirmenizi öneririz.

- Güvenlik tarayıcısı taşınabilir bir yürütülebilir dosyadır ve Windows Başlat menüsünde veya masaüstünde simge olarak görünmez. Bu indirmeyi kaydettiğiniz yeri not edin.

- Bu araç kötü amaçlı yazılımdan koruma ürününüzün yerini almaz. Otomatik güncelleştirmelerle gerçek zamanlı koruma için [Windows 7'de Windows 11, Windows 10 ve Windows 8](https://www.microsoft.com/windows/comprehensive-security) veya [Microsoft Security Essentials'ta](https://support.microsoft.com/help/14210/security-essentials-download) Microsoft Defender Virüsten Koruma'yı kullanın. Bu kötü amaçlı yazılımdan koruma ürünleri de güçlü kötü amaçlı yazılım temizleme özellikleri sağlar. Bu ürünlerle kötü amaçlı yazılımları kaldırmakta güçlük çekiyorsanız [, zor tehditleri kaldırma](https://www.microsoft.com/wdsi/help/troubleshooting-infection) yardımımıza başvurabilirsiniz.

## <a name="system-requirements"></a>Sistem gereksinimleri

Güvenlik Tarayıcısı, Windows 11, Windows 10, Windows 10 Tech Preview, Windows 8.1, Windows 8, Windows 7, Windows Server 2019, Windows Server 2016, Windows Server Tech Preview çalıştıran bilgisayarlardan kötü amaçlı yazılımların kaldırılmasına yardımcı olur. R2, Windows Server 2012, Windows Server 2008 R2 veya Windows Server 2008'i Windows Server 2012. Ayrıntılar için [Microsoft Yaşam Döngüsü İlkesi'ne](/lifecycle/) bakın.

## <a name="how-to-run-a-scan"></a>Tarama nasıl çalıştırılır?

1. Bu aracı indirin ve açın.
2. Çalıştırmak istediğiniz tarama türünü seçin ve taramayı başlatın.
3. Ekranda görüntülenen tarama sonuçlarını gözden geçirin. Ayrıntılı algılama sonuçları için **günlüğü %SYSTEMROOT%\debug\msert.log** konumunda görüntüleyin.

Bu aracı kaldırmak için yürütülebilir dosyayı silin (varsayılan olarak msert.exe).

Güvenlik Tarayıcısı hakkında daha fazla bilgi için [Güvenlik Tarayıcısı'nı kullanarak sorunları gidermeye yönelik destek makalesine](https://support.microsoft.com/kb/2520970) bakın.

## <a name="related-resources"></a>İlgili kaynaklar

- [Güvenlik Tarayıcısı Sorunlarını Giderme](https://support.microsoft.com/help/2520970/how-to-troubleshoot-an-error-when-you-run-the-microsoft-safety-scanner)
- [Microsoft Defender Virüsten Koruma](https://www.microsoft.com/windows/comprehensive-security)
- [Microsoft Security Essentials](https://support.microsoft.com/help/14210/security-essentials-download)
- [Zor tehditleri kaldırma](https://support.microsoft.com/help/4466982/windows-10-troubleshoot-problems-with-detecting-and-removing-malware)
- [Kötü amaçlı yazılım analizi için dosya gönderme](https://www.microsoft.com/wdsi/filesubmission)
- [Microsoft kötü amaçlı yazılımdan koruma ve tehdit koruması çözümleri](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint)
