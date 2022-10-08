---
title: Microsoft Whiteboard için paylaşımı yönetme
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
description: Microsoft Whiteboard için paylaşımı yönetmeyi öğrenin.
ms.openlocfilehash: aeb6da3d6bd66c02468ff19efa072af4d7084389
ms.sourcegitcommit: d0557f757cfa48330ed57e966033891d10f03688
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/06/2022
ms.locfileid: "68492518"
---
# <a name="manage-sharing-for-microsoft-whiteboard"></a>Microsoft Whiteboard için paylaşımı yönetme

Paylaşım deneyimi, Teams toplantısında olmanıza, paylaşılan bir cihaz kullanıyor olmanıza veya hangi kiracı düzeyinde paylaşım ayarlarının etkinleştirildiğine bağlı olarak farklılık gösterir. Aşağıdaki senaryolar yalnızca Whiteboard OneDrive İş depolamayı kullanmaya geçtikten sonra oluşturulan yeni beyaz tahtalar için geçerlidir. Azure'da depolanmaya devam eden önceden oluşturulmuş panolarda herhangi bir değişiklik yoktur.

## <a name="share-in-teams-meetings"></a>Teams toplantılarında paylaşma

Teams toplantısında beyaz tahta paylaştığınızda Whiteboard bir paylaşım bağlantısı oluşturur. Bu bağlantıya kuruluştaki herkes erişebilir. Beyaz tahta, toplantıdaki kiracı içi kullanıcılarla da paylaşılır. Beyaz tahtalar, varsayılan ayardan bağımsız olarak şirket tarafından paylaşılabilir bağlantılar kullanılarak paylaşılır. Varsayılan paylaşım bağlantı türü desteği planlandı.

Teams toplantısı sırasında dış ve paylaşılan cihaz hesapları tarafından geçici işbirliğine yönelik daha fazla özellik vardır. Kullanıcılar, bir toplantıda paylaşılan beyaz tahtaları PowerPoint Canlı paylaşımına benzer şekilde geçici olarak görüntüleyebilir ve üzerinde işbirliği yapabilir.

Bu durumda Whiteboard, yalnızca Teams toplantısı sırasında beyaz tahta üzerinde geçici görüntüleme ve işbirliği sağlar. Paylaşım bağlantısı oluşturulmaz ve Beyaz Tahta dosyaya erişim izni vermez.

Bu davranışı etkinleştirmek için şu adımları izleyin:

1. Whiteboard'un kuruluşunuz için etkinleştirildiğinden emin olun. Daha fazla bilgi için bkz. [Whiteboard erişimini yönetme](manage-whiteboard-access-organizations.md).

2. PowerShell kullanarak kiracınıza bağlanın ve aşağıdaki komutu çalıştırarak SharePoint Online modülünün güncelleştirildiğinden emin olun:

   ```powershell
   Update-Module -Name Microsoft.Online.SharePoint.PowerShell
   ```

3. Ardından aşağıdaki **Set-SPOTenant** komutunu çalıştırın:

   ```powershell
   Set-SPOTenant -AllowAnonymousMeetingParticipantsToAccessWhiteboards On
   ```

4. **Anonim kullanıcıların toplantılardaki uygulamalarla etkileşim kurabileceği Teams toplantı** ayarının etkinleştirildiğinden emin olun. Devre dışı bırakdıysanız, toplantı sırasında anonim kullanıcıların (konuklar veya federasyon kullanıcılarının aksine) beyaz tahtaya erişimi olmaz.

Bu ayar yalnızca beyaz tahtalar için geçerlidir ve önceden paylaşılan ayarların yerini alır: **OneDriveLoopSharingCapability** ve **CoreLoopSharingCapability**. Bu ayarlar artık geçerli değildir ve göz ardı edilebilir.

> [!NOTE]
> Varsayılan olarak, **Anonim kullanıcılar toplantılardaki uygulamalarla etkileşimde bulunabilir Teams toplantı** ayarı etkindir. Devre dışı bırakdıysanız, toplantı sırasında hiçbir anonim kullanıcı (konuklar veya federasyon kullanıcıları yerine) beyaz tahtaya erişemez.

Bu değişikliklerin kiracınız genelinde uygulanması yaklaşık 60 dakika sürmelidir.

