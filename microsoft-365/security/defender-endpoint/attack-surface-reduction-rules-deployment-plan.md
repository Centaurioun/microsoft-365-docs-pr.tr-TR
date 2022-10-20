---
title: Saldırı yüzeyini azaltma (ASR) kuralları dağıtım planı
description: Saldırı yüzeyi azaltma (ASR) kuralları dağıtımınızı planlamak için rehberlik sağlar.
keywords: Saldırı yüzeyi azaltma kuralları dağıtımı, Uç Nokta için Microsoft Defender (MDE) ASR dağıtımı, Defender ASR kuralları, asr kurallarını etkinleştirme, ASR'yi yapılandırma, konak yetkisiz erişim önleme sistemi, koruma kuralları, kötüye kullanım önleme kuralları, kötüye kullanım önleme kuralları, bulaşma önleme kuralları, Uç Nokta için Microsoft Defender, ASR kurallarını yapılandırma
search.product: eADQiWindows 10XVcnh
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.service: microsoft-365-security
ms.subservice: mde
ms.localizationpriority: medium
audience: ITPro
author: jweston-1
ms.author: v-jweston
ms.reviewer: oogunrinde, sugamar
manager: dansimp
ms.custom: asr
ms.topic: conceptual
ms.collection:
- m365-security
- m365solution-asr-rules
- highpri
- tier1
ms.date: 1/18/2022
search.appverid: met150
ms.openlocfilehash: 2682fa5f877e429f515aa16b647098c5fe14c188
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68638840"
---
# <a name="plan-attack-surface-reduction-asr-rules-deployment"></a>Saldırı yüzeyini azaltma (ASR) kuralları dağıtım planı

Uç Nokta için Microsoft Defender (MDE) saldırı yüzeyi azaltma (ASR) kurallarını test etmeden veya etkinleştirmeden önce dağıtımınızı nasıl dağıtabileceğinizi planlamanız gerekir. Dikkatli planlama yalnızca ASR kuralları dağıtımınızın test edilmesine ve etkinleştirilmesine yardımcı olmakla kalmaz, AYNı zamanda ASR kuralları özel durumlarını yapılandırdığınızda da yararlı olur. Saldırı yüzeyi azaltma (ASR) kurallarını test etmek veya etkinleştirmek için doğru iş birimiyle başlamak önemlidir. Belirli bir iş birimindeki küçük bir grup kişiyle başlamak istersiniz. Belirli bir iş birimi içinde, ASR kuralları hakkında gerçek dünya etkisi sağlayabilecek ve uygulamanızı ayarlamanıza yardımcı olabilecek bazı ASR şampiyonlarını tanımlayabilirsiniz.

> :::image type="content" source="images/asr-rules-planning-steps.png" alt-text="ASR kuralları planlama adımları. Uç Nokta için Microsoft Defender (MDE) ASR kurallarını test etmeden veya MDE ASR kurallarını etkinleştirmeden önce hazırlık." lightbox="images/asr-rules-planning-steps.png":::

