---
title: Exchange Online, e-posta sırlarınızı nasıl güvence altına alır?
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 07/01/2019
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: 989ba10c-f73f-4efb-ad1b-af3322e5f376
ms.collection:
- M365-security-compliance
description: Microsoft 365 için Güvenlik, Gizlilik ve Uyumluluk Bilgileri sağlayan Office 365 Güven Merkezi'ne ek olarak, Microsoft'un veri merkezlerinde depoladığınız gizli dizileri korumaya nasıl yardımcı olduğunu bilmek isteyebilirsiniz. Dağıtılmış Anahtar Yöneticisi (DKM) adlı bir teknoloji kullanıyoruz.
ms.openlocfilehash: a1d939ebfc1ecba1e7cb8b97111f677f754894b1
ms.sourcegitcommit: 437461fa1d38ff9bb95dd8a1c5f0b94e8111ada2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67679053"
---
# <a name="how-exchange-online-secures-your-email-secrets"></a>Exchange Online, e-posta sırlarınızı nasıl güvence altına alır?

Bu makalede, Microsoft'un veri merkezlerindeki e-posta gizli dizilerinizi nasıl güvenli bir şekilde sakladığı açıklanmaktadır.
  
## <a name="how-do-we-secure-secret-information-provided-by-you"></a>Sizin sağladığınız gizli bilgileri nasıl güvence altına alıyacağız?

Office 365 [için Güvenlik, Gizlilik ve Uyumluluk Bilgileri sağlayan Office 365](./get-started-with-service-trust-portal.md) Güven Merkezi'ne ek olarak, Microsoft'un veri merkezlerinde sağladığınız gizli dizilerin korunmasına nasıl yardımcı olduğunu bilmek isteyebilirsiniz. Dağıtılmış Anahtar Yöneticisi (DKM) adlı bir teknoloji kullanıyoruz.
  
[Dağıtılmış Anahtar Yöneticisi](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) (DKM), bilgileri şifrelemek ve şifresini çözmek için bir dizi gizli anahtar kullanan bir istemci tarafı işlevidir. DKM tarafından şifrelenen verilerin şifresini çözmek için yalnızca Active Directory Domain Services'daki belirli bir güvenlik grubunun üyeleri bu anahtarlara erişebilir. Exchange Online yalnızca Exchange işlemlerinin çalıştırıldığı belirli hizmet hesapları bu güvenlik grubunun bir parçasıdır. Veri merkezinde standart çalışma yordamının bir parçası olarak, hiçbir insana bu güvenlik grubunun parçası olan kimlik bilgileri verilmez ve bu nedenle hiçbir insan bu gizli dizilerin şifresini çözebilecek anahtarlara erişemez.
  
Hata ayıklama, sorun giderme veya denetim amacıyla, bir veri merkezi yöneticisinin güvenlik grubunun parçası olan geçici kimlik bilgilerini kazanmak için yükseltilmiş erişim istemesi gerekir. Bu işlem için birden fazla yasal onay düzeyi gerekir. Erişim verilirse tüm etkinlikler günlüğe kaydedilir ve denetlener. Ayrıca erişim yalnızca otomatik olarak sona erdiği belirli bir süre için verilir.
  
Ek koruma için DKM teknolojisi otomatik anahtar geçişi ve arşivleme içerir. Bu ayrıca aynı anahtara süresiz olarak güvenmek zorunda kalmadan eski içeriğinize erişmeye devam edebilirsiniz.
  
## <a name="where-does-exchange-online-make-use-of-dkm"></a>Exchange Online DKM'Exchange Online nereden yararlanır?

Microsoft, Exchange Online veri merkezlerinde gizli dizilerinizi şifrelemek için [Dağıtılmış Anahtar Yöneticisi'ni](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) kullanır. Örneğin:
  
- Bağlı hesaplar için hesap kimlik bilgilerini Email. Bağlı hesaplar Hotmail, Gmail ve Yahoo! gibi üçüncü taraf hesaplardır posta hesapları.

- Müşteri anahtarı. [Müşteri Anahtarı ile Hizmet şifrelemesi](customer-key-overview.md) kullanıyorsanız, gizli dizilerinizi korumak için [Azure Key Vault](/azure/key-vault/key-vault-whatis) kullanırsınız.

## <a name="related-topics"></a>İlgili konular

[Office 365'de şifreleme](encryption.md)
  
[Şifreleme hakkında teknik başvuru ayrıntıları](technical-reference-details-about-encryption.md)
  
[Güvenlik &amp; Uyumluluk Merkezi'nde hizmet güvencesi](./service-assurance.md)
