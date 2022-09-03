---
title: Uç Nokta için Microsoft Defender İstemci Çözümleyicisi'ni kullanarak algılayıcı sistem durumu sorunlarını giderme
description: Algılayıcı verilerini veya özelliğini etkileyen olası yapılandırma, ortam, bağlantı veya telemetri sorununu belirlemek için cihazlarda algılayıcı sistem durumu sorunlarını giderin.
keywords: algılayıcı, algılayıcı durumu, yanlış yapılandırılmış, etkin değil, algılayıcı verileri yok, algılayıcı verileri, iletişim bozukluğu, iletişim
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
ms.subservice: m365d
ms.openlocfilehash: d689589def68ba98dd952dbd3991eecee38ec4be
ms.sourcegitcommit: d3ef9391f621e8f4ca70661184b3bb82c6cbda94
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/02/2022
ms.locfileid: "67586456"
---
# <a name="troubleshoot-sensor-health-using-microsoft-defender-for-endpoint-client-analyzer"></a>Uç Nokta için Microsoft Defender İstemci Çözümleyicisi'ni kullanarak algılayıcı sistem durumu sorunlarını giderme

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

Uç Nokta için Microsoft Defender İstemci Çözümleyicisi (MDECA), Windows, Linux veya macOS çalıştıran [ekli cihazlarda](/microsoft-365/security/defender-endpoint/onboard-configure) algılayıcı sistem durumu veya güvenilirlik sorunlarını tanılarken yararlı olabilir. Örneğin, çözümleyiciyi güvenlik portalında görüntülenen [algılayıcı sistem durumuna](/microsoft-365/security/defender-endpoint/fix-unhealthy-sensors) (Etkin Olmayan, Algılayıcı Verileri Yok veya Engelli İletişimler) göre iyi durumda olmayan bir makinede çalıştırmak isteyebilirsiniz.

MDECA, belirgin algılayıcı sistem durumu sorunlarının yanı sıra aşağıdaki gibi karmaşık senaryolarda sorun gidermeye yönelik diğer izlemeleri, günlükleri ve tanılama bilgilerini de toplayabilir:

- Uygulama uyumluluğu (AppCompat), performans, ağ bağlantısı veya
- [Uç Nokta Veri Kaybı Önleme](/microsoft-365/compliance/endpoint-dlp-learn-about) ile ilgili beklenmeyen davranış.

## <a name="privacy-notice"></a>Gizlilik bildirimi

- Uç Nokta için Microsoft Defender İstemci Çözümleyicisi aracı, Microsoft Müşteri Destek Hizmetleri (CSS) tarafından Uç Nokta için Microsoft Defender karşılaştığınız sorunları gidermeye yardımcı olacak bilgileri toplamak için düzenli olarak kullanılır.

- Toplanan veriler IP adresleri, bilgisayar adları ve kullanıcı adları gibi Kişisel Bilgileri (PII) ve/veya hassas verileri (ancak bunlarla sınırlı olmamak üzere) içerebilir.

- Veri toplama tamamlandıktan sonra araç, verileri bir alt klasör ve sıkıştırılmış zip dosyası içinde makineye yerel olarak kaydeder.

- Microsoft'a otomatik olarak veri gönderilmez. Bir destek sorunu üzerinde işbirliği sırasında aracı kullanıyorsanız, sorunun araştırılmasını kolaylaştırmak için sıkıştırılmış verileri Güvenli Dosya Değişimi'ni kullanarak Microsoft CSS'ye göndermeniz istenebilir.

Güvenli Dosya Değişimi hakkında daha fazla bilgi için bkz. [Microsoft Desteği ile dosya alışverişi yapmak için Güvenli Dosya Değişimi'ni kullanma](/troubleshoot/azure/general/secure-file-exchange-transfer-files)

Gizlilik bildirimimiz hakkında daha fazla bilgi için bkz. [Microsoft Gizlilik Bildirimi](https://privacy.microsoft.com/privacystatement).

## <a name="requirements"></a>Gereksinimler

- Çözümleyiciyi çalıştırmadan önce ara sunucu veya güvenlik duvarı yapılandırmanızın [Uç Nokta için Microsoft Defender hizmet URL'lerine](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server) erişime izin verdiğinden emin olunmasını öneririz.

- Çözümleyici, Uç Nokta için Microsoft Defender ekledikten sonra [desteklenen Windows](minimum-requirements.md#supported-windows-versions), [Linux](microsoft-defender-endpoint-linux.md#system-requirements) veya [macOS](microsoft-defender-endpoint-mac.md#system-requirements) sürümlerinde çalıştırılabilir.

- Windows cihazları için çözümleyiciyi doğrudan belirli makinelerde çalıştırıyorsanız ve [Canlı Yanıt](/microsoft-365/security/defender-endpoint/troubleshoot-collect-support-log) aracılığıyla uzaktan çalıştırmıyorsanız SysInternals [PsExec.exe](/sysinternals/downloads/psexec) çalışmasına (en azından geçici olarak) izin verilmelidir. Çözümleyici, bulut bağlantı denetimlerini Yerel Sistem olarak çalıştırmak ve SENSE hizmetinin davranışını öykünmek için PsExec.exe aracını çağırır.

    > [!NOTE]
    > Windows cihazlarında, [PSExec ve WMI komutlarından kaynaklanan](attack-surface-reduction-rules-reference.md#block-process-creations-originating-from-psexec-and-wmi-commands) Saldırı Yüzeyi Azaltma (ASR) kuralını engelleme işlemi oluşturma işlemlerini kullanıyorsanız, çözümleyicinin buluta bağlantı denetimlerini beklendiği gibi çalıştırmasına izin vermek için kuralı geçici olarak devre dışı bırakmak veya [ASR kuralında bir dışlama yapılandırmak](enable-attack-surface-reduction.md#exclude-files-and-folders-from-asr-rules) isteyebilirsiniz.
