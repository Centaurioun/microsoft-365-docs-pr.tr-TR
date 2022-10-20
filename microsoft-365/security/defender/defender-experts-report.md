---
title: Microsoft 365 Defender'da Avcılık için Defender Uzmanları raporunu anlama
ms.reviewer: ''
description: Avcılık hizmeti için Defender Uzmanları, ortamınızda ortaya çıkan tüm tehditleri anlamanıza yardımcı olmak için aylık raporlar yayımlar
keywords: analist raporu, defender uzmanlar raporu, algılamalar, defender uzman bildirimi, avcılık, bildirimler, tehdit kategorileri, avcılık raporları
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: vpattnaik
author: vpattnai
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier1
ms.topic: conceptual
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 44c12c77e141490df39b774e3c3d5f399cb2310d
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68645725"
---
# <a name="understand-the-defender-experts-for-hunting-report-in-microsoft-365-defender"></a>Microsoft 365 Defender'da Avcılık için Defender Uzmanları raporunu anlama

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Microsoft Tehdit Avcılığı için Defender Uzmanları, Microsoft 365 Defender müşterilerin karşılaştıkları önemli tehditleri anlamasına yardımcı olmak için insan zekasını ve uzman tarafından eğitilmiş teknolojiyi katmanlar. Defender Uzman'ın tehdit avcılığı becerileri, tehdit ortamının kapsamlı bir şekilde anlaşılması ve yeni ortaya çıkan tehditlerle ilgili bilgilerin ortamınızdaki bu tehditleri belirlemenize, önceliklendirmenize ve ele almanıza nasıl yardımcı olabileceğini gösterir. 

Avcılık için Defender Uzmanları, Microsoft 365 Defender ürünleriniz tarafından oluşturulan uyarıların yanı sıra, ortamınızda ortaya çıkan tüm tehditleri anlamanıza yardımcı olmak için aylık raporlar yayımlar.

Microsoft 365 Defender portalınızda en son raporu görüntülemek için **Raporlar'a** gidin,**Avcılık raporu için Defender Uzmanları'nı** >  seçin.

## <a name="scan-the-defender-experts-for-hunting-report-to-know-what-to-prioritize"></a>Hangi önceliklerin belirleneceklerini öğrenmek için Defender Uzmanlarını Tehdit Avcılığı raporunu tarayın

Raporun her bölümü, Defender Uzmanlarımızın ortamınızda bulduğu tehditler hakkında daha fazla içgörü sağlamak üzere tasarlanmıştır. Raporlar aşağıdaki tabloda açıklanan bölümleri içerir:

