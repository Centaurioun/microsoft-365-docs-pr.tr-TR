---
title: Kiracı İzin Ver/Engelle Listesindeki izin ver ve blokları yönet
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
ms.date: 08/11/2022
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom: ''
description: Güvenlik portalındaki Kiracı İzin Ver/Engelle Listesi'nde izin verme ve blokları yönetmeyi öğrenin.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 1eae7f137d9457ca507efb592414127223af4f87
ms.sourcegitcommit: 2b89bcff547e00be3d38dc8d1e6cbcf8f41eba42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2022
ms.locfileid: "67598988"
---
# <a name="manage-your-allows-and-blocks-in-the-tenant-allowblock-list"></a>Kiracı İzin Ver/Engelle Listesinde izinlerinizi ve bloklarınızı yönetin

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Uygulandığı öğe**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365 için Microsoft Defender plan 1 ve plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

posta kutuları olmayan Exchange Online veya tek başına Exchange Online Protection (EOP) kuruluşlarında posta kutuları olan Microsoft 365 kuruluşlarında, Exchange Online EOP filtreleme kararına katılamayabilirsiniz. Örneğin, iyi bir ileti kötü (hatalı pozitif) olarak işaretlenebilir veya hatalı bir iletiye (hatalı negatif) izin verilir.

Microsoft 365 Defender portalındaki Kiracı İzin Ver/Engelle Listesi, Microsoft 365 filtreleme kararlarını el ile geçersiz kılmanın bir yolunu sunar. Kiracı İzin Ver/Engelle Listesi, gelen iletiler için posta akışı sırasında dış gönderenler (kuruluş içi iletiler için geçerli değildir) ve kullanıcı tıklamaları sırasında kullanılır.

Kiracı İzin Ver/Engelle listesi, kurallar & **kurallar** \> **Tehdit İlkeleri** **Kiracı İzin Ver/Engelle Listelerinin** \> **Kurallar** bölümündeki Microsoft 365 Defender portalında <https://security.microsoft.com> \> bulunabilir. **Doğrudan Kiracı İzin Ver/Listeleri Engelle** sayfasına gitmek için kullanın<https://security.microsoft.com/tenantAllowBlockList>.

Giriş oluşturma ve yapılandırma yönergeleri için aşağıdaki konulara bakın:

