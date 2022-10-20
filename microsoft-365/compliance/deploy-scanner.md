---
title: Microsoft Purview Bilgi Koruması tarayıcısı hakkında bilgi edinin
f1.keywords: ''
ms.author: libarson
author: libarson
manager: aashishr
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.localizationpriority: normal
ms.collection:
- purview-compliance
- tier3
description: Microsoft Purview Bilgi Koruması tarayıcının veri depolarında dosyaları nasıl bulabileceğini, sınıflandırabileceğini ve koruyabileceğini öğrenin.
ms.openlocfilehash: 624abb6e989612098c7ac47eb2ef15e48af1479b
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68647631"
---
# <a name="learn-about-the-information-protection-scanner"></a>Bilgi koruma tarayıcısı hakkında bilgi edinin

Microsoft Purview bilgi koruma tarayıcısı hakkında bilgi edinmek ve ardından başarıyla yükleme, yapılandırma, çalıştırma ve gerekirse sorun giderme hakkında bilgi edinmek için bu bölümdeki bilgileri kullanın.

Tarayıcı, Windows Server'da bir hizmet olarak çalışır ve aşağıdaki veri depolarında dosyaları bulmanıza, sınıflandırmanıza ve korumanıza olanak tanır:

- SMB veya NFS (Önizleme) protokollerini kullanan ağ paylaşımları için **UNC yolları**.

- SharePoint Server 2013 aracılığıyla SharePoint Server 2019 için SharePoint **belge kitaplıkları ve klasörü**.

Tarayıcı, dosyalarınızı sınıflandırmak ve korumak için Microsoft Purview uyumluluk portalı yapılandırılan [duyarlılık etiketlerini](sensitivity-labels.md) kullanır.

## <a name="overview-of-the-scanner"></a>Tarayıcıya genel bakış

Bilgi koruma tarayıcısı, Windows'un dizine ekleyebileceği tüm dosyaları inceleyebilir. Otomatik sınıflandırma uygulamak için duyarlılık etiketlerini yapılandırdıysanız, tarayıcı bulunan dosyaları bu sınıflandırmayı uygulamak için etiketleyebilir ve isteğe bağlı olarak koruma uygulayabilir veya kaldırabilir. 

Aşağıdaki görüntüde, tarayıcının şirket içi ve SharePoint sunucularınızdaki dosyaları keşfettiği tarayıcı mimarisi gösterilmektedir.

:::image type="content" source="../media/ul-scanner-arch.png" alt-text="Microsoft Purview Bilgi Koruması tarayıcı mimarisi":::

Dosyalarınızı incelemek için tarayıcı, bilgisayarda yüklü olan IFilters'ı kullanır. Dosyaların etiketlenmesi gerekip gerekmediğini belirlemek için tarayıcı hassas bilgi türlerini ve desen algılamayı veya regex desenlerini kullanır.

Tarayıcı, Azure Information Protection istemcisini kullanır ve istemciyle aynı dosya türlerini sınıflandırabilir ve koruyabilir. Daha fazla bilgi için bkz. [Azure Information Protection birleşik etiketleme istemcisi tarafından desteklenen dosya türleri](/azure/information-protection/rms-client/clientv2-admin-guide-file-types).

Taramalarınızı gerektiği gibi yapılandırmak için aşağıdakilerden birini yapın:

- **Tarayıcıyı bulma modunda çalıştırarak yalnızca** dosyalarınız etiketlendiğinde ne olduğunu kontrol eden raporlar oluşturun.
- **Hassas bilgilere sahip dosyaları otomatik** sınıflandırma uygulayan etiketler yapılandırmadan bulmak için tarayıcıyı çalıştırın.
- Etiketleri yapılandırıldığı gibi uygulamak için **tarayıcıyı otomatik olarak çalıştırın**. 
- Taranacak veya hariç tutulacak belirli dosyaları belirtmek için **bir dosya türleri listesi tanımlayın**.

> [!NOTE]
> Tarayıcı gerçek zamanlı olarak bulmaz ve etiketlemez. Belirttiğiniz veri depolarında dosyalarda sistematik olarak gezinilir. Bu döngüyü bir kez veya tekrar tekrar çalışacak şekilde yapılandırın.

> [!TIP]
> Tarayıcı, birden çok düğüme sahip tarayıcı kümelerini destekleyerek kuruluşunuzun ölçeği genişletmesini, daha hızlı tarama sürelerine ve daha geniş kapsamlı kapsama ulaşmasını sağlar. 
> 
> En baştan birden çok düğüm dağıtın veya tek düğümlü bir kümeyle başlayın ve daha sonra büyüdükçe ek düğümler ekleyin. **Install-AIPScanner** cmdlet'i için aynı küme adını ve veritabanını kullanarak birden çok düğüm dağıtın.
> 

