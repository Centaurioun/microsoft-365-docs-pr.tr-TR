---
title: Teams'i ön cephe çalışanları için uygun ölçekte dağıtma
author: LanaChin
ms.author: v-lanachin
ms.reviewer: rahuldey
manager: samanro
ms.topic: how-to
audience: admin
ms.service: microsoft-365-frontline
search.appverid: MET150
description: Teams'i kuruluşunuzdaki ön cephe çalışanları için uygun ölçekte dağıtmayı öğrenin.
ms.localizationpriority: high
ms.collection:
- M365-collaboration
- m365-frontline
- highpri
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
ms.openlocfilehash: 9c28df7d017c09f015aa650cb4592976bf5a3f4f
ms.sourcegitcommit: 0ad7edcfdcdd11d02fa8a14ffe4b36e120d92deb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2022
ms.locfileid: "68785869"
---
# <a name="deploy-teams-at-scale-for-frontline-workers"></a>Teams'i ön cephe çalışanları için uygun ölçekte dağıtma

## <a name="overview"></a>Genel bakış

Kuruluşunuz, ön cephe iş gücünüz arasında iletişim ve işbirliği sağlamak için çok sayıda ekip kullanıyor mu? Bu makale, uygun ölçekte ekipler oluşturmanız ve yönetmeniz gerekiyorsa size yöneliktir.

PowerShell'i kullanarak aynı anda en fazla 500 ekip dağıtabilir ve ekip başına en fazla 25 kullanıcı ekleyebilirsiniz. Ayrıca, uygun ölçekte mevcut ekiplere kullanıcı ekleyebilir ve bu ekiplerden kullanıcıları kaldırabilirsiniz. Kuruluşunuzun ölçek gereksinimlerini karşılamak ve dağıtım süresini önemli ölçüde azaltmak için bu çözümü kullanın.

Teams'i uygun ölçekte dağıtmak şunları yapabilirsiniz:

- Önceden oluşturulmuş şablonları veya kendi özel şablonlarınızı kullanarak ekipler oluşturun.
- Kullanıcıları ekiplere sahip veya üye olarak ekleyin.
- Kullanıcıları mevcut ekiplere ekleyerek veya mevcut ekiplerden kaldırarak ekipleri uygun ölçekte yönetin.
- Tamamlama, durum ve hatalar (varsa) dahil olmak üzere e-posta yoluyla bildirim alın. Dağıttığınız her ekip grubunun durumu hakkında en fazla beş kişiyi bilgilendirmeyi seçebilirsiniz. Ekip sahiplerine ve üyelerine ekiliğe eklendiklerinde otomatik olarak bildirim gönderilir.

Bu makale, Teams'i uygun ölçekte dağıtma konusunda size yol gösterir.

:::image type="content" source="media/deploy-teams-at-scale.png" alt-text="Teams'i uygun ölçekte dağıtma adımlarına genel bakış.":::

## <a name="set-up-and-deploy-your-teams"></a>Ekiplerinizi ayarlama ve dağıtma

> [!IMPORTANT]
> Ekip sahiplerinin Teams lisansı olmalıdır. Ekiplerinizi dağıtmak için bu adımları kullanmadan önce tüm ekip sahiplerinin bir lisansı olduğundan emin olun.

Aynı anda en fazla 500 ekip dağıtmak için bu adımları izleyin.

### <a name="step-1-prepare-your-csv-files"></a>1. Adım: CSV dosyalarınızı hazırlama

Dağıttığınız her ekip grubu için iki CSV dosyası oluşturmanız gerekir:

