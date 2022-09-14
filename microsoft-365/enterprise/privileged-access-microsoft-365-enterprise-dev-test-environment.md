---
title: Kurumsal test ortamınız için Microsoft 365 için ayrıcalıklı erişim yönetimi
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: scotv
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom: Ent_TLGs
description: Kurumsal test ortamı için Microsoft 365'inizde ayrıcalıklı erişim yönetimini etkinleştirmek için bu Test Laboratuvarı Kılavuzu'nu kullanın.
ms.openlocfilehash: e55fcc13c4a86db7b507ad28e61c37df3ab156ab
ms.sourcegitcommit: 437461fa1d38ff9bb95dd8a1c5f0b94e8111ada2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67670299"
---
# <a name="privileged-access-management-for-your-microsoft-365-for-enterprise-test-environment"></a>Kurumsal test ortamınız için Microsoft 365 için ayrıcalıklı erişim yönetimi

*Bu Test Laboratuvarı Kılavuzu hem kurumsal hem de Office 365 Kurumsal test ortamları için Microsoft 365 için kullanılabilir.*

Bu makalede, kurumsal test ortamınız için Microsoft 365'te güvenliği artırmak için ayrıcalıklı erişim yönetiminin nasıl yapılandırıldığı açıklanır.

Ayrıcalıklı erişim yönetiminin yapılandırılması üç aşamayı kapsar:

