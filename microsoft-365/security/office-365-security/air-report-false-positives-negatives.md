---
title: Office 365 için Microsoft Defender'da otomatik araştırma sonrasında hatalı pozitif veya hatalı negatifleri bildirme
description: Office 365 için Microsoft Defender'da AIR tarafından bir şey mi atlandı veya yanlış algılandı? Hatalı pozitif veya hatalı negatifleri analiz için Microsoft'a göndermeyi öğrenin.
keywords: otomatik, araştırma, uyarı, tetikleyici, eylem, düzeltme, yanlış pozitif, yanlış negatif
search.appverid: met150
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
author: dansimp
ms.author: dansimp
ms.service: microsoft-365-security
ms.date: 01/29/2021
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- m365initiative-defender-office365
ms.topic: how-to
ms.custom:
- autoir
ms.subservice: mdo
ms.openlocfilehash: 6a7779ced613f5e6c175c2cd6a7181c2c4a00fa0
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68082889"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a>Otomatik araştırma ve yanıt özelliklerinde hatalı pozitif/negatifleri bildirme

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Uygulandığı öğe**
- [Office 365 için Microsoft Defender plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[Office 365'daki otomatik araştırma ve yanıt (AIR) özellikleri](automated-investigation-response-office.md) bir şeyi atladıysa veya yanlış algıladıysa, güvenlik operasyonları ekibinizin bunu düzeltmek için atabileceği adımlar vardır. Bu tür eylemler şunlardır:

- [Microsoft'a hatalı pozitif/negatif raporlama](#report-a-false-positivenegative-to-microsoft-for-analysis);
- [Uyarıları ayarlama](#adjust-an-alert-to-prevent-false-positives-from-recurring) (gerekirse); Ve
- [Gerçekleştirilen düzeltme eylemleri geri alınıyor](#undo-a-remediation-action).

Bu makaleyi kılavuz olarak kullanın.

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a>Hatalı pozitif/negatifi analiz için Microsoft'a bildirme

Office 365 için Microsoft Defender'da AIR bir e-posta iletisini, e-posta ekini, e-posta iletisindeki URL'yi veya Office dosyasındaki bir URL'yi kaçırdıysa, [şüpheli istenmeyen posta, kimlik avı, URL'ler ve dosyaları Office 365 tarama için Microsoft'a gönderebilirsiniz](admin-submission.md).

Ayrıca [kötü amaçlı yazılım analizi için Microsoft'a dosya gönderebilirsiniz](https://www.microsoft.com/wdsi/filesubmission).

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a>Hatalı pozitif sonuçların yinelenmesini önlemek için uyarıyı ayarlama

Bir uyarı geçerli kullanımla tetiklenirse veya uyarı yanlışsa [, Uyarıları Cloud Apps için Defender portalında yönetebilirsiniz](/cloud-app-security/managing-alerts).

Kuruluşunuz Office 365 ek olarak [Uç Nokta için Microsoft Defender](/windows/security/threat-protection) kullanıyorsa ve dosya, IP adresi, URL veya etki alanı güvenli olsa bile bir cihazda kötü amaçlı yazılım olarak değerlendirilirse, [cihazınız için "İzin Ver" eylemiyle özel bir gösterge oluşturabilirsiniz](/windows/security/threat-protection/microsoft-defender-atp/manage-indicators).

## <a name="undo-a-remediation-action"></a>Düzeltme eylemini geri alma

Çoğu durumda, bir e-posta iletisinde, e-posta ekinde veya URL'de düzeltme eylemi yapıldıysa ve öğe aslında bir tehdit değilse, güvenlik operasyonları ekibiniz düzeltme eylemini geri alabilir ve hatalı pozitif sonucun yinelenmesini önlemek için adımlar atabilir. Bir eylemi geri almak [için bir araştırma için](#undo-an-action-in-the-action-center) [Tehdit Gezgini'ni](#undo-an-action-using-threat-explorer) veya Eylemler sekmesini kullanabilirsiniz.

> [!IMPORTANT]
> Aşağıdaki görevleri gerçekleştirmeye çalışmadan önce gerekli izinlere sahip olduğunuzdan emin olun.

### <a name="undo-an-action-using-threat-explorer"></a>Tehdit Gezgini'nin kullanıldığı bir eylemi geri alma

Tehdit Gezgini ile güvenlik operasyonları ekibiniz bir eylemden etkilenen bir e-posta bulabilir ve eylemi geri alabilir.

|Senaryo|Geri Alma Seçenekleri|Daha fazla bilgi|
|---|---|---|
|E-posta iletisi kullanıcının Gereksiz Email klasörüne yönlendirildi|<ul><li>İletiyi kullanıcının Silinmiş Öğeler klasörüne taşıma</li><li>İletiyi kullanıcının Gelen Kutusuna taşıma</li><li>İletiyi silme</li></ul>|[Office 365'de teslim edilen kötü amaçlı e-postayı bulma ve araştırma](investigate-malicious-email-that-was-delivered.md)|
|E-posta iletisi veya dosya karantinaya alındı|<ul><li>E-postayı veya dosyayı serbest bırakma</li><li> E-postayı veya dosyayı silme</li></ul>|[Karantinaya alınan iletileri yönetici olarak yönetme](manage-quarantined-messages-and-files.md)|

### <a name="undo-an-action-in-the-action-center"></a>İşlem merkezindeki bir eylemi geri alma

İşlem merkezinde, gerçekleştirilen düzeltme eylemlerini görebilir ve eylemi geri alabilirsiniz.

1. konumundaki Microsoft 365 Defender portalında <https://security.microsoft.com>İşlem merkezi'ni seçerek **İşlem merkezine** gidin. Doğrudan İşlem merkezine gitmek için kullanın <https://security.microsoft.com/action-center/>.
2. İşlem merkezinde **Geçmiş** sekmesini seçerek tamamlanan eylemlerin listesini görüntüleyin.
3. Bir öğe seçin. Açılır pencere bölmesi açılır.
4. Açılır bölmede **Geri Al'ı** seçin. (Yalnızca geri alınabilen eylemlerde **Geri Al** düğmesi olur.)

## <a name="see-also"></a>Ayrıca bkz.

- [Office 365 için Microsoft Defender](defender-for-office-365.md)
- [Office 365 için Microsoft Defender'de otomatik araştırma](office-365-air.md)