## <a name="the-scanning-process"></a>Tarama işlemi

Dosyaları tararken, bilgi koruma tarayıcısı aşağıdaki adımları izler:

[1. Dosyaların tarama için dahil edilip edilmediğini veya dışlanıp dışlanmadığını belirleme](#1-determine-whether-files-are-included-or-excluded-for-scanning)

[2. Dosyaları inceleme ve etiketleme](#2-inspect-and-label-files)

[3. Denetlenemez dosyaları etiketle](#3-label-files-that-cant-be-inspected) 

Daha fazla bilgi için bkz. [Tarayıcı tarafından etiketlenmemiş dosyalar](#files-not-labeled-by-the-scanner).

### <a name="1-determine-whether-files-are-included-or-excluded-for-scanning"></a>1. Dosyaların tarama için dahil edilip edilmediğini veya dışlanıp dışlanmadığını belirleme 

Tarayıcı, yürütülebilir dosyalar ve sistem dosyaları gibi sınıflandırma ve korumanın dışında tutulan dosyaları otomatik olarak atlar. Daha fazla bilgi için bkz. [Sınıflandırma ve korumanın dışında tutulan dosya türleri](/azure/information-protection/rms-client/clientv2-admin-guide-file-types#file-types-excluded-from-classification-and-protection).

Tarayıcı ayrıca taramak veya taramanın dışında tutmak için açıkça tanımlanan tüm dosya listelerini de dikkate alır. Dosya listeleri varsayılan olarak tüm veri depoları için geçerlidir ve yalnızca belirli depolar için de tanımlanabilir.

Tarama veya dışlama için dosya listeleri tanımlamak için, içerik **tarama işinde Taramak için dosya türleri** ayarını kullanın. Örneğin:

![Purview uyumluluk portalında taramak için dosya türlerini yapılandırma](../media/scanner-file-types-purview.png)

Daha fazla bilgi için bkz. [Dosyaları otomatik olarak sınıflandırmak ve korumak için tarayıcıyı dağıtma](deploy-scanner-configure-install.md).

### <a name="2-inspect-and-label-files"></a>2. Dosyaları inceleme ve etiketleme

Dışlanan dosyaları tanımladıktan sonra, bilgi koruma tarayıcısı inceleme için desteklenen dosyaları tanımlamak için yeniden filtrelenir.

Bu filtreler, işletim sistemi tarafından Windows Search ve dizin oluşturma için kullanılan filtrelerle aynıdır ve ek yapılandırma gerektirmez. Windows IFilter, Word, Excel ve PowerPoint tarafından kullanılan dosya türlerini taramak ve PDF belgeleri ile metin dosyaları için de kullanılır.

İnceleme için desteklenen dosya türlerinin tam listesi ve filtreleri .zip ve .tiff dosyalarını içerecek şekilde yapılandırmaya yönelik diğer yönergeler için bkz. [İnceleme için desteklenen dosya türleri](/azure/information-protection/rms-client/clientv2-admin-guide-file-types#file-types-supported-for-inspection).

İncelemeden sonra, desteklenen dosya türleri etiketleriniz için belirtilen koşullar kullanılarak etiketlenir. Bulma modunu kullanıyorsanız, bu dosyalar etiketleriniz için belirtilen koşulları içerecek şekilde bildirilebilir veya bilinen hassas bilgi türlerini içerdiği bildirilebilir.

#### <a name="stopped-scanner-processes"></a>Durdurulan tarayıcı işlemleri

Tarayıcı durursa ve deponuzda çok sayıda dosya için taramayı tamamlamazsa, dosyaları barındıran işletim sistemi için dinamik bağlantı noktası sayısını artırmanız gerekebilir.

Örneğin, tarayıcının izin verilen ağ bağlantısı sayısını aşmasının ve dolayısıyla durmasının nedenlerinden biri SharePoint için sunucu sağlamlaştırmadır.

Tarayıcının durmasının nedeninin SharePoint için sunucu sağlamlaştırma olup olmadığını denetlemek için **, %localappdata%\Microsoft\MSIP\Logs\MSIPScanner.iplog** konumundaki tarayıcı günlüklerinde aşağıdaki hata iletisini denetleyin (birden çok günlük zip dosyasına sıkıştırılır):

`Unable to connect to the remote server ---> System.Net.Sockets.SocketException: Only one usage of each socket address (protocol/network address/port) is normally permitted IP:port`

Geçerli bağlantı noktası aralığını görüntüleme ve gerekirse artırma hakkında daha fazla bilgi için bkz. [Ağ performansını geliştirmek için değiştirilebilen ayarlar](/biztalk/technical-guides/settings-that-can-be-modified-to-improve-network-performance).

> [!TIP]
> Büyük SharePoint grupları için varsayılan değeri **5.000** olan liste görünümü eşiğini artırmanız gerekebilir.
>
> Daha fazla bilgi için bkz. [SharePoint'te büyük listeleri ve kitaplıkları yönetme](https://support.office.com/article/manage-large-lists-and-libraries-in-sharepoint-b8588dae-9387-48c2-9248-c24122f07c59#__bkmkchangelimit&ID0EAABAAA=Server).
>

### <a name="3-label-files-that-cant-be-inspected"></a>3. Denetlenemez dosyaları etiketle

Tarayıcı, denetlenemez tüm dosya türleri için, duyarlılık etiketi ilkesinden veya tarayıcı için yapılandırılan varsayılan etiketten varsayılan etiketi uygular.

### <a name="files-not-labeled-by-the-scanner"></a>Tarayıcı tarafından etiketlenmemiş dosyalar
Tarayıcı aşağıdaki koşullarda dosyaları etiketleyemez:

- Etiket sınıflandırma uyguladığında ancak koruma uygulamadığında ve dosya türü istemci tarafından yalnızca sınıflandırmayı desteklemediğinde. Daha fazla bilgi için bkz. [Yalnızca sınıflandırma için desteklenen dosya türleri](/azure/information-protection/rms-client/clientv2-admin-guide-file-types#file-types-supported-for-classification-only).

- Etiket sınıflandırma ve koruma uyguladığında, ancak tarayıcı dosya türünü desteklemediğinde.
  
    Varsayılan olarak tarayıcı, PDF şifrelemesi için ISO standardı kullanılarak korunduğunda yalnızca Office dosya türlerini ve PDF dosyalarını korur. 

    Korunacak dosya türlerini değiştirdiğinizde koruma için diğer [dosya türleri](deploy-scanner-configure-install.md#change-which-file-types-to-protect) eklenebilir.

**Örnek**: .txt dosyaları inceledikten sonra, .txt dosya türü yalnızca sınıflandırmayı desteklemediğinden tarayıcı yalnızca sınıflandırma için yapılandırılmış bir etiket uygulayamaz. 

Ancak etiket hem sınıflandırma hem de koruma için yapılandırılmışsa ve tarayıcının koruması için .txt dosya türü varsa, tarayıcı dosyayı etiketleyebilir.

## <a name="next-steps"></a>Sonraki adımlar

Tarayıcıyı dağıtma hakkında daha fazla bilgi için aşağıdaki makalelere bakın:

- [Tarayıcı dağıtımı önkoşulları](deploy-scanner-prereqs.md)
- [Tarayıcıyı yapılandırma ve yükleme](deploy-scanner-configure-install.md)
- [Tarayıcıyı kullanarak tarama çalıştırma](deploy-scanner-manage.md)

**Daha fazla bilgi**:

- [Tarayıcı uçtan uca tanıtım videomuzu izleyin!](https://www.youtube.com/watch?v=f1gy1KalSts) Tarayıcı mimarisinin, mimarisinin, önerinin, yüklemenin ve yapılandırmanın adım adım gözden geçirilmesini izleyin.

- Tarayıcı için en iyi yöntemlerle ilgili blogumuza göz atın: [AIP UL tarayıcısını dağıtmaya ve kullanmaya yönelik en iyi yöntemler](https://aka.ms/AIPScannerBestPractices)

- Microsoft'taki Core Services Mühendislik ve Operasyon ekibinin bu tarayıcıyı nasıl uyguladığıyla ilgileniyor musunuz?  Teknik örnek olay incelemesini okuyun: [Azure Information Protection tarayıcısıyla veri korumayı otomatikleştirme](https://www.microsoft.com/itshowcase/Article/Content/1070/Automating-data-protection-with-Azure-Information-Protection-scanner).

- PowerShell'i kullanarak dosyaları masaüstü bilgisayarınızdan etkileşimli olarak sınıflandırabilir ve koruyabilirsiniz. Bu ve PowerShell kullanan diğer senaryolar hakkında daha fazla bilgi için bkz. [PowerShell'i Azure Information Protection birleşik etiketleme istemcisiyle kullanma](./
- .md).
