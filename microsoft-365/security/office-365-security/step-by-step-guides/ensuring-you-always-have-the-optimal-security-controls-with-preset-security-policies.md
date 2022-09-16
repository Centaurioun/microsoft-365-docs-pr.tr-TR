---
title: Office 365 için Microsoft Defender için Standart veya Katı önceden ayarlanmış güvenlik ilkelerini hızlı bir şekilde ayarlama adımları
description: Ürün tarafından önerilen güvenliği elde etmek için Office 365 için Microsoft Defender'da önceden ayarlanmış güvenlik ilkelerini ayarlama adımı. Önceden ayarlanmış ilkeler *, Standart* veya *Katı* bir güvenlik profili ayarlar. Bunları ayarlayın ve Office 365 için Microsoft Defender bu güvenlik denetimlerini sizin için yönetir ve korur.
search.product: ''
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-guidance-templates
ms.topic: how-to
ms.subservice: mdo
search.appverid: met150
ms.openlocfilehash: 70ec57955b2f7ce9c79c464334842659a3db57f3
ms.sourcegitcommit: c29af68260ba8676083674b3c70209bff2c2e362
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/16/2022
ms.locfileid: "67740280"
---
# <a name="set-up-steps-for-the-standard-or-strict-preset-security-policies-in-microsoft-defender-for-office-365"></a>Office 365 için Microsoft Defender'da Standart veya Katı önceden ayarlanmış güvenlik ilkeleri için adımları ayarlama

Office 365 için Microsoft Defender size daha sonra korunacak güvenlik ilkelerini uygulamak için bir yol verdi mi?

Bir güvenlik denetimi için en iyi yöntem, gelişen tehdit ortamı nedeniyle değiştiğinde veya yeni denetimler eklendikçe Microsoft'un *Standart* veya *Katı* ön ayarlı güvenlik ilkesine atanan kullanıcılar için güvenlik denetimi ayarlarını *otomatik olarak* güncelleştirdiğini biliyor muydunuz?

Önceden ayarlanmış güvenlik ilkelerini (*Standart* veya *Katı*) kullanarak, kullanıcılarınız için her zaman Microsoft'un *önerilen, en iyi uygulaması olan yapılandırmaya* sahip olursunuz.

Önceden ayarlanmış güvenlik ilkeleri uygulamak ve Office 365 için Microsoft Defender sizin için güvenlik denetimlerini yönetmesini ve korumasını *sağlamak için* **aşağıdaki adımları kullanın**.

