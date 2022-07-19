---
title: Kuruluşunuz için Microsoft Whiteboard erişimini etkinleştirme ve yönetme
ms.author: chucked
author: chuckedmonson
manager: alexfaulkner
ms.reviewer: ''
audience: admin
ms.topic: article
ms.custom: ''
ms.prod: microsoft-365-enterprise
search.appverid: MET150
ms.collection: ''
ms.localizationpriority: medium
description: Microsoft 365 yönetim merkezi kuruluşunuz için Microsoft Whiteboard'u ayarlamayı öğrenin.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: b84a49f51b60b1aab7ea2ee791dbcc2e47520c64
ms.sourcegitcommit: b0b1be67de8f40b199bb9b51eb3568e59377e93a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/18/2022
ms.locfileid: "66861946"
---
# <a name="enable-and-manage-access-to-microsoft-whiteboard-for-your-organization"></a>Kuruluşunuz için Microsoft Whiteboard erişimini etkinleştirme ve yönetme

>[!NOTE]
> Bu makale, Whiteboard kullanan Kurumsal veya Eğitim kuruluşları için geçerlidir. US Government GCC High ortamları için bkz. [GCC High ortamları için Microsoft Whiteboard erişimini etkinleştirme ve yönetme](enable-whiteboard-access-gcc-high.md).

Microsoft Whiteboard, kişilerin, içeriğin ve fikirlerin bir araya geldiği görsel bir işbirliği tuvalidir. Whiteboard bugün Kurumsal ve Eğitim için Azure müşterileri üzerinde çalışmaktadır. Beyaz Tahta, OneDrive İş üzerinde çalıştırılmaya geçiliyor. Bu geçiş birçok yeni özellik getirir ve beyaz tahtaları herhangi bir Office belgesi kadar kolay bir şekilde oluşturmanıza, paylaşmanıza, keşfetmenize ve yönetmenize olanak sağlar.

Beyaz Tahta, geçerli Microsoft 365 kiracıları için otomatik olarak etkinleştirilir. 

Whiteboard SOC 1, SOC 2, ISO 27001, HIPAA ve AB Model Maddeleri gibi küresel standartlara uygundur. 

Whiteboard için aşağıdaki yönetici ayarları gereklidir:

- Beyaz Tahta Microsoft 365 yönetim merkezi genel olarak etkinleştirilmelidir.

- Cmdlet,SharePoint <code>Set-SPOTenant -IsWBFluidEnabled</code> [Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) kullanılarak etkinleştirilmelidir.

>[!NOTE]
> OneDrive İş depolamanın dağıtımı devam ediyor. Microsoft 365 yönetim merkezi gittiğinizde, kiracınız zaten OneDrive İş'e geçirilmişse OneDrive İş depolamayı kabul etme veya devre dışı bırakma seçeneği devre dışı bırakılır.

Whiteboard'a erişimi aşağıdaki yollarla denetleyebilirsiniz:

- Microsoft 365 yönetim merkezi kullanarak beyaz tahtayı tüm kiracınız için etkinleştirin veya devre dışı bırakın.

- Teams toplantı ilkesi kullanarak toplantılarda belirli kullanıcılar için Beyaz Tahta'nın gösterilmesi veya gizlenir. Web, yerel istemciler ve Teams sekme uygulaması aracılığıyla görünmeye devam eder.

- Azure Active Directory yönetim merkezini kullanarak Whiteboard'a erişmek için koşullu erişim ilkeleri gerektir.

>[!NOTE]
> Teams toplantı ilkeleri yalnızca Beyaz Tahta giriş noktalarını gizler; kullanıcıların Whiteboard kullanmasını engellemez. Koşullu erişim ilkeleri Beyaz Tahta'ya erişimi engeller, ancak giriş noktalarını gizlemez.

## <a name="enable-or-disable-whiteboard"></a>Beyaz Tahta'yı etkinleştirme veya devre dışı bırakma

Kiracınızda Whiteboard'ı etkinleştirmek veya devre dışı bırakmak için aşağıdaki adımları uygulayın:

1. Microsoft 365 yönetim merkezi gidin.

2. Yönetim merkezinin giriş sayfasında, sağ üstteki Arama kutusuna *Beyaz Tahta* yazın.

3. Arama sonuçlarında **Beyaz Tahta ayarları'nı** seçin.

4. Beyaz Tahta panelinde Beyaz **Tahta'yı tüm kuruluşunuz için aç veya kapat** seçeneğini **Açık** duruma getirin.

5. **Kaydet**'i seçin.

6. [SharePoint Online PowerShell'e](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) bağlanın.

7. Aşağıdaki <code>Set-SPOTenant</code> cmdlet'i kullanarak Fluid'ı etkinleştirin:

   <pre><code class="lang-powershell">Set-SPOTenant -IsWBFluidEnabled $true</code></pre>
 
## <a name="show-or-hide-whiteboard"></a>Beyaz Tahtayı gösterme veya gizleme

Toplantılarda Beyaz Tahta'yı göstermek veya gizlemek için bkz [. Toplantı ilkesi ayarları](/microsoftteams/meeting-policies-content-sharing). 

## <a name="prevent-access-to-whiteboard"></a>Whiteboard'a erişimi engelleme

Belirli kullanıcılar için Whiteboard'a erişimi engellemek için bkz. [Koşullu Erişim ilkesi oluşturma](/azure/active-directory/conditional-access/concept-conditional-access-policies).

## <a name="see-also"></a>Ayrıca bkz.

[Whiteboard için verileri yönetme](manage-data-organizations.md)

[Whiteboard için paylaşımı yönetme](manage-sharing-organizations.md)

[Windows'da Whiteboard'ı dağıtma](deploy-on-windows-organizations.md)
