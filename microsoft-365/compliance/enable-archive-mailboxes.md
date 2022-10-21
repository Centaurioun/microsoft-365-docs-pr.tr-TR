---
title: Microsoft 365 için arşiv posta kutularını etkinleştirme
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.ArchivingHelp
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- purview-compliance
- tier2
search.appverid:
- MOE150
- MET150
ms.assetid: 268a109e-7843-405b-bb3d-b9393b2342ce
ms.custom:
- seo-marvel-apr2020
- admindeeplinkCOMPLIANCE
- admindeeplinkEXCHANGE
description: Kuruluşunuzun ileti saklama, eKeşif ve saklama gereksinimlerini desteklemek için arşiv posta kutularını etkinleştirmeyi veya devre dışı bırakmayı öğrenin.
ms.openlocfilehash: 2dbece4e898ff4c01a6f224a1e7b69ab3a533448
ms.sourcegitcommit: 87283bb02ca750286f7c069f811b788730ed5832
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2022
ms.locfileid: "68660213"
---
# <a name="enable-archive-mailboxes-for-microsoft-365"></a>Microsoft 365 için arşiv posta kutularını etkinleştirme

>*[Güvenlik & uyumluluğu için Microsoft 365 lisanslama kılavuzu](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

Microsoft 365’te arşivleme ( *Yerinde Arşivleme* olarak da adlandırılır) kullanıcılara ek posta kutusu depolama alanı sağlar. Daha fazla bilgi için bkz. [Arşiv posta kutuları hakkında bilgi](archive-mailboxes.md).

Yönetici portalı veya PowerShell kullanarak arşiv posta kutusunu etkinleştirmek veya devre dışı bırakmak için bu makaledeki bilgileri kullanın. Ayrıca, herhangi bir sorunu ve önerilen çözümü belirlemek için bir kullanıcının arşiv posta kutusunda otomatik tanılama denetiminin nasıl çalıştırıldığını da öğrenin.

Arşiv posta kutularını etkinleştirme veya devre dışı bırakma yapılandırması[, Microsoft Purview uyumluluk portalı](microsoft-365-compliance-center.md) [yeni Exchange yönetim merkezine (EAC)](/exchange/exchange-admin-center) taşınıyor. Bu taşıma tüm kiracılar için tamamlanana kadar, bu sayfa her iki yönetici deneyimine yönelik yönergeler içerir.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="get-the-necessary-permissions"></a>Gerekli izinleri alma

Arşiv posta kutularını etkinleştirmek veya devre dışı bırakmak için Exchange Online'da Posta Alıcıları rolüne atanmış olmanız gerekir. Varsayılan olarak bu rol, <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange yönetim merkezi</a>’nde **İzinler** sayfasındaki Alıcı Yönetimi ve Kuruluş Yönetimi rol gruplarına atanır. 


## <a name="how-to-enable-an-archive-mailbox"></a>Arşiv posta kutusunu etkinleştirme

Arşiv posta kutularını yönetme yapılandırması Microsoft 365 Purview uyumluluk portalından yeni Exchange yönetim merkezine taşınıyor.

### <a name="use-the-new-exchange-admin-center-to-enable-an-archive-mailbox"></a>Arşiv posta kutusunu etkinleştirmek için yeni Exchange yönetim merkezini kullanma

> [!NOTE]
> Arşiv posta kutusunu etkinleştirdiğinizde, kullanıcının posta kutusunda posta kutusuna atanan arşivleme ilkesinden daha eski olan öğeler yeni arşiv posta kutusuna taşınır. Exchange Online posta kutularına atanan bekletme ilkesinin bir parçası olan varsayılan arşiv ilkesi, öğeleri, öğenin posta kutusuna teslim edildiği veya kullanıcı tarafından oluşturulduğu tarihten iki yıl sonra arşiv posta kutusuna taşır. Daha fazla bilgi için bkz. [Arşiv posta kutuları hakkında bilgi](archive-mailboxes.md).

1. Yeni EAC'de **Alıcılar** \> **Posta Kutuları'na** gidin.

2. Posta kutuları listesinde, arşiv için posta kutusunu etkinleştirmek üzere kullanıcıyı seçin.

3. Açılır bölmede **Diğer'i** seçin ve **Posta kutusu arşivi'nin** altında **Posta kutusu arşivini yönet'i** seçin: 
    
   ![Seçili kullanıcı için posta kutusu arşivlerini yönetme.](../media/manage-mailbox-archive-option.png)

4. **Posta kutusu arşivini yönet** bölmesinde Posta **kutusu arşivini** açın ve ardından **Kaydet'i açın**.

Arşiv posta kutusunu oluşturmak birkaç dakika sürebilir. Oluşturulduktan sonra, seçili kullanıcının **Arşiv durumu** sütununda **Etkin** görüntülenir, ancak durum değişikliğini görmek için sayfayı yenilemeniz gerekebilir.

### <a name="use-the-purview-compliance-portal-to-enable-an-archive-mailbox"></a>Purview uyumluluk portalını kullanarak arşiv posta kutusunu etkinleştirme

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft Purview uyumluluk portalı’na</a> gidin ve oturum açın.

2. Uyumluluk portalının sol bölmesinde **Veri yaşam döngüsü yönetimi** > **Microsoft 365** > **Arşiv'i** seçin.

   **Arşiv** sayfasında  **Arşiv posta kutusu** sütunu, her kullanıcı için bir arşiv posta kutusunun etkinleştirilmiş olup olmadığını gösterir.

   > [!NOTE]
   > **Arşiv** sayfası en fazla 500 kullanıcı gösterir. İstediğiniz kullanıcının adını hemen göremiyorsanız arama kutusunu kullanın.

3. Posta kutuları listesinde, arşiv posta kutusunu etkinleştirmek istediğiniz kullanıcıyı seçin ve ardından **Arşivi etkinleştir** seçeneğini seçin:
    
   ![Seçili bir kullanıcı için arşiv seçeneğini etkinleştirin.](../media/enable-archive-option.png)
    
   Arşiv posta kutusunu etkinleştirirseniz, kullanıcının posta kutusundaki posta kutusuna atanan arşivleme ilkesinden daha eski olan öğelerin yeni arşiv posta kutusuna taşınacağını söyleyen bir uyarı görüntülenir. Exchange Online posta kutularına atanan bekletme ilkesinin bir parçası olan varsayılan arşiv ilkesi, öğeleri, öğenin posta kutusuna teslim edildiği veya kullanıcı tarafından oluşturulduğu tarihten iki yıl sonra arşiv posta kutusuna taşır. Daha fazla bilgi için bkz. [Arşiv posta kutuları hakkında bilgi](archive-mailboxes.md).

5. Onaylamak için **Etkinleştir**’i seçin.

   Arşiv posta kutusunu oluşturmak birkaç dakika sürebilir. Oluşturulduğunda, Seçili kullanıcının **Arşiv posta kutusu** sütununda **Etkin** görüntülenir, ancak durum değişikliğini görmek için sayfayı yenilemeniz gerekebilir.

## <a name="how-to-disable-an-archive-mailbox"></a>Arşiv posta kutusunu devre dışı bırakma

Arşiv posta kutusunu nasıl etkinleştirdiğinize benzer şekilde, kullanıcının arşiv posta kutusunu devre dışı bırakmak için EAC veya uyumluluk portalında aynı yapılandırmayı kullanabilirsiniz. Bu kez EAC'de **Posta Kutusu arşivini** kapatın veya uyumluluk portalında kullanıcıyı seçtikten sonra **Arşivi devre dışı bırak** seçeneğini belirleyin.

Bir arşiv posta kutusunu devre dışı bıraktıktan sonra, devre dışı bırakmadan sonraki 30 gün içinde onu kullanıcının birincil posta kutusuna yeniden bağlayabilirsiniz. Bu durumda, arşiv posta kutusunun özgün içeriği geri yüklenir. 30 gün sonra, özgün arşiv posta kutusunun içeriği kalıcı olarak silinir ve kurtarılamaz. Bu nedenle, arşivi devre dışı bıraktıktan 30 gün sonra yeniden etkinleştirirseniz yeni bir arşiv posta kutusu oluşturulur.

Kullanıcıların posta kutularına atanan varsayılan arşiv ilkesi, öğelerin teslim edildikten iki yıl sonra arşiv posta kutusuna taşımasını sağlar. Bir kullanıcının arşiv posta kutusunu devre dışı bıraktığınızda, posta kutusu öğeleri üzerinde herhangi bir işlem yapılmaz ve bunlar kullanıcının birincil posta kutusunda kalır.

## <a name="use-exchange-online-powershell-to-enable-or-disable-archive-mailboxes"></a>Arşiv posta kutularını etkinleştirmek veya devre dışı bırakmak için Exchange Online PowerShell'i kullanın

Arşiv posta kutularını etkinleştirmek için Exchange Online PowerShell'i kullanabilirsiniz. PowerShell'i kullanmanın birincil nedeni, arşiv posta kutusunu kuruluşunuzdaki tüm kullanıcılar için hızlı bir şekilde etkinleştirebilmenizdir.

İlk adım, Exchange Online PowerShell'e bağlanmaktır. Yönergeler için bkz. [Exchange Online PowerShell'e bağlanma](/powershell/exchange/connect-to-exchange-online-powershell).

