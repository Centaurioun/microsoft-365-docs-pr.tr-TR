---
title: PowerShell ile Microsoft 365’e bağlanma
ms.author: kvice
author: kelleyvice-msft
manager: scotv
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: high
ms.collection:
- scotvorg
- Ent_O365
f1.keywords:
- CSH
ms.custom:
- LIL_Placement
- O365ITProTrain
- Ent_Office_Other
ms.assetid: 5ebc0e21-b72d-46d8-96fa-00643b18eaec
description: Komut satırından yönetim merkezi görevlerini gerçekleştirmek için Microsoft 365 için PowerShell'i kullanarak Microsoft 365 kiracınıza bağlanın.
ms.openlocfilehash: 0192ed18c1c99cd08008570ce4b97a558621761f
ms.sourcegitcommit: edc9d4dec92ca81cff39bbf9590f1cd3a75ec436
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/06/2022
ms.locfileid: "68484357"
---
# <a name="connect-to-microsoft-365-with-powershell"></a>PowerShell ile Microsoft 365’e bağlanma

*Bu makale hem Microsoft 365 Kurumsal hem de Office 365 Kurumsal için geçerlidir.*

Microsoft 365 için PowerShell, Microsoft 365 ayarlarınızı komut satırından yönetmenizi sağlar. PowerShell'e bağlanmak için gerekli yazılımı yüklemeniz ve ardından Microsoft 365 kuruluşunuza bağlanmanız gerekir.

PowerShell modülünün Microsoft 365'e bağlanmak ve kullanıcı hesaplarını, gruplarını ve lisanslarını yönetmek için kullanabileceğiniz iki sürümü vardır:

- Cmdlet'leri adında *AzureAD* bulunan Graph için Azure Active Directory PowerShell
- cmdlet'leri adında *Msol* bulunan Windows PowerShell için Microsoft Azure Active Directory Modülü

Şu anda Graph için Azure Active Directory PowerShell modülü, kullanıcı, grup ve lisans yönetimi için Windows PowerShell modülü için Microsoft Azure Active Directory Modülü'nin işlevselliğini tamamen değiştirmez. Bazı durumlarda, her iki sürümü de kullanmanız gerekir. Her iki sürümü de aynı bilgisayara güvenle yükleyebilirsiniz.

>[!Note]
>Ayrıca [azure Cloud Shell](#connect-with-the-azure-cloud-shell) Microsoft 365 yönetim merkezi de bağlanabilirsiniz.
>


## <a name="what-do-you-need-to-know-before-you-begin"></a>Başlamadan önce bilmeniz gerekenler

>[!NOTE]
> Azure Active Directory Modülü, Microsoft Graph PowerShell SDK'sı ile değiştiriliyor. Tüm Microsoft Graph API'lerine erişmek için Microsoft Graph PowerShell SDK'sını kullanabilirsiniz. Daha fazla bilgi için bkz. [Microsoft Graph PowerShell SDK'sını kullanmaya başlama](/powershell/microsoftgraph/get-started).

**İşletim sistemi**

Windows'un 64 bit sürümünü kullanmanız gerekir. Windows PowerShell için Microsoft Azure Active Directory Modülünün 32 bit sürümü desteği 2014'te sona erdi.

Aşağıdaki Windows sürümlerini kullanabilirsiniz:
    
  - Windows 10, Windows 8.1, Windows 8 veya Windows 7 Service Pack 1 (SP1) 
    
  - Windows Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012 veya Windows Server 2008 R2 SP1

