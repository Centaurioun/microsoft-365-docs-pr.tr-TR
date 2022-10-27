---
title: Kuruluşunuzdaki herkes için Odaklanmış Gelen Kutusu'nu yapılandırma
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: high
ms.collection:
- Tier3
- scotvorg
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
- admindeeplinkMAC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 613a845c-4b71-41de-b331-acdcf5b6625d
description: İşletmedeki herkes için e-posta ayarlarını yapılandırmaktan sorumluysanız, bu makalede kullanıcılar için Odaklanmış Gelen Kutusu'nu yapılandırma açıklanmaktadır.
ms.openlocfilehash: 7e627e077ee5e906f78300cda8366199692dd511
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2022
ms.locfileid: "68726408"
---
# <a name="configure-focused-inbox-for-everyone-in-your-organization"></a>Kuruluşunuzdaki herkes için Odaklanmış Gelen Kutusu'nu yapılandırma

İşletmede HERKES için e-postanın nasıl çalışacağını yapılandırmaktan sorumluysanız, bu makale tam size göre! İşletmeniz için nasıl özelleştirebileceğinizi veya kapattığınızı açıklar ve [sık sorulan soruları](#faq-for-focused-inbox) yanıtlar.

Odaklanmış Gelen Kutusu'nu yalnızca kendiniz için kapatmak istiyorsanız, bkz. [Odaklanmış Gelen Kutusu'nu kapatma](https://support.microsoft.com/office/f714d94d-9e63-4217-9ccb-6cb2986aa1b2).      

If you want to be sure that your users receive business-specific email messages, for example, from HR or payroll, you can configure Focused Inbox so these messages reach the Focused view. You can also control whether users in your organization see the Focused Inbox in their mailbox.
  
## <a name="turn-focused-inbox-on-or-off-in-your-organization"></a>Kuruluşunuzda Odaklanmış Gelen Kutusu'nu açma veya kapatma

Kuruluşunuzda herkes için Odaklanmış Gelen Kutusu'nu açma veya kapatma işlemini PowerShell kullanarak yaparsınız. Bunu Microsoft 365 yönetim merkezi yapmak ister misin? Bunu Mühendislik ekibimize iletin. **[Buradan oylayın!](https://go.microsoft.com/fwlink/?linkid=862489)**
  
**Odaklanmış Gelen Kutusu'nu kapatmak için:**
  
The following PowerShell example turns Focused Inbox **Off** in your organization. However, it doesn't block the availability of the feature for your users. If they want, they can still re-enable Focused Inbox again on each of their clients. 
  
1. [Exchange Online PowerShell’e bağlanma](/powershell/exchange/connect-to-exchange-online-powershell).

2. You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Transport rules" entry in [Messaging policy and compliance permissions](/exchange/messaging-policy-and-compliance-permissions-exchange-2013-help).

3. **Get-OrganizationConfig** cmdlet'ini çalıştırın. 

    ```powershell
    Get-OrganizationConfig
    ```

4. Geçerli ayarı görmek için **FocusedInboxOn** öğesini bulun: 

    ![Response from PowerShell on state of Focused Inbox.](../../media/419d8caa-89b9-45c5-91d9-8c023297456e.png)
  
5. Odaklanmış Gelen Kutusu'nu kapatmak için aşağıdaki cmdlet'i çalıştırın.

    ```powershell
    Set-OrganizationConfig -FocusedInboxOn $false
    ```

6. **Get-OrganizationConfig** cmdlet'ini çalıştırın; FocusedInboxOn değerinin $false olarak ayarlandığını görürsünüz ve bu da kapatıldığı anlamına gelir. 

**Odaklanmış Gelen Kutusu'nu açmak için:**
  
- Yukarıdaki 5. Adımda, Odaklanmış Gelen Kutusu'nu açmak için aşağıdaki cmdlet'i çalıştırın.

  ```powershell
  Set-OrganizationConfig -FocusedInboxOn $true
  ```
    
## <a name="what-do-users-see-after-i-turn-on-focused-inbox"></a>Ben Odaklanmış Gelen Kutusu'nu açtıktan sonra kullanıcılar ne görüyor?

Your users will see the Focused view only after they close and restart Outlook. When they restart Outlook, they'll see a Tip in the Outlook user interface giving them to the option to use the new Focused Inbox.
  
![An image of what Focused Inbox looks like when a user first opens Outlook on the web.](../../media/f6ef79e7-0f4c-4a23-b6f0-7c15d927b5f0.png)
  
If you're switching from Clutter to Focused Inbox, they can decide to enable it ("Try it") or dismiss the feature. If the user has multiple (supported) clients, they can enable/disable Focused Inbox individually on each one. The tip looks like this:
  
![An image of what Focused Inbox looks like when it's rolled out to your users and Outlook is re-opened.](../../media/c034f969-d650-4333-88f1-dd10ade0a94c.png)
  
When a user decides to start using Focused Inbox, Clutter gets disabled automatically. The Clutter folder gets converted into a standard folder, that allows the user to rename or delete it.
  
## <a name="turn-focused-inbox-on-or-off-for-specific-users"></a>Odaklanmış Gelen Kutusu'nu belirli kullanıcılar için açma ve kapatma

Bu örnek, Contoso kuruluşundaki Fatih Kara için Odaklanmış Gelen Kutusunu **Kapalı** olarak ayarlar. Ancak bu kişiye sağlanan özelliklerin kullanılabilmesini engellemez. İstediği takdirde, her istemcisinde Odaklanmış Gelen Kutusu'nu yeniden etkinleştirebilir. 
  
1. [Exchange Online PowerShell’e bağlanma](/powershell/exchange/connect-to-exchange-online-powershell).

2. You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Transport rules" entry in the Messaging policy and compliance permissions topic.

3. **Get-FocusedInbox** cmdlet'ini çalıştırın, örneğin: 

    ```powershell
    Get-FocusedInbox -Identity <tim@contoso.com>
    ```

4. Geçerli ayarı görmek için FocusedInboxOn öğesini bulun:

    ![Response from PowerShell on state of Focused Inbox.](../../media/419d8caa-89b9-45c5-91d9-8c023297456e.png)
  
5. Odaklanmış Gelen Kutusu'nu kapatmak için aşağıdaki cmdlet'i çalıştırın:

    ```powershell
    Set-FocusedInbox -Identity <tim@contoso.com> -FocusedInboxOn $false
    ```

    VEYA, açmak için aşağıdaki cmdlet'i çalıştırın:

    ```powershell
    Set-FocusedInbox -Identity <tim@contoso.com> -FocusedInboxOn $true
    ```

## <a name="use-the-ui-to-create-a-transport-rule-to-direct-email-messages-to-the-focused-view-for-all-your-users"></a>Tüm kullanıcılarınızın e-posta iletilerini Odaklanmış görünüme yönlendirecek aktarım kuralını oluşturmak için kullanıcı arabirimini kullanma

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange yönetim merkezine</a> gidin.

2. **Posta akışı** \> **Kuralları'na** gidin. EAC Ekle simgesi'ne tıklayın ![.](../../media/795e5bdd-48bb-433f-8e07-3c7a19f8eca2.gif) ve ardından **Yeni kural oluştur...** öğesini seçin. 

3. Yeni kuralı oluşturmayı tamamladıktan sonra, kuralı başlatmak için **Kaydet'i** seçin.

    Aşağıdaki görüntüde, "Bordro Departmanı"ndan gelen tüm iletilerin Odaklanmış Gelen Kutusu'na teslim edildiği bir örnek gösterilmektedir.

    ![focusedinbox bordrosu.](../../media/focusedinbox-transport-rule.PNG)

    > [!NOTE]
    > Bu örnekteki ileti üst bilgisi değeri metni, **X-MS-Exchange-Organization-BypassFocusedInbox şeklindedir**.
  
## <a name="use-powershell-to-create-a-transport-rule-to-direct-email-messages-to-the-focused-view-for-all-your-users"></a>Tüm kullanıcılarınızın e-posta iletilerini Odaklanmış görünüme yönlendirecek aktarım kuralını oluşturmak için PowerShell kullanma

1. [Exchange Online PowerShell’e bağlanma](/powershell/exchange/connect-to-exchange-online-powershell).

2. You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Transport rules" entry in [Messaging policy and compliance permissions](/exchange/messaging-policy-and-compliance-permissions-exchange-2013-help).

3. "Bordro Departmanı"ndan gelen tüm iletilerin (örneğin, Odaklanmış Gelen Kutusuna) teslim edilmesine izin vermek için aşağıdaki komutu çalıştırın.

    ```powershell
    New-TransportRule -Name <name_of_the_rule> -From "Payroll Department" -SetHeaderName "X-MS-Exchange-Organization-BypassFocusedInbox" -SetHeaderValue "true"
    ```

> [!IMPORTANT]
> Bu örnekte hem "X-MS-Exchange-Organization-BypassFocusedInbox" hem de "true" büyük/küçük harfe duyarlıdır.
> Ayrıca, Odaklanmış Gelen Kutusu İkincil'i atlayan X üst bilgisini kabul eder, bu nedenle bu ayarı İkincil'de kullanırsanız, Odaklanmış Gelen Kutusu'nda kullanılır. Ayrıntılı söz dizimi ve parametre bilgileri için bkz. [New-TransportRule](/powershell/module/exchange/new-transportrule).

### <a name="how-do-you-know-this-worked"></a>Bunun çalıştığını nasıl anlarsınız?

E-posta iletilerinin Odaklanmış Gelen Kutusu aktarım kuralını atlaması nedeniyle Gelen Kutusuna ulaşıp ulaşmadığını görmek için e-posta iletisi üst bilgilerini denetleyebilirsiniz. Kuruluşunuzda, Odaklanmış Gelen Kutusu aktarım kuralının uygulandığı posta kutusundan bir e-posta iletisi seçin. İletide yazılı üst bilgilere bakın; **X-MS-Exchange-Organization-BypassFocusedInbox: true** üst bilgisini görmeniz gerekir. Bu atlama işleminin çalıştığı anlamına gelir. [Üst bilgi bilgilerini bulma hakkında bilgi için E-posta iletisi için İnternet üst](https://go.microsoft.com/fwlink/p/?LinkId=822530) bilgi bilgilerini görüntüleme makalesine göz atın.

### <a name="what-will-the-user-see"></a>Kullanıcı ne görecek?

Aktarım kuralı varsa geçersiz kılma için bir bildirim gösterilir. Web üzerinde Outlook "Her zaman Diğer'e taşı" seçeneğini devre dışı bırakır ve bir araç ipucu gösterir. Masaüstündeki Outlook istemcileri "Her zaman Diğer'e taşı" seçeneğinin seçilmesine izin verir ve bir iletişim kutusu açılır.

## <a name="turn-onoff-clutter"></a>İkincil özelliğini açma/kapatma

We've received reports that Clutter suddenly stopped working for some users. If this happens, you can enable it again for specific users. See [Configure Clutter for your organization](../email/configure-clutter.md).

## <a name="faq-for-focused-inbox"></a>Odaklanmış Gelen Kutusu hakkında SSS

Burada, Odaklanmış Gelen Kutusu hakkında Sık Sorulan Soruların yanıtları verilmiştir.

### <a name="can-i-control-how-i-roll-out-focused-inbox-in-my-organization"></a>Odaklanmış Gelen Kutusu'nun kuruluşumda nasıl dağıtılacağını denetleyebilir miyim?

Yes. You can turn Focused Inbox on or off for your entire organization, or you can turn it on or off for specified users. See above.
  
### <a name="is-the-focused-inbox-feature-only-available-for-office-2016-clients"></a>Odaklanmış Gelen Kutusu özelliği YALNIZCA Office 2016 istemcilerinde mi kullanılabilir?

Evet, yalnızca Office 2016'ya sahip kullanıcılar etkilenir. Özellik Outlook 2013 veya daha önceki bir sürüme geri aktarılmayacak.
  
### <a name="how-long-does-it-take-for-focused-inbox-changes-to-take-place-in-outlook"></a>Odaklanmış Gelen Kutusu değişikliklerinin Outlook'ta geçerlilik kazanması ne kadar sürer?

Odaklanmış Gelen Kutusu'nu açtıktan veya kapattıktan sonra, ayarların geçerlilik kazanması için kullanıcılar Outlook'u kapatıp yeniden başlatması gerekir.
  
### <a name="what-happens-to-clutter-once-i-turn-on-focused-inbox"></a>Odaklanmış Gelen Kutusu'nu açtıktan sonra İkincil klasörüne ne olur?

After switching, you'll no longer receive less actionable email in the Clutter folder. Instead, email will be split between the Focused and Other tabs in your inbox. The same algorithm that moved items to the Clutter folder now powers Focused Inbox, meaning that any emails that were set to move to Clutter will now be moved to Other. Any messages already in your Clutter folder will remain there until you decide to delete or move them.
  
Microsoft MVP'si [Tony Redmond](https://www.petri.com/author/tony-redmond)'ın şu gönderisini gözden geçirin: [Office 365'te Odaklanmış Gelen Kutusu Nasıl İkincil Klasörünün Yerini Alır](https://www.petri.com/focused-inbox-office-365).
  
### <a name="can-i-keep-users-on-clutter-what-is-microsofts-recommendation-when-it-comes-to-using-clutter-vs-focused-inbox"></a>Kullanıcıları İkincil'de tutabilir miyim? Odaklanmış Gelen Kutusu yerine İkincil kullanılması konusunda Microsoft'un önerisi nedir?

Yes, you can keep users on Clutter and disable Focused Inbox, however, eventually Clutter will be fully replaced with Focused Inbox so Microsoft's recommends moving to Focused Inbox now. To learn more about when you use Clutter with Exchange Online, see this blog post: [Update on Focused Inbox and our plans for Clutter](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448).
  
### <a name="should-i-disable-clutter-for-my-end-users-if-we-are-going-to-move-everyone-to-focused-inbox"></a>Herkesi Odaklanmış Gelen Kutusu'na geçireceksek son kullanıcılarım için İkincil'i devre dışı bırakabilir miyim?

No. It's possible to disable Clutter for a mailbox explicitly by running the Set-Clutter cmdlet. However, if you do this, the mailbox owner will see messages that were previously redirected to the Clutter folder remain in the Inbox and they'll have to process those messages until their client is upgraded to a version that supports the Focused Inbox. It's therefore best not to disable Clutter until the upgraded clients are available.
  
### <a name="why-are-there-two-different-cmdlets-for-managing-focused-inbox"></a>Odaklanmış Gelen Kutusu'nu yönetmek için neden iki farklı cmdlet var?

Odaklanmış Gelen Kutusu'yla ilişkili iki durum vardır.
  
- **Kuruluş Düzeyi**: Odaklanmış Gelen Kutusu durumu ve ilişkilendirilmiş bir son güncelleştirme zaman damgası.

- **Posta Kutusu Düzeyi**: Odaklanmış Gelen Kutusu durumu ve ilişkilendirilmiş bir son güncelleştirme zaman damgası 

### <a name="how-does-outlook-decide-to-show-the-focused-inbox-experience-with-these-two-states"></a>Outlook, Odaklanmış Gelen Kutusu deneyimini bu iki durum bilgisinden hangisiyle göstereceğine nasıl karar verir?

Outlook decides to show the experience by choosing which cmdlet has the latest time stamp. By default, both time stamps are "null" and in this case, the feature is enabled.
  
### <a name="why-does-the-get-focusedinbox-cmdlet-return-true-when-ive-turned-focused-inbox-off-in-my-organization"></a>Kuruluşumda Odaklanmış Gelen Kutusu'nu kapattığımda Get-FocusedInbox cmdlet'i neden "true" döndürüyor?

There are two cmdlets for controlling Focused Inbox. When you run Get-FocusedInbox for a mailbox, it returns the mailbox level state of the feature. The experience in Outlook is chosen based on which cmdlet state was last modified.
  
### <a name="can-i-run-a-script-to-see-who-has-turned-on-focused-inbox"></a>Odaklanmış Gelen Kutusu'nu etkinleştiren kişileri görmek için bir betik çalıştırabilir miyim?

Hayır, ve bu tasarım gereği. Odaklanmış Gelen Kutusu etkinleştirmesi bir istemci tarafı ayarı olduğundan, cmdlet'in tüm yapabilecekleri kullanıcının posta kutusunun istemci deneyimi için uygun olup olmadığını size bildirmektir. Bazı istemcilerde aynı anda etkinleştirilmesi ve bazılarında devre dışı bırakılması mümkündür; örneğin, Outlook uygulamasında ve Outlook Mobile'da etkinleştirilebilir ancak Web üzerinde Outlook devre dışı bırakılabilir.

## <a name="related-content"></a>İlgili içerik

[Kuruluşunuz için İkincil'i yapılandırma](../email/configure-clutter.md) (makale)\
[Paylaşılan posta kutusu ayarlarını yapılandırma](../email/configure-a-shared-mailbox.md) (makale)\
[İmzalar ve sorumluluk reddi oluşturma](create-signatures-and-disclaimers.md) (video)
