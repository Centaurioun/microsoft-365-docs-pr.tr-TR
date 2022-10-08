---
title: Kimlik avından koruma
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: 75af74b2-c7ea-4556-a912-8c48e07271d3
ms.collection:
- m365-security
- m365initiative-defender-office365
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
description: Yöneticiler, Exchange Online Protection (EOP) ve Office 365 için Microsoft Defender kimlik avı koruması özellikleri hakkında bilgi edinebilir.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: a1f5914d0687a437dfe7b026ea02c9c33b026a9d
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68090937"
---
# <a name="anti-phishing-protection-in-microsoft-365"></a>Microsoft 365'te kimlik avı koruması

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Uygulandığı öğe**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365 için Microsoft Defender plan 1 ve plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

*Kimlik avı* , meşru veya güvenilir gönderenlerden geliyormuş gibi görünen iletilerdeki hassas bilgileri çalmaya çalışan bir e-posta saldırısıdır. Belirli kimlik avı kategorileri vardır. Örneğin:

- **Zıpkınla kimlik avı** , hedeflenen alıcılara özel olarak uyarlanmış odaklanmış, özelleştirilmiş içeriği kullanır (genellikle, saldırgan tarafından alıcılar üzerinde keşif yaptıktan sonra).

- **Balina avcılığı** , maksimum etki için bir kuruluştaki yöneticilere veya diğer yüksek değerli hedeflere yönlendirilir.