| Rapor bölümü | Açıklama |
|--|--|
| Avlandı ve önceliklendirildi | Ortamınızda bulunan olası siber güvenlik sorunlarının toplam sayısı. |
| Araştır | Doğasını ve kapsamını belirlemek için daha fazla analiz gerektiren siber güvenlik sorunlarının sayısı. |
| Bildirimli (Bildirimi görüntüle) | Defender Uzmanlarının gönderdiği Defender Uzman Bildirimlerinin sayısı. Bu bildirimler, ortamınızda aciliyet ve etki temelinde önceliklendirilmek zorunda olan araştırılan olası tehdit etkinlikleriyle ilgilidir. |
| MITRE ATT&CK taktikleri gözlemlendi | Ortamınızda gözlemlenen ve [MITRE ATT&CK çerçevesine](https://attack.mitre.org/) göre eşlenen saldırı taktikleri ve teknikleri sayısı. Bu bölümde her taktiğin kaç saldırıya ulaştığı görselleştirildiğinden, önce daha fazla ilerleme gösterenleri gözden geçirme gibi uygun eylemleri gerçekleştirebilirsiniz. |
| Gözlenen tehdit kategorileri | Kategoriler, ortamınızda gözlemlenen en önemli tehditleri ve riskleri gösterir. Tehditlerin bilinen özelliklerine, davranışlarına ve olası etkilerine göre güvenlik duruşunuzu daha fazla değerlendirmenize ve değerlendirmenize yardımcı olmak için en kritik kategoriler vurgulanır. Ayrıca ele alınması gereken acil görevlere odaklanmanıza ve öncelik vermenizi sağlar. |

Örnek raporun aşağıdaki ekran görüntüsüne bakın:

![Microsoft 365 Defender portalındaki Microsoft Tehdit Avcılığı için Defender Uzmanları raporunun ekran görüntüsü.](../../media/mte/defenderexperts/defender-experts-report.png)

## <a name="view-defender-experts-notifications"></a>Defender Uzman Bildirimlerini Görüntüleme

Defender Uzmanlar Bildirimi, ortamınızda gözlemlenen önemli tehdit etkinliği Defender Uzmanlar'ı açıklar ve kuruluşunuzu düzeltmek ve savunmak için öneriler sağlar.

Avcılık için Defender Uzmanları raporları, Defender Uzmanlarımızın seçtiğiniz süre için gönderdiği toplam Defender Uzmanları Bildirimi sayısını sağlar. Bu bildirimleri görüntülemek için **Bildirim'in** yanındaki **Bildirimi görüntüle'yi** seçin.

Bu bağlantı sizi Microsoft 365 Defender olaylar sayfasına yönlendirir. Avcılık uyarıları için Defender Uzmanı veya Defender Uzmanları Bildirimleri **, Defender Uzmanları** ile etiketlenmiştir.

> [!NOTE]
> **Bildirim görüntüle** bağlantısı yalnızca **Bildirimde** görüntülenen değer en az 1 ise görüntülenir.

## <a name="identify-potential-attack-entry-points-and-other-security-weak-spots"></a>Olası saldırı giriş noktalarını ve diğer güvenlik zayıf noktalarını belirleme

MITRE ATT&CK taktikleri, her saldırı aşamasında ulaşmaya çalıştıkları saldırgan hedefleri temsil eder. Raporun **bölümünde gözlemlenen MITRE ATT&CK taktikleri** , ulaştıkları aşamaya karşı saldırının ilerleme durumunu izler:

1. Keşif
2. Kaynak Geliştirme
3. İlk erişim
4. Yürütme
5. Kalıcılık
6. Ayrıcalık yükseltme
7. Savunma kaçamak
8. Kimlik bilgisi erişimi
9. Keşif
10. Yanal hareket
11. Koleksiyon
12. Komut ve denetim
13. Sızdırma
14. Etki

Avcılık için Defender Uzmanları tarafından yapılan Microsoft 365 Defender ve araştırmalardan gelen sinyaller, çubuk grafikte gösterilen bu taktiklerin tanımlanmasına yardımcı olur. Bu grafik, dalgalanmanın nerede olduğunu görselleştirmenize yardımcı olur ve ilgili kapsama ve düzeltme eylemlerini planlamak için ihtiyacınız olan bilgileri sağlar.

## <a name="know-and-understand-the-prevalent-threats-in-your-environment"></a>Ortamınızdaki yaygın tehditleri öğrenme ve anlama

Tehdit kategorileri, ortamınıza yönelik bu tehditleri önlemek veya azaltmak için etkilerini değerlendirmek ve değerlendirmek ve stratejiler geliştirmek için güvenlik tehditlerini tanımlamaya ve sınıflar halinde düzenlemeye yardımcı olur. Raporun **gözlenen Tehdit kategorileri** bölümünde, ortamınızda algılanan önemli risklere ve tehditlere sahip bir çubuk grafik gösterilir ve bu da maruz kalmanızın kapsamını ve kapsamını anlamanıza yardımcı olur.

Kullanılabilir çeşitli tehdit kategorileri arasında, MITRE ATT&CK çerçevesinin kapsamına alınmadığı için aşağıdaki kategoriler dikkatle seçilir:

- Fidye Yazılımı
- Malware
- Silahlaştırma
- Istismar
- Teslim

Düzeltmeye, çubuk grafikte gösterildiği gibi en çok etkilenen kategoriye göre öncelik vekleyebilirsiniz.
