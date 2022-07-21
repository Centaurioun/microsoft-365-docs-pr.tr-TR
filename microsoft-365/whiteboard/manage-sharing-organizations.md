---
title: Microsoft Whiteboard için paylaşımı yönetme
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
description: Microsoft Whiteboard için paylaşımı yönetmeyi öğrenin.
ms.openlocfilehash: 22f5d80a914ce7b97765fca1e20f00a30732b820
ms.sourcegitcommit: 24827a509b3e78959ce67679646e572a0c996282
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66917617"
---
# <a name="manage-sharing-for-microsoft-whiteboard"></a>Microsoft Whiteboard için paylaşımı yönetme

Paylaşım deneyimi, Teams toplantısında olmanıza, paylaşılan bir cihaz kullanıyor olmanıza veya hangi kiracı düzeyinde paylaşım ayarlarının etkinleştirildiğine bağlı olarak farklılık gösterir. Aşağıdaki senaryolar yalnızca Whiteboard OneDrive İş depolamayı kullanmaya geçtikten sonra oluşturulan yeni beyaz tahtalar için geçerlidir. Azure'da depolanmaya devam eden önceden oluşturulmuş panolarda herhangi bir değişiklik yoktur.

## <a name="share-in-teams-meetings"></a>Teams toplantılarında paylaşma

Teams toplantısında beyaz tahta paylaştığınızda Whiteboard, kuruluştaki herkes tarafından erişilebilen bir paylaşım bağlantısı oluşturur. Ardından beyaz tahtayı toplantıdaki kiracı içi kullanıcılarla otomatik olarak paylaşır.

Toplantı sırasında dış ve paylaşılan cihaz hesapları tarafından geçici işbirliği için ek bir özellik vardır. Bu özellik, bu kullanıcıların teams toplantısında paylaşıldıklarında beyaz tahtaları PowerPoint Canlı paylaşımına benzer şekilde geçici olarak görüntülemesine ve üzerinde işbirliği yapmasına olanak tanır.

>[!NOTE]
> Bu bir paylaşım bağlantısı değildir ve dosyaya erişim izni vermez. Yalnızca Teams toplantısı süresi boyunca beyaz tahta üzerinde geçici görüntüleme ve işbirliği sağlar.

OneDrive İş için dış paylaşımı etkinleştirdiyseniz başka işlem yapmanız gerekmez.

OneDrive İş için dış paylaşımı kısıtlarsanız, dış ve paylaşılan cihaz hesaplarının çalışması için bu ayarı kısıtlayabilir ve yalnızca yeni bir ayarı etkinleştirebilirsiniz. Bunu yapmak için şu adımları uygulayın:

1. PowerShell kullanarak kiracınıza bağlanın ve aşağıdaki komutu çalıştırarak SharePoint Online modülünün güncelleştirildiğinden emin olun:

   <pre><code class="lang-powershell">Update-Module -Name Microsoft.Online.SharePoint.PowerShell</code></pre>
 
2. Ardından aşağıdaki <code>Set-SPOTenant</code> cmdlet'i çalıştırın:

   <pre><code class="lang-powershell">Set-SPOTenant -AllowAnonymousMeetingParticipantsToAccessWhiteboards On</code></pre>

Bu ayar yalnızca beyaz tahtalar için geçerlidir ve önceden paylaşılan **OneDriveLoopSharingCapability** ve **CoreLoopSharingCapability ayarlarının** yerini alır. Bu ayarlar artık geçerli değildir ve göz ardı edilebilir.

>[!NOTE]
> Varsayılan olarak, **Anonim kullanıcılar toplantılardaki uygulamalarla etkileşimde bulunabilir Teams toplantı** ayarı etkindir. Devre dışı bırakdıysanız, toplantı sırasında hiçbir anonim kullanıcı (konuklar veya federasyon kullanıcıları yerine) beyaz tahtaya erişemez.

Bu değişikliklerin kiracınız genelinde uygulanması yaklaşık 60 dakika sürmelidir. 

