---
title: Windows ve Office 365 dağıtım laboratuvarı seti
f1.keywords:
- NOCSH
ms.author: aaroncz
author: cdmm12
manager: dougeby
ms.reviewer: alainme
ms.date: 05/11/2022
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Windows ve Office Dağıtım Laboratuvar Seti'ne nereden erişeceğinizi öğrenin.
ms.openlocfilehash: 3457d949887877f6ba3e514d68ca145ef3d155b3
ms.sourcegitcommit: ecc04b5b8f84b34255a2d5e90b5ab596af0d16c7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/01/2022
ms.locfileid: "67497615"
---
# <a name="windows-and-office-365-deployment-lab-kit"></a>Windows ve Office 365 dağıtım laboratuvarı seti

Windows ve Office 365 dağıtım laboratuvar seti, Windows 10 Enterprise veya Windows 11 Enterprise çalıştıran masaüstlerinin dağıtımını ve yönetimini planlamanıza, test edip doğrulamanıza yardımcı olmak için tasarlanmıştır ve Kurumlar için Microsoft 365 Uygulamaları. Kitteki laboratuvarlar, Microsoft Endpoint Configuration Manager, OneDrive, Windows Autopilot ve daha fazlasını kullanarak ele alınıyor. Bu set, masaüstü yükseltmelerine hazırlanan kuruluşlar için kesinlikle önerilir. Yalıtılmış bir ortam olarak laboratuvar, dağıtım aracı güncelleştirmelerini keşfetmek ve dağıtımla ilgili otomasyonunuzu test etme için de idealdir.

Laboratuvarın iki sürümü ücretsiz olarak indirilebilir:  