> [!IMPORTANT]
>
> ASR kurallarını planlama, denetleme ve etkinleştirme sürecinde ilerlerken aşağıdaki üç _standart koruma kuralını_ etkinleştirmeniz önerilir. İki ASR kuralı türü hakkında önemli ayrıntılar için bkz [. Türe göre saldırı yüzeyi azaltma](attack-surface-reduction-rules-reference.md#attack-surface-reduction-rules-by-type) kuralları.
>
> - [Windows yerel güvenlik yetkilisi alt sisteminden (lsass.exe) kimlik bilgilerinin çalınmalarını engelleme](attack-surface-reduction-rules-reference.md#block-credential-stealing-from-the-windows-local-security-authority-subsystem)
> - [Güvenlik açığı bulunan imzalı sürücülerin kötüye kullanılması engellendi](attack-surface-reduction-rules-reference.md#block-abuse-of-exploited-vulnerable-signed-drivers)
> - [Windows Yönetim Araçları (WMI) olay aboneliği aracılığıyla kalıcılığı engelleme](attack-surface-reduction-rules-reference.md#block-persistence-through-wmi-event-subscription)
>
> Standart koruma kurallarını genellikle son kullanıcı üzerinde en az fark edilebilir etkiyle etkinleştirebilirsiniz. Standart koruma kurallarını etkinleştirmek için kolay bir yöntem için bkz. [Basitleştirilmiş standart koruma seçeneği](attack-surface-reduction-rules-report.md#simplified-standard-protection-option).

## <a name="start-your-asr-rules-deployment-with-the-right-business-unit"></a>ASR kuralları dağıtımınızı doğru iş birimiyle başlatma

ASR kuralları dağıtımınızı dağıtmak için iş birimini nasıl seçeceğiniz aşağıdakiler gibi faktörlere bağlıdır:

- İş biriminin boyutu
- ASR kural şampiyonlarının kullanılabilirliği  
- Dağıtımı ve kullanımı:
  - Yazılım
  - Paylaşılan klasörler
  - Betiklerin kullanımı
  - Office makroları
  - ASR kurallarından etkilenen diğer varlıklar

İş gereksinimlerinize bağlı olarak, yazılımın, paylaşılan klasörlerin, betiklerin, makroların vb. kapsamlı bir örneklemesini almak için birden çok iş birimi dahil etmeye karar vekleyebilirsiniz. Buna karşılık, ilk ASR kuralları dağıtımınızın kapsamını tek bir iş birimiyle sınırlamaya karar verebilir, ardından ASR kuralları dağıtım işleminin tamamını diğer iş birimlerinizle tek tek yinelemeye karar verebilirsiniz.

## <a name="identify-asr-rules-champions"></a>ASR kuralları şampiyonlarını belirleme

ASR kuralları şampiyonları, kuruluşunuzda ön test ve uygulama aşamalarında ilk ASR kuralları dağıtımınıza yardımcı olacak üyelerdir. Şampiyonlarınız genellikle teknik açıdan daha usta olan ve aralıklı iş akışı kesintileri tarafından raydan çıkarılmayan çalışanlardır. Şampiyonların katılımı, ASR kuralları dağıtımının kuruluşunuza daha geniş kapsamlı bir şekilde genişletilmesi boyunca devam edecektir. ASR kural şampiyonlarınız, ASR kuralları dağıtımının her düzeyini ilk kez deneyimleyecek.

ASR kurallarıyla ilgili iş kesintileri konusunda sizi uyarmak ve ASR kuralları dağıtımıyla ilgili iletişimleri almak için ASR kural şampiyonlarınız için bir geri bildirim ve yanıt kanalı sağlamak önemlidir.

## <a name="get-inventory-of-line-of-business-apps-and-understand-the-business-unit-processes"></a>İş kolu uygulamalarının envanterini alma ve iş birimi süreçlerini anlama

Kuruluşunuz genelinde kullanılan uygulamaları ve iş birimi başına işlemleri tam olarak anlamak, başarılı bir ASR kuralları dağıtımı için kritik öneme sahiptir. Ayrıca, bu uygulamaların kuruluşunuzdaki çeşitli iş birimlerinde nasıl kullanıldığını anlamanız şarttır.
Başlamak için, kuruluşun genelinde kullanım için onaylanan uygulamaların bir envanterini almanız gerekir. Yazılım uygulamalarının envanterini oluşturmanıza yardımcı olması için Microsoft 365 Uygulamaları yönetim merkezi gibi araçları kullanabilirsiniz. Bkz. [Microsoft 365 Uygulamaları yönetim merkezinde envantere genel bakış](/deployoffice/admincenter/inventory).

## <a name="define-reporting-and-response-asr-rules-team-roles-and-responsibilities"></a>Raporlama ve yanıt ASR kuralları ekip rollerini ve sorumluluklarını tanımlama

ASR kurallarının durumunu ve etkinliğini izlemek ve iletmekle sorumlu kişilerin rollerini ve sorumluluklarını açıkça ifade etmek ASR bakımının temel etkinliğidir. Bu nedenle, şunları belirlemek önemlidir:

- Rapor toplamadan sorumlu kişi veya ekip
- Raporların nasıl ve kimlerle paylaşıldığı
- ASR kurallarının neden olduğu yeni tanımlanan tehditler veya istenmeyen engellemeler için yükseltme nasıl giderilir?

Tipik roller ve sorumluluklar şunlardır:

- BT yöneticileri: ASR kurallarını uygulayın, dışlamaları yönetin. Uygulamalar ve süreçler üzerinde farklı iş birimleriyle çalışın. Raporların toplanması ve paydaşlara paylaşılması
- Sertifikalı güvenlik operasyonları merkezi (CSOC) analisti: Tehdidin geçerli olup olmadığını belirlemek için yüksek öncelikli, engellenen süreçlere yatırım yapmaktan sorumludur
- Bilgi güvenliği müdürü (CISO): Kuruluşun genel güvenlik duruşu ve sağlığından sorumludur

## <a name="asr-rules-ring-deployment"></a>ASR kuralları halka dağıtımı

Microsoft, büyük kuruluşlar için ASR kurallarının "halkalar" içinde dağıtılması önerilir. Halkalar, çakışmayan ağaç halkaları gibi dışa doğru yayılan eşmerkezli daireler olarak görsel olarak temsil edilen cihaz gruplarıdır. En içteki halka başarıyla dağıtıldığında, bir sonraki halkayı test aşamasına geçirebilirsiniz. İş birimlerinizin, ASR kuralları şampiyonlarınızın, uygulamalarınızın ve süreçlerinizin kapsamlı bir şekilde değerlendirilmesi halkalarınızı tanımlamak için zorunludur.
Çoğu durumda, kuruluşunuz Windows güncelleştirmelerinin aşamalı dağıtımları için dağıtım halkaları tasarlayacaktır. ASR kurallarını uygulamak için mevcut halka tasarımınızı kullanabilirsiniz.
Bkz. [Windows için dağıtım planı oluşturma](/windows/deployment/update/create-deployment-plan)

## <a name="additional-topics-in-this-deployment-collection"></a>Bu dağıtım koleksiyonundaki ek konular

[Saldırı yüzeyini azaltma (ASR) kuralları dağıtımına genel bakış](attack-surface-reduction-rules-deployment.md)

[Saldırı yüzeyini azaltma (ASR) kuralları testi](attack-surface-reduction-rules-deployment-test.md)

[Saldırı yüzeyini azaltma (ASR) kurallarını etkinleştirme](attack-surface-reduction-rules-deployment-implement.md)

[Saldırı yüzeyini azaltma (ASR) kurallarını kullanıma hazır hale getirme](attack-surface-reduction-rules-deployment-operationalize.md)

[Saldırı yüzeyini azaltma (ASR) kuralları başvurusu](attack-surface-reduction-rules-reference.md)