## <a name="what-you-will-need"></a>İhtiyacınız olan şey
- Office 365 için Microsoft Defender Plan 1 veya üzeri (E5'e dahildir)
- Yeterli izinler (Güvenlik Yöneticisi rolü)
- Aşağıdaki adımları gerçekleştirmek için 5 dakika.

## <a name="choose-between-standard-and-strict-policies"></a>Standart ve Katı ilkeler arasında seçim yapma

Katı ön ayarlı güvenlik ilkemiz, daha agresif algılamalara neden olacak ve yöneticinin son kullanıcılara hangi engellenen e-postaların yayımlanacağına karar vermesine neden olacak güvenlik denetimleri için daha agresif sınırlar ve ayarlara sahiptir.

- Daha iyi postaların şüpheli olarak işaretlenmeleri anlamına gelse bile daha agresif algılamalar gerektiren kullanıcılarınızın listesini toplayın. Bunlar genellikle yönetici personeliniz, yönetici destek personeliniz ve geçmişte yüksek oranda hedeflenen kullanıcılardır.

- Son kullanıcı postanın iyi olabileceğini düşünüyorsa ve iletinin kendilerine yayımlanmasını isterse, seçili kullanıcıların e-postaları gözden geçirmek ve yayınlamak için yönetici kapsamına sahip olduğundan emin olun.

- Yukarıdaki ölçütler karşılanırsa, kullanıcı Katı önceden ayarlanmış güvenlik ilkesine yerleştirilmelidir. Aksi takdirde kullanıcı Standart önceden ayarlanmış güvenlik ilkesine yerleştirilmelidir.

> [!TIP]
> Standart ve Katı güvenlik ilkelerinin ne olduğu hakkında bilgi için bu [makaleye](../../office-365-security/recommended-settings-for-eop-and-office365.md) bakın.

## <a name="enable-security-presets-in-microsoft-defender-for-office-365"></a>Office 365 için Microsoft Defender'de Güvenlik Ön Ayarlarını Etkinleştirme

Kullanıcılarınız için Standart ve Katı güvenlik önayar ilkeleri arasında seçim yaptıktan sonra, kullanıcıları her ön ayara atamak birkaç adım daha sürer.

1. Standart ve Katı güvenlik ön ayarlarına eklemek istediğiniz kullanıcıları, grupları veya etki alanlarını belirleyin.
1. adresinden Microsoft Güvenlik portalında https://security.microsoft.comoturum açın.
1. Sol gezinti bölmesinde, **işbirliği Email &** altında **İlkeler & kuralları'nı** seçin.
1. **Tehdit ilkeleri'ne tıklayın**.
1. Şablonlu ilkeler başlığının altında **Önceden Ayarlanmış Güvenlik** **İlkeleri'ni** seçin
1. Standart koruma ön ayarının altında **Yönet'i** seçin.
1. Kiracı genelinde Exchange Online Protection uygulamak için **Tüm Alıcılar'ı** seçin veya koruma ilkesini uygulamak istediğiniz kullanıcıları, grupları veya etki alanlarını el ile eklemek için **Belirli alıcılar'ı** seçin. **İleri** düğmesine tıklayın.
1. Office 365 için Defender Koruması kiracısı genelinde uygulamak için **Tüm Alıcılar'ı** seçin veya koruma ilkesini uygulamak istediğiniz kullanıcıları, grupları veya etki alanlarını el ile eklemek için **Belirli alıcılar'ı** seçin. **İleri** düğmesine tıklayın.
1. **Kimliğe Bürünme Koruması bölümünde, kimliğe bürünme** saldırılarından korunmak için e-posta adreslerini & etki alanları ekleyin, ardından kimliğe bürünme korumasının uygulanmasını istemediğiniz güvenilen gönderenleri ve etki alanlarını ekleyin ve **İleri'ye** basın.
1. **Onayla** düğmesine tıklayın.
1. Katı koruma ön ayarında **Yönet** bağlantısını seçin.
1. 7-10 arası adımları tekrarlayın, ancak kullanıcılar için sıkı koruma uygulanmalıdır. (varsa)
1. **Onayla** düğmesine tıklayın.

> [!TIP]
> Önceden ayarlanmış ilkeler hakkında daha fazla bilgi edinmek için [buraya](../../office-365-security/preset-security-policies.md) tıklayın

## <a name="your-next-step-is-config-analyzer"></a>Sonraki adımınız Yapılandırma Çözümleyicisi'dir

Kullanıcılarınızın Microsoft'un en iyi yöntemlerine göre yapılandırılıp yapılandırılmadığını belirlemek için yapılandırma çözümleyicisini kullanın.

> [!TIP]
> Yapılandırma çözümleyicisi yöneticilerin, ayarların önceden ayarlanmış güvenlik ilkelerindeki Standart veya Katı koruma profili ayarlarının altında olduğu güvenlik ilkelerini bulmasını ve düzeltmesini sağlar. Yapılandırma çözümleyicisi hakkında daha fazla bilgi [için buraya bakın](../../office-365-security/configuration-analyzer-for-security-policies.md).

Yöneticilerin Microsoft'un en iyi yöntemlerini *kullanmalarını sağladığından* , Güvenli Ön Ayarlar her zaman önerilir. Ancak bazı durumlarda özelleştirilmiş yapılandırmalar gereklidir. Özel ilkeler hakkında [buradan](../../office-365-security/tenant-wide-setup-for-increased-security.md) bilgi edinin.