- **İş e-posta güvenliğinin aşılması (BEC),** sahte güvenilir gönderenleri (finans görevlileri, müşteriler, güvenilir iş ortakları vb.) kullanarak alıcıları ödemeleri onaylama, fon aktarma veya müşteri verilerini ortaya çıkarma konusunda kandırabilir. [Bu videoyu](https://www.youtube.com/watch?v=8Kn31h9HwIQ&list=PL3ZTgFEc7LystRja2GnDeUFqk44k7-KXf&index=2) izleyerek daha fazla bilgi edinin.

- Verilerinizi şifreleyen ve şifresini çözmek için ödeme gerektiren **fidye yazılımı** neredeyse her zaman kimlik avı iletilerinde başlar. Kimlik avı koruması şifrelenmiş dosyaların şifresini çözmenize yardımcı olmaz, ancak fidye yazılımı kampanyasıyla ilişkili ilk kimlik avı iletilerini algılamanıza yardımcı olabilir. Fidye yazılımı saldırısından kurtarma hakkında daha fazla bilgi için bkz. [Microsoft 365'te fidye yazılımı saldırısından kurtarma](recover-from-ransomware.md).

Saldırıların karmaşıklığının artmasıyla, eğitilmiş kullanıcıların gelişmiş kimlik avı iletilerini tanımlaması bile zordur. Neyse ki Exchange Online Protection (EOP) ve Office 365 için Microsoft Defender'deki ek özellikler yardımcı olabilir.

## <a name="anti-phishing-protection-in-eop"></a>EOP'de kimlik avı koruması

EOP (başka bir deyişle, Office 365 için Microsoft Defender olmayan Microsoft 365 kuruluşları), kuruluşunuzun kimlik avı tehditlerine karşı korunmasına yardımcı olabilecek özellikler içerir:

- **Kimlik sahtekarlık zekası**: Dış ve iç etki alanlarından gelen iletilerde algılanan sahte gönderenleri gözden geçirmek ve bu algılanan gönderenlere el ile izin vermek veya bunları engellemek için kimlik sahtekarlığına ilişkin akıllı bilgi içgörülerini kullanın. Daha fazla bilgi için bkz [. EOP'de sahte zeka içgörüleri](learn-about-spoof-intelligence.md).

- **EOP'de kimlik avı önleme ilkeleri**: Kimlik sahtekarlığı zekasını açın veya kapatın, Outlook'ta kimliği doğrulanmamış gönderen göstergelerini açın veya kapatın ve engellenen sahte gönderenler için eylemi belirtin. Daha fazla bilgi için bkz. [EOP'de kimlik avı önleme ilkelerini yapılandırma](configure-anti-phishing-policies-eop.md).

- **Kiracı İzin Ver/Engelle Listesinde sahte gönderenlere izin ver veya engelle**: Kimlik sahtekarı zeka içgörülerinde kararı geçersiz kıldığınızda, sahte gönderen yalnızca Kiracı İzin Ver/Engelle Listesi'ndeki Sahte **Gönderenler** sekmesinde görünen el ile izin verme veya engelleme girdisine dönüşür. Ayrıca kimlik sahtekarı gönderenler için kimlik sahtekarı zekası tarafından algılanana kadar el ile izin verme veya engelleme girdileri oluşturabilirsiniz. Daha fazla bilgi için bkz. [EOP'de Kiracı İzin Verme/Engelleme Listesini Yönetme](manage-tenant-allow-block-list.md).

- **Örtük e-posta kimlik doğrulaması**: EOP, sahte gönderenleri tanımlamaya yardımcı olmak için gelen e-posta ([SPF](set-up-spf-in-office-365-to-help-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md) ve [DMARC](use-dmarc-to-validate-email.md) ) için standart e-posta kimlik doğrulama denetimlerini gönderenin itibarı, gönderen geçmişi, alıcı geçmişi, davranış analizi ve diğer gelişmiş tekniklerle geliştirir. Daha fazla bilgi için bkz. [Microsoft 365'te kimlik doğrulaması Email](email-validation-and-authentication.md).

## <a name="additional-anti-phishing-protection-in-microsoft-defender-for-office-365"></a>Office 365 için Microsoft Defender'de ek kimlik avı koruması

Office 365 için Microsoft Defender ek ve daha gelişmiş kimlik avı önleme özellikleri içerir:

- **Office 365 için Microsoft Defender kimlik avı önleme ilkeleri**: Belirli ileti gönderenleri ve gönderen etki alanları, posta kutusu zekası ayarları ve ayarlanabilir gelişmiş kimlik avı eşikleri için kimliğe bürünme koruma ayarlarını yapılandırın. Daha fazla bilgi için bkz. [Office 365 için Microsoft Defender'de kimlik avı önleme ilkelerini yapılandırma](configure-mdo-anti-phishing-policies.md). EOP'deki kimlik avı önleme ilkeleri ile Office 365 için Defender kimlik avı önleme ilkeleri arasındaki farklar hakkında daha fazla bilgi için bkz. [Microsoft 365'te kimlik avı önleme ilkeleri](set-up-anti-phishing-policies.md).
- **Kampanya Görünümleri**: Makine öğrenmesi ve diğer buluşsal yöntemler, hizmetin tamamına ve kuruluşunuza yönelik eşgüdümlü kimlik avı saldırılarına katılan iletileri tanımlar ve analiz eder. Daha fazla bilgi için bkz. [Office 365 için Microsoft Defender'de Kampanya Görünümleri](campaigns.md).
- **Saldırı simülasyonu eğitimi**: Yöneticiler sahte kimlik avı iletileri oluşturabilir ve bunları eğitim aracı olarak dahili kullanıcılara gönderebilir. Daha fazla bilgi için bkz. [Kimlik avı saldırısı benzetimi](attack-simulation-training.md) yapma.

## <a name="other-anti-phishing-resources"></a>Diğer kimlik avı önleme kaynakları

- Son kullanıcılar için: Kendinizi [kimlik avı düzenlerinden ve diğer çevrimiçi dolandırıcılık biçimlerinden koruyun](https://support.microsoft.com/office/be0de46a-29cd-4c59-aaaf-136cf177d593).

- [Microsoft 365, kimlik avının önlenmesi için Kimden adresini nasıl doğrular](how-office-365-validates-the-from-address.md)?