Exchange Online'a bağlandıktan sonra, arşiv posta kutularını etkinleştirmek veya devre dışı bırakmak için aşağıdaki bölümlerdeki komutları çalıştırabilirsiniz.

### <a name="enable-archive-mailboxes"></a>Arşiv posta kutularını etkinleştirme

Tek bir kullanıcı için arşiv posta kutusunu etkinleştirmek için aşağıdaki komutu çalıştırın.

```powershell
Enable-Mailbox -Identity <username> -Archive
```

Kuruluşunuzdaki (arşiv posta kutusu şu anda etkin olmayan) tüm kullanıcılar için arşiv posta kutusunu etkinleştirmek için aşağıdaki komutu çalıştırın.

```powershell
Get-Mailbox -Filter {ArchiveGuid -Eq "00000000-0000-0000-0000-000000000000" -AND RecipientTypeDetails -Eq "UserMailbox"} | Enable-Mailbox -Archive
```

### <a name="disable-archive-mailboxes"></a>Arşiv posta kutularını devre dışı bırakma

Tek bir kullanıcı için arşiv posta kutusunu devre dışı bırakmak için aşağıdaki komutu çalıştırın.

```powershell
Disable-Mailbox -Identity <username> -Archive
```

Kuruluşunuzdaki (arşiv posta kutusu şu anda etkin olan) tüm kullanıcılar için arşiv posta kutusunu devre dışı bırakmak için aşağıdaki komutu çalıştırın.

