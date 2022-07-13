---
title: 7. Adım. Bilgi koruma yetenekleriyle veri kaybı önleme (DLP) uygulayın
ms.author: bcarter
author: brendacarter
f1.keywords:
- Endpoint dlp
- data loss prevention
- dlp policies
manager: dougeby
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.localizationpriority: high
ms.collection:
- endpoint dlp
- data loss prevention
- dlp policies
- M365-security-compliance
- m365solution-managedevices
- m365solution-scenario
- zerotrust-solution
ms.custom: ''
keywords: ''
description: Kuruluşunuz için DLP ilkeleri oluşturmak üzere bilgi koruma ve idare ekibinizle birlikte çalışarak Uç Nokta DLP'sini uygulayın.
ms.openlocfilehash: d8544a0ddeb0327d50baa87407a152c559afcb74
ms.sourcegitcommit: 61b22df76e0f81e5ef11c587b129287886151c79
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2022
ms.locfileid: "66749231"
---
# <a name="step-7-implement-data-loss-prevention-dlp-with-information-protection-capabilities"></a>7. Adım. Bilgi koruma yetenekleriyle veri kaybı önleme (DLP) uygulayın


Kuruluşunuz verilerinizi anlamak, veri duyarlılığı şeması geliştirmek ve şemayı uygulamak için zaten zaman ayırmışsa, Microsoft Purview veri kaybı önleme (DLP) ilkelerini kullanarak bu şemanın öğelerini uç noktalara genişletmeye hazır olabilirsiniz. 

Uç nokta veri kaybı önleme (Endpoint DLP) şu anda şunlar için geçerlidir:
- Windows 10, Windows 11
- macOS

DLP ilkeleri, bilgi koruma ve idare ekibiniz tarafından oluşturulur. Her DLP ilkesi, hassas bilgi türleri veya etiketler gibi bir veri kümesi içindeki hangi öğelerin aranacağını ve bu verilerin nasıl korunacağını tanımlar. 

Örneğin, DLP ilkesi pasaport numarası gibi kişisel verileri arayabilir. DLP ilkesi, bir pasaport numarasının kuruluşunuz dışındaki kişilerle paylaşılması gibi, ilkenin eyleme geçmelerini tetikleyen bir koşul içerir. İlkenin gerçekleştirilen eylemi de yapılandırılabilir. Seçenekler yalnızca eylemi yöneticilere raporlama, kullanıcıları uyarma ve hatta verilerin paylaşılmasını engelleme arasında değişir.

DLP ilkesi, exchange e-postası ve SharePoint siteleri gibi ilkenin uygulanacağı konumu da belirtir. Yöneticilerin kullanabileceği konumlardan biri cihazlardır. Cihazlar seçiliyse, ilkenin hangi kullanıcılara ve kullanıcı gruplarına uygulanacağını belirtebilirsiniz. İlkenin dışında tutulacak kullanıcıları ve kullanıcı gruplarını da belirtebilirsiniz.

Bilgi koruma ve idare ekibiniz DLP ilkelerini uç noktalara genişletmeye hazırsa, Uç Nokta DLP için cihazları etkinleştirmek, DLP ilkelerini test etmek ve ayarlamak, kullanıcıları eğitmek ve sonuçları izlemek için onlarla koordine olmanız gerekir. 

![Cihaz yöneticisi için uç nokta DLP adımları](../media/devices/endpoint-dlp-steps.png#lightbox)


Bilgi koruma ekibinizle çalışmak için aşağıdaki adımları kullanın.


|Adım  |Açıklama  |
|---------|---------|
|1     |  [Uç nokta veri kaybını önleme hakkında bilgi edinin](../compliance/endpoint-dlp-learn-about.md).        |
|2     | Uç Nokta DLP için cihazları etkinleştirin. Cihazlarınızı Uç Nokta için Microsoft Defender'a eklerseniz, cihazlarınız Uç Nokta DLP için zaten etkindir. Cihazlarınız Uç Nokta için Defender'a eklenmemişse yönergeler için bkz. [Uç nokta veri kaybı önlemeyi kullanmaya başlama](../compliance/endpoint-dlp-getting-started.md) .|
|3     |   İlkeleri tanımlamak, test etmek ve ayarlamak için bilgi koruma ve idare ekibinizle birlikte çalışın. Bu, sonuçları izlemeyi içerir. Şu kaynaklara bakın:<br>- [Uç nokta veri kaybı önlemeyi kullanma](../compliance/endpoint-dlp-using.md)<br>- [Veri kaybı önleme raporlarını görüntüleme](../compliance/view-the-dlp-reports.md)      |