- **Etki alanları ve e-posta adresleri** ve **kimlik sahtekarı gönderenler**: [Kiracı İzin Ver/Engelle Listesi'ni kullanarak e-postalara izin verme veya e-postaları engelleme](allow-block-email-spoof.md)
- **Dosyalar**: [Kiracı İzin Ver/Engelle Listesini kullanarak dosyalara izin verme veya dosyaları engelleme](allow-block-files.md)
- **URL'ler**: [Kiracı İzin Ver/Engelle Listesi'ni kullanarak URL'lere izin verin veya engelleyin](allow-block-urls.md).

Bu makaleler, Microsoft 365 Defender Portalı'nda ve PowerShell'de yordamlar içerir.

## <a name="block-entries-in-the-tenant-allowblock-list"></a>Kiracı İzin Ver/Engelle Listesindeki girişleri engelle

Microsoft'a hatalı pozitifler olarak bildirirken aşağıdaki öğe türleri için blok girdileri oluşturmak için adresinden Gönderimler portalını ( *yönetici gönderimi* olarak da bilinir) <https://security.microsoft.com/reportsubmission> kullanın:

- **Etki alanları ve e-posta adresleri**:
  - Bu gönderenlerden gelen Email iletileri *yüksek güvenilirlikli istenmeyen posta* olarak işaretlenir (SCL = 9). İletilere ne olacağı, alıcı için iletiyi algılayan [istenmeyen posta önleme ilkesi](configure-your-spam-filter-policies.md) tarafından belirlenir. Varsayılan istenmeyen posta önleme ilkesinde ve yeni özel ilkelerde, yüksek güvenilirlikli istenmeyen posta olarak işaretlenmiş iletiler varsayılan olarak Gereksiz Email klasörüne teslim edilir. Standart ve Katı [önceden ayarlanmış güvenlik ilkelerinde](preset-security-policies.md) yüksek güvenilirlikli istenmeyen posta iletileri karantinaya alınır.
  - Kuruluştaki kullanıcılar bu engellenen etki alanlarına ve adreslere e-posta gönderemez. Aşağıdaki teslim edilmedi raporunu (NDR veya geri dönen ileti olarak da bilinir) alırlar: `5.7.1  Your message can't be delivered because one or more recipients are blocked by your organization's tenant allow/block list policy.`

- **Dosyalar**: Bu engellenen dosyaları içeren Email iletiler *kötü amaçlı yazılım* olarak engellenir.

- **URL'ler**: Bu engellenen URL'leri içeren Email iletiler *yüksek güvenilirlikli kimlik avı* olarak engellenir.

Kiracı İzin Ver/Engelle Listesi'nde, aşağıdaki öğe türleri için doğrudan blok girdileri de oluşturabilirsiniz:

- **Etki alanları ve e-posta adresleri**, **Dosyalar** ve **URL'ler**.

- **Kimlik sahtekarlığına neden olan gönderenler**: Kimlik sahtekarlığına ilişkin mevcut bir izin verme kararını el ile geçersiz kılarsanız [,](learn-about-spoof-intelligence.md) engellenen sahte gönderen yalnızca Kiracı İzin Ver/Engelle Listesi'ndeki Kimlik **Sahtekarı gönderenler** sekmesinde görünen bir el ile engelleme girdisine dönüşür.

Varsayılan olarak, **etki alanları ve e-posta adresleri**, **dosyalar** ve **URL'ler** için girişleri engelleyin 30 gün sonra sona erer, ancak bunların süresi 90 gün dolacak veya hiçbir zaman dolamayacak şekilde ayarlayabilirsiniz. Sahte **gönderenlerin girdilerinin** süresi hiçbir zaman dolmaz.

## <a name="allow-entries-in-the-tenant-allowblock-list"></a>Kiracı İzin Ver/Engelle Listesindeki girdilere izin ver

Çoğu durumda, Kiracı İzin Ver/Engelle Listesinde doğrudan izin verme girdileri oluşturamazsınız:

- **Etki alanları ve e-posta adresleri**, **dosyalar** ve **URL'ler**: İzin verme girdilerini doğrudan Kiracı İzin Ver/Engelle Listesi'nde oluşturamazsınız. Bunun yerine, **e-postayı**, **e-posta ekini** veya **URL'yi** **Engellenmemesi Gerekir (Hatalı pozitif)** olarak Microsoft'a bildirmek için adresinden <https://security.microsoft.com/reportsubmission> Gönderimler portalını kullanırsınız.

- **Sahte gönderenler**:
  - Kimlik sahtekarlığına yönelik bilgi sahtekarlık olarak iletiyi zaten engellediyse, **e-postayı** **Engellenmemesi Gerekir (Hatalı pozitif)** olarak Microsoft'a bildirmek için adresinden <https://security.microsoft.com/reportsubmission> Gönderimler portalını kullanın.
  - Kimlik sahtekarlık [zekası](learn-about-spoof-intelligence.md) iletiyi kimlik sahtekarı olarak tanımlamadan ve engellemeden önce Kiracı İzin Ver/Engelle Listesi'ndeki Kimlik **Sahtekarı gönderen** sekmesinde sahte gönderen için proaktif olarak bir izin girişi oluşturabilirsiniz.

Aşağıdaki listede, Gönderimler portalında Bir şeyi Microsoft'a hatalı pozitif olarak bildirdiğinizde Kiracı İzin Verme/Engelleme Listesi'nde ne olacağı açıklanmaktadır:

- **ekleri** ve **URL'leri** Email: İzin ver girişi oluşturulur ve Kiracı İzin Ver/Engelle Listesi'ndeki **Dosyalar** veya **URL'ler** sekmesinde görüntülenir.

- **Email**: Bir ileti Microsoft 365 filtreleme yığını tarafından engellendiyse, Kiracı İzin Ver/Engelle Listesinde bir izin ver girişi oluşturulabilir:

  - İleti kimlik [sahtekarlığına](learn-about-spoof-intelligence.md) karşı engellenmişse, gönderen için bir izin girdisi oluşturulur ve Kiracı İzin Ver Engelleme Listesi'ndeki Kimlik **Sahtekarı gönderenler** sekmesinde görüntülenir.

  - İleti [Office 365 için Defender'da etki alanı veya kullanıcı kimliğe bürünme koruması](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) tarafından engellendiyse, Kiracı İzin Ver/Engelle Listesi'nde izin verme girdisi oluşturulmaz. Bunun yerine, etki alanı veya gönderen, iletiyi algılayan [kimlik avı önleme ilkesinin](configure-mdo-anti-phishing-policies.md#use-the-microsoft-365-defender-portal-to-modify-anti-phishing-policies) **Güvenilen gönderenler ve etki alanları bölümüne** eklenir.

  - İleti başka nedenlerle engellendiyse, gönderen için bir izin verme girdisi oluşturulur ve Kiracı İzin Verme Engelleme Listesi'ndeki **Etki Alanları & adresleri** sekmesinde görüntülenir.

  - İleti engellenmediyse ve gönderen için izin ver girişi oluşturulmazsa, bu nedenle Sahte **gönderenler** sekmesinde veya **Etki Alanları & adresleri** sekmesinde oluşturulmaz.

Varsayılan olarak, **etki alanları ve e-posta adresleri**, **dosyalar** ve **URL'ler** için girişlerin süresi 30 gün sonra dolar ve bu da maksimum değerdir. **Sahte gönderenler için girişlerin** süresi hiçbir zaman dolmaz.

> [!NOTE]
> Microsoft sizin için izin verme girdilerini yönettiği için etki **alanları ve e-posta adresleri**, **URL'ler** veya **dosyalar** için gereksiz izin verme girdileri kaldırılır. Bu davranış, kuruluşunuzu korur ve yanlış yapılandırılmış izin verme girdilerinin önlenmesine yardımcı olur. Karara katılmıyorsanız, iletinin neden hala kötü kabul edildiğini saptamak için bir destek olayı açmanız gerekebilir.
>
> İletinin kötü amaçlı olduğunu belirleyen filtrelere bağlı olarak posta akışı sırasında izinler eklenir. Örneğin, gönderen ve iletideki bir URL'nin hatalı olduğu belirlendiyse, gönderen için bir izin girdisi oluşturulur ve URL için bir izin girdisi oluşturulur.
>
> Bu varlıkla (etki alanı veya e-posta adresi, URL, dosya) yeniden karşılaşıldığında, bu varlıkla ilişkili tüm filtreler atlanır.
>
> Posta akışı sırasında, etki alanından veya e-posta adresinden gelen iletiler filtreleme yığınında başka denetimler geçirirse, iletiler teslim edilecek. Örneğin, [e-posta kimlik doğrulaması](email-validation-and-authentication.md) geçerse, izin ver girişindeki bir gönderenden gelen bir ileti teslim edilecek.

## <a name="what-to-expect-after-you-add-an-allow-or-block-entry"></a>İzin ver veya engelle girdisi ekledikten sonra beklenmesi gerekenler

Gönderimler portalı aracılığıyla bir izin girişi veya Kiracı İzin Ver/Engelle Listesi'ne bir blok girişi ekledikten sonra, girdi hemen çalışmaya başlamalıdır.

Sistemin izin verme veya engelleme hakkında bilgi edinip öğrenmediğini görmek için girişlerin 30 gün sonra otomatik olarak süresinin dolmasına izin vermenizi öneririz. Aksi takdirde, sisteme öğrenmesi için 30 gün daha vermek için başka bir giriş yapmanız gerekir.
