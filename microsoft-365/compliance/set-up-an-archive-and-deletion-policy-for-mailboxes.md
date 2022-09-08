---
title: Posta kutuları için arşiv ve silme ilkesini (MRM) özelleştirme
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MBS150
- BCS160
- MET150
ms.assetid: ec3587e4-7b4a-40fb-8fb8-8aa05aeae2ce
ms.custom:
- seo-marvel-apr2020
- admindeeplinkEXCHANGE
description: Öğeleri otomatik olarak kullanıcının arşiv posta kutusuna taşımak için özel mesajlaşma kayıtları yönetimi (MRM) arşivleme ve silme ilkesi oluşturma.
ms.openlocfilehash: 08037607aa183462c560fb95641e3b0bc50da2e7
ms.sourcegitcommit: 6f36cb8c69090c62a006d461bfc5aa1139cf09a9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/08/2022
ms.locfileid: "67631314"
---
# <a name="customize-an-archive-and-deletion-policy-for-mailboxes-in-your-organization"></a>Kuruluşunuzdaki posta kutuları için arşiv ve silme ilkesini özelleştirme

Microsoft Purview yöneticileri, öğeleri otomatik olarak kullanıcının arşiv [posta kutusuna taşıyan ve posta kutusundan](archive-mailboxes.md) öğeleri otomatik olarak silecek bir arşivleme ve silme ilkesi oluşturabilir.

Bunu, daha sonra posta kutularına atadığınız bir mesajlaşma kayıtları yönetimi (MRM) bekletme ilkesi oluşturarak yaparsınız. Bu ilke, öğeleri belirli bir süre sonra kullanıcının arşiv posta kutusuna taşır ve ayrıca belirli bir yaş sınırına ulaştıktan sonra öğeleri posta kutusundan siler.

Hangi öğelerin taşındığını veya silindiğini belirleyen gerçek kurallar ve bunun ne zaman gerçekleştiği bekletme etiketleri olarak adlandırılır. Bekletme etiketleri bir MRM bekletme ilkesine bağlanır ve bu ilke de kullanıcının posta kutusuna atanır. Bekletme etiketi, bekletme ayarlarını kullanıcının posta kutusundaki tek tek iletilere ve klasörlere uygular. İletinin posta kutusunda ne kadar süre kaldığını ve ileti belirtilen saklama yaşına ulaştığında hangi eylemin gerçekleştirilecek olduğunu tanımlar. İleti saklama yaşına ulaştığında, kullanıcının arşiv posta kutusuna taşınır veya silinir.
  
Bu makaledeki adımlar, Alpine House adlı kurgusal bir kuruluş için arşivleme ve bekletme ilkesi ayarlar. Bu ilkenin ayarlanması aşağıdaki görevleri içerir:
  
- Kuruluştaki her kullanıcı için arşiv posta kutusunu etkinleştirin. Bu yordam kullanıcılara daha fazla posta kutusu depolama alanı sağlar ve bekletme ilkesinin öğeleri otomatik olarak arşiv posta kutusuna taşıyabilmesi için gereklidir. Kullanıcı ayrıca arşiv depolaması için öğeleri arşiv posta kutusuna el ile taşıyabilir.

