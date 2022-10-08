---
title: Office 365 için Microsoft Defender'da öncelik hesaplarını yapılandırma ve gözden geçirme
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: 3/21/2022
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- m365-security
ms.custom: ''
description: Bir kuruluştaki kritik kişileri tanımlamayı ve onlara ek koruma sağlamak için öncelik hesabı etiketini eklemeyi öğrenin.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 0133a684780ab59514d576bf619ebe2c4aa45099
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68066618"
---
# <a name="configure-and-review-priority-accounts-in-microsoft-defender-for-office-365"></a>Office 365 için Microsoft Defender'de Öncelik hesaplarını yapılandırma ve gözden geçirme

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Uygulandığı öğe**
- [Office 365 için Microsoft Defender plan 1 ve plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Her kuruluşta yöneticiler, liderler, yöneticiler veya hassas, özel veya yüksek öncelikli bilgilere erişimi olan diğer kullanıcılar gibi kritik öneme sahip kişiler vardır. Office 365 için Microsoft Defender içindeki bu kullanıcıları öncelik hesapları olarak etiketleyerek güvenlik ekiplerinin bu kritik kişilere odaklanmasını sağlayabilirsiniz. Öncelik hesapları için farklı koruma ile, öncelik hesapları olarak etiketlenen kullanıcılar tehditlere karşı daha yüksek bir koruma düzeyine sahip olur.

Öncelik hesapları saldırganlar tarafından daha sık hedeflenir ve genellikle daha gelişmiş tekniklerle saldırıya uğrar. Öncelik hesapları için farklı koruma, bu belirli kullanıcı kümesine odaklanır ve gelişmiş makine öğrenmesi modellerini kullanarak daha yüksek düzeyde koruma sağlar. Öğrenme ve ileti işlemedeki bu fark, bu hesaplar için en yüksek koruma düzeyini sağlar ve düşük hatalı pozitif oranın korunmasına yardımcı olur, yüksek hatalı pozitif oranı da bu kullanıcılar üzerinde olumsuz bir etkiye sahip olabilir.

## <a name="configure-priority-account-protection"></a>Öncelik hesabı korumasını yapılandırma

Önceden tanımlanmış kritik kullanıcılar için öncelik hesabı koruması varsayılan olarak açıktır. Ancak, kuruluşunuzun güvenlik yöneticisi şu adımları izleyerek öncelik hesabı korumasını da açabilir:

1. konumundaki Microsoft 365 Defender portalında <https://security.microsoft.com>**Ayarlar** \> **Email & işbirliği** \> **Öncelik hesabı koruması'na** gidin. **Doğrudan Öncelik hesabı koruma** sayfasına gitmek için kullanın<https://security.microsoft.com/securitysettings/priorityAccountProtection>.

2. **Öncelik hesabı koruması** sayfasında **, Öncelik hesabı korumasını** (:::image type="icon" source="../../media/scc-toggle-on.png" border="false":::) açın.

    > [!div class="mx-imgBorder"]
    > ![Öncelik hesabı korumasını açın.](../../media/mdo-priority-account-protection.png)

> [!NOTE]
> Öncelik hesabı korumasını devre dışı bırakmanızı veya kapatmanızı önermeyiz.

PowerShell'Exchange Online kullanarak öncelik hesabı korumasını açmak istiyorsanız aşağıdaki adımları uygulayın:

1. [Exchange Online PowerShell'e bağlanın](/powershell/exchange/connect-to-exchange-online-powershell) ve aşağıdaki komutu çalıştırın:

   ```powershell
   Set-EmailTenantSettings -EnablePriorityAccountProtection $true
   ```

2. Öncelik hesabı korumasının açık olduğunu doğrulamak için aşağıdaki komutu çalıştırarak EnablePriorityAccountProtection özellik değerini doğrulayın:

   ```powershell
   Get-EmailTenantSettings | Format-List Identity,EnablePriorityAccountProtection
   ```

   True değeri, öncelik hesabı korumasının açık olduğu anlamına gelir. False değeri, öncelik hesabı korumasının kapalı olduğu anlamına gelir.

### <a name="assign-the-priority-account-tag-to-users"></a>Kullanıcılara Öncelik hesabı etiketini atama

Office 365 için Microsoft Defender, uyarılarda, raporlarda, olaylarda ve daha birçok uygulamada filtre olarak kullanılabilecek etiketler olarak öncelik hesaplarını destekler.

Daha fazla bilgi için bkz. [Office 365 için Microsoft Defender'de kullanıcı etiketleri](user-tags.md).

## <a name="review-differentiated-protection-from-priority-account-protection"></a>Öncelik hesabı korumasından farklı korumayı gözden geçirin

Öncelik hesabı korumasının etkileri aşağıdaki özelliklerde görünür:

- [Uyarılar](alerts.md)
- [Özel uyarı ilkeleri](../../compliance/alert-policies.md#view-alerts)
- [Tehdit Gezgini ve gerçek zamanlı algılamalar](threat-explorer.md)
- [Güvenliği aşılmış kullanıcı raporu](view-email-security-reports.md#compromised-users-report)
- [varlık sayfasını Email](mdo-email-entity-page.md#other-innovations)
- [Tehdit koruması durum raporu](view-email-security-reports.md#threat-protection-status-report)
- [En çok gönderenler ve alıcılar raporu](view-email-security-reports.md#top-senders-and-recipients-report)
- [Saldırı benzetimi](attack-simulation-training.md#target-users)
- [Kampanya Görünümleri](campaigns.md)
- [Yönetici ve kullanıcı gönderimleri](admin-submission.md)
- [Karantina](quarantine.md)

### <a name="threat-protection-status-report"></a>Tehdit koruması durum raporu

**Tehdit koruması durum** raporu, Office 365 için Microsoft Defender tarafından algılanan ve engellenen kötü amaçlı içerik ve kötü amaçlı e-posta hakkındaki bilgileri bir araya getiren tek bir görünümdür.

Raporu görüntülemek için aşağıdaki adımları uygulayın:

1. konumundaki Microsoft 365 Defender portalında <https://security.microsoft.com>**Raporlar** \> **Email & işbirliği** \> **sayfasına gidin Email & işbirliği raporları** \> **Tehdit koruması durumunu** bulun ve **Ayrıntıları görüntüle'ye** tıklayın. Doğrudan rapora gitmek için kullanın <https://security.microsoft.com/reports/TPSAggregateReportATP>.

2. Varsayılan görünüm, **Verileri Genel Bakış'a göre görüntüle'dir**. Aşağıdaki değerlerden birini seçerek görünümü değiştirmek için bu değere tıklayın:
   - **Email \> Kimlik Avına göre verileri görüntüleme**
   - **Email \> Kötü Amaçlı Yazılıma göre verileri görüntüleme**
   - **Email İstenmeyen \> Postaya göre verileri görüntüleme**

3. Filtre simgesine tıklayın ![.](../../media/m365-cc-sc-filter-icon.png) **Filtrele'ye bakın**.

4. Açılan **Filtreler** açılır öğesinde, **Öncelik hesapları** bölümünde **Evet**, **Hayır** veya her iki değeri de seçin.

   ![Tehdit koruması durum raporundaki öncelik hesabı koruma filtreleri.](../../media/priority-account-protection-tps-report.png)

### <a name="threat-explorer"></a>Tehdit Gezgini

Tehdit Gezgini'ndeki bağlam filtresi, iletinin algılanmasında öncelikli hesap korumasının söz konusu olduğu e-postaları aramaya yardımcı olur. Bu, güvenlik operasyonları ekiplerinin bu koruma tarafından sağlanan değeri görebilmesini sağlar. Belirli bir kullanıcı kümesine ait tüm iletileri bulmak için iletileri öncelik hesabı etiketine göre filtrelemeye devam edebilirsiniz.

Tehdit Gezgini'nde ek korumayı görüntülemek için aşağıdaki adımları uygulayın:

1. konumundaki Microsoft 365 Defender portalında <https://security.microsoft.com>**Email & işbirliği** \> **Gezgini'ne** gidin. **Doğrudan Tehdit Gezgini** sayfasına gitmek için kullanın<https://security.microsoft.com/threatexplorer>.

2. Açılan listeden **Bağlam'ı** seçin ve ardından **Öncelik hesabı koruması'nın** yanındaki onay kutusunu seçin.

> [!div class="mx-imgBorder"]
> ![Tehdit Gezgini'nin içindeki bağlam filtresi.](../../media/threat-explorer-context-filter.png)

### <a name="email-entity-page"></a>varlık sayfasını Email

E-posta varlığı sayfası **Tehdit Gezgini'nde** kullanılabilir. Araştırdığınız e-postanın konusunu seçin. Bu posta için e-posta açılır öğesinin üst kısmında altın renkli bir çubuk görüntülenir. Yeni sayfayı görüntülemek için öğesini seçin.

Varlık sayfasının üst kısmındaki sekmeler, e-postayı verimli bir şekilde araştırmanıza olanak sağlar. **Çözümleme** sekmesine tıklayın. Öncelik hesabı koruması artık **Tehdit algılama ayrıntıları altında listelenmiştir**.

## <a name="more-information"></a>Daha fazla bilgi

- [Office 365 için Microsoft Defender kullanıcı etiketleri](user-tags.md)
- [Öncelikli hesapları yönetme ve izleme](../../admin/setup/priority-accounts.md)
