---
title: Kuruluşunuzdaki veri gizliliği olaylarını izleme ve yanıtlama
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 01/04/2021
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection:
- highpri
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
- zerotrust-solution
ms.custom: ''
description: Kişisel veri olaylarını izlemek ve yanıtlamak için denetim ve uyarı ilkelerini ve veri sahibi isteklerini kullanın.
ms.openlocfilehash: ed30acfb052e31352ca2719a00d4ba8ed1a4c3bd
ms.sourcegitcommit: fce27da5140691b013a6f7c0ea9c88b4ea4b7c10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/23/2022
ms.locfileid: "67985597"
---
# <a name="monitor-and-respond-to-data-privacy-incidents-in-your-organization"></a>Kuruluşunuzdaki veri gizliliği olaylarını izleme ve yanıtlama

microsoft 365 özellikleri, kuruluşunuzdaki veri gizliliği olaylarını izlemenize, araştırmanıza ve yanıtlamanıza yardımcı olur ve ilgili özellikleri kullanıma hazır hale getirmenize yardımcı olur. Bunların her biri için süreçlere, yordamlara ve diğer belgelere sahip olmak, düzenleyici kurumlara uyumluluğu göstermek için de önemli olabilir.

Şunlar dahildir: 

- Denetim ve uyarı ilkeleri
- Veri sahibi istekleri (içerik arama ve eBulma dahil)
- Ek araştırma araçları ve raporlama

## <a name="data-privacy-regulations-impacting-the-use-of-monitoring-and-response-tools"></a>İzleme ve yanıt araçlarının kullanımını etkileyen veri gizliliği düzenlemeleri

Bilgi idaresi denetimleriyle ilgili olabilecek veri gizliliği düzenlemelerinin örnek bir listesi aşağıda verilmiştir:

- LGPD Makale 46
- LGPD Makale 48
- GDPR Makalesi (5)(1)(f)
- GDPR Makalesi (15)(1)(e)
- HIPAA-HITECH (45 C.F.R. 164.308(a)(1)(ii)(D))
- HIPAA-HITECH (45 C.F.R. 164.308(a)(6)(ii)
- HIPAA-HITECH (45 C.F.R. 164.312(b))
- CCPA (1798.105(c))

Daha fazla bilgi için bkz [. Veri gizliliği risklerini değerlendirme ve hassas bilgileri tanımlama](information-protection-deploy-assess.md).

Veri gizliliği düzenlemeleri genellikle izleme ve yanıt için aşağıdakileri çağırır:

- Kişisel verilerin depolanması, paylaşılması ve işlenmesiyle ilgili etkinlikler için denetim, uyarı ve raporlama
- Veri sahibi isteğine (DSR) yanıt verebilme ve bazı durumlarda bu tür isteklere uymak için araştırma ve diğer yönetim önlemlerini gerçekleştirme.

Kuruluşunuz ayrıca diğer uyumluluk gereksinimleri veya iş nedeniyle başka amaçlarla izleme ve yanıt etkinlikleri gerçekleştirmek isteyebilir. Veri gizliliği için izleme ve yanıt şemanızı oluşturma işlemi genel izleme ve yanıt planlaması, uygulaması ve yönetimi kapsamında yapılmalıdır.

Microsoft 365'te veri gizliliği düzenlemelerine yönelik izleme ve yanıt şemasını kullanmaya başlamanıza yardımcı olmak için, bu makalede Microsoft 365'te aşağıdaki gibi soruları yanıtlamaya yönelik yararlı özellikler listelenmektedir: 

- Farklı veri türleri ve kaynakları için günlük izleme, araştırma ve raporlama teknikleri ne tür kullanılabilir?
- Veri sahibi isteklerini (DSR) ve anonimleştirme, yeniden düzenleme ve silme gibi tüm düzeltme eylemlerini işlemek için hangi mekanizmaların gerekli olacağı.

## <a name="auditing-and-alert-policies-in-the-microsoft-purview-compliance-portal"></a>Microsoft Purview uyumluluk portalı Denetim ve Uyarı İlkeleri

Denetim, gelişmiş denetim ve uyarı ilkelerini ayarlamak için şu makalelere bakın:

- [Birleşik denetim](../compliance/search-the-audit-log-in-security-and-compliance.md)
- [Posta kutusu denetimi](../compliance/enable-mailbox-auditing.md)
- [Denetim (Premium)](../compliance/advanced-audit.md)
- [Uyarı ilkeleri](../compliance/alert-policies.md)

## <a name="data-subject-requests-for-the-gdpr-and-ccpa"></a>GDPR ve CCPA için veri sahibi istekleri

Microsoft 365'te DSR'ye yanıt verme hakkında bilgi için bkz. [GDPR ve CCPA için Veri Sahibi İstekleri](/compliance/regulatory/gdpr-dsr-Office365) .

## <a name="manage-deleted-users-in-microsoft-stream"></a>Microsoft Stream'de silinen kullanıcıları yönetme

Microsoft Stream için, bir kullanıcı Azure Active Directory'den (Azure AD) silindiğinde, adı bu noktadan önce gönderilen bir Stream videosuyla ilişkilendirildiyse, e-posta adresi videoyla ilişkili kalır. Kaldırmak için bkz. [Silinmiş kullanıcıları Microsoft Stream'den yönetme](/stream/managing-deleted-users).

## <a name="insider-risk-management-as-an-investigative-tool"></a>Araştırma aracı olarak Insider risk yönetimi

[Insider risk yönetimi](../compliance/insider-risk-management.md), kuruluşunuzdaki riskli etkinlikleri algılamanıza, araştırmanıza ve üzerinde işlem yapmanıza olanak tanıyarak iç riski en aza indirmenize yardımcı olmak için Microsoft Purview uyumluluk portalı bir özelliğidir.