- **Oluşturduğunuz ekipleri tanımlayan bir CSV dosyası**. Bu dosya, ilk sütundan başlayarak bu gerekli sütunları aşağıdaki sırayla içermelidir:

    |Sütun adı  |Açıklama  |
    |---------|---------|
    |**Ekip Adı**|Takımın adı.|
    |**Mevcut Ekip Kimliği**|Mevcut bir ekipte kullanıcı ekliyor veya kaldırıyorsanız, ekibin ekip kimliğini belirtin.|
    |**Görünür -lük**|Ekibin genel (kuruluşunuzdaki herkes katılabilir) veya özel (kullanıcıların katılmak için ekip sahiplerinden onay istemesi gerekir) olup olmadığı. Seçenekler **Genel** ve **Özel'dir**.|
    |**Ekip Şablonu Kimliği**|Önceden oluşturulmuş veya özel bir şablondan ekip oluşturuyorsanız ekip şablonu kimliğini belirtin. Önceden oluşturulmuş [ekip şablonlarını ve kimliklerini listelemek için Teams yönetim merkezinde](/microsoftteams/get-started-with-teams-templates-in-the-admin-console) ekip şablonlarını kullanmaya başlama bölümüne bakın. Standart varsayılan ekip şablonunu kullanmak istiyorsanız, bunu boş bırakın.|

- **Eklediğiniz kullanıcıları her takıma eşleyen bir CSV dosyası**. Bu dosya, ilk sütundan başlayarak bu gerekli sütunları aşağıdaki sırayla içermelidir:

    |Sütun adı  |Açıklama  |
    |---------|---------|
    |**Kullanıcı Tam Adı**|Kullanıcının görünen adı.|
    |**Kullanıcı UPN'si veya kimliği**|Kullanıcının asıl adı (UPN) veya kimliği. Örneğin, averyh@contoso.com.|
    |**Ekip Adı**|Takımın adı.|
    |**ActionType**|Kullanıcıyı takıma ekleyip eklemediğiniz veya ekipten kaldırdığınız. **Seçenekler AddMember** ve **RemoveMember'dır**.|
    |**Sahip veya Üye**|Kullanıcının ekip sahibi veya ekip üyesi olup olmadığı. Seçenekler **Sahip** ve **Üye'dir**.|

#### <a name="examples"></a>Örnekler

CSV dosyalarınızı oluşturmanıza yardımcı olması için aşağıdaki örnekleri kullanın. Burada dosyaları Teams.csv ve Users.csv olarak adlandırdık.

**Teams.csv**

|Ekip Adı|Mevcut Ekip Kimliği|Görünür -lük|Ekip Şablonu Kimliği|
|---------|---------|---------|---------|
|Contoso Store 1||Kamu|com.microsoft.teams.template.retailStore|
|Contoso Store 2||Kamu|com.microsoft.teams.template.retailStore|
|Contoso Store 3||Kamu|com.microsoft.teams.template.retailStore|
|Contoso Store 4||Kamu|com.microsoft.teams.template.retailStore|
|Contoso Store 5||Kamu|com.microsoft.teams.template.ManageAProject|
|Contoso Store 6||Kamu|com.microsoft.teams.template.ManageAProject|
|Contoso Store 7||Kamu||
|Contoso Store 8||Özel|com.microsoft.teams.template.OnboardEmployees|
|Contoso Store 9||Özel|com.microsoft.teams.template.OnboardEmployees|
|Contoso Store 10||Özel|com.microsoft.teams.template.OnboardEmployees|

**Users.csv**

|Kullanıcı Tam Adı |Kullanıcı UPN'si veya kimliği|Ekip Adı|ActionType|Sahip veya Üye|
|---------|---------|---------|---------|---------|
|Avery Howard|averyh@contoso.com|Contoso Store 1|AddMember|Sahibi|
|Casey Jensen|caseyj@contoso.com|Contoso Store 2|AddMember|Sahibi|
|Jessie Irwin|jessiei@contoso.com|Contoso Store 3|AddMember|Sahibi|
|Manjeet Bhatia|manjeetb@contoso.com|Contoso Store 4|AddMember|Sahibi|
|Mikaela Lee|mikaelal@contoso.com|Contoso Store 5|AddMember|Sahibi|
|Morgan Conners|morganc@contoso.com|Contoso Store 6|AddMember|Üye|
|Oscar Ward|oscarw@contoso.com|Contoso Store 7|AddMember|Üye|
|Rene Pelletier|renep@contoso.com|Contoso Store 8|AddMember|Üye|
|Sydney Mattos|sydneym@contoso.com|Contoso Store 9|AddMember|Üye|
|Violet Martinez|violetm@contoso.com|Contoso Store 10|AddMember|Üye|