|Windows 10 Laboratuvarı|Windows 11 Laboratuvarı|
|---|---|
|[Windows 10 laboratuvar ortamı](https://download.microsoft.com/download/8/5/e/85e007b0-1f3e-460c-bd0a-5a8c6ec490b5/Win10_21H2_lab.zip)|[Windows 11 laboratuvar ortamı](https://download.microsoft.com/download/5/0/b/50bbe36a-9291-4339-9dcc-2a444fcd1659/Microsoft365DeviceLabKit.zip)|
|[Windows 10 laboratuvar kılavuzları](https://download.microsoft.com/download/b/d/4/bd4f430b-8cd1-4a07-97b1-c32100fce7ae/Win_10_21H2_lab_guides.zip)|[Windows 11 laboratuvar kılavuzları](https://download.microsoft.com/download/5/0/b/50bbe36a-9291-4339-9dcc-2a444fcd1659/Win11_SetUp_Guide_08.05.zip)|

## <a name="a-complete-lab-environment"></a>Eksiksiz bir laboratuvar ortamı

Laboratuvar, etki alanına katılmış masaüstü istemcileri, etki alanı denetleyicisi, İnternet ağ geçidi ve tam olarak yapılandırılmış bir Configuration Manager örneği de dahil olmak üzere otomatik olarak sağlanan bir sanal laboratuvar ortamı sağlar. Laboratuvarlar aşağıdaki ürünlerin değerlendirme sürümlerini içerir:

|Windows 10 Laboratuvarı|Windows 11 Laboratuvarı|
|---|---|
|Windows 10 Enterprise, Sürüm 21H2|Windows 11 Enterprise|
|Microsoft Uç Nokta Yapılandırma Yöneticisi, Sürüm 2103|Microsoft Endpoint Configuration Manager, Sürüm 2203|
|Windows 10 için Windows Değerlendirme ve Dağıtım Seti|Windows 11 için Windows Değerlendirme ve Dağıtım Seti|
|Windows Server 2019|Windows Server 2022|

Laboratuvarlar ayrıca aşağıdakiler için denemelere bağlanacak şekilde tasarlanmıştır:

- Microsoft 365 E5
- Microsoft 365 Kurumsal Uygulamaları
- Enterprise Mobility + Security (EMS) ile Office 365 E5

## <a name="step-by-step-labs"></a>Adım adım laboratuvarlar

Ayrıntılı laboratuvar kılavuzları, birden çok dağıtım ve yönetim senaryosunda size yol gösterir. Laboratuvarlar, Intune ve Configuration Manager en son sürümleri için güncelleştirildi. Not: Laboratuvarın yeni Windows 11 sürümü kullanıma sunuldu. Laboratuvar kılavuzları aşağıdaki senaryoları içerir:

### <a name="plan-and-prepare-infrastructure"></a>Altyapıyı planlama ve hazırlama

- Bulut Yönetimi Ağ Geçidi
- Kiracı ekleme ve ortak yönetim
- Uç nokta analizi
- Güncelleştirme teslimi iyileştirme

### <a name="deploy-windows"></a>Windows'ı dağıtma

- Configuration Manager işletim sistemi dağıtımı görev dizileri
- Windows Autopilot

### <a name="service-windows"></a>Hizmet Pencereleri

- grup ilkesi kullanarak Windows'a hizmet verme
- Microsoft Intune kullanarak Windows'a hizmet verme
- Configuration Manager ile Windows'a hizmet verme

### <a name="deploy-microsoft-365-apps-for-enterprise"></a>Kurumlar için Microsoft 365 Uygulamaları dağıtma

- Bulut tarafından yönetilen dağıtım
- Yerel olarak yönetilen dağıtım
- AD'ye Katılmamış Cihazlarda dağıtım Kurumlar için Microsoft 365 Uygulamaları
- Configuration Manager kullanarak kurumsal yönetilen dağıtım
- Microsoft Intune kullanarak kurumsal yönetilen dağıtım
- Configuration Manager kullanarak hizmet Kurumlar için Microsoft 365 Uygulamaları
- Intune kullanarak hizmet Kurumlar için Microsoft 365 Uygulamaları
- Microsoft Intune ile LOB Dağıtımı ve Yönetimi
- Microsoft Teams'i dağıtma
- Atama filtreleri

### <a name="managing-microsoft-edge"></a>Microsoft Edge'i yönetme

- Edge'i Dağıtma ve Güncelleştirme
- IE Modu
- Kurumsal Yeni Sekme Sayfasını Ayarlama

### <a name="security-and-compliance"></a>Güvenlik ve Uyumluluk

- Bitlocker
- Microsoft Defender Virüsten Koruma
- İş İçin Windows Hello
- Windows Defender Credential Guard       
- Microsoft Defender Application Guard     
- Windows Defender Exploit Guard             
- Uygulama Denetimini Windows Defender   
- Uç Nokta için Microsoft Defender 


> [!NOTE]
> Lütfen bu içeriği indirmek için geniş bant İnternet bağlantısı kullanın ve otomatik sağlama için yaklaşık 30 dakika bekleyin. Laboratuvar ortamı için en az 16 GB kullanılabilir bellek ve 150 GB boş disk alanı gerekir. En iyi performans için 32 GB kullanılabilir bellek ve 300 GB boş alan önerilir. Windows istemci sanal makinelerinin süresi laboratuvarın etkinleştirilmesinin ardından 90 gün sonra dolar. Laboratuvarların yeni sürümleri 5 Kasım 2022 tarihinde veya öncesinde yayımlanacaktır. 

## <a name="additional-guidance"></a>Ek yönergeler

- [Windows istemci dağıtım kaynakları ve belgeleri](/windows/deployment)
- [Microsoft Mechanics'ten Masaüstü Dağıtım serisi videoları](https://www.aka.ms/watchhowtoshift)
- [Microsoft Endpoint Configuration Manager İşletim Sistemi Dağıtımı](/mem/configmgr/osd/understand/introduction-to-operating-system-deployment)
- [Microsoft 365 Uygulamaları için dağıtım rehberi](/deployoffice/deployment-guide-microsoft-365-apps)
- [Intune Kullanmaya Başlama](/intune/get-started-evaluation)

## <a name="related-resources"></a>İlgili kaynaklar

- [Microsoft 365 ile tanışın](https://www.microsoft.com/microsoft-365/default.aspx)
- [İş için Microsoft 365](https://products.office.com/business/office)
- [Enterprise Mobility + Security tanıtımı](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
- [İş için Windows](https://www.microsoft.com/windows/business)