|Senaryo  |Depolama ve sahiplik  |Paylaşım ayarları  |Paylaşım deneyimi  |
|---------|---------|---------|---------|
|Beyaz tahtayı masaüstünden veya mobil cihazdan başlatma  |Depolama: OneDrive İş<br><br>Sahip: Beyaz tahtayı oluşturan kullanıcı  |Etkin  |Kiracı içi kullanıcılar: Oluşturabilir, görüntüleyebilir ve işbirliği yapabilir<br><br>Dış kullanıcılar: Yalnızca toplantı sırasında görüntüleyebilir ve işbirliği yapabilir (beyaz tahtayı paylaşma düğmesi dış kullanıcılar için görünmez)<br><br>Paylaşılan cihaz hesapları: Yalnızca toplantı sırasında görüntüleyebilir ve işbirliği yapabilir  |
|Beyaz tahtayı masaüstünden veya mobil cihazdan başlatma  |Depolama: OneDrive İş<br><br>Sahip: Beyaz tahtayı oluşturan kullanıcı  |Devre dışı  |Kiracı içi kullanıcılar: Başlatabilir, görüntüleyebilir ve işbirliği yapabilir<br><br>Dış kullanıcılar: Görüntülenemez veya işbirliği yapılamaz<br><br>Paylaşılan cihaz hesapları: Görüntülenemez veya işbirliği yapılamaz  |
|Beyaz tahtayı Surface Hub'dan veya Microsoft Teams Odaları başlatma  |Depolama: Azure (bu işlem gelecekte OneDrive İş taşınacaktır)<br><br>Sahip: Toplantı katılımcısı   |Geçerli değil  |Kiracı içi kullanıcılar: Başlatabilir, görüntüleyebilir ve işbirliği yapabilir<br><br>Dış kullanıcılar: Yalnızca toplantı sırasında görüntüleyebilir ve işbirliği yapabilir<br><br>Paylaşılan cihaz hesapları: Yalnızca toplantı sırasında görüntüleyebilir ve işbirliği yapabilir  |

## <a name="add-as-a-tab-in-teams-channels-and-chats"></a>Teams kanallarında ve sohbetlerinde sekme olarak ekleme

Teams kanalına veya sohbete sekme olarak beyaz tahta eklediğinizde Whiteboard, kuruluştaki herkes tarafından erişilebilen bir paylaşım bağlantısı oluşturur.

|Senaryo  |Depolama ve sahiplik  |Paylaşım ayarları  |Paylaşım deneyimi  |
|---------|---------|---------|---------|
|Beyaz tahtayı bir kanala ekleme veya masaüstü veya mobil cihazdan sohbet etme  |Depolama: OneDrive İş<br><br>Sahip: Beyaz tahtayı oluşturan kullanıcı  |Uygulanamaz (yalnızca toplantılar için geçerlidir)  |Kiracı içi kullanıcılar: Başlatabilir, görüntüleyebilir ve işbirliği yapabilir<br><br>Dış kullanıcılar: Desteklenmez<br><br>Teams konukları: Görüntüleyebilir ve işbirliği yapabilir<br><br>Paylaşılan cihaz hesapları: Geçerli değil  |

## <a name="create-and-share-in-whiteboard-native-clients"></a>Whiteboard yerel istemcilerinde oluşturma ve paylaşma

Beyaz tahtaları web, masaüstü veya mobil istemcilerden paylaştığınızda belirli kişileri seçebilirsiniz. Kuruluştaki herkes tarafından erişilebilen bir paylaşım bağlantısı da oluşturabilirsiniz. 

>[!NOTE]
> Teams toplantısı sırasında dış paylaşım henüz sunulmaz, ancak gelecek bir sürümde eklenecektir.

|Senaryo  |Depolama ve sahiplik  |Paylaşım ayarları  |Paylaşım deneyimi  |
|---------|---------|---------|---------|
|Masaüstü veya mobil cihazdan beyaz tahta oluşturma  |Depolama: OneDrive İş<br><br>Sahip: Beyaz tahtayı oluşturan kullanıcı  |Uygulanamaz (yalnızca toplantılar için geçerlidir)  |Kiracı içi kullanıcılar: Kuruluşlarında paylaşabilir<br><br>Dış kullanıcılar: Dış kullanıcılarla paylaşım şu anda desteklenmiyor  |
|Surface Hub'dan beyaz tahta oluşturma  |Depolama: Yerel<br><br>Sahip: Yok (Kullanıcı panoyu kaydetmek ve paylaşmak için oturum açmadığı sürece, bu da OneDrive İş kaydeder. Kolay paylaşım gelecekte yeniden eklenecektir.  |Uygulanamaz (yalnızca toplantılar için geçerlidir)  |Kiracı içi kullanıcılar: Kullanıcının panoyu kaydedip paylaşmak için oturum açması gerekir (Gelecekte Kolay paylaşım eklenecektir)<br><br>Dış kullanıcılar: Şu anda Teams toplantısı dışında dış kullanıcılarla paylaşım desteklenmez  |
|Microsoft Teams Odaları'dan beyaz tahta oluşturma  |Henüz desteklenmiyor  |Uygulanamaz (yalnızca toplantılar için geçerlidir)  |Henüz desteklenmiyor  |

## <a name="see-also"></a>Ayrıca bkz.

[Whiteboard'a erişimi yönetme](manage-whiteboard-access-organizations.md)

[Whiteboard için verileri yönetme](manage-data-organizations.md)

[Windows'da Whiteboard'ı dağıtma](deploy-on-windows-organizations.md)