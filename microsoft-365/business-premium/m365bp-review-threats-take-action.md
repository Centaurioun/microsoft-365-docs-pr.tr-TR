---
title: Cihazlarda algılanan tehditleri gözden geçirin ve işlem yapın
f1.keywords: NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.topic: conceptual
ms.service: microsoft-365-security
ms.subservice: other
ms.date: 09/15/2022
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid: MET150
description: Windows cihazlarınızda Microsoft Defender Virüsten Koruma tarafından algılanan tehditleri gözden geçirmeyi ve yönetmeyi öğrenin.
ms.openlocfilehash: 446a51c0d6bb1c595ae40674cffb1108f9f89a4b
ms.sourcegitcommit: c29af68260ba8676083674b3c70209bff2c2e362
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/16/2022
ms.locfileid: "67739928"
---
# <a name="review-detected-threats"></a>Algılanan tehditleri gözden geçirme

Kötü amaçlı bir dosya veya yazılım algılanır algılanmaz, Microsoft Defender dosyayı engeller ve çalışmasını engeller. Bulut tabanlı koruma açıkken, diğer cihazlarınızın ve kullanıcılarınızın da korunması için virüsten koruma ve kötü amaçlı yazılımdan koruma altyapısına yeni algılanan tehditler eklenir.

Microsoft Defender Virüsten Koruma aşağıdaki tehdit türlerini algılar ve bu tehditlere karşı korur:

- Cihazlarda virüsler, kötü amaçlı yazılımlar ve web tabanlı tehditler
- Kimlik avı girişimleri
- Veri hırsızlığı girişimleri

BT uzmanı/yöneticisi olarak, Microsoft 365 yönetim merkezi Intune [kaydedilen Windows cihazlarında](/mem/intune/enrollment/device-enrollment) tehdit algılamaları hakkındaki bilgileri görüntüleyebilirsiniz. Özet bilgileri görürsünüz, örneğin:

- Kaç cihaz virüsten koruma gerekiyor?
- Kaç cihazın güvenlik ilkeleriyle uyumlu olmadığını
- Şu anda etkin, azaltılmış veya çözümlenmiş kaç tehdit var?

## <a name="actions-you-can-take"></a>Gerçekleştirebileceğiniz eylemler

Belirli tehditler veya cihazlar hakkındaki ayrıntıları görüntülediğinizde önerileri ve gerçekleştirebileceğiniz bir veya daha fazla eylemi görürsünüz. Aşağıdaki tabloda, görebileceğiniz eylemler açıklanmaktadır.<br><br>

