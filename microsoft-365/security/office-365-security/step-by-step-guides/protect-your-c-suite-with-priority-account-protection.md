---
title: Office 365 için Microsoft Defender Plan 2'de c-suite'inizi Öncelik hesabı koruması ile koruma
description: C paketinizi öncelikli hesap korumasıyla koruma adımları. Bir hesabın Öncelik hesabı olarak etiketlenmesi, şirket yöneticilerini hedefleyen posta akışı düzenleri için ayarlanmış ek korumanın yanı sıra raporlarda, uyarılarda ve araştırmalarda ek görünürlük sağlar.
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
ms.collection:
- m365-guidance-templates
- m365-security
- tier3
ms.topic: how-to
ms.subservice: mdo
search.appverid: met150
ms.openlocfilehash: 6f0bcce48b88d00e5ba8d6b28b9bbc9bfe2c1720
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2022
ms.locfileid: "68232550"
---
# <a name="protect-your-c-suite-with-priority-account-protection"></a>C-paketinizi öncelikli hesap korumasıyla koruyun

Öncelikli hesap koruması, BT ve güvenlik ekiplerinin kuruluşunuzdaki kritik kişiler için yüksek hizmet kalitesi ve koruma sağlamasına yardımcı olur. Bir hesabın öncelik hesabı olarak etiketlenmesi, şirket yöneticilerini hedefleyen posta akışı düzenleri için ayarlanmış ek korumanın yanı sıra raporlarda, uyarılarda ve araştırmalarda ek görünürlük sağlar.

## <a name="what-youll-need"></a>İhtiyacınız olan şey
- Office 365 için Microsoft Defender Plan 2 (E5 planlarının bir parçası olarak dahildir)
- Yeterli izinler (Güvenlik Yöneticisi rolü)
- Aşağıdaki adımları gerçekleştirmek için 5 dakika.

## <a name="tag-priority-users"></a>Etiket Önceliği kullanıcıları
1. Öncelik hesapları olarak etiketlemek istediğiniz kullanıcıları, grupları veya etki alanlarını belirleyin.
1. [Microsoft Güvenlik Portalı'nda](https://security.microsoft.com/) oturum açın ve sol gezinti çubuğunda Ayarlar'a gidin.
1. Yüklenen sayfada işbirliği Email & seçin ve ardından Kullanıcı etiketleri'ne tıklayın
1. Kullanıcı etiketleri sayfasında Öncelik hesabı etiketini seçin ve Etiketi düzenle'ye basın
1. Görüntülenen açılır öğede Üye ekle'yi seçin
1. Etiketlemek istediğiniz kullanıcıları arayın, bir veya daha fazla kullanıcı seçin ve Ekle'ye basın
1. Seçtiğiniz üyeleri gözden geçirin ve İleri'ye basın
1. Değişiklikleri onaylamak için Gönder'e basın

Öncelikli hesap etiketlerinin ne olduğunu öğrenmek için bkz. [Öncelik hesaplarını yönetme ve izleme - Microsoft 365 yönetici | Microsoft Docs](../../../admin/setup/priority-accounts.md).

## <a name="next-steps"></a>Sonraki Adımlar
[Öncelik hesapları olarak etiketlenen kullanıcılar için farklı korumayı gözden geçirin](../../office-365-security/configure-review-priority-account.md).

## <a name="powershell-configuration"></a>PowerShell yapılandırması
Bu adımları [PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) aracılığıyla gerçekleştirmek istiyorsanız, bunu aşağıdaki cmdlet'leri kullanarak yapabilirsiniz:
1. Öncelik hesaplarının listesini görüntüleme: **Get-User -IsVIP | Kimlik'i seçin**
1. Öncelik hesapları listesine kullanıcı ekleme: **Set-User -VIP:$true -Identity \<Identity\>**
1. Kullanıcıyı öncelik hesapları listesinden kaldırma: **Set-User -VIP:$false -Identity \<Identity\>**
