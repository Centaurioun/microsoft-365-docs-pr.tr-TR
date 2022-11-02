---
title: Exchange Online, e-posta sırlarınızı nasıl güvence altına alır?
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/31/2022
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- purview-compliance
description: "Microsoft 365 için Güvenlik, Gizlilik ve Uyumluluk Bilgileri sağlayan Microsoft Güven Merkezi'ne ek olarak, Microsoft'un veri merkezlerinde depoladığınız gizli dizileri korumaya nasıl yardımcı olduğunu öğrenin. "
ms.openlocfilehash: e46788c763e7b930c79abc918a9f4706b896ff23
ms.sourcegitcommit: a66b30765efc0ea0eca865f08a62d45047a90246
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/02/2022
ms.locfileid: "68828064"
---
# <a name="how-exchange-online-secures-your-email-secrets"></a>Exchange Online, e-posta sırlarınızı nasıl güvence altına alır?

Bu makalede, Microsoft'un veri merkezlerindeki e-posta gizli dizilerinizi nasıl güvenli bir şekilde sakladığı açıklanmaktadır.
  
[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="how-we-secure-secret-information-provided-by-you"></a>Sizin tarafınızdan sağlanan gizli bilgileri nasıl güvenli bir şekilde sağlarız?

Office 365 [için Güvenlik, Gizlilik ve Uyumluluk Bilgileri sağlayan Office 365](./get-started-with-service-trust-portal.md) Güven Merkezi'ne ek olarak Dağıtılmış Anahtar Yöneticisi (DKM) adlı bir teknoloji kullanıyoruz.
  
[Dağıtılmış Anahtar Yöneticisi](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) (DKM), bilgileri şifrelemek ve şifresini çözmek için bir dizi gizli anahtar kullanan bir istemci tarafı teknolojisidir. DKM tarafından şifrelenen verilerin şifresini çözmek için yalnızca Active Directory Domain Services'daki belirli bir güvenlik grubunun üyeleri bu anahtarlara erişebilir. Exchange Online yalnızca Exchange işlemlerinin çalıştırıldığı belirli hizmet hesapları bu güvenlik grubunun bir parçasıdır. Hiçbir insana bu güvenlik grubunun parçası olan kimlik bilgileri verilmez ve bu nedenle hiçbir insan bu gizli dizilerin şifresini çözebilecek anahtarlara erişemez.
  
Hata ayıklama, sorun giderme veya denetim amacıyla, bir veri merkezi yöneticisinin güvenlik grubunun parçası olan geçici kimlik bilgilerini kazanmak için yükseltilmiş erişim istemesi gerekir. Bu işlem için birden fazla yasal onay düzeyi gerekir. Erişim verilirse tüm etkinlikler günlüğe kaydedilir ve denetlener. Erişim yalnızca otomatik olarak sona erdiği belirli bir zaman aralığı için verilir.
  
Ek koruma için DKM teknolojisi otomatik anahtar geçişi ve arşivleme içerir. Otomatik geçiş ve arşivleme, aynı anahtarı süresiz olarak kullanmak zorunda kalmadan eski içeriğinize erişmeye devam edebilirsiniz.
  
## <a name="where-exchange-online-uses-dkm"></a>Exchange Online DKM kullandığı yer

Microsoft, Exchange Online veri merkezlerinde gizli dizilerinizi şifrelemek için [Dağıtılmış Anahtar Yöneticisi'ni](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) kullanır. Örneğin:
  
- Bağlı hesaplar için hesap kimlik bilgilerini Email. Bağlı hesaplar Hotmail, Gmail ve Yahoo! gibi üçüncü taraf hesaplardır posta hesapları.

- Müşteri Anahtarı. [Microsoft Purview Müşteri Anahtarı ile Hizmet şifrelemesi](customer-key-overview.md) kullanıyorsanız, gizli dizilerinizi korumak için [Azure Key Vault](/azure/key-vault/key-vault-whatis) kullanırsınız.

## <a name="related-articles"></a>İlgili makaleler

[Office 365'de şifreleme](encryption.md)
  
[Şifreleme hakkında teknik başvuru ayrıntıları](technical-reference-details-about-encryption.md)
  
[Microsoft Purview uyumluluk portalı hizmet güvencesi](./service-assurance.md)