- [1. Aşama: Kurumsal test ortamı için Microsoft 365'inizi oluşturma](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [2. Aşama: Ayrıcalıklı erişim yönetimini yapılandırma](#phase-2-configure-privileged-access-management)
- [3. Aşama: Yükseltilmiş ve ayrıcalıklı görevler için onay gerektiğini doğrulayın](#phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks)

![Microsoft bulutu için Test Laboratuvarı Kılavuzları.](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Microsoft 365 kurumsal Test Laboratuvarı Kılavuzu yığınındaki tüm makalelere yönelik görsel bir harita için [, Kurumsal Test Laboratuvarı Kılavuz Yığını için Microsoft 365'e](../downloads/Microsoft365EnterpriseTLGStack.pdf) gidin.
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>1. Aşama: Kurumsal test ortamı için Microsoft 365'inizi oluşturma

Ayrıcalıklı erişim yönetimini minimum gereksinimlerle basit bir şekilde yapılandırmak istiyorsanız [, Basit temel yapılandırma](lightweight-base-configuration-microsoft-365-enterprise.md) yönergelerini izleyin.
  
Sanal bir kuruluşta ayrıcalıklı erişim yönetimini yapılandırmak istiyorsanız Doğrudan [kimlik doğrulamasındaki](pass-through-auth-m365-ent-test-environment.md) yönergeleri izleyin.
  
> [!NOTE]
> Ayrıcalıklı erişim yönetimini test etmek, İnternet'e bağlı bir sanal intranet ve bir Active Directory Domain Services ormanı için dizin eşitlemesi içeren sanal kurumsal test ortamını gerektirmez. Ayrıcalıklı erişim yönetimini test edebilmeniz ve tipik bir kuruluşu temsil eden bir ortamda denemeler yapabilmeniz için burada bir seçenek olarak sağlanır.

## <a name="phase-2-configure-privileged-access-management"></a>2. Aşama: Ayrıcalıklı erişim yönetimini yapılandırma

Bu aşamada, kurumsal test ortamınız için Microsoft 365'te bir onaylayan grubu yapılandırın ve ayrıcalıklı erişim yönetimini etkinleştirin. Ek ayrıntılar ve ayrıcalıklı erişim yönetimine genel bakış için bkz [. Ayrıcalıklı erişim yönetimi](../compliance/privileged-access-management-overview.md).

Kuruluşunuzda ayrıcalıklı erişimi ayarlamak ve kullanmak için aşağıdaki adımları uygulayın.

### <a name="step-1-create-an-approvers-group"></a>[1. Adım: Onaylayan grubu oluşturma](../compliance/privileged-access-management-configuration.md#step-1-create-an-approvers-group)

Ayrıcalıklı erişimi kullanmaya başlamadan önce, yükseltilmiş ve ayrıcalıklı görevlere erişim için gelen istekler için kimlerin onay yetkisine sahip olacağını belirleyin. Onaylayanlar grubunun parçası olan tüm kullanıcılar erişim isteklerini onaylayabilir. Ayrıcalıklı erişimi kullanmak için Microsoft 365'te posta özellikli bir güvenlik grubu oluşturmanız gerekir. Test ortamınızda yeni güvenlik grubunu "Privileged Access Approvers" olarak adlandırın ve önceki test laboratuvarı kılavuzu adımlarında daha önce oluşturulmuş olan "Kullanıcı 3" öğesini ekleyin.

### <a name="step-2-enable-privileged-access"></a>[2. Adım: Ayrıcalıklı erişimi etkinleştirme](../compliance/privileged-access-management-configuration.md#step-2-enable-privileged-access)

Ayrıcalıklı erişimin Microsoft 365'te varsayılan onaylayan grubuyla açık bir şekilde açılması ve ayrıcalıklı erişim yönetimi erişim denetiminden dışlanmasını istediğiniz bir dizi sistem hesabı içermesi gerekir. Bu kılavuzun 3. aşamasına başlamadan önce kuruluşunuzda ayrıcalıklı erişimi etkinleştirdiğinizden emin olun.

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a>3. Aşama: Yükseltilmiş ve ayrıcalıklı görevler için onay gerektiğini doğrulayın

Bu aşamada ayrıcalıklı erişim ilkesinin çalıştığını ve kullanıcıların tanımlı yükseltilmiş ve ayrıcalıklı görevleri yürütmek için onay gerektirdiğini doğrulayın.

### <a name="test-the-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a>Ayrıcalıklı erişim ilkesinde tanımlanmayan bir görevi yürütme özelliğini test etme

İlk olarak, PowerShell'Exchange Online yeni bir Günlük kuralı oluşturmayı deneyin. [New-JournalRule](/powershell/module/exchange/new-journalrule) görevi şu anda kuruluşunuz için ayrıcalıklı erişim ilkesinde tanımlanmamıştır.

1. Yerel bilgisayarınızda, test ortamınız için Exchange Rol Yönetimi rolüne sahip kimlik bilgilerini kullanarak [Exchange Online PowerShell'e bağlanın](/powershell/exchange/connect-to-exchange-online-powershell).
2. Aşağıdaki komutu çalıştırarak kuruluşunuz için yeni bir Günlük kuralı oluşturun:

   ```PowerShell
   New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
   ```

3. Yeni Günlük Kuralının başarıyla oluşturulduğunu doğrulayın:

   ```PowerShell
   Get-JournalRule -Identity "JournalRule1"
   ```

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a>New-JournalRule görevi için yeni bir ayrıcalıklı erişim ilkesi oluşturma

> [!NOTE]
> Bu kılavuzun 2. Aşamasından 1. ve 2. Adımları henüz tamamlamadıysanız, test ortamınızda ayrıcalıklı erişimi etkinleştirmek için onaylayanın "Privilege Access Approvers" adlı grubunu oluşturma adımlarını izlediğinizden emin olun.

1. Test ortamınız için Exchange Rol Yönetimi rolüyle kimlik bilgilerini kullanarak [Microsoft 365 yönetim merkezi](https://admin.microsoft.com) oturum açın.
2. Yönetici Merkezi'nde **Ayarlar** > **Güvenlik & Gizlilik** > **Ayrıcalıklı erişimi'ne** gidin.
3. **Erişim ilkelerini ve isteklerini yönet'i** seçin.
4. **İlkeleri yapılandır'ı** ve ardından **İlke ekle'yi** seçin.
5. Açılan alanlardan aşağıdaki değerleri seçin veya girin:

    **İlke türü**: Görev  **İlkesi kapsamı**: Exchange  **İlkesi adı**: Yeni Günlük Kuralı  **Onay türü**: El ile  **Onay grubu**: Ayrıcalıklı Erişim Onaylayıcıları

6. **Oluştur'u** ve ardından **Kapat'ı** seçin. İlkenin tam olarak yapılandırılması ve etkinleştirilmesi birkaç dakika sürebilir. Sonraki adımda onay gereksinimini test etmeden önce ilkenin tam olarak etkinleştirilmesi için zaman tanıyın.

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a>Ayrıcalıklı erişim ilkesinde tanımlanan New-JournalRule görevi için test onayı gereksinimi

1. Yerel bilgisayarınızda, test ortamınız için Exchange Rol Yönetimi rolüne sahip kimlik bilgilerini kullanarak [Exchange Online PowerShell'e bağlanın](/powershell/exchange/connect-to-exchange-online-powershell).

2. Exchange Online PowerShell'de kuruluşunuz için yeni bir Günlük kuralı oluşturun:

   ```PowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

3. Exchange Online PowerShell'de "Yetersiz izinler" hatasını görüntüleyin:

   ```PowerShell
   Insufficient permissions. Please raise an elevated access request for this task.
       + CategoryInfo          : NotSpecified: (:) [], LocalizedException
       + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
       7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
       + PSComputerName        : outlook.office365.com
   ```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a>New-JournalRule görevini kullanarak yeni günlük kuralı oluşturmak için erişim isteme

1. Test ortamınız için Exchange Rol Yönetimi rolüyle kimlik bilgilerini kullanarak [Microsoft 365 yönetim merkezi](https://admin.microsoft.com) oturum açın.

2. Yönetici Merkezi'nde **Ayarlar** > **Güvenlik & Gizlilik** > **Ayrıcalıklı erişimi'ne** gidin.

3. **Erişim ilkelerini ve isteklerini yönet'i** seçin.

4. **Yeni istek'i** seçin. Açılan alanlardan kuruluşunuz için uygun değerleri seçin:

    **İstek türü**: Görev  **İsteği kapsamı**: Exchange  **İsteği**: Yeni Günlük Kuralı  **Süresi (saat)**: 2  **Açıklamalar**: Yeni günlük kuralı oluşturmak için izin isteme

5. **Kaydet'i** ve ardından **Kapat'ı** seçin. İsteğiniz onaylayanın grubuna e-postayla gönderilir.

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a>Yeni günlük kuralı oluşturmak için ayrıcalıklı erişim isteğini onaylama

1. Test ortamınızdaki Kullanıcı 3 için kimlik bilgilerini kullanarak [Microsoft 365 yönetim merkezi](https://admin.microsoft.com) oturum açın (test ortamınızdaki "Ayrıcalıklı Erişim Onaylayanları" güvenlik grubunun üyesi).

2. Yönetici Merkezi'nde **Ayarlar** > **Güvenlik & Gizlilik** > **Ayrıcalıklı erişimi'ne** gidin.

3. **Erişim ilkelerini ve isteklerini yönet'i** seçin.

4. Bekleyen isteği seçin ve ardından yeni bir Günlük Kuralı oluşturmak üzere kullanıcı hesabına erişim vermek için **Onayla'yı** seçin. Hesap (istekte bulunan kullanıcı) onay verildiğine ilişkin bir e-posta onayı alır.

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a>New-JournalRule görevi için ayrıcalıklı erişim onaylı yeni bir Günlük Kuralı oluşturmayı test edin

1. Yerel bilgisayarınızda, test ortamınız için Exchange Rol Yönetimi rolüne sahip kimlik bilgilerini kullanarak [Exchange Online PowerShell'e bağlanın](/powershell/exchange/connect-to-exchange-online-powershell).

2. Exchange Online PowerShell'de kuruluşunuz için yeni bir Günlük kuralı oluşturun:

   ```PowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

3. Yeni Günlük kuralının başarıyla oluşturulduğunu doğrulayın:

   ```PowerShell
   Get-JournalRule -Identity "JournalRule2"
   ```

## <a name="next-step"></a>Sonraki adım

Test ortamınızdaki ek [bilgi koruma](m365-enterprise-test-lab-guides.md#information-protection) özelliklerini ve özelliklerini keşfedin.

## <a name="see-also"></a>Ayrıca bkz.

- [Kurumsal test laboratuvarı kılavuzları için Microsoft 365](m365-enterprise-test-lab-guides.md)
- [Microsoft 365 Kurumsal’a genel bakış](microsoft-365-overview.md)
- [Kurumsal belgeler için Microsoft 365](/microsoft-365-enterprise/)
