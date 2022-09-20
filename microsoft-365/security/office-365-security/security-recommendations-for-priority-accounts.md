---
title: Microsoft 365'teki öncelik hesapları, öncelik hesapları, Office 365 öncelik hesapları, Microsoft 365'teki öncelik hesapları için güvenlik önerileri
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: conceptual
ms.date: ''
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-protecthve
- highpri
ms.custom: ''
description: Yöneticiler, Microsoft 365 kuruluşlarında güvenlik ayarlarını yükseltmeyi ve öncelikli hesaplar için raporları, uyarıları ve araştırmaları kullanmayı öğrenebilir.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 61a8dd68635c3ef71ca8573ce4d08451a581ba95
ms.sourcegitcommit: 078149c9645ce220911ccd6ce54f984a4c92ce53
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/20/2022
ms.locfileid: "67811340"
---
# <a name="security-recommendations-for-priority-accounts-in-microsoft-365"></a>Microsoft 365'te öncelikli hesaplar için güvenlik önerileri

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Şunlar için geçerlidir:**
- [Office 365 için Microsoft Defender plan 1 ve plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Tüm kullanıcı hesaplarının aynı şirket bilgilerine erişimi yoktur. Bazı hesapların finansal veriler, ürün geliştirme bilgileri, kritik derleme sistemlerine iş ortağı erişimi ve daha fazlası gibi hassas bilgilere erişimi vardır. Gizliliği tehlikeye girerse, son derece gizli bilgilere erişimi olan hesaplar ciddi bir tehdit oluşturur. Bu tür hesapları _öncelikli hesaplar_ olarak adlandırıyoruz. Öncelik hesapları ARASıNDA CEO'lar, CISO'lar, CFO'lar, altyapı yönetici hesapları, derleme sistemi hesapları ve daha fazlası bulunur (ancak bunlarla sınırlı değildir).

Saldırganlar için, sıradan veya bilinmeyen kullanıcılar için rastgele bir ağ oluşturan sıradan kimlik avı saldırıları verimli değildir. Öte yandan, öncelikli hesapları hedefleyen _zıpkınla kimlik avı_ veya _balina avı_ saldırıları saldırganlar için çok değerlidir. Bu nedenle, öncelik hesapları, hesap güvenliğinin aşılmasını önlemeye yardımcı olmak için sıradan korumadan daha güçlü bir koruma gerektirir.

Microsoft 365 ve Office 365 için Microsoft Defender, öncelik hesaplarınız için ek güvenlik katmanları sağlayan çeşitli temel özellikler içerir. Bu makalede bu özellikler ve bunların nasıl kullanılacağı açıklanmaktadır.

:::image type="content" source="../../media/security-recommendations-for-priority-users.png" alt-text="Simge formundaki güvenlik önerilerinin özeti" lightbox="../../media/security-recommendations-for-priority-users.png":::

|Görev|Tüm Office 365 Kurumsal planları|Microsoft 365 E3|Microsoft 365 E5|
|---|:---:|:---:|:---:|
|[Öncelik hesapları için oturum açma güvenliğini artırma](#increase-sign-in-security-for-priority-accounts)|![Dahil.](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Dahil.](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Dahil.](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|[Öncelik hesapları için katı önceden ayarlanmış güvenlik ilkeleri kullanma](#use-strict-preset-security-policies-for-priority-accounts)|![Dahil.](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Dahil.](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Dahil.](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|[Öncelik hesaplarına kullanıcı etiketleri uygulama](#apply-user-tags-to-priority-accounts)|||![Dahil](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|[Uyarılarda, raporlarda ve algılamalarda öncelik hesaplarını izleme](#monitor-priority-accounts-in-alerts-reports-and-detections)|||![Dahil](../../media/d238e041-6854-4a78-9141-049224df0795.png)|
|[Kullanıcıları eğitme](#train-users)|![Dahil.](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Dahil](../../media/d238e041-6854-4a78-9141-049224df0795.png)|![Dahil](../../media/d238e041-6854-4a78-9141-049224df0795.png)|

> [!NOTE]
> _Ayrıcalıklı hesapların (yönetici hesaplarının_) güvenliğini sağlama hakkında bilgi için [bu konuya](/security/compass/critical-impact-accounts) bakın.

## <a name="increase-sign-in-security-for-priority-accounts"></a>Öncelik hesapları için oturum açma güvenliğini artırma

Öncelik hesapları için daha fazla oturum açma güvenliği gerekir. Çok faktörlü kimlik doğrulaması (MFA) gerektirerek ve eski kimlik doğrulama protokollerini devre dışı bırakarak oturum açma güvenliğini artırabilirsiniz.

Yönergeler için bkz [. 1. Adım. MFA ile uzak çalışanlar için oturum açma güvenliğini artırın](../../solutions/empower-people-to-work-remotely-secure-sign-in.md). Bu makale uzak çalışanlar hakkında olsa da, aynı kavramlar öncelikli kullanıcılar için de geçerlidir.

**Not**: Önceki makalede açıklandığı gibi tüm öncelikli kullanıcılar için eski kimlik doğrulama protokollerini genel olarak devre dışı bırakmanızı kesinlikle öneririz. İş gereksinimleriniz bunu yapmanıza engel olursa, Exchange Online eski kimlik doğrulama protokollerinin kapsamını sınırlamaya yardımcı olmak için aşağıdaki denetimleri sunar:

- Belirli kullanıcılar için POP3, IMAP4 ve kimliği doğrulanmış SMTP gibi Temel kimlik doğrulaması ve eski kimlik doğrulama protokollerini engellemek veya izin vermek için Exchange Online kimlik doğrulama [ilkelerini](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online) ve [İstemci Erişim Kurallarını](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) kullanabilirsiniz.

- Tek tek posta kutularında POP3 ve IMAP4 erişimini devre dışı bırakabilirsiniz. Kimliği doğrulanmış SMTP'yi kuruluş düzeyinde devre dışı bırakabilir ve hala gerektiren belirli posta kutularında etkinleştirebilirsiniz. Yönergeler için aşağıdaki makalelere bakın:
  - [Kullanıcı için POP3 veya IMAP4 erişimini etkinleştirme veya devre dışı bırakma](/exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)
  - [Kimliği doğrulanmış istemci SMTP gönderimini etkinleştirme veya devre dışı bırakma (SMTP AUTH)](/exchange/clients-and-mobile-in-exchange-online/authenticated-client-smtp-submission)

Temel kimlik doğrulamasının Exchange Web Services (EWS), Exchange ActiveSync, POP3, IMAP4 ve uzak PowerShell için Exchange Online kullanım dışı bırakıldığını da belirtmek gerekir. Ayrıntılar için bu [blog gönderisini inceleyin](https://developer.microsoft.com/office/blogs/deferred-end-of-support-date-for-basic-authentication-in-exchange-online/).

## <a name="use-strict-preset-security-policies-for-priority-accounts"></a>Öncelik hesapları için katı önceden ayarlanmış güvenlik ilkeleri kullanma

Öncelik kullanıcıları, Exchange Online Protection (EOP) ve Office 365 için Defender'de kullanılabilen çeşitli korumalar için daha sıkı eylemler gerektirir.

Örneğin, gereksiz posta olarak sınıflandırılan iletileri Gereksiz Email klasörüne teslim etmek yerine, öncelik hesaplarına yönelikse aynı iletileri karantinaya almalısınız.

Önceden belirlenmiş güvenlik ilkelerinde Katı profilini kullanarak öncelik hesapları için bu katı yaklaşımı uygulayabilirsiniz.

Önceden ayarlanmış güvenlik ilkeleri, EOP ve Office 365 için Defender tüm korumalar için önerilen Katı ilke ayarlarımızı uygulamak için kullanışlı ve merkezi bir konumdur. Daha fazla bilgi için bkz. [EOP'de önceden ayarlanmış güvenlik ilkeleri ve Office 365 için Microsoft Defender](preset-security-policies.md).

Katı ilke ayarlarının varsayılan ve Standart ilke ayarlarından nasıl farklı olduğu hakkında ayrıntılı bilgi için bkz. [EOP ve Office 365 için Microsoft Defender güvenliği için önerilen ayarlar](recommended-settings-for-eop-and-office365.md).

## <a name="apply-user-tags-to-priority-accounts"></a>Öncelik hesaplarına kullanıcı etiketleri uygulama

Office 365 için Microsoft Defender Plan 2'deki kullanıcı etiketleri (Microsoft 365 E5 veya eklenti aboneliğinin parçası olarak), raporlarda ve olay araştırmalarında belirli kullanıcıları veya kullanıcı gruplarını hızla tanımlamanın ve sınıflandırmanın bir yoludur.

**Öncelik hesapları** , öncelik hesaplarını içeren olayları ve uyarıları tanımlamak için kullanabileceğiniz yerleşik bir kullanıcı etiketi türüdür ( _sistem etiketi_ olarak bilinir). **Öncelik hesapları** hakkında daha fazla bilgi için bkz. [Öncelik hesaplarını yönetme ve izleme](../../admin/setup/priority-accounts.md).

Ayrıca, öncelik hesaplarınızı daha fazla tanımlamak ve sınıflandırmak için özel etiketler oluşturabilirsiniz. Daha fazla bilgi için bkz. [Kullanıcı etiketleri](user-tags.md). Özel kullanıcı etiketleriyle aynı arabirimde **öncelik hesaplarını** (sistem etiketleri) yönetebilirsiniz.

## <a name="monitor-priority-accounts-in-alerts-reports-and-detections"></a>Uyarılarda, raporlarda ve algılamalarda öncelik hesaplarını izleme

Öncelikli kullanıcılarınızın güvenliğini sağlayıp etiketledikten sonra, öncelik hesaplarını içeren olayları veya algılamaları hızla tanımlamak için EOP ve Office 365 için Defender kullanılabilir raporları, uyarıları ve araştırmaları kullanabilirsiniz. Kullanıcı etiketlerini destekleyen özellikler aşağıdaki tabloda açıklanmıştır.

|Özellik|Açıklama|
|---|---|
|Uyarılar|Etkilenen kullanıcıların kullanıcı etiketleri görünür ve Microsoft 365 Defender portalındaki **Uyarılar** sayfasında filtre olarak kullanılabilir. Daha fazla bilgi için bkz [. Uyarıları görüntüleme](../../compliance/alert-policies.md#view-alerts).|
|Explorer <p> Gerçek zamanlı algılamalar|**Gezgin'de** (Office 365 için Defender Plan 2) veya **Gerçek zamanlı algılamalarda** (Office 365 için Defender Plan 1), kullanıcı etiketleri Email kılavuz görünümünde ve Email ayrıntıları açılır penceresinde görünür. Kullanıcı etiketleri filtrelenebilir bir özellik olarak da kullanılabilir. Daha fazla bilgi için bkz.  [Explorer'da Etiketler](threat-explorer.md#tags-in-threat-explorer).|
|Kampanya Görünümleri|Kullanıcı etiketleri, Office 365 için Microsoft Defender Plan 2'deki Kampanya Görünümlerinde filtrelenebilir özelliklerden biridir. Daha fazla bilgi için bkz. [Kampanya Görünümleri](campaigns.md).|
|Tehdit koruması durum raporu|**Tehdit koruması durum raporundaki** neredeyse tüm görünümlerde ve ayrıntı tablolarında, sonuçları **öncelik hesaplarına** göre filtreleyebilirsiniz. Daha fazla bilgi için bkz [. Tehdit koruması durum raporu](view-email-security-reports.md#threat-protection-status-report).|
|Öncelik hesapları raporu için Email sorunları|Exchange yönetim merkezindeki (EAC) **öncelik hesapları raporunun Email sorunları**, **öncelik hesapları** için teslim edilmemiş ve gecikmiş iletiler hakkında bilgi içerir. Daha fazla bilgi için bkz. [öncelik hesapları raporuyla ilgili Email sorunları](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report).|

## <a name="train-users"></a>Kullanıcıları eğitme

Öncelikli hesapları olan kullanıcıları eğiterek bu kullanıcılar ve güvenlik operasyonları ekibiniz çok zaman ve hayal kırıklığı kaydedebilir. Savvy kullanıcılarının şüpheli e-posta iletilerindeki ekleri açma veya bağlantılara tıklama olasılığı daha düşüktür ve şüpheli web sitelerinden kaçınma olasılıkları daha yüksektir.

Harvard Kennedy School [Siber Güvenlik Kampanyası El Kitabı](https://www.belfercenter.org/CyberPlaybook) , kullanıcıları kimlik avı saldırılarını belirlemeye yönelik eğitim de dahil olmak üzere kuruluşunuzda güçlü bir güvenlik farkındalığı kültürü oluşturmak için mükemmel rehberlik sağlar.

Microsoft 365, kuruluşunuzdaki kullanıcıları bilgilendirmeye yardımcı olmak için aşağıdaki kaynakları sağlar:

|Kavram|Kaynaklar|Açıklama|
|---|---|---|
|Microsoft 365|[Özelleştirilebilir öğrenme yolları](/office365/customlearning/)|Bu kaynaklar, kuruluşunuzdaki kullanıcılar için eğitimleri bir araya getirebilmenize yardımcı olabilir.|
|Microsoft 365 güvenlik|[Öğrenme modülü: Microsoft 365'ten yerleşik ve akıllı güvenlikle kuruluşunuzun güvenliğini sağlama](/training/modules/security-with-microsoft-365)|Bu modül, Microsoft 365 güvenlik özelliklerinin birlikte nasıl çalıştığını açıklamanızı ve bu güvenlik özelliklerinin avantajlarını açıklamanızı sağlar.|
|Çok faktörlü kimlik doğrulaması|[İki aşamalı doğrulama: Ek doğrulama sayfası nedir?](/azure/active-directory/user-help/multi-factor-authentication-end-user-first-time)|Bu makale, son kullanıcıların çok faktörlü kimlik doğrulamasının ne olduğunu ve kuruluşunuzda neden kullanıldığını anlamasına yardımcı olur.|
|Saldırı simülasyonu eğitimi|[Saldırı simülasyonu eğitimini kullanmaya başlama](attack-simulation-training-get-started.md)|Office 365 için Microsoft Defender Plan 2'deki Saldırı simülasyonu eğitimi, yöneticinin belirli kullanıcı gruplarına yönelik sanal kimlik avı saldırılarını yapılandırmasına, başlatmasına ve izlemesine olanak tanır.|

Ayrıca Microsoft, kullanıcıların bu makalede açıklanan eylemleri gerçekleştirmelerini önerir: [Hesabınızı ve cihazlarınızı korsanlara ve kötü amaçlı yazılımlara karşı koruma](https://support.microsoft.com/office/066d6216-a56b-4f90-9af3-b3a1e9a327d6). Bu eylemler şunlardır:

- Güçlü parolalar kullanma
- Cihazları koruma
- Windows ve Mac bilgisayarlarda güvenlik özelliklerini etkinleştirme (yönetilmeyen cihazlar için)

## <a name="see-also"></a>Ayrıca bkz.

[Office 365 için Microsoft Defender'de Öncelik Hesabı Koruması Duyurusunda](https://techcommunity.microsoft.com/t5/microsoft-defender-for-office/announcing-priority-account-protection-in-microsoft-defender-for/ba-p/1696385)