### <a name="step-2-set-up-your-environment"></a>2. Adım: Ortamınızı ayarlama

Teams PowerShell modülünün en son sürümünü yüklemek ve bu sürüme bağlanmak için bu adımları izleyin.

1. PowerShell sürüm 7 veya üzerini yükleyin. Adım adım yönergeler için bkz [. PowerShell'i Windows'a yükleme](/powershell/scripting/install/installing-powershell-on-windows).
1. PowerShell'i yönetici modunda çalıştırın.
1. Daha önce yüklenmiş teams PowerShell modüllerini kaldırmak için aşağıdakileri çalıştırın.

    ```powershell
    Uninstall-module -Name MicrosoftTeams -Force -Allversions
    ```

    Hata iletisi alırsanız, zaten hazırsınız demektir. Sonraki adıma geçin.
1. [Teams PowerShell modülünün en son sürümünü](https://www.powershellgallery.com/packages/MicrosoftTeams) indirin ve yükleyin. Sürüm 4.7.0 (önizleme) veya sonraki bir sürümü çalıştırıyor olmanız gerekir.  

1. Teams'e bağlanmak için aşağıdakileri çalıştırın.

    ```powershell
    Connect-MicrosoftTeams
    ```

    İstendiğinde yönetici kimlik bilgilerinizi kullanarak oturum açın.

1. Teams PowerShell modülündeki komutların listesini almak için aşağıdakileri çalıştırın.

    ```powershell
    Get-Command -Module MicrosoftTeams
    ```

    ve ```Get-CsBatchTeamsDeploymentStatus``` öğesinin listelendiğini ```New-CsBatchTeamsDeployment``` doğrulayın.

### <a name="step-3-deploy-your-teams"></a>3. Adım: Ekiplerinizi dağıtma

CSV dosyalarınızı oluşturduğunuza ve ortamınızı ayarladığınıza göre, ekiplerinizi dağıtmaya hazırsınız demektir.

Oluşturulacak bir ekip grubu göndermek için [New-CsBatchTeamsDeployment](/powershell/module/teams/New-CsBatchTeamsDeployment) cmdlet'ini kullanırsınız. Her toplu iş için bir düzenleme kimliği oluşturulur. Ardından [get-CsBatchTeamsDeploymentStatus](/powershell/module/teams/Get-CsBatchTeamsDeploymentstatus) cmdlet'ini kullanarak her bir toplu iş için ilerleme durumunu izleyebilirsiniz.

1. Bir ekip grubu dağıtmak için aşağıdakileri çalıştırın. Bu komutta, bu dağıtım hakkında bildirimde bulunabilmek için CSV dosyalarınızın yolunu ve en fazla beş alıcının e-posta adreslerini belirtirsiniz.

    ```powershell
    New-CsBatchTeamsDeployment -TeamsFilePath "Your CSV file path" -UsersFilePath "Your CSV file path" -UsersToNotify "Email addresses" 
    ```

    Alıcılar dağıtım durumu hakkında e-posta bildirimleri alır. E-posta, gönderdiğiniz toplu işlemin düzenleme kimliğini ve oluşmuş olabilecek hataları içerir.

    Örneğin:

    ```powershell
    New-CsBatchTeamsDeployment -TeamsFilePath "C:\dscale\Teams.csv" -UsersFilePath "C:\dscale\Users.csv" -UsersToNotify "adminteams@contoso.com,adelev@contoso.com"
    ```

1. Gönderdiğiniz toplu iş durumunu denetlemek için aşağıdakileri çalıştırın.

    ```powershell
    Get-CsBatchTeamsDeploymentStatus -OrchestrationId "OrchestrationId"
    ```

## <a name="related-articles"></a>İlgili makaleler

- [New-CsBatchTeamsDeployment](/powershell/module/teams/New-CsBatchTeamsDeployment)
- [Get-CsBatchTeamsDeploymentStatus](/powershell/module/teams/Get-CsBatchTeamsDeploymentstatus)
- [Teams PowerShell'e Genel Bakış](/microsoftteams/teams-powershell-overview)
- [Ön cephe dağıtımıyla nereden başlayacağını öğrenin](flw-deploy-overview.md)
