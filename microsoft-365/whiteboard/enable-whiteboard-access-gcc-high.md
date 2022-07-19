---
title: GCC High ortamları için Microsoft Whiteboard erişimini etkinleştirme ve yönetme
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
description: Whiteboard verilerini etkinleştirmeyi, devre dışı bırakmayı ve yönetmeyi öğrenin.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: e99e1cd92038f02e38dcd28c8f94400344f53fe7
ms.sourcegitcommit: b0b1be67de8f40b199bb9b51eb3568e59377e93a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/18/2022
ms.locfileid: "66861940"
---
# <a name="enable-and-manage-access-to-microsoft-whiteboard-for-gcc-high-environments"></a>GCC High ortamları için Microsoft Whiteboard erişimini etkinleştirme ve yönetme

>[!NOTE]
> Bu kılavuz, ABD Kamu Topluluk Bulutu (GCC) Yüksek ortamları için geçerlidir.

OneDrive İş'da Microsoft Whiteboard, geçerli Microsoft 365 kiracıları için varsayılan olarak etkindir. Kiracı genelinde bir düzeyde etkinleştirilebilir veya devre dışı bırakılabilir. Ayrıca **Azure Active Directory yönetim merkezi** > **Kurumsal uygulamalarında** **Microsoft Whiteboard Services'ın** etkinleştirildiğinden de emin olmanız gerekir.

Aşağıdaki URL'ler gereklidir:

- 'https://*.office365.us/'
- 'https://login.microsoftonline.us/'
- 'https://graph.microsoft.us/'
- 'https://graph.microsoftazure.us/'
- 'https://admin.onedrive.us'
- 'https://shell.cdn.office.net/'
- 'https://config.ecs.gov.teams.microsoft.us'
- 'https://tb.events.data.microsoft.com/'

Whiteboard'a erişimi aşağıdaki yollarla denetleyebilirsiniz:

- [SharePoint Online PowerShell modülünü](/microsoft-365/enterprise/manage-sharepoint-online-with-microsoft-365-powershell) kullanarak beyaz tahtayı tüm kiracınız için etkinleştirin veya devre dışı bırakın.

- Teams toplantı ilkesi kullanarak toplantılarda belirli kullanıcılar için Beyaz Tahta'nın gösterilmesi veya gizlenir. Web, yerel istemciler ve Teams sekme uygulaması aracılığıyla görünmeye devam eder.

- Azure Active Directory yönetim merkezini kullanarak Whiteboard'a erişmek için koşullu erişim ilkeleri gerektir.

>[!NOTE]
> OneDrive İş beyaz tahta Microsoft 365 yönetim merkezi görünmez. Teams toplantı ilkesi yalnızca Beyaz Tahta giriş noktalarını gizler, kullanıcıların Whiteboard kullanmasını engellemez. Koşullu erişim diskleri Whiteboard'a erişimi engeller, ancak giriş noktalarını gizlemez.

## <a name="enable-or-disable-whiteboard"></a>Beyaz Tahta'yı etkinleştirme veya devre dışı bırakma

Kiracınızda Whiteboard'ı etkinleştirmek veya devre dışı bırakmak için aşağıdaki adımları uygulayın: 

1. Microsoft 365 kiracınızdaki tüm Akıcı Deneyimleri etkinleştirmek veya devre dışı bırakmak için [SharePoint Online PowerShell modülünü](/microsoft-365/enterprise/manage-sharepoint-online-with-microsoft-365-powershell) kullanın.

2. [SharePoint Online PowerShell'e](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) bağlanın.

3. Aşağıdaki <code>Set-SPOTenant</code> cmdlet'i kullanarak Fluid'ı etkinleştirin:

   <pre><code class="lang-powershell">Set-SPOTenant -IsWBFluidEnabled $true</code></pre>

Değişikliğin kiracınıza uygulanması yaklaşık 60 dakika sürmelidir. Bu seçeneği görmüyorsanız modülü güncelleştirmeniz gerekir.

>[!NOTE]
> Beyaz Tahta varsayılan olarak etkindir. Azure Active Directory kurumsal uygulamalarında devre dışı bırakıldıysa OneDrive İş'da Beyaz Tahta çalışmaz.

## <a name="show-or-hide-whiteboard"></a>Beyaz Tahtayı gösterme veya gizleme

Toplantılarda Beyaz Tahta'yı göstermek veya gizlemek için bkz [. Toplantı ilkesi ayarları](/microsoftteams/meeting-policies-content-sharing).

## <a name="see-also"></a>Ayrıca bkz.

[Whiteboard için verileri yönetme - GCC High](manage-data-gcc-high.md)

[Whiteboard için paylaşımı yönetme - GCC High](manage-sharing-gcc-high.md)

[Whiteboard için istemcileri yönetme - GCC High](manage-clients-gcc-high.md)




