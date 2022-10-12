---
title: GCC ortamlarında Microsoft Whiteboard için paylaşımı yönetme
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
description: GCC ortamlarında Microsoft Whiteboard için paylaşımı yönetmeyi öğrenin.
ms.openlocfilehash: 48b1b517bb75977f2537d8365b3a00d01e077858
ms.sourcegitcommit: 8d3c027592a638f411f87d89772dd3d39e92aab0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/12/2022
ms.locfileid: "68536994"
---
# <a name="manage-sharing-for-microsoft-whiteboard-in-gcc-environments"></a>GCC ortamlarında Microsoft Whiteboard için paylaşımı yönetme

> [!NOTE]
> Bu kılavuz US Government Community Cloud (GCC) ortamları için geçerlidir. Paylaşım deneyimi, cihaza ve hangi kiracı düzeyinde paylaşım ayarlarının etkinleştirildiğine göre farklılık gösterir.

## <a name="share-in-teams-meetings"></a>Teams toplantılarında paylaşma

Teams toplantısında beyaz tahta paylaştığınızda Whiteboard bir paylaşım bağlantısı oluşturur. Bu bağlantıya kuruluştaki herkes erişebilir. Beyaz tahta, toplantıdaki kiracı içi kullanıcılarla da paylaşılır. Beyaz tahtalar, varsayılan ayardan bağımsız olarak şirket tarafından paylaşılabilir bağlantılar kullanılarak paylaşılır. Varsayılan paylaşım bağlantı türü desteği planlandı.

Toplantı sırasında dış ve paylaşılan cihaz hesaplarının çoğu tarafından geçici işbirliğine yönelik daha fazla özellik vardır. Kullanıcılar teams toplantısında paylaşıldıklarında beyaz tahtaları PowerPoint Canlı paylaşımına benzer şekilde geçici olarak görüntüleyebilir ve üzerinde işbirliği yapabilir.

Bu durumda Whiteboard, yalnızca Teams toplantısı sırasında beyaz tahta üzerinde geçici görüntüleme ve işbirliği sağlar. Paylaşım bağlantısı oluşturulmaz ve Beyaz Tahta dosyaya erişim izni vermez.

Bu davranışı etkinleştirmek için şu adımları izleyin:

1. Whiteboard'un kuruluşunuz için etkinleştirildiğinden emin olun. Daha fazla bilgi için bkz. [GCC ortamlarında Whiteboard erişimini yönetme](manage-whiteboard-access-gcc.md).

2. PowerShell kullanarak kiracınıza bağlanın ve aşağıdaki komutu çalıştırarak SharePoint Online modülünün güncelleştirildiğinden emin olun:

   ```powershell
   Update-Module -Name Microsoft.Online.SharePoint.PowerShell
   ```

3. Ardından aşağıdaki **Set-SPOTenant** komutunu çalıştırın:

   ```powershell
   Set-SPOTenant -AllowAnonymousMeetingParticipantsToAccessWhiteboards On
   ```

Bu ayar yalnızca beyaz tahtalar için geçerlidir ve önceden paylaşılan ayarların yerini alır: **OneDriveLoopSharingCapability** ve **CoreLoopSharingCapability**. Bu ayarlar artık geçerli değildir ve göz ardı edilebilir.

> [!NOTE]
> Varsayılan olarak, **Anonim kullanıcılar toplantılardaki uygulamalarla etkileşimde bulunabilir Teams toplantı** ayarı varsayılan olarak etkindir. Devre dışı bırakdıysanız, toplantı sırasında hiçbir anonim kullanıcı (konuklar veya federasyon kullanıcıları yerine) beyaz tahtaya erişemez
>
> Paylaşılan cihaz hesaplarının Teams toplantılarında Whiteboard'a erişmesini istiyorsanız ancak anonim kullanıcılara erişim sağlamak istemiyorsanız, **AllowAnonymousMeetingParticipantsToAccessWhiteboards** etkinken **Anonim kullanıcıların toplantılardaki uygulamalarla etkileşim kurabilmesini** devre dışı bırakabilirsiniz

Bu değişikliklerin kiracınız genelinde uygulanması yaklaşık 60 dakika sürmelidir.