| Eylem | Açıklama |
|--|--|
| Korumayı yapılandırma | Tehdit koruma ilkelerinizin yapılandırılması gerekir. İlke yapılandırma sayfanıza gitmek için bağlantıyı seçin.<br><br>Yardıma mı ihtiyacınız var? Bkz. [Microsoft Intune uç nokta güvenlik ilkeleriyle cihaz güvenliğini yönetme](/mem/intune/protect/endpoint-security-policy). |
| İlkeyi güncelleştirme | Virüsten koruma ve gerçek zamanlı koruma ilkelerinizin güncelleştirilmiş veya yapılandırılmış olması gerekir. İlke yapılandırma sayfasına gitmek için bağlantıyı seçin.<br><br>Yardıma mı ihtiyacınız var? Bkz. [Microsoft Intune uç nokta güvenlik ilkeleriyle cihaz güvenliğini yönetme](/mem/intune/protect/endpoint-security-policy). |
| Hızlı tarama çalıştırma | Kayıt defteri anahtarları ve bilinen Windows başlangıç klasörleri gibi kötü amaçlı yazılımların kaydedilebileceği yaygın konumlara odaklanarak cihazda hızlı bir virüsten koruma taraması başlatır. |
| Tam tarama çalıştırma | Cihazda tam virüsten koruma taraması başlatır ve kötü amaçlı yazılımların kaydedilebileceği yaygın konumlara ve cihazdaki her dosya ve klasöre odaklanır. Sonuçlar [Microsoft Endpoint Manager'e](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) gönderilir. |
| Virüsten korumayı güncelleştirme | Cihazın virüsten koruma ve kötü amaçlı yazılımdan koruma için [güvenlik bilgileri güncelleştirmelerini](https://go.microsoft.com/fwlink/?linkid=2149926) alması gerekir. |
| Cihazı yeniden başlatma | Bir Windows cihazını beş dakika içinde yeniden başlatmaya zorlar.<br><br>**ÖNEMLİ:** Cihaz sahibine veya kullanıcıya yeniden başlatma bildirimi otomatik olarak bildirilmez ve kaydedilmemiş çalışmayı kaybedebilir. |

## <a name="view-and-manage-threat-detections-in-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender portalında tehdit algılamalarını görüntüleme ve yönetme

1. ([Microsoft 365 Defender portalına](https://security.microsoft.com)) gidin ve oturum açın.

1. Tüm geçerli tehditleri görmek için gezinti bölmesinde **Tehdit Analizi'ni** seçin. Bunlar tehdit önem derecesine ve türüne göre kategorilere ayrılmıştır.

1. Tehdit hakkında daha fazla ayrıntı görmek için bir tehdide tıklayın.

1. Tabloda, uyarıları bir dizi ölçüte göre filtreleyebilirsiniz.

## <a name="manage-threat-detections-in-microsoft-intune"></a>Microsoft InTune'da tehdit algılamalarını yönetme

Tehdit algılamalarını yönetmek için Microsoft Endpoint Manager'ı da kullanabilirsiniz. İlk olarak, Windows, iOS veya Android gibi tüm cihazların Intune (Microsoft Endpoint Manager'nin bir parçası) olarak [kaydedilmesi](/mem/intune/enrollment/windows-enrollment-methods) gerekir.

1. adresinden Microsoft Endpoint Manager yönetim merkezine <a href="https://go.microsoft.com/fwlink/p/?linkid=2150463" target="_blank">https://endpoint.microsoft.com</a> gidin ve oturum açın.

2. Gezinti bölmesinde **Uç nokta güvenliği'ni** seçin.

3. **Yönet'in** altında **Virüsten Koruma'yı** seçin. **Özet**, **İyi durumda olmayan uç noktalar** ve **Etkin kötü amaçlı yazılım** sekmelerini görürsünüz.

4. Kullanılabilir sekmelerdeki bilgileri gözden geçirin ve gerekli eylemleri gerçekleştirin.

Örneğin, cihazların **Etkin kötü amaçlı yazılım** sekmesinde listelendiğini varsayalım. Bir cihaz seçtiğinizde **, Yeniden Başlatma**, **Hızlı Tarama**, **Tam Tarama**, **Eşitleme** veya **İmzaları güncelleştirme** gibi bazı eylemleriniz olur. Bu cihaz için bir eylem seçin.

Aşağıdaki tabloda, Microsoft Endpoint Manager'de görebileceğiniz eylemler açıklanmaktadır.<br><br>

| Eylem | Açıklama |
|--|--|
| Yeniden başlatma | Bir Windows cihazını beş dakika içinde yeniden başlatmaya zorlar.<br><br>**ÖNEMLİ:** Cihaz sahibine veya kullanıcıya yeniden başlatma bildirimi otomatik olarak bildirilmez ve kaydedilmemiş çalışmayı kaybedebilir. |
| Hızlı Tarama | Kayıt defteri anahtarları ve bilinen Windows başlangıç klasörleri gibi kötü amaçlı yazılımların kaydedilebileceği yaygın konumlara odaklanarak cihazda hızlı bir virüsten koruma taraması başlatır. Sonuçlar [Microsoft Endpoint Manager'e](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) gönderilir. |
| Tam Tarama | Cihazda tam virüsten koruma taraması başlatır ve kötü amaçlı yazılımların kaydedilebileceği yaygın konumlara ve cihazdaki her dosya ve klasöre odaklanır. Sonuçlar [Microsoft Endpoint Manager'e](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) gönderilir. |
| Eşitleme | Bir cihazın Intune (Microsoft Endpoint Manager'ın bir parçası) ile iade etmelerini gerektirir. Cihaz iade ettiğinde, cihaza atanan bekleyen eylemleri veya ilkeleri alır. |
| İmzaları güncelleştirme | Cihazın virüsten koruma ve kötü amaçlı yazılımdan koruma için [güvenlik bilgileri güncelleştirmelerini](https://go.microsoft.com/fwlink/?linkid=2149926) alması gerekir. |

> [!TIP]
> Daha fazla bilgi için bkz. [Cihazlar için uzak eylemler](/mem/intune/protect/endpoint-security-manage-devices#remote-actions-for-devices).

## <a name="how-to-submit-a-file-for-malware-analysis"></a>Kötü amaçlı yazılım analizi için dosya gönderme

Kaçırıldığını veya yanlış şekilde kötü amaçlı yazılım olarak sınıflandırıldığını düşündüğünüz bir dosyanız varsa, bu dosyayı kötü amaçlı yazılım analizi için Microsoft'a gönderebilirsiniz. Kullanıcılar ve BT yöneticileri analiz için bir dosya gönderebilir. adresini ziyaret edin [https://www.microsoft.com/wdsi/filesubmission](https://www.microsoft.com/wdsi/filesubmission).

## <a name="see-also"></a>Ayrıca bkz.

[İş için Microsoft 365 planlarının güvenliğini sağlamaya yönelik en iyi yöntemler](../admin/security-and-compliance/secure-your-business-data.md)

[İş için Microsoft Defender genel bakış](../security/defender-business/mdb-overview.md) (Defender for Business, 1 Mart 2022'de başlayarak Microsoft 365 İş Ekstra müşterilerine dağıtılıyor)