|Senaryo|Depolama ve sahiplik|Paylaşım ayarları|Paylaşım deneyimi|
|---|---|---|---|
|Beyaz tahtayı masaüstünden veya mobil cihazdan başlatma|Depolama: OneDrive İş<br><br>Sahip: Beyaz tahtayı oluşturan kullanıcı|Etkin|Kiracı içi kullanıcılar: Oluşturabilir, görüntüleyebilir ve işbirliği yapabilir<br><br>Dış kullanıcılar: Yalnızca toplantı sırasında görüntüleyebilir ve işbirliği yapabilir (beyaz tahtayı paylaşma düğmesi dış kullanıcılar için görünmez)<br><br>Paylaşılan cihaz hesapları: Yalnızca toplantı sırasında görüntüleyebilir ve işbirliği yapabilir|
|Beyaz tahtayı masaüstünden veya mobil cihazdan başlatma|Depolama: OneDrive İş<br><br>Sahip: Beyaz tahtayı oluşturan kullanıcı|Devre dışı|Kiracı içi kullanıcılar: Başlatabilir, görüntüleyebilir ve işbirliği yapabilir<br><br>Dış kullanıcılar: Görüntülenemez veya işbirliği yapılamaz<br><br>Paylaşılan cihaz hesapları: Görüntülenemez veya işbirliği yapılamaz|
|Beyaz tahtayı Surface Hub'dan veya Microsoft Teams Odaları başlatma|Depolama: Azure (Whiteboard dosyaları gelecekte OneDrive İş taşınacaktır)<br><br>Sahip: Toplantı katılımcısı|Geçerli değil|Kiracı içi kullanıcılar: Başlatabilir, görüntüleyebilir ve işbirliği yapabilir<br><br>Dış kullanıcılar: Yalnızca toplantı sırasında görüntüleyebilir ve işbirliği yapabilir<br><br> Paylaşılan cihaz hesapları: Yalnızca toplantı sırasında görüntüleyebilir ve işbirliği yapabilir|

> [!NOTE]
> Beyaz Tahta OneDrive'da depolanıyorsa ve zaten bir toplantıya bağlıysa, Surface Hub'da veya Microsoft Teams Odaları cihazda başlatılamaz. Başka bir cihazdaki kimliği doğrulanmış bir kullanıcının bunu yapması gerekir. Bu işlevi gelecek bir sürümde etkinleştirmeyi planlıyoruz.

## <a name="add-as-a-tab-in-teams-channels-and-chats"></a>Teams kanallarında ve sohbetlerinde sekme olarak ekleme

Teams kanalına veya sohbete sekme olarak beyaz tahta eklediğinizde Whiteboard, kuruluştaki herkes tarafından erişilebilen bir paylaşım bağlantısı oluşturur.

|Senaryo|Depolama ve sahiplik|Paylaşım ayarları|Paylaşım deneyimi|
|---|---|---|---|
|Beyaz tahtayı bir kanala ekleme veya masaüstü veya mobil cihazdan sohbet etme|Depolama: OneDrive İş<br><br>Sahip: Beyaz tahtayı oluşturan kullanıcı|Uygulanamaz (yalnızca toplantılar için geçerlidir)|Kiracı içi kullanıcılar: Başlatabilir, görüntüleyebilir ve işbirliği yapabilir<br><br>Dış kullanıcılar: Desteklenmez<br><br>Teams konukları: Desteklenmez<br><br>Paylaşılan cihaz hesapları: Geçerli değil|

## <a name="create-and-share-in-whiteboard-native-clients"></a>Whiteboard yerel istemcilerinde oluşturma ve paylaşma

Beyaz tahtaları web, masaüstü veya mobil istemcilerden paylaştığınızda belirli kişileri seçebilirsiniz. Kuruluştaki herkes tarafından erişilebilen bir paylaşım bağlantısı da oluşturabilirsiniz.

> [!NOTE]
> Teams toplantısı sırasında dış paylaşım henüz kullanılamamaktadır ancak gelecek bir sürümde eklenecektir.

|Senaryo|Depolama ve sahiplik|Paylaşım ayarları|Paylaşım deneyimi|
|---|---|---|---|
|Masaüstü veya mobil cihazdan beyaz tahta oluşturma|Depolama: OneDrive İş<br><br>Sahip: Beyaz tahtayı oluşturan kullanıcı|Uygulanamaz (yalnızca toplantılar için geçerlidir)|Kiracı içi kullanıcılar: Kuruluşlarında paylaşabilir<br><br>Dış kullanıcılar: Dış kullanıcılarla paylaşım şu anda desteklenmiyor|
|Surface Hub'dan beyaz tahta oluşturma|Depolama: Yerel<br><br>Sahip: Yok (Kullanıcı panoyu kaydetmek ve paylaşmak için oturum açmadığı sürece, bu da OneDrive İş kaydeder. Kolay paylaşım gelecekte yeniden eklenecektir.|Uygulanamaz (yalnızca toplantılar için geçerlidir)|Kiracı içi kullanıcılar: Kullanıcının panoyu kaydedip paylaşmak için oturum açması gerekir (Gelecekte Kolay paylaşım eklenecektir)<br><br>Dış kullanıcılar: Şu anda Teams toplantısı dışında dış kullanıcılarla paylaşım desteklenmez|
|Microsoft Teams Odaları'dan beyaz tahta oluşturma|Henüz desteklenmiyor|Uygulanamaz (yalnızca toplantılar için geçerlidir)|Henüz desteklenmiyor|

## <a name="see-also"></a>Ayrıca bkz.

[Whiteboard'a erişimi yönetme](manage-whiteboard-access-organizations.md)

[Whiteboard için verileri yönetme](manage-data-organizations.md)

[Cloud Apps Microsoft Defender için ağ gereksinimleri](/defender-cloud-apps/network-requirements)

[Windows'da Whiteboard'ı dağıtma](deploy-on-windows-organizations.md)
