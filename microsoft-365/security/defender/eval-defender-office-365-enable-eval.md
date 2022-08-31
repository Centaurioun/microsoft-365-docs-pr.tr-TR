---
title: Üretim ortamınızdaki Office 365 için Microsoft Defender için değerlendirme ortamını etkinleştirme
description: Deneme lisansları, MX kaydı işleme, kabul edilen etki alanlarının ve gelen bağlantıların denetlenme & Office 365 için Microsoft Defender değerlendirmesini etkinleştirme adımları.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: 07/01/2021
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
- zerotrust-solution
- highpri
ms.topic: how-to
ms.openlocfilehash: b41754e6fe8930f2b01c983ff7d30e1d478efcb4
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/31/2022
ms.locfileid: "67478871"
---
# <a name="enable-the-evaluation-environment"></a>Değerlendirme ortamını etkinleştirme

**Şunlar için geçerlidir:**
- Microsoft 365 Defender

Bu makale, Office 365 için Microsoft Defender için değerlendirme ortamını ayarlama işleminde [3.Adım 2'dir](eval-defender-office-365-overview.md). Bu işlem hakkında daha fazla bilgi için [genel bakış makalesine](eval-defender-office-365-overview.md) bakın.

Office 365 için Microsoft Defender için değerlendirmeyi etkinleştirmek için aşağıdaki adımları kullanın.

:::image type="content" source="../../media/defender/m365-defender-office-eval-enable-steps.png" alt-text="Microsoft Defender değerlendirme ortamında Office 365 için Microsoft Defender etkinleştirme adımları" lightbox="../../media/defender/m365-defender-office-eval-enable-steps.png":::


- [1. Adım: Deneme lisanslarını etkinleştirme](#step-1-activate-trial-licenses)
- [2. Adım: Genel MX kaydını denetleme ve doğrulama](#step-2-audit-and-verify-the-public-mx-record)
- [3. Adım: Kabul edilen etki alanlarını denetleme](#step-3-audit-accepted-domains)
- [4. Adım: Gelen bağlayıcıları denetleme](#step-4-audit-inbound-connectors)
- [5. Adım: Değerlendirmeyi etkinleştirme](#step-5-activate-the-evaluation)

## <a name="step-1-activate-trial-licenses"></a>1. Adım: Deneme lisanslarını etkinleştirme

Mevcut Office 365 için Microsoft Defender ortamınızda veya kiracı yönetim portalınızda oturum açın.

1. Yönetim portalına gidin.
2. Hızlı başlatmadan Hizmetleri Satın Al'ı seçin.

   :::image type="content" source="../../media/mdo-eval/1_m365-purchase-services.png" alt-text="Microsoft 365 yönetim merkezi tıklanacak Hizmetleri satın al seçeneği" lightbox="../../media/mdo-eval/1_m365-purchase-services.png":::

3. Office 365 için Microsoft Defender planlarını bulmak için ekranı aşağı kaydırarak Add-On bölümüne gidin (veya "Defender" araması yapın).
4. Değerlendirmek istediğiniz planın yanındaki Ayrıntılar'a tıklayın.

   :::image type="content" source="../../media/mdo-eval/2_mdo-eval-license-details.png" alt-text="Tıklanacak Ayrıntılar düğmesi" lightbox="../../media/mdo-eval/2_mdo-eval-license-details.png":::

5. *Ücretsiz denemeyi başlat* bağlantısına tıklayın.

   :::image type="content" source="../../media/mdo-eval/3-m365-purchase-button.png" alt-text="Ücretsiz denemeyi başlat köprüsü" lightbox="../../media/mdo-eval/3-m365-purchase-button.png":::

6. İsteğinizi onaylayın ve *Şimdi deneyin* düğmesine tıklayın.

   :::image type="content" source="../../media/mdo-eval/4_mdo-trial-order.png" alt-text="Şimdi deneyin düğmesi" lightbox="../../media/mdo-eval/4_mdo-trial-order.png":::

## <a name="step-2-audit-and-verify-the-public-mx-record"></a>2. Adım: Genel MX kaydını denetleme ve doğrulama

Office 365 için Microsoft Defender etkili bir şekilde değerlendirmek için gelen dış e-postanın kiracınızla ilişkilendirilmiş Exchange Online Protection (EOP) örneği üzerinden geçirilmesi önemlidir.

1. M365 Yönetici Portalı'nda oturum açın, Ayarlar'ı genişletin ve Etki Alanları'nı seçin.
2. Doğrulanmış e-posta etki alanınızı seçin ve DNS'yi yönet'e tıklayın.
3. Oluşturulan ve EOP kiracınıza atanan MX kaydını not edin.
4. Dış (genel) DNS bölgenize erişin ve e-posta etki alanınızla ilişkili birincil MX kaydını denetleyin.
    - *Genel MX kaydınız şu anda atanan EOP adresiyle (örneğin tenant-com.mail.protection.outlook.com) eşleşiyorsa başka yönlendirme değişikliği gerekmez*.
    - Genel MX kaydınız şu anda üçüncü taraf veya şirket içi SMTP ağ geçidine çözümleniyorsa ek yönlendirme yapılandırmaları gerekebilir.
    - Genel MX kaydınız şu anda şirket içi Exchange'e çözümlenmişse, bazı alıcı posta kutularının henüz EXO'ya geçirilmediği karma bir modelde olabilirsiniz.

## <a name="step-3-audit-accepted-domains"></a>3. Adım: Kabul edilen etki alanlarını denetleme

1. Exchange Online Yönetici Portalı'nda oturum açın, Posta Akışı'nı seçin ve ardından Kabul Edilen Etki Alanları'na tıklayın.
2. Kiracınıza eklenen ve doğrulanan kabul edilen etki alanları listesinden, birincil e-posta **etki alanınızın etki alanı türünü** not edin.
    - Etki alanı türü ***Yetkili*** olarak ayarlanırsa, kuruluşunuz için tüm alıcı posta kutularının şu anda Exchange Online olduğu varsayılır.
    - Etki alanı türü ***İç Geçiş*** olarak ayarlandıysa, bazı alıcı posta kutularının hala şirket içinde bulunduğu karma modelde olabilirsiniz.

## <a name="step-4-audit-inbound-connectors"></a>4. Adım: Gelen bağlayıcıları denetleme

1. Exchange Online Yönetici Portalı'nda oturum açın, Posta Akışı'nı seçin ve bağlayıcılar'a tıklayın.
2. Yapılandırılan bağlayıcılar listesinden **, İş Ortağı Kuruluşu'ndan** gelen ve üçüncü taraf SMTP ağ geçidiyle ilişkilendirebilecek tüm girişleri not edin.
3. Yapılandırılmış bağlayıcılar listesinden, **kuruluşunuzun e-posta sunucusundan** etiketli ve hala karma senaryoda olduğunuzu gösterebilecek girişleri not edin.

## <a name="step-5-activate-the-evaluation"></a>5. Adım: Değerlendirmeyi etkinleştirme

Office 365 için Microsoft Defender değerlendirmenizi Microsoft 365 Defender portalından etkinleştirmek için buradaki yönergeleri kullanın.

1. Microsoft 365 Defender portalına erişimi olan bir hesapla kiracınızda oturum açın.
2. **Microsoft 365 Defender portalını Office 365 için Microsoft Defender** yönetimi için varsayılan arabiriminiz yapmak isteyip istemediğinizi seçin (önerilir).

   :::image type="content" source="../../media/mdo-eval/1_mdo-eval-activate-eval.png" alt-text="Yönetim için merkezi ve geliştirilmiş bir Microsoft 365 Defender portalına yol açmak için Ayarlar'da aç düğmesi" lightbox="../../media/mdo-eval/1_mdo-eval-activate-eval.png":::

3. Gezinti menüsünden *İşbirliği* Email & altında **İlkeler & Kuralları'nı** seçin.

   :::image type="content" source="../../media/mdo-eval/2_mdo-eval-activate-eval.png" alt-text="Tıklanacak İlkeler & kuralları menü öğesi" lightbox="../../media/mdo-eval/2_mdo-eval-activate-eval.png":::

4. *İlke & Kuralları* panosunda **Tehdit İlkeleri'ne** tıklayın.

   :::image type="content" source="../../media/mdo-eval/3_mdo-eval-activate-eval.png" alt-text="Tıklanacak Tehdit ilkeleri menü öğesi" lightbox="../../media/mdo-eval/3_mdo-eval-activate-eval.png":::

5. Ekranı aşağı kaydırarak *Ek İlkeler'e* gelin ve **Office 365 için Defender Değerlendir** kutucuğunu seçin.

   :::image type="content" source="../../media/mdo-eval/4_mdo-eval-activate-eval.png" alt-text="Değerlendirme Office 365 için Defender kutucuğu" lightbox="../../media/mdo-eval/4_mdo-eval-activate-eval.png":::

6. Şimdi dış e-postanın doğrudan Exchange Online mı yoksa üçüncü taraf ağ geçidine mi yoksa hizmete mi yönlendirileceğini seçin ve İleri'ye tıklayın.

   :::image type="content" source="../../media/mdo-eval/5_mdo-eval-activate-eval.png" alt-text="Office 365 için Microsoft Defender portalındaki Yönlendirme ayarları bölmesi" lightbox="../../media/mdo-eval/5_mdo-eval-activate-eval.png":::

7. Üçüncü taraf ağ geçidi kullanıyorsanız, açılan listeden satıcı adını ve bu çözümle ilişkilendirilmiş gelen bağlayıcıyı seçin. Yanıtlarınızı listeledikten sonra İleri'ye tıklayın.

   :::image type="content" source="../../media/mdo-eval/6-mdo-eval-activate-eval-settings.png" alt-text="Office 365 için Microsoft Defender portalındaki Üçüncü taraf veya şirket içi ayarlar bölmesi" lightbox="../../media/mdo-eval/6-mdo-eval-activate-eval-settings.png":::

8. Ayarlarınızı gözden geçirin ve **Değerlendirme Oluştur** düğmesine tıklayın.

   |Önce|Sonra|
   |:---:|:---:|
   |:::image type="content" source="../../media/mdo-eval/7-mdo-eval-activate-review.png" alt-text="Office 365 için Microsoft Defender portalındaki Ayarlarınızı gözden geçirin bölmesi" lightbox="../../media/mdo-eval/7-mdo-eval-activate-review.png":::|:::image type="content" source="../../media/mdo-eval/8-mdo-eval-activate-complete.png" alt-text="Office 365 için Microsoft Defender portalında Değerlendirme kurulumu tamamlama bildirimi" lightbox="../../media/mdo-eval/8-mdo-eval-activate-complete.png":::|
   |

## <a name="next-steps"></a>Sonraki adımlar

Adım 3 /3: Office 365 için Microsoft Defender için pilotu ayarlama

[Değerlendirme Office 365 için Microsoft Defender](eval-defender-office-365-overview.md) için genel bakışa dönün

[Değerlendirme ve pilot Microsoft 365 Defender](eval-overview.md) genel bakışa dönün
