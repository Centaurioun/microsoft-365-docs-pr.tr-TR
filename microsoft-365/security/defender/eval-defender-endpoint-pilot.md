---
title: Pilot Uç Nokta için Microsoft Defender
description: Pilot grubu doğrulama ve özellikleri deneme de dahil olmak üzere Uç Nokta için Microsoft Defender(MDE) için pilot çalıştırmayı öğrenin.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: v-jweston
author: jweston-1
ms.date: 07/09/2021
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
- zerotrust-solution
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: c12d1bca36884a7b43580b0685f38df99e51ba1d
ms.sourcegitcommit: 61b22df76e0f81e5ef11c587b129287886151c79
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2022
ms.locfileid: "66750417"
---
# <a name="pilot-microsoft-defender-for-endpoint"></a>Pilot Uç Nokta için Microsoft Defender

Bu makale, Uç Nokta için Microsoft Defender için pilot çalıştırma sürecinde size yol gösterir. 

Uç Nokta için Microsoft Defender için pilotu ayarlamak ve yapılandırmak için aşağıdaki adımları kullanın. 

:::image type="content" source="../../media/defender/m365-defender-endpoint-pilot-steps.png" alt-text="Microsoft Defender değerlendirme ortamına Kimlik için Microsoft Defender ekleme adımları" lightbox="../../media/defender/m365-defender-endpoint-pilot-steps.png":::

- Adım 1. Pilot grubu doğrulama
- Adım 2. Özellikleri deneyin

Uç Nokta için Microsoft Defender pilot Uç Nokta için Microsoft Defender, kuruluşunuzun tamamını eklemeden önce birkaç cihazı hizmete eklemeyi seçebilirsiniz.  

Ardından, saldırı simülasyonlarını çalıştırma ve Uç Nokta için Defender'ın kötü amaçlı etkinlikleri nasıl ortaya çıkardığını ve verimli bir yanıt vermenizi nasıl sağladığını görme gibi kullanılabilir özellikleri deneyebilirsiniz. 

## <a name="step-1-verify-pilot-group"></a>Adım 1. Pilot grubu doğrulama
[Değerlendirmeyi etkinleştir](eval-defender-endpoint-enable-eval.md) bölümünde özetlenen ekleme adımlarını tamamladıktan sonra cihazları yaklaşık bir saat sonra Cihaz envanteri listesinde görmeniz gerekir. 

Eklenen cihazlarınızı gördüğünüzde, özellikleri denemeye devam edebilirsiniz. 

## <a name="step-2-try-out-capabilities"></a>Adım 2. Özellikleri deneyin
Artık bazı cihazları eklemeyi tamamladığınıza ve bunların hizmete bildirildiğini doğruladığınıza göre, hemen kullanıma sunulan güçlü özellikleri deneyerek ürünü tanıyın.

Pilot sırasında, karmaşık yapılandırma adımlarından geçmeden ürünü çalışır durumda görmek için bazı özellikleri denemeye kolayca başlayabilirsiniz.

Panolara göz atarak başlayalım.

### <a name="view-the-device-inventory"></a>Cihaz envanterini görüntüleme
Cihaz envanteri, ağınızdaki uç noktaların, ağ cihazlarının ve IoT cihazlarının listesini göreceğiniz yerdir. Ağınızdaki cihazların görünümünü sağlamakla kalmaz, aynı zamanda etki alanı, risk düzeyi, işletim sistemi platformu ve en riskli cihazların kolay tanımlanması için diğer ayrıntılar gibi bunlar hakkında ayrıntılı bilgi verir.

### <a name="view-the-threat-and-vulnerability-management-dashboard"></a>Tehdit ve güvenlik açığı yönetimi panosunu görüntüleme 
Tehdit ve güvenlik açığı yönetimi, kuruluş için en acil ve en yüksek riski oluşturan zayıflıklara odaklanmanıza yardımcı olur. Panodan kuruluşun maruz kalma puanı, Cihazlar için Microsoft Güvenli Puanı, cihaz açığa çıkarma dağıtımı, en iyi güvenlik önerileri, en savunmasız yazılımlar, en iyi düzeltme etkinlikleri ve en çok kullanıma sunulan cihaz verilerinin üst düzey bir görünümünü elde edin. 

### <a name="run-a-simulation"></a>Simülasyon çalıştırma
Uç Nokta için Microsoft Defender, pilot cihazlarınızda çalıştırabileceğiniz ["Kendiniz Yapın" saldırı senaryolarıyla](https://securitycenter.windows.com/tutorials) birlikte gelir.  Her belgede işletim sistemi ve uygulama gereksinimlerinin yanı sıra bir saldırı senaryosuna özgü ayrıntılı yönergeler bulunur. Bu betikler güvenlidir, belgelenir ve kullanımı kolaydır. Bu senaryolar Uç Nokta için Defender özelliklerini yansıtır ve araştırma deneyiminde size yol gösterir.

Sağlanan simülasyonlardan herhangi birini çalıştırmak için en az [bir yerleşik cihaza](../defender-endpoint/onboard-configure.md) ihtiyacınız vardır.

1. **Yardım** > **Benzetimleri & öğreticilerinde**, kullanılabilir saldırı senaryolarından hangisinin benzetimini yapmak istediğinizi seçin:

   - **Senaryo 1: Belge arka kapı bırakma** - sosyal olarak tasarlanmış bir yem belgesinin teslimini simüle eder. Belge, saldırganlara denetim sağlayan özel olarak hazırlanmış bir arka kapı başlatır.

   - **Senaryo 2: Dosyasız saldırıda PowerShell betiği** - PowerShell'i kullanan, saldırı yüzeyini azaltmayı ve kötü amaçlı bellek etkinliğinin cihaz öğrenmesi algılamasını gösteren dosyasız bir saldırının benzetimini sağlar.

   - **Senaryo 3: Otomatik olay yanıtı - güvenlik olayı yanıt** kapasitenizi ölçeklendirmek için ihlal yapıtlarını otomatik olarak avlayan ve düzelten otomatik araştırmayı tetikler.

2. Seçtiğiniz senaryoyla birlikte sağlanan ilgili izlenecek yol belgesini indirin ve okuyun.

3. **Yardım** > **Simülasyonları & öğreticilerine** giderek simülasyon dosyasını indirin veya simülasyon betiğini kopyalayın. Dosyayı veya betiği test cihazına indirmeyi seçebilirsiniz, ancak zorunlu değildir.

4. Simülasyon dosyasını veya betiği, izlenecek yol belgesinde açıklandığı gibi test cihazında çalıştırın.

> [!NOTE]
> Simülasyon dosyaları veya betikler saldırı etkinliğini taklit eder ancak aslında zararsızdır ve test cihazına zarar vermez veya tehlikeye atmaz.

## <a name="next-steps"></a>Sonraki adımlar
[değerlendirme Microsoft Defender for Cloud Apps](eval-defender-mcas-overview.md)

[Değerlendirme Uç Nokta için Microsoft Defender](eval-defender-endpoint-overview.md) için genel bakışa dönün

[Değerlendirme ve pilot Microsoft 365 Defender](eval-overview.md) genel bakışa dönün