>[!Note]
>Windows 8.1, Windows 8, Windows 7 Service Pack 1 (SP1), Windows Server 2012 R2, Windows Server 2012 ve Windows Server 2008 R2 SP1 için [Windows Management Framework 5.1'i](https://www.microsoft.com/download/details.aspx?id=54616) indirip yükleyin.

**PowerShell**

- Graph için Azure Active Directory PowerShell modülü için PowerShell sürüm 5.1'i kullanmanız gerekir.

- Windows PowerShell modülü için Microsoft Azure Active Directory Modülü için PowerShell sürüm 6'ya kadar PowerShell sürüm 5.1 veya üzerini kullanmanız gerekir. PowerShell sürüm 7'i kullanamazsınız.
       
>[!Note]
>Bu yordamlar, Microsoft 365 yönetici rolünün üyesi olan kullanıcılara yöneliktir. Daha fazla bilgi için bkz. [Yönetici rolleri hakkında](../admin/add-users/about-admin-roles.md).


## <a name="connect-with-the-azure-active-directory-powershell-for-graph-module"></a>Graph için Azure Active Directory PowerShell modülüyle bağlanma

Graph için Azure Active Directory PowerShell modülündeki komutların cmdlet'i adında *AzureAD* bulunur. [Graph için Azure Active Directory PowerShell](/powershell/azure/active-directory/install-adv2) modülünü veya [Azure PowerShell](/powershell/azure/install-az-ps) yükleyebilirsiniz.

Graph için Azure Active Directory PowerShell modülündeki yeni cmdlet'leri gerektiren yordamlar için bu adımları izleyerek modülü yükleyin ve Microsoft 365 aboneliğinize bağlanın.

> [!Note]
> Windows'un farklı sürümleri için destek hakkında bilgi için bkz. [Graph için Azure Active Directory PowerShell modülü](/powershell/azure/active-directory/install-adv2) .

### <a name="step-1-install-the-required-software"></a>1. Adım: Gerekli yazılımı yükleme

Bu adımlar bilgisayarınızda yalnızca bir kez gereklidir. Ancak büyük olasılıkla yazılımı düzenli aralıklarla güncelleştirmeniz gerekir.
  
1. bir Windows PowerShell Komut İstemi penceresi açın.
    
2. Bu komutu çalıştırın:
    
    ```powershell
    Install-Module -Name AzureAD
    ```

  Varsayılan olarak, PowerShell Galerisi (PSGallery) **PowerShellGet** için güvenilir bir depo olarak yapılandırılmaz. PSGallery'yi ilk kez kullandığınızda aşağıdaki iletiyi görürsünüz:

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

Yüklemeye devam etmek için **Evet** veya **Tümüne Evet** yanıtını verin.

3.  Modülü içeri aktarmak için şu komutu çalıştırın:
    
    ```powershell
    Import-Module  AzureAD
    ```
    
### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a>2. Adım: Microsoft 365 aboneliğiniz için Azure AD bağlanma

Microsoft 365 aboneliğinizin Azure Active Directory'ye (Azure AD) hesap adı ve parolayla veya çok faktörlü kimlik doğrulamasıyla bağlanmak için, Windows PowerShell komut isteminden bu komutlardan birini çalıştırın. (Yükseltilmesi gerekmez.)

| Office 365 bulut | Komut |
|:-------|:-----|
| Office 365 Worldwide (+GCC) | `Connect-AzureAD` |
| 21 Vianet tarafından sağlanan Office 365 | `Connect-AzureAD -AzureEnvironmentName AzureChinaCloud` |
| Office 365 Almanya | `Connect-AzureAD -AzureEnvironmentName AzureGermanyCloud` |
| Office 365 ABD Kamu DoD ve Office 365 ABD Kamu GCC High | `Connect-AzureAD -AzureEnvironmentName AzureUSGovernment` |
|||

**Hesabınızda oturum açın** iletişim kutusunda, Microsoft 365 iş veya okul hesabı kullanıcı adınızı ve parolanızı yazın ve **tamam'ı** seçin.

Çok faktörlü kimlik doğrulaması kullanıyorsanız doğrulama kodu gibi ek kimlik doğrulama bilgileri sağlamak için yönergeleri izleyin.

Bağlandıktan sonra [Graph için Azure Active Directory PowerShell modülü](/powershell/module/azuread) cmdlet'lerini kullanabilirsiniz.

## <a name="connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Windows PowerShell için Microsoft Azure Active Directory Modülü ile bağlanma

>[!Note]
>Windows PowerShell için Microsoft Azure Active Directory Modülü'ndeki cmdlet'lerin adında *Msol* bulunur.

PowerShell sürüm 7 ve üzeri, Windows PowerShell modülü için Microsoft Azure Active Directory Modülünü ve adında *Msol* bulunan cmdlet'leri desteklemez. PowerShell sürüm 7 ve üzeri için Microsoft Graph PowerShell SDK'sını kullanmanız gerekir.

PowerShell Core, Windows PowerShell modülü için Microsoft Azure Active Directory Modülünü ve adında *Msol* bulunan cmdlet'leri desteklemez. Bu cmdlet'leri Windows PowerShell çalıştırın.
    
### <a name="step-1-install-the-required-software"></a>1. Adım: Gerekli yazılımı yükleme

Bu adımlar bilgisayarınızda yalnızca bir kez gereklidir. Ancak büyük olasılıkla yazılımı düzenli aralıklarla güncelleştirmeniz gerekir.
  
1.  Windows 10 çalıştırmıyorsanız, Microsoft Online Services Oturum Açma Yardımcısı: [BT Uzmanları için Microsoft Online Services Oturum Açma Yardımcısı RTW'nin](https://download.microsoft.com/download/7/1/E/71EF1D05-A42C-4A1F-8162-96494B5E615C/msoidcli_32bit.msi) 32 bit sürümünü yükleyin.
    
2. Windows PowerShell için Microsoft Azure Active Directory Modülünü yüklemek için şu adımları izleyin:
    
   1. Yükseltilmiş bir Windows PowerShell komut istemi açın (yönetici olarak Windows PowerShell çalıştırın).
   1.  **Install-Module MSOnline** komutunu çalıştırın.
   1. NuGet sağlayıcısını yüklemeniz istenirse **Y** yazın ve Enter tuşuna basın.
   1. Modülü PSGallery'den yüklemeniz istenirse **Y** yazın ve Enter tuşuna basın.
    
### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a>2. Adım: Microsoft 365 aboneliğiniz için Azure AD bağlanma

Microsoft 365 aboneliğinizin Azure AD bir hesap adı ve parolayla veya çok faktörlü kimlik doğrulamasıyla bağlanmak için, Windows PowerShell komut isteminden bu komutlardan birini çalıştırın. (Yükseltilmesi gerekmez.)

| Office 365 bulut | Komut |
|:-------|:-----|
| Office 365 Worldwide (+GCC) | `Connect-MsolService` |
| 21 Vianet tarafından sağlanan Office 365 | `Connect-MsolService -AzureEnvironment AzureChinaCloud` |
| Office 365 Almanya | `Connect-MsolService -AzureEnvironment AzureGermanyCloud` |
| Office 365 ABD Kamu DoD ve Office 365 ABD Kamu GCC High | `Connect-MsolService -AzureEnvironment USGovernment` |
|||

**Hesabınızda oturum açın** iletişim kutusunda, Microsoft 365 iş veya okul hesabı kullanıcı adınızı ve parolanızı yazın ve **tamam'ı** seçin.

Çok faktörlü kimlik doğrulaması kullanıyorsanız doğrulama kodu gibi ek kimlik doğrulama bilgileri sağlamak için yönergeleri izleyin.

### <a name="how-do-you-know-it-worked"></a>İşe yaramış olduğunu nereden biliyorsun?

Hata iletisi alamazsanız başarıyla bağlandınız. Hızlı test için  **Get-MsolUser** gibi bir Microsoft 365 cmdlet'ini çalıştırın ve sonuçlara bakın.
  
Hata iletisi alırsanız aşağıdaki sorunları denetleyin:
  
- **Sık karşılaşılan bir sorun yanlış paroladır**. [2. Adımı](#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) yeniden çalıştırın ve girdiğiniz kullanıcı adına ve parolaya çok dikkat edin.
    
- **Windows PowerShell için Microsoft Azure Active Directory Modülü, Microsoft'un 3.5 .NET Framework gerektirir.* x* bilgisayarınızda etkin**. Bilgisayarınızda daha yeni bir sürüm yüklü olabilir (örneğin, 4 veya 4.5).* x*). Ancak .NET Framework eski sürümleriyle geriye dönük uyumluluk etkinleştirilebilir veya devre dışı bırakılabilir. Daha fazla bilgi için aşağıdaki makalelere bakın:
    
  - Windows Server 2012 veya Windows Server 2012 R2 için bkz. [Rol ve Özellik Ekleme Sihirbazı'nı kullanarak .NET Framework 3.5'i etkinleştirme](/previous-versions/windows/it-pro/windows-8.1-and-8/dn482071(v=win.10)).
    
  - Windows 7 veya Windows Server 2008 R2 için bkz. [Windows PowerShell için Azure Active Directory Modülünü açamazsınız](/troubleshoot/azure/active-directory/cant-open-aad-module-powershell).

  - Windows 10, Windows 8.1 ve Windows 8 için bkz. [.NET Framework 3.5'i Windows 10, Windows 8.1 ve Windows 8 yükleme](/dotnet/framework/install/dotnet-35-windows-10).

  
- **Windows PowerShell için Microsoft Azure Active Directory Modülü sürümünüz güncel olmayabilir.** Denetlemek için, Microsoft 365 için PowerShell'de veya Windows PowerShell için Microsoft Azure Active Directory Modülü'nde aşağıdaki komutu çalıştırın:
    
  ```powershell
  (Get-Item C:\Windows\System32\WindowsPowerShell\v1.0\Modules\MSOnline\Microsoft.Online.Administration.Automation.PSModule.dll).VersionInfo.FileVersion
  ```

    Döndürülen sürüm numarası *1.0.8070.2'den* düşükse, Windows PowerShell için Microsoft Azure Active Directory Modülünü kaldırın ve yukarıdaki [1. Adım'dan](#step-1-install-the-required-software) yükleyin.

- **Bağlantı hata iletisi alırsanız**, ["Connect-MsolService: Tür özel durumu oluşturuldu" hatasına](/office365/troubleshoot/active-directory/connect-msoservice-throw-exception) bakın.
    
- **"Get-Item: Path bulunamıyor" hata iletisini alırsanız** şu komutu çalıştırın:


   ```powershell
     (dir "C:\Program Files\WindowsPowerShell\Modules\MSOnline").Name
   ```

## <a name="connect-with-the-azure-cloud-shell"></a>Azure Cloud Shell ile bağlanma

Microsoft 365 yönetim merkezi azure Cloud Shell ile bağlantı kurmak ve kullanmak için görev çubuğunun sağ üst köşesindeki PowerShell penceresi simgesini seçin. **Azure'a Hoş Geldiniz Cloud Shell** bölmesinde **PowerShell'i** seçin.

Kuruluşunuz için Microsoft 365 aboneliğinize bağlı etkin bir Azure aboneliğine ihtiyacınız olacaktır. Henüz bir hesabınız yoksa oluşturabilirsiniz. Azure aboneliğiniz olduktan sonra, PowerShell komutlarını ve betiklerini çalıştırabileceğiniz bir PowerShell penceresi açılır.

Daha fazla bilgi için bkz. [Azure Cloud Shell](/azure/cloud-shell/overview).



## <a name="see-also"></a>Ayrıca bkz.

- [PowerShell ile Microsoft 365’i yönetme](manage-microsoft-365-with-microsoft-365-powershell.md)
- [Microsoft 365 için PowerShell'i kullanmaya başlama](getting-started-with-microsoft-365-powershell.md)
- [Tek bir Windows PowerShell penceresinde tüm Microsoft 365 hizmetlerine bağlanma](connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window.md)