```powershell
Get-Mailbox -Filter {ArchiveGuid -Ne "00000000-0000-0000-0000-000000000000" -AND RecipientTypeDetails -Eq "UserMailbox"} | Disable-Mailbox -Archive
```

## <a name="run-diagnostics-on-archive-mailboxes"></a>Arşiv posta kutularda tanılamayı çalıştırma

Herhangi bir sorunu ve önerilen çözümleri belirlemek için bir kullanıcının arşiv posta kutusunda otomatik tanılama denetimi çalıştırabilirsiniz.

Tanılama denetimi çalıştırmak için aşağıdaki düğmeye tıklayın. 

> [!div class="nextstepaction"]
> [Testleri Çalıştırma: Arşiv Posta Kutusu](https://aka.ms/PillarArchiveMailbox)

![Bir arşiv posta kutusunda tanılamayı çalıştırın.](../media/ArchiveMailboxDiagnostics.png)

Microsoft 365 yönetim merkezinde bir açılır sayfa açılır. Denetlemek istediğiniz posta kutusunun e-posta adresini girin ve **Testleri Çalıştır**'a tıklayın.

> [!NOTE]
> Arşiv posta kutusu tanılama denetimini kullanmak için bir Microsoft 365 genel yöneticisi olmanız gerekir. Ayrıca, bu özellik Microsoft 365 Kamu bulutlarında, 21Vianet tarafından yürütülen Microsoft 365'te veya Microsoft 365 Almanya'da kullanılamaz.

## <a name="instructions-for-end-users"></a>Son kullanıcılar için yönergeler

Kullanıcılara arşiv posta kutularının nasıl çalıştığını ve Windows, macOS ve web üzerinde Outlook'ta bunlarla nasıl etkileşim kurabileceklerini açıklayın. En etkili belgeler, kuruluşunuz için özelleştirilir. Ancak temel yönergeler için bkz. [Çevrimiçi arşiv posta kutuları ile e-posta depolama alanını yönetme](https://prod.support.services.microsoft.com/en-us/office/manage-email-storage-with-online-archive-mailboxes-1cae7d17-7813-4fe8-8ca2-9a5494e9a721).

## <a name="next-steps"></a>Sonraki adımlar

Ek depolama alanı için [otomatik olarak genişleyen arşivleme](autoexpanding-archiving.md)’yi etkinleştirmeyi göz önünde bulundurun. Yönergeler için bkz. [Otomatik genişleyen arşivlemeyi etkinleştirme](enable-autoexpanding-archiving.md).