|Senaryo|Depolama ve sahiplik|Paylaşım ayarları|Paylaşım deneyimi|
|---|---|---|---|
|Beyaz tahtayı masaüstünden veya mobil cihazdan başlatma|Depolama: OneDrive İş<br><br>Sahip: Beyaz tahtayı oluşturan kullanıcı|Etkin|Kiracı içi kullanıcılar: Oluşturabilir, görüntüleyebilir ve işbirliği yapabilir<br><br>Dış kullanıcılar (yakında): Yalnızca toplantı sırasında görüntüleyebilir ve işbirliği yapabilir<br><br>Paylaşılan cihaz hesapları (yakında): Yalnızca toplantı sırasında görüntüleyebilir ve işbirliği yapabilir|
|Beyaz tahtayı masaüstünden veya mobil cihazdan başlatma|Depolama: OneDrive İş<br><br>Sahip: Beyaz tahtayı oluşturan kullanıcı|Devre dışı|Kiracı içi kullanıcılar: Başlatabilir, görüntüleyebilir ve işbirliği yapabilir<br><br>Dış kullanıcılar: Görüntülenemez veya işbirliği yapılamaz<br><br>Paylaşılan cihaz hesapları: Görüntülenemez veya işbirliği yapılamaz|
|Beyaz tahtayı Surface Hub'dan veya Microsoft Teams Odaları başlatma|Henüz kullanılamıyor|||

## <a name="add-as-a-tab-in-teams-channels-and-chats"></a>Teams kanallarında ve sohbetlerinde sekme olarak ekleme

Teams kanalına veya sohbete sekme olarak beyaz tahta eklediğinizde Whiteboard, kuruluştaki herkes tarafından erişilebilen bir paylaşım bağlantısı oluşturur.

|Senaryo|Depolama ve sahiplik|Paylaşım ayarları|Paylaşım deneyimi|
|---|---|---|---|
|Beyaz tahtayı bir kanala ekleme veya masaüstü veya mobil cihazdan sohbet etme|Depolama: OneDrive İş<br><br>Sahip: Beyaz tahtayı oluşturan kullanıcı|Uygulanamaz (yalnızca toplantılar için geçerlidir)|Kiracı içi kullanıcılar: Başlatabilir, görüntüleyebilir ve işbirliği yapabilir<br><br>Dış kullanıcılar: Desteklenmez<br><br>Teams konukları: Görüntüleyebilir ve işbirliği yapabilir<br><br>Paylaşılan cihaz hesapları: Geçerli değil|

## <a name="create-and-share-in-whiteboard-native-clients"></a>Whiteboard yerel istemcilerinde oluşturma ve paylaşma

Web, masaüstü veya mobil istemcilerden bir beyaz tahta paylaştığınızda, belirli kişileri seçebilirsiniz. Kuruluştaki herkes tarafından erişilebilen bir paylaşım bağlantısı da oluşturabilirsiniz. Kuruluş dışındaki dış kullanıcılar için paylaşım bağlantıları henüz kullanılamıyor.

|Senaryo|Depolama ve sahiplik|Paylaşım ayarları|Paylaşım deneyimi|
|---|---|---|---|
|Masaüstü veya mobil cihazdan beyaz tahta oluşturma|Depolama: OneDrive İş<br><br>Sahip: Beyaz tahtayı oluşturan kullanıcı|Uygulanamaz (yalnızca toplantılar için geçerlidir)|Kiracı içi kullanıcılar: Kuruluşlarında paylaşabilir<br><br>Dış kullanıcılar: Dış kullanıcılarla paylaşım şu anda desteklenmiyor|
|Surface Hub'dan beyaz tahta oluşturma|Depolama: Yerel<br><br>Sahip: Yok|Uygulanamaz (yalnızca toplantılar için geçerlidir)|Kiracı içi kullanıcılar (yakında): Kullanıcı panoyu kaydetmek ve paylaşmak için oturum açabilecek<br><br>Dış kullanıcılar: Şu anda Teams toplantısı dışında dış kullanıcılarla paylaşım desteklenmez|
|Microsoft Teams Odaları'dan beyaz tahta oluşturma|Henüz kullanılamıyor|||

## <a name="see-also"></a>Ayrıca bkz.

[Whiteboard erişimini yönetme - GCC](manage-whiteboard-access-gcc.md)

[Whiteboard için verileri yönetme - GCC](manage-data-gcc.md)

[Whiteboard için istemcileri yönetme - GCC](manage-clients-gcc.md)