- Aşağıdaki eylemleri gerçekleştirmek için üç özel bekletme etiketi oluşturun:

  - 3 yaşındaki öğeleri otomatik olarak kullanıcının arşiv posta kutusuna taşıyın. Öğeleri arşiv posta kutusuna taşımak, kullanıcının birincil posta kutusunda yer açmasını sağlar.

  - Silinmiş Öğeler klasöründen 5 yaşındaki öğeleri otomatik olarak silin. Bu, kullanıcının birincil posta kutusunda da yer açmasını sağlar. Kullanıcı gerekirse bu öğeleri kurtarma fırsatına sahip olur. Daha fazla ayrıntı için [Daha fazla bilgi](#more-information) bölümündeki dipnota bakın. 

  - Hem birincil hem de arşiv posta kutusundan 7 yaşında olan öğeleri otomatik olarak (ve kalıcı olarak) silin. Uyumluluk düzenlemeleri nedeniyle, bazı kuruluşlarda belirli bir süre boyunca e-postanın tutulması gerekir. Bu süre dolduğunda, kuruluş bu öğeleri kullanıcı posta kutularından kalıcı olarak kaldırmak isteyebilir.

- Yeni bir bekletme ilkesi oluşturun ve yeni özel bekletme etiketlerini ekleyin. Ayrıca, yeni bekletme ilkesine yerleşik bekletme etiketleri de ekleyeceksiniz. Bu, kullanıcıların posta kutularındaki öğelere atayabileceği kişisel etiketleri içerir. Ayrıca, kullanıcının birincil posta kutusunda bulunan Kurtarılabilir Öğeler klasöründeki öğeleri arşiv posta kutularındaki Kurtarılabilir Öğeler klasörüne taşıyan bir bekletme etiketi de ekleyeceksiniz. Bu eylem, posta kutusu beklemeye alındığında kullanıcının Kurtarılabilir Öğeler klasöründe yer açmasına yardımcı olur.

Kendi kuruluşunuzdaki posta kutuları için arşiv ve silme ilkesi ayarlamak için bu makaledeki adımların bazılarını veya tümünü izleyebilirsiniz. Kuruluşunuzdaki tüm posta kutularına uygulamadan önce bu işlemi birkaç posta kutusunda test etmenizi öneririz.

> [!NOTE]
> Bu makaledeki yönergelerde [Microsoft Purview uyumluluk portalı](microsoft-365-compliance-center.md) ve [yeni Exchange yönetim merkezi](/exchange/features-in-new-eac) kullanılır.

## <a name="before-you-set-up-an-archive-and-deletion-policy"></a>Arşiv ve silme ilkesi ayarlamadan önce

- Bu makaledeki adımları gerçekleştirmek için kuruluşunuzda genel yönetici olmanız gerekir.

- Yeni bir kullanıcı hesabı oluşturduğunuzda ve kullanıcıya Exchange Online lisansı atadığınızda, kullanıcı için otomatik olarak bir posta kutusu oluşturulur. Posta kutusu oluşturulduğunda, otomatik olarak Varsayılan MRM İlkesi adlı bir varsayılan bekletme ilkesi atanır. Bu makalede, yeni bir MRM bekletme ilkesi oluşturacak ve bunu kullanıcı posta kutularına atayarak Varsayılan MRM ilkesini değiştireceksiniz. Bir posta kutusuna bir kerede yalnızca bir MRM bekletme ilkesi atanabilir.

- Exchange Online'da bekletme etiketleri ve MRM bekletme ilkeleri hakkında daha fazla bilgi edinmek için bkz[. Bekletme etiketleri ve bekletme ilkeleri](/exchange/security-and-compliance/messaging-records-management/retention-tags-and-policies).

## <a name="step-1-enable-archive-mailboxes-for-users"></a>1. Adım: Kullanıcılar için arşiv posta kutularını etkinleştirme

İlk adım, kuruluşunuzdaki her kullanıcının bir arşiv posta kutusuna sahip olduğundan emin olmaktır. "Arşive Taşı" bekletme eylemine sahip bir bekletme etiketinin saklama süresi dolduktan sonra öğeyi taşıyabilmesi için kullanıcının arşiv posta kutusunun etkinleştirilmesi gerekir.

Arşiv posta kutularını etkinleştirme yönergeleri için bkz [. Microsoft 365'te arşiv posta kutularını etkinleştirme](enable-archive-mailboxes.md).
  
> [!NOTE]
> Bu işlem sırasında, işlemi tamamlamadan önce belirli bir noktada etkinleştirildiği sürece arşiv posta kutularını istediğiniz zaman etkinleştirebilirsiniz. Arşiv posta kutusu etkinleştirilmemişse, kendisine atanmış arşiv veya silme ilkesi olan öğeler üzerinde hiçbir işlem yapılmaz.

## <a name="step-2-create-new-retention-tags-for-the-archive-and-deletion-policies"></a>2. Adım: Arşiv ve silme ilkeleri için yeni bekletme etiketleri oluşturma

Bu adımda, daha önce açıklanan üç özel bekletme etiketini oluşturacaksınız.
  
- Alpine House 3 Yıl Arşive Taşı (özel arşiv ilkesi)

- Alpine House 7 Yıl Kalıcı Silme (özel silme ilkesi)

- Alpine House Silinmiş Öğeler 5 Yıl Silme ve Kurtarmaya İzin Ver (Silinmiş Öğeler klasörü için özel etiket)

Yeni bekletme etiketleri oluşturmak için [Microsoft Purview uyumluluk portalı](microsoft-365-compliance-center.md) kullanacaksınız.
  
1. [Microsoft Purview uyumluluk portalı](https://compliance.microsoft.com/) gidin ve kimlik bilgilerinizi kullanarak oturum açın.
  
2. Uyumluluk portalında **Çözüm** \> **Verileri yaşam döngüsü yönetimi** \> **Exchange (eski)** > **Bekletme etiketleri'ne** gidin
    
    Kuruluşunuzun bekletme etiketlerinin listesi görüntülenir.

### <a name="create-a-custom-archive-default-policy-tag"></a>Özel arşiv varsayılan ilke etiketi oluşturma
  
İlk olarak, öğeleri 3 yıl sonra arşiv posta kutusuna taşıyacak özel bir arşiv varsayılan ilke etiketi (DPT) oluşturacaksınız.
  
1. **Bekletme etiketleri** sayfasında **+ Yeni etiket'i** seçin ve **etiketin nasıl uygulanacağını tanımla** sayfasında **Otomatik olarak tüm posta kutusuna (varsayılan)** seçeneğini belirleyin.

2. **Bekletme ayarlarını tanımla** sayfasında aşağıdaki alanları doldurun: 
  
   1. **Öğeler aşağıdaki yaşa ulaştığında (gün olarak)** Saklama süresinin süresini girin. Bu senaryoda, öğeler 1095 gün (3 yıl) sonra arşiv posta kutusuna taşınacaktır. 

   2. **Bekletme Eylemi için,** bekletme süresi dolduğunda öğeleri arşiv posta kutusuna taşımak için **Öğeyi arşive taşı'yı** seçin.

3. **Etiketinizi adlandırın** sayfasında, yeni bekletme etiketi için bir ad ve özel bekletme etiketinin amacını açıklayan isteğe bağlı bir açıklama yazın. 
    
    Örnek senaryomuzda bu etiketi "Alpine House 3 Year Move to Archive" olarak adlandıracağız.

4. **İleri'yi** seçin ve ardından gözden geçirip göndererek özel arşiv DPT'sini oluşturun.

Yeni arşiv DPT,bekletme etiketleri listesinde görüntülenir.

### <a name="create-a-custom-deletion-default-policy-tag"></a>Özel silme varsayılan ilke etiketi oluşturma
  
Ardından, başka bir özel DPT oluşturacaksınız, ancak bu, 7 yıl sonra öğeleri kalıcı olarak silecek bir silme ilkesi olacaktır.
  
1. **Bekletme etiketleri** sayfasına geri dönün **, + Yeni etiket'i** seçin ve **etiketin nasıl uygulanacağını tanımla** sayfasında **Otomatik olarak tüm posta kutusuna (varsayılan)** öğesini yeniden seçin.

2. **Bekletme ayarlarını tanımla** sayfasında aşağıdaki alanları doldurun: 
  
   1. **Öğeler aşağıdaki yaşa ulaştığında (gün olarak)** Saklama süresinin süresini girin. Bu senaryo için öğeler 2555 gün (7 yıl) sonra temizlenir. 

   2. **Bekletme Eylemi için,** bekletme süresi dolduğunda posta kutusundan öğeleri temizlemek için **Kalıcı olarak sil'i** seçin.

3. **Etiketinizi adlandırın** sayfasında, yeni bekletme etiketi için bir ad ve özel bekletme etiketinin amacını açıklayan isteğe bağlı bir açıklama yazın. 
    
    Örnek senaryomuz için bu etiketi "Alpine House 7 Yıl Kalıcı Olarak Sil" olarak adlandıracağız.

4. **İleri'yi** seçin ve ardından gözden geçirip göndererek özel silme DPT'sini oluşturun.

Yeni silme DPT'i bekletme etiketleri listesinde görüntülenir.

### <a name="create-a-custom-retention-policy-tag-for-the-deleted-items-folder"></a>Silinmiş Öğeler klasörü için özel bekletme ilkesi etiketi oluşturma
  
Oluşturulacak son bekletme etiketi, Silinmiş Öğeler klasörü için özel bir bekletme ilkesi etiketidir (RPT). Bu etiket, Silinmiş Öğeler klasöründeki öğeleri 5 yıl sonra siler ve kullanıcıların bir öğeyi kurtarmak için Silinmiş Öğeleri Kurtar aracını kullanabileceği bir kurtarma süresi sağlar.

1. **Bekletme etiketleri** sayfasına geri dönün **, + Yeni etiket'i** seçin ve **etiketin nasıl uygulanacağını tanımla** sayfasında **Otomatik olarak tüm posta kutusuna (varsayılan)** öğesini yeniden seçin.

2. **Bekletme ayarlarını tanımla** sayfasında aşağıdaki alanları doldurun: 
  
   1. **Öğeler aşağıdaki yaşa ulaştığında (gün olarak)** Saklama süresinin süresini girin. Bu senaryo için öğeler 1825 gün (5 yıl) sonra silinir. 

   2. **Bekletme Eylemi** için **Sil'i seçin ve** bekletme süresi dolduğunda kurtarmanın öğeleri silmesine izin verin, ancak kullanıcıların silinen öğe saklama süresi içinde (varsayılan olarak 14 gündür) silinen bir öğeyi kurtarmasına izin verin.

3. **Etiketinizi adlandırın** sayfasında, yeni bekletme etiketi için bir ad ve özel bekletme etiketinin amacını açıklayan isteğe bağlı bir açıklama yazın.
    
    Örnek senaryomuz için bu etiketi "Alpine House Deleted Items 5 Years Delete and Allow Recovery" olarak adlandıracağız.

4. **İleri'yi** seçin ve ardından gözden geçirip göndererek özel silme DPT'sini oluşturun.

Yeni RPT, bekletme etiketleri listesinde görüntülenir.

## <a name="step-3-create-a-new-retention-policy"></a>3. Adım: Yeni bir bekletme ilkesi oluşturma

Özel bekletme etiketlerini oluşturduktan sonra, sonraki adım yeni bir bekletme ilkesi oluşturmak ve bekletme etiketlerini eklemektir. 2. Adımda oluşturduğunuz üç özel bekletme etiketini ve ilk bölümde bahsedilen yerleşik etiketleri ekleyeceksiniz. 4. Adımda, bu yeni bekletme ilkesini kullanıcı posta kutularına atayacaksınız.
  
1. [Microsoft Purview uyumluluk portalı](https://compliance.microsoft.com/) **Veri yaşam döngüsü yönetimi** \> **Exchange (eski)** > **Bekletme ilkeleri'ne** gidin.

2. **Bekletme ilkeleri** sayfasında **Yeni ilke'yi** seçin.

3. **Ad** kutusuna yeni bekletme ilkesi için bir ad yazın; örneğin, **Alpine House Arşiv ve Silme İlkesi**.

4. **+ Etiket ekle'yi** seçin.

    2. Adımda oluşturduğunuz özel etiketleri içeren, kuruluşunuzdaki bekletme etiketlerinin listesi görüntülenir.

5. [Daha fazla bilgi](#more-information) bölümünde daha ayrıntılı olarak açıklanan 9 bekletme etiketini ekleyin:
    
    - **Alpine House 3 Year Move to Archive** - Bu yönergelerin 2. adımında oluşturulan özel arşiv varsayılan ilke etiketi
    - **Alpine House 7 Yıl Kalıcı Silme** - bu yönergelerin 2. adımında oluşturulan özel silme etiketi
    - **Alpine House Silinmiş Öğeler 5 Yıl Silme ve Kurtarmaya İzin Ver** - bu yönergelerin 2. adımında oluşturulan Silinmiş Öğeler klasörünün özel etiketi
    - **Kurtarılabilir Öğeler 14 gün Arşive Taşı**
    - **Gereksiz Email**
    - **1 Ay Silme**
    - **1 Yıllık Silme**
    - **Hiçbir Zaman Silme**
    - **Kişisel 1 yıl arşive taşıma**
    
    Bu bekletme etiketlerini eklemek için bunları seçin ve ardından **Ekle'yi** seçin.

7. **İlkenizi yapılandırın** sayfasına geri dönüp **İleri'yi** seçerek yeni ilkeyi gözden geçirin ve gönderin.

Yeni bekletme ilkesi listede görüntülenir. Ayrıntılar bölmesinde bağlantılı bekletme etiketlerini görüntülemek için bunu seçin.

## <a name="step-4-assign-the-new-retention-policy-to-user-mailboxes"></a>4. Adım: Yeni bekletme ilkesini kullanıcı posta kutularına atama

Yeni bir posta kutusu oluşturulduğunda, varsayılan olarak Varsayılan MRM ilkesi adlı bir bekletme ilkesi atanır. Bu adımda, 3. Adımda oluşturduğunuz yeni bekletme ilkesini kuruluşunuzdaki kullanıcı posta kutularına atayarak bu bekletme ilkesini değiştireceksiniz. 

Bir posta kutusuna aynı anda yalnızca bir MRM bekletme ilkesi atanabileceğinden değiştirme gereklidir. Bu adım, yeni ilkeyi kuruluşunuzdaki tüm posta kutularına atayabileceğinizi varsayar.

Bu adımları izlemek için klasik sürüm yerine [yeni Exchange yönetim merkezini](/exchange/features-in-new-eac) kullandığınızdan emin olun.
  
1. Yeni [Exchange yönetim merkezinde (EAC)](https://admin.exchange.microsoft.com/) oturum açın ve **Alıcılar** > **Posta Kutuları'na** gidin.

    Kuruluşunuzdaki tüm kullanıcı posta kutularının listesi görüntülenir.

2. **Görünen ad** kutusunu seçerek tüm posta kutularını seçin. 

3. **Posta kutusu ilkeleri** seçeneğini belirleyin.

4. **Posta kutusu ilkeleri** açılır penceresinde, **Bekletme İlkesi'nin** altında, 3. Adımda oluşturduğunuz bekletme ilkesini seçin; örneğin, **Alpine House Arşiv ve Bekletme İlkesi**.

5. Yeni bekletme ilkesi atamasını kaydetmek için **Kaydet'i** seçin.

6. Yeni bekletme ilkesinin posta kutularına atandığını doğrulamak için:

   1. **Posta Kutuları sayfasında bir posta kutusu** seçin.

   2. Seçili kullanıcının posta kutusu özellikleri sayfasında **Posta Kutusu'na** tıklayın.
    
    Bekletme ilkesi için posta kutusuna atanan yeni **ilkenin** adı görüntülenir.

## <a name="optional-step-5-run-the-managed-folder-assistant-to-apply-the-new-settings"></a>(İsteğe bağlı) 5. Adım: Yeni ayarları uygulamak için Yönetilen Klasör Yardımcısı'nı çalıştırın

4. Adımda posta kutularına yeni bekletme ilkesini uyguladıktan sonra, yeni bekletme ayarlarının posta kutularına uygulanması Exchange Online 7 güne kadar sürebilir. Bunun nedeni *, Yönetilen Klasör Yardımcısı* adlı bir işlemin posta kutularını en az 7 günde bir işlemesidir. Yönetilen Klasör Yardımcısı'nın çalışmasını beklemek yerine, Exchange Online PowerShell'de **Start-ManagedFolderAssistant** cmdlet'ini çalıştırarak bunun gerçekleşmesini zorlayabilirsiniz.

 **Yönetilen Klasör Yardımcısı'nı çalıştırdığınızda ne olur?** Posta kutusunda öğeleri inceleyerek ve bekletmeye tabi olup olmadıklarını belirleyerek bekletme ilkesindeki ayarları uygular. Ardından, bekletmeye tabi olan öğeleri uygun bekletme etiketiyle damgalar ve bekletme yaşlarını geçen öğelerde belirtilen bekletme eylemini gerçekleştirir.
  
Exchange Online PowerShell'e bağlanma ve ardından yönetilen klasör yardımcısı'nı kuruluşunuzdaki her posta kutusunda çalıştırma adımları aşağıdadır.

1. [Exchange Online PowerShell’e bağlanma](/powershell/exchange/connect-to-exchange-online-powershell).
  
2. Kuruluşunuzdaki tüm kullanıcı posta kutuları için Yönetilen Klasör Yardımcısı'nı başlatmak için aşağıdaki iki komutu çalıştırın.

    ```powershell
    $Mailboxes = Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"}
    ```

    ```powershell
    $Mailboxes.Identity | Start-ManagedFolderAssistant
    ```

İşte bu kadar! Alpine House kuruluşu için bir arşiv ve silme ilkesi ayarladınız.

### <a name="more-information-about-the-managed-folder-assistant"></a>Yönetilen Klasör Yardımcısı hakkında daha fazla bilgi

Daha önce belirtildiği gibi, Yönetilen Klasör Yardımcısı posta kutularını en az 7 günde bir işler. Bu nedenle, bir posta kutusunun Yönetilen Klasör Yardımcısı tarafından daha sık işlenebilmesi mümkündür. Ayrıca yöneticiler, bir posta kutusunun Yönetilen Klasör Yardımcısı tarafından bir sonraki işlenme zamanını tahmin edememektedir. Bu nedenle, posta kutusunu el ile çalıştırmak isteyebilirsiniz. 

Ancak, Yönetilen Klasör Yardımcısı'nın yeni bekletme ayarlarını bir posta kutusuna uygulamasını geçici olarak engellemek istiyorsanız, Yönetilen Klasör Yardımcısı'nın posta kutusunu işlemesini geçici olarak devre dışı bırakmak için komutunu çalıştırabilirsiniz `Set-Mailbox -ElcProcessingDisabled $true` . 

Yönetilen Klasör Yardımcısı'nı bir posta kutusu için yeniden etkinleştirmek için komutunu çalıştırın `Set-Mailbox -ElcProcessingDisabled $false` . 

Son olarak, posta kutusu kullanıcısı devre dışı bırakılmış bir hesaba sahipse, öğeler bu posta kutusunun arşiv posta kutusuna taşınmaz.
  
## <a name="optional-step-6-make-the-new-retention-policy-the-default-for-your-organization"></a>(İsteğe bağlı) 6. Adım: Yeni bekletme ilkesini kuruluşunuz için varsayılan hale getirme

4. Adımda, yeni bekletme ilkesini mevcut posta kutularına atamanız gerekir. Ancak Exchange Online yapılandırarak yeni bekletme ilkesinin gelecekte oluşturulan yeni posta kutularına atanması sağlanır. 

Bunu, kuruluşunuzun varsayılan posta kutusu planını güncelleştirmek için Exchange Online PowerShell kullanarak yaparsınız. *Posta kutusu planı*, yeni posta kutularında özellikleri otomatik olarak yapılandıran bir şablondur.  Bu isteğe bağlı adımda, posta kutusu planına atanan geçerli bekletme ilkesini (varsayılan olarak, Varsayılan MRM İlkesi) 3. Adımda oluşturduğunuz MRM bekletme ilkesiyle değiştirebilirsiniz. Posta kutusu planını güncelleştirdikten sonra, yeni MRM bekletme ilkesi yeni posta kutularına atanır.

1. [Exchange Online PowerShell’e bağlanma](/powershell/exchange/connect-to-exchange-online-powershell).

2. Kuruluşunuzdaki posta kutusu planları hakkında bilgi görüntülemek için aşağıdaki komutu çalıştırın.

    ```powershell
    Get-MailboxPlan | Format-Table DisplayName,RetentionPolicy,IsDefault
    ```
    
    Varsayılan olarak ayarlanan posta kutusu planını not edin.

3. 3. Adımda oluşturduğunuz yeni MRM bekletme ilkesini (örneğin **Alpine House Arşiv ve Bekletme İlkesi**) varsayılan posta kutusu planına atamak için aşağıdaki komutu çalıştırın. Bu örnekte, varsayılan posta kutusu planının adının **ExchangeOnlineEnterprise** olduğu varsayılır.
    
    ```powershell
    Set-MailboxPlan "ExchangeOnlineEnterprise" -RetentionPolicy "Alpine House Archive and Retention Policy"
    ```

4. Varsayılan posta kutusu planına atanan MRM bekletme ilkesinin değiştirildiğini doğrulamak için 2. adımda komutu yeniden çalıştırabilirsiniz.

## <a name="more-information"></a>Daha fazla bilgi

- Posta kutusu öğelerinin saklama yaşı, teslim tarihinden itibaren hesaplanır. Veya, gönderilmemiş ancak kullanıcı tarafından oluşturulan taslak iletiler gibi öğeler için oluşturulma tarihinden itibaren. Yönetilen Klasör Yardımcısı bir posta kutusunda öğeleri işlediğinde, Silme ve Kurtarmaya İzin Ver veya Kalıcı Olarak Sil bekletme eylemiyle bekletme etiketlerine sahip tüm öğeler için bir başlangıç tarihi ve son kullanma tarihi damgalar. Arşiv etiketine sahip öğeler taşıma tarihiyle damgalanır.

- Aşağıdaki tabloda, bu makaledeki özel MRM bekletme ilkesi için her bekletme etiketi hakkında daha fazla bilgi sağlanır.

    | Bekletme etiketi | Bu etiketin yaptığı | Yerleşik mi yoksa özel mi? | Tür |
    |:-----|:-----|:-----|:-----|
    |Alpine House 3 Yıl Arşive Taşı  <br/> |1095 gün (3 yıl) eski öğeleri arşiv posta kutusuna taşır.  <br/> |Özel (Bkz [. 2. Adım: Arşiv ve silme ilkeleri için yeni bekletme etiketleri oluşturma](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies))  <br/> |Varsayılan İlke Etiketi (arşiv); bu etiket, posta kutusunun tamamına otomatik olarak uygulanır.  <br/> |
    |Alpine House 7 Yıl Kalıcı Olarak Sil  <br/> |Birincil posta kutusunda veya arşiv posta kutusunda bulunan öğeler 7 yaşındayken kalıcı olarak silinir.  <br/> |Özel (Bkz [. 2. Adım: Arşiv ve silme ilkeleri için yeni bekletme etiketleri oluşturma](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies))  <br/> |Varsayılan İlke Etiketi (silme); bu etiket, posta kutusunun tamamına otomatik olarak uygulanır.  <br/> |
    |Alpine House Silinmiş Öğeler 5 Yıl Silme ve Kurtarmaya İzin Ver  <br/> |Silinmiş Öğeler klasöründeki 5 yaşındaki öğeleri siler. Kullanıcılar bu öğeleri silindikten sonra 14 gün boyunca kurtarabilir.<sup>\*</sup> <br/> |Özel (Bkz [. 2. Adım: Arşiv ve silme ilkeleri için yeni bekletme etiketleri oluşturma](#step-2-create-new-retention-tags-for-the-archive-and-deletion-policies))  <br/> |Bekletme İlkesi Etiketi (Silinmiş Öğeler); bu etiket, Silinmiş öğeler klasöründeki öğelere otomatik olarak uygulanır.  <br/> |
    |Kurtarılabilir Öğeler 14 gün Arşive Taşı  <br/> |14 gün boyunca Kurtarılabilir Öğeler klasöründe bulunan öğeleri arşiv posta kutusunda Kurtarılabilir Öğeler klasörüne taşır.  <br/> |Yerleşik  <br/> |Bekletme İlkesi Etiketi (Kurtarılabilir Öğeler); bu etiket, Kurtarılabilir Öğeler klasöründeki öğelere otomatik olarak uygulanır.  <br/> |
    |Gereksiz Email  <br/> |Gereksiz Email klasöründe 30 gün boyunca bulunan öğeleri kalıcı olarak siler. Kullanıcılar bu öğeleri silindikten sonra 14 gün boyunca kurtarabilir.<sup>\*</sup> <br/> |Yerleşik  <br/> |Bekletme İlkesi Etiketi (Gereksiz Email); Bu etiket, Gereksiz Email klasöründeki öğelere otomatik olarak uygulanır.  <br/> |
    |1 Ay Silme  <br/> |30 günlük öğeleri kalıcı olarak siler. Kullanıcılar bu öğeleri silindikten sonra 14 gün boyunca kurtarabilir.<sup>\*</sup> <br/> |Yerleşik  <br/> |Kişisel; bu etiket kullanıcılar tarafından uygulanabilir.  <br/> |
    |1 Yıllık Silme  <br/> |365 günlük öğeleri kalıcı olarak siler. Kullanıcılar bu öğeleri silindikten sonra 14 gün boyunca kurtarabilir.<sup>\*</sup> <br/> |Yerleşik  <br/> |Kişisel; bu etiket kullanıcılar tarafından uygulanabilir.  <br/> |
    |Hiçbir Zaman Silme  <br/> |Bu etiket, öğelerin bekletme ilkesi tarafından silinmesini engeller.  <br/> |Yerleşik  <br/> |Kişisel; bu etiket kullanıcılar tarafından uygulanabilir.  <br/> |
    |Kişisel 1 yıl arşive taşıma  <br/> |Öğeleri 1 yıl sonra arşiv posta kutusuna taşır.  <br/> |Yerleşik  <br/> |Kişisel; bu etiket kullanıcılar tarafından uygulanabilir.  <br/> |

    > <sup>\*</sup>Kullanıcılar, Silinmiş Öğeleri Kurtarma aracını Outlook'ta ve Web üzerinde Outlook (eski adıyla Outlook Web App) kullanarak silinmiş bir öğeyi silinmiş öğe saklama süresi içinde kurtarabilir ve bu da varsayılan olarak Exchange Online 14 gündür. Yönetici, silinmiş öğe saklama süresini en fazla 30 güne yükseltmek için PowerShell Exchange Online kullanabilir. Daha fazla bilgi için bkz. [Windows için Outlook'ta silinen öğeleri kurtarma](https://support.office.com/article/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce) ve [Exchange Online bir posta kutusunun silinmiş öğe saklama süresini değiştirme](/exchange/recipients-in-exchange-online/manage-user-mailboxes/change-deleted-item-retention).
  
- **Kurtarılabilir Öğeler 14 gün Arşive Taşı** bekletme etiketinin kullanılması, kullanıcının birincil posta kutusunda Kurtarılabilir Öğeler klasöründe depolama alanı boşaltmaya yardımcı olur. Bu, kullanıcının posta kutusu beklemeye alındığında veya öğeleri tutan bir bekletme ilkesi uygulandığında yararlıdır. Her iki yapılandırma da e-postaların kullanıcının posta kutusundan kalıcı olarak silinmesini engeller. Öğeleri arşiv posta kutusuna taşımadan, birincil posta kutusunda Kurtarılabilir Öğeler klasörünün depolama kotasına ulaşılması mümkündür. Bu senaryo hakkında daha fazla bilgi için bkz. [Beklemedeki posta kutuları için Kurtarılabilir Öğeler kotasını artırma](./increase-the-recoverable-quota-for-mailboxes-on-hold.md).
