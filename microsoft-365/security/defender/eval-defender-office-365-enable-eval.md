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
ms.date: 09/01/2021
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- m365solution-scenario
- m365solution-evalutatemtp
- zerotrust-solution
- highpri
- tier1
ms.topic: how-to
ms.openlocfilehash: 2bf372cb9836b5565a5e311a17806d6f52d3945a
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68072975"
---
# <a name="enable-the-evaluation-environment"></a>Değerlendirme ortamını etkinleştirme

**Şunlar için geçerlidir:**
- Microsoft 365 Defender

Bu makale, Office 365 için Microsoft Defender için değerlendirme ortamını ayarlama işleminde [3.Adım 2'dir](eval-defender-office-365-overview.md). Bu işlem hakkında daha fazla bilgi için [genel bakış makalesine](eval-defender-office-365-overview.md) bakın.

Office 365 için Microsoft Defender için değerlendirmeyi etkinleştirmek için aşağıdaki adımları kullanın.

:::image type="content" source="../../media/defender/m365-defender-office-eval-enable-steps.png" alt-text="Microsoft Defender değerlendirme ortamında Office 365 için Microsoft Defender etkinleştirme adımları." lightbox="../../media/defender/m365-defender-office-eval-enable-steps.png":::

- [1. Adım: Genel MX kaydını denetleme ve doğrulama](#step-1-audit-and-verify-the-public-mx-record)
- [2. Adım: Kabul edilen etki alanlarını denetleme](#step-2-audit-accepted-domains)
- [3. Adım: Gelen bağlayıcıları denetleme](#step-3-audit-inbound-connectors)
- [4. Adım: Değerlendirmeyi etkinleştirme](#step-4-activate-the-evaluation)

## <a name="step-1-audit-and-verify-the-public-mx-record"></a>1. Adım: Genel MX kaydını denetleme ve doğrulama

Office 365 için Microsoft Defender etkili bir şekilde değerlendirmek için, gelen dış e-postanın kiracınızla ilişkilendirilmiş Exchange Online Protection (EOP) örneği üzerinden geçirilmesi önemlidir.

1. konumundaki M365 Yönetici Portalı'nda <https://admin.microsoft.com>*... Gerekirse tümünü göster'i* seçin, *Ayarlar'ı* genişletin ve **ardından Etki Alanları'nı** seçin. Veya doğrudan *Etki Alanları* sayfasına gitmek için kullanın <https://admin.microsoft.com/Adminportal/Home#/Domains>.
2. *Etki Alanları* sayfasında, onay kutusundan başka bir girişe tıklayarak doğrulanmış e-posta etki alanınızı seçin.
3. Açılan etki alanı ayrıntıları açılır öğesinde **DNS kayıtları** sekmesini seçin. Oluşturulan ve EOP kiracınıza atanan MX kaydını not edin.
4. Dış (genel) DNS bölgenize erişin ve e-posta etki alanınızla ilişkili birincil MX kaydını denetleyin:
    - *Genel MX kaydınız şu anda atanan EOP adresiyle eşleşiyorsa (örneğin, contoso-com.mail.protection.outlook.com) başka yönlendirme değişikliği gerekmez*.
    - Genel MX kaydınız şu anda üçüncü taraf veya şirket içi SMTP ağ geçidine çözümleniyorsa ek yönlendirme yapılandırmaları gerekebilir.
    - Genel MX kaydınız şu anda şirket içi Exchange'e çözümlenmişse, bazı alıcı posta kutularının henüz EXO'ya geçirilmediği karma bir modelde olabilirsiniz.

## <a name="step-2-audit-accepted-domains"></a>2. Adım: Kabul edilen etki alanlarını denetleme

1. konumundaki Exchange yönetim merkezinde (EAC) <https://admin.exchange.microsoft.com>*Posta akışı'nı* genişletin ve **kabul edilen etki alanları'na** tıklayın. Veya doğrudan *Kabul edilen etki alanları* sayfasına gitmek için kullanın<https://admin.exchange.microsoft.com/#/accepteddomains>.
2. *Kabul edilen etki alanları* sayfasında, birincil e-posta etki **alanınız için Etki alanı türü** değerini not edin.
    - Etki alanı türü **Yetkili** olarak ayarlanırsa, kuruluşunuz için tüm alıcı posta kutularının şu anda Exchange Online olduğu varsayılır.
    - Etki alanı türü **InternalRelay** olarak ayarlandıysa, bazı alıcı posta kutularının hala şirket içinde bulunduğu karma modelde olabilirsiniz.

## <a name="step-3-audit-inbound-connectors"></a>3. Adım: Gelen bağlayıcıları denetleme

1. konumundaki Exchange yönetim merkezinde (EAC) <https://admin.exchange.microsoft.com>*Posta akışı'nı* genişletin ve **bağlayıcılar'a** tıklayın. Veya doğrudan *Bağlayıcılar* sayfasına gitmek için kullanın <https://admin.exchange.microsoft.com/#/connectors>.
2. *Bağlayıcılar* sayfasında, aşağıdaki ayarlara sahip bağlayıcıları not edin:
   - **From** değeri, üçüncü taraf SMTP ağ geçidiyle bağıntı oluşturabilen **İş Ortağı kuruluşudur**.
   - **Kaynak** değeri, hala karma bir senaryoda olduğunuzu gösterebilecek **Kuruluşunuz** değeridir.

## <a name="step-4-activate-the-evaluation"></a>4. Adım: Değerlendirmeyi etkinleştirme

Office 365 için Microsoft Defender değerlendirmenizi Microsoft 365 Defender portalından etkinleştirmek için buradaki yönergeleri kullanın.

Ayrıntılı bilgi için bkz[. Deneme Office 365 için Microsoft Defender](../office-365-security/try-microsoft-defender-for-office-365.md).

1. Microsoft 365 Defender portalında *, Email & işbirliği'nde* \> <https://security.microsoft.com> **İlkeler & kuralları'nı** \> seçin **, Tehdit ilkeleri** \> bölümünü aşağı kaydırıp **Değerlendirme modu'nu** *seçin*. Veya doğrudan *Değerlendirme modu* sayfasına gitmek için kullanın <https://security.microsoft.com/atpEvaluation>.

2. *Değerlendirme modu* sayfasında **Değerlendirmeyi başlat'a** tıklayın.

   :::image type="content" source="../../media/mdo-eval/mdo-eval-activate-eval_05.png" alt-text="Değerlendirme modu sayfası ve Tıklayacak değerlendirmeyi başlat düğmesi." lightbox="../../media/mdo-eval/mdo-eval-activate-eval_05.png":::

3. *Korumayı aç* iletişim kutusunda **Hayır, yalnızca raporlamak istiyorum'u** seçin ve **ardından Devam'a** tıklayın.

   :::image type="content" source="../../media/mdo-eval/mdo-eval-activate-eval_06.png" alt-text="Korumayı aç iletişim kutusu ve Hayır, yalnızca raporlama seçeneğinin seçilmesini istiyorum." lightbox="../../media/mdo-eval/mdo-eval-activate-eval_06.png":::

4. *Eklemek istediğiniz kullanıcıları seçin* iletişim kutusunda **Tüm kullanıcılar'ı** seçin ve **ardından Devam'a** tıklayın.

   :::image type="content" source="../../media/mdo-eval/mdo-eval-activate-eval_07.png" alt-text="Eklemek istediğiniz kullanıcıları seçin iletişim kutusu ve seçecek Tüm kullanıcılar seçeneği." lightbox="../../media/mdo-eval/mdo-eval-activate-eval_07.png":::

5. *Posta akışınızı anlamamıza yardımcı olun* iletişim kutusunda, etki alanınız için MX kaydını algılamamıza bağlı olarak aşağıdaki seçeneklerden biri otomatik olarak seçilir:

   - **Yalnızca Microsoft Exchange Online kullanıyorum**: Etki alanınızın MX kayıtları Microsoft 365'e işaret etti. Yapılandıracak bir şey kalmadığından **Son'a** tıklayın.

     :::image type="content" source="../../media/mdo-eval/mdo-eval-activate-eval_08a.png" alt-text="Yalnızca Microsoft Exchange Online kullanıyorum seçeneğinin seçili olduğu Posta akışınızı anlamamıza yardımcı olun iletişim kutusu." lightbox="../../media/mdo-eval/mdo-eval-activate-eval_08a.png":::

   - **Üçüncü taraf ve/veya şirket içi hizmet sağlayıcısı kullanıyorum**: Gelecek ekranlarda, bu çözümden gelen postaları kabul eden gelen bağlayıcıyla birlikte satıcı adını seçin. Ayrıca üçüncü taraf koruma hizmetinden veya cihazından gelen iletiler için istenmeyen posta filtrelemeyi atlayan bir Exchange Online posta akışı kuralına (aktarım kuralı olarak da bilinir) ihtiyacınız olup olmadığını da siz karar verirsiniz. İşiniz bittiğinde **Son'a** tıklayın.

## <a name="next-steps"></a>Sonraki adımlar

Adım 3 /3: Office 365 için Microsoft Defender için pilotu ayarlama

[Değerlendirme Office 365 için Microsoft Defender](eval-defender-office-365-overview.md) için genel bakışa dönün

[Değerlendirme ve pilot Microsoft 365 Defender](eval-overview.md) genel bakışa dönün
