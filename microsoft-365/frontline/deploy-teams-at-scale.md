---
title: Microsoft Teams'de ön cephe çalışanları için uygun ölçekte ekip dağıtma
author: LanaChin
ms.author: v-lanachin
ms.reviewer: rahuldey
manager: samanro
ms.topic: article
audience: admin
ms.service: microsoft-365-frontline
search.appverid: MET150
description: Kuruluşunuzdaki ön cephe çalışanları için uygun ölçekte ekip dağıtmayı öğrenin.
ms.localizationpriority: high
ms.collection:
- M365-collaboration
- m365-frontline
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
ms.openlocfilehash: 9a06b695d6e9cffe03ed2a42590c1489f3678056
ms.sourcegitcommit: 6f565d9e0f91ebc76fd13d7005619531391ab5f9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2022
ms.locfileid: "67439596"
---
# <a name="deploy-teams-at-scale-for-frontline-workers-in-microsoft-teams"></a>Microsoft Teams'de ön cephe çalışanları için uygun ölçekte ekip dağıtma

> [!NOTE]
> Bu özellik şu anda genel önizleme aşamasındadır. Katılmak isterseniz [dscale@microsoft.com](mailto:dscale@microsoft.com) bize ulaşın.

## <a name="overview"></a>Genel bakış
 
Kuruluşunuzda, farklı mağazalara, konumlara ve rollere yayılmış ön cephe iş gücünüz arasında iletişim ve işbirliği sağlamak için kullandığınız birçok ekip olabilir. Şu anda bu ekipleri ve kullanıcıları büyük ölçekte dağıtmak, ayarlamak ve yönetmek için kolay bir çözüm yoktur.

Yöneticilerin büyük ölçekte ekip dağıtıp yönetmesini sağlamak için bir çözüm oluşturuyoruz.

Burada, bir kerede çok sayıda ekip oluşturup yönetmeye yönelik özelliklere ve yakın gelecekte neleri planladığımıza ilişkin genel bir bakış bulabilirsiniz.

||Bugün kullanılabilir |2022'nin ilerleyen bölümlerinde  |
|---------|---------|---------|
|**Toplu iş başına oluşturabileceğiniz ekip sayısı**|En fazla 100 |En fazla 500|
|**Ekip başına ekleyebileceğiniz kullanıcı sayısı**|En fazla 25|En fazla 25|

Ekipleri büyük ölçekte dağıtmak şunları yapmanızı sağlar:

- Önceden oluşturulmuş şablonları veya kendi özel şablonlarınızı kullanarak ekipler oluşturun.
- Kullanıcıları ekiplere sahip veya üye olarak ekleyin.
- Kullanıcıları mevcut ekiplere ekleyerek veya mevcut ekiplerden kaldırarak ekipleri uygun ölçekte yönetin.
- Tamamlama, durum ve hatalar (varsa) dahil olmak üzere e-posta yoluyla bildirim alın. Dağıttığınız her ekip grubunun durumu hakkında en fazla beş kişiyi bilgilendirmeyi seçebilirsiniz. Ekip sahiplerine ve üyelerine ekiliğe eklendiklerinde otomatik olarak bildirim gönderilir.

## <a name="how-to-deploy-teams-at-scale"></a>Ekipleri uygun ölçekte dağıtma

> [!NOTE]
> Ekiplerinizi dağıtmadan önce tüm ekip sahiplerinin Teams lisansına sahip olduğundan emin olun.

Aynı anda çok sayıda ekip dağıtmak için bu adımları izleyin.

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

### <a name="step-2-deploy-your-teams"></a>2. Adım: Ekiplerinizi dağıtma

CSV dosyalarınızı oluşturduğunuza göre ortamınızı ayarlamaya ve ekiplerinizi dağıtmaya hazırsınız.

Oluşturmak üzere bir grup ekip göndermek için cmdlet'ini kullanırsınız ```New-CsBatchTeamsDeployment``` . Her toplu iş için bir düzenleme kimliği oluşturulur. Ardından cmdlet'ini ```Get-CsBatchTeamsDeployment``` kullanarak her bir toplu iş için ilerleme durumunu ve ilerleme durumunu izleyebilirsiniz.

1. PowerShell sürüm 7 veya üzerini yükleyin. Adım adım yönergeler için bkz [. PowerShell'i Windows'a yükleme](/powershell/scripting/install/installing-powershell-on-windows).
1. PowerShell'i yönetici modunda çalıştırın.
1. Daha önce yüklenmiş teams PowerShell modüllerini kaldırmak için aşağıdakileri çalıştırın.

    ```powershell
    Uninstall-module -Name MicrosoftTeams -Force -Allversions
    ```

    Hata iletisi alırsanız, zaten hazırsınız demektir. Sonraki adıma geçin.
1. [Teams PowerShell modülünün en son önizleme sürümünü](https://www.powershellgallery.com/packages/MicrosoftTeams) indirin ve yükleyin. Sürüm 4.3.1 (önizleme) veya sonraki bir önizleme sürümünü çalıştırıyor olmanız gerekir.  

1. Teams'e bağlanmak için aşağıdakileri çalıştırın.

    ```powershell
    Connect-MicrosoftTeams
    ```

    İstendiğinde yönetici kimlik bilgilerinizi kullanarak oturum açın.

1. Teams PowerShell modülündeki komutların listesini almak için aşağıdakileri çalıştırın.

    ```powershell
    Get-Command -Module MicrosoftTeams
    ```

    ve ```Get-CsBatchTeamsDeployment``` öğesinin listelendiğini ```New-CsBatchTeamsDeployment``` doğrulayın.

1. Bir ekip grubu dağıtmak için aşağıdakileri çalıştırın. Bu komutta, bu dağıtım hakkında bildirimde bulunabilmek için CSV dosyalarınızın yolunu ve en fazla beş alıcının e-posta adreslerini belirtirsiniz.

    ```powershell
    New-CsBatchTeamsDeployment -TeamsFilePath "Your CSV file path" -UsersFilePath "Your CSV file path" -UsersToNotify "Email addresses" 
    ```

    Örneğin:

    ```powershell
    New-CsBatchTeamsDeployment -TeamsFilePath "C:\dscale\Teams.csv" -UsersFilePath "C:\dscale\Users.csv" -UsersToNotify "adminteams@contoso.com,adelev@contoso.com"
    ```

    Alıcılar dağıtım durumu hakkında e-posta bildirimleri alır. E-posta, gönderdiğiniz toplu işlemin düzenleme kimliğini ve oluşmuş olabilecek hataları içerir.

1. Gönderdiğiniz toplu iş durumunu denetlemek için aşağıdakileri çalıştırın.

    ```powershell
    Get-CsBatchTeamsDeployment -OrchestrationId "OrchestrationId"
    ```

## <a name="send-us-feedback"></a>Görüşlerinizi bize gönderin

Görüşleriniz bizim için önemlidir. Kullanılabilirlik, güvenilirlik, performans&mdash;her şeyi memnuniyetle karşılıyoruz!

dscale@microsoft.com [Email](mailto:dscale@microsoft.com) ve varsa düzenleme kimliğinizi ve hata dosyanızı ekleyin.

## <a name="related-articles"></a>İlgili makaleler

- [Teams PowerShell'e Genel Bakış](/microsoftteams/teams-powershell-overview)
