---
title: GCC ortamları için Microsoft Whiteboard'a erişimi yönetme
ms.author: v-jdeweese
author: johnddeweese
manager: alexfaulkner
ms.reviewer: ''
audience: admin
ms.topic: article
ms.custom: ''
ms.service: microsoft-365-enterprise
search.appverid: MET150
ms.collection: ''
ms.localizationpriority: medium
description: Whiteboard verilerini etkinleştirmeyi, devre dışı bırakmayı ve yönetmeyi öğrenin.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 46a4c6db8755f7ee2928828453518acdb2a2eb36
ms.sourcegitcommit: 2b89bcff547e00be3d38dc8d1e6cbcf8f41eba42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2022
ms.locfileid: "67877891"
---
# <a name="manage-access-to-microsoft-whiteboard-for-gcc-environments"></a>GCC ortamları için Microsoft Whiteboard'a erişimi yönetme

>[!NOTE]
> Bu kılavuz US Government Community Cloud (GCC) ortamları için geçerlidir.

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

- Microsoft Teams toplantı ilkesi kullanarak toplantılarda belirli kullanıcılar için Beyaz Tahta'nın gösterilmesi veya gizlenir. Web, yerel istemciler ve Teams sekme uygulaması aracılığıyla görünmeye devam eder.

- Azure Active Directory yönetim merkezini kullanarak Whiteboard'a erişmek için koşullu erişim ilkeleri gerektir.

>[!NOTE]
> Teams toplantı ilkesi yalnızca Beyaz Tahta giriş noktalarını gizler. Kullanıcıların Whiteboard kullanmasını engellemez. Koşullu erişim ilkeleri Beyaz Tahta'ya erişimi engeller, ancak giriş noktalarını gizlemez.

## <a name="enable-or-disable-whiteboard"></a>Beyaz Tahta'yı etkinleştirme veya devre dışı bırakma

Kiracınızda Whiteboard'ı etkinleştirmek veya devre dışı bırakmak için aşağıdaki adımları uygulayın: 

1. Microsoft 365 kiracınızdaki tüm Akıcı Deneyimleri etkinleştirmek veya devre dışı bırakmak için [SharePoint Online PowerShell modülünü](/microsoft-365/enterprise/manage-sharepoint-online-with-microsoft-365-powershell) kullanın.

2. [SharePoint Online PowerShell'e](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) bağlanın.

3. Aşağıdaki <code>Set-SPOTenant</code> cmdlet'i kullanarak Fluid'ı etkinleştirin:

   <pre><code class="lang-powershell">Set-SPOTenant -IsWBFluidEnabled $true</code></pre>

Değişikliğin kiracınıza uygulanması yaklaşık 60 dakika sürmelidir. Bu seçeneği görmüyorsanız modülü güncelleştirmeniz gerekir.

## <a name="show-or-hide-whiteboard"></a>Beyaz Tahtayı gösterme veya gizleme

Toplantılarda Beyaz Tahta'yı göstermek veya gizlemek için bkz [. Toplantı ilkesi ayarları](/microsoftteams/meeting-policies-content-sharing).

## <a name="see-also"></a>Ayrıca bkz.

[Whiteboard için verileri yönetme - GCC](manage-data-gcc.md)

[Whiteboard için paylaşımı yönetme - GCC](manage-sharing-gcc.md)

[Whiteboard için istemcileri yönetme - GCC](manage-clients-gcc.md)