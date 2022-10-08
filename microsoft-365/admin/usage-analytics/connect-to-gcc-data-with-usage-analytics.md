---
title: Kullanım Analizi ile Microsoft 365 Kamu Topluluk Bulutu (GCC) verilerine bağlanma
f1.keywords:
- CSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- scotvorg
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9db96e9f-a622-4d5d-b134-09dcace55b6a
description: Power BI'daki Microsoft 365 Kullanım Analizi şablon uygulamasını kullanarak Microsoft 365 Kamu Topluluğu Bulutu (GCC) kiracınızdaki verilere bağlanmayı öğrenin.
ms.openlocfilehash: c82dd3d358621e874281b89a22976e583cc0df95
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68193487"
---
# <a name="connect-to-microsoft-365-government-community-cloud-gcc-data-with-usage-analytics"></a>Kullanım Analizi ile Microsoft 365 Kamu Topluluk Bulutu (GCC) verilerine bağlanma

Microsoft 365 Kamu Topluluk Bulutu (GCC) kiracısında Microsoft 365 Kullanım Analizi raporuyla verilerinize bağlanmak için aşağıdaki yordamları kullanın. 

> [!NOTE]
> Bu yönergeler özellikle Microsoft 365 GCC kiracılarına yöneliktir. 

## <a name="before-you-begin"></a>Başlamadan önce

Başlangıçta Microsoft 365 Kullanım Analizini yapılandırmak için: 

- Veri toplamayı etkinleştirmek için Microsoft 365 Genel yöneticisi olmanız gerekir. 
- Şablon dosyasını kullanmak için [Power BI Desktop](https://powerbi.microsoft.com/en-us/desktop/) uygulamasına ihtiyacınız vardır. 
- Raporu yayımlamak ve görüntülemek için [Power BI Pro lisansına](https://go.microsoft.com/fwlink/p/?linkid=845347) veya Premium kapasiteye ihtiyacınız vardır. 

## <a name="step-1-make-you-organizations-data-available-for-the-microsoft-365-usage-analytics-report"></a>1. Adım: Kuruluşunuzun verilerini Microsoft 365 Kullanım Analizi raporu için kullanılabilir hale getirme

1. Microsoft 365 yönetim merkezi gezinti menüsünü genişletin, **Raporlar'ı** ve ardından **Kullanım'ı** seçin. 
2. **Kullanım Raporları** sayfasındaki Microsoft 365 Kullanım Analizi bölümünde **Başlarken'i** seçin. 
3. **Kullanım analizi için Power BI'ı etkinleştir'in** altında **Kurumsal kullanım verilerini Power BI için Microsoft kullanım analizinin kullanımına sun'u** ve ardından **Kaydet'i** seçin.

    ![Kiracı verilerinizi kullanılabilir hale getirin.](../../media/usage-analytics/make-data-available.png) 



    Bu işlem, kuruluşunuzun verilerini bu rapor için erişilebilir hale getirmek için bir süreç başlatır ve **verilerinizi Microsoft 365 kullanım analizine hazır hale getirebileceğimizi** belirten bir ileti görürsünüz. Bu işlemin tamamlanmasının 24 saat sürebileceğini unutmayın. 

4. Kuruluş verileriniz hazır olduğunda, sayfayı yenilediğinizde verilerinizin artık kullanılabilir olduğunu belirten bir ileti gösterilir ve **kiracı kimlik** numaranızı da sağlar. Kiracı verilerinize bağlanmayı denediğinizde sonraki bir adımda kiracı kimliğini kullanmanız gerekir. 
 
    ![Kiracı Kimliği.](../../media/usage-analytics/tenant-id-gcc.png) 
 
    > [!IMPORTANT]
    > Verileriniz kullanılabilir olduğunda **Power BI'a git'i** seçmeyin. Bu işlem sizi Power BI Market'e götürür.  GCC kiracıları için gerekli olan bu raporun şablon uygulaması Power BI Market'te kullanılamaz.  


## <a name="step-2-download-the-power-bi-template-connect-to-your-data-and-publish-the-report"></a>2. Adım: Power BI şablonunu indirme, verilerinize bağlanma ve raporu yayımlama

Microsoft 365 GCC kullanıcıları verilerine bağlanmak için Microsoft 365 Kullanım Analizi rapor şablonu dosyasını indirebilir ve kullanabilir. Şablon dosyasını açmak ve kullanmak için Power BI Desktop gerekir. 

 > [!NOTE]
 > Şu anda Power BI Market'teki GCC kiracıları için Microsoft 365 Kullanım Analizi raporu için bir şablon uygulaması sağlanmamaktadır.  

1. [Power BI şablonunu](https://download.microsoft.com/download/7/8/2/782ba8a7-8d89-4958-a315-dab04c3b620c/Microsoft%20365%20Usage%20Analytics.pbit) indirdikten sonra Power BI Desktop kullanarak açın. 
2. **Kiracı Kimliği** istendiğinde, 1. adımda kuruluşunuzun verilerini bu rapor için hazırlarken aldığınız kiracı kimliğini girin. Ardından **Yükle'yi** seçin. Verilerinizin yüklenmesi birkaç dakika sürer. 

    ![Kiracı kimliğini girin.](../../media/usage-analytics/add-tenant-id.png) 



3. Yükleme tamamlandığında raporunuz görüntülenir ve verilerinizin yönetici özetini görürsünüz. 

    ![Yönetici Özeti.](../../media/usage-analytics/exec-summary.png) 
 

4. Değişikliklerinizi rapora kaydedin. 
5. Raporu görüntülenebileceği Power BI Online hizmetinde yayımlamak için Power BI Desktop menüsünde **Yayımla'yı** seçin. Bunun için Power BI Pro lisansı veya Power BI Premium kapasitesi gerekir. [Yayımlama işleminin](/power-bi/create-reports/desktop-upload-desktop-files#to-publish-a-power-bi-desktop-dataset-and-reports) bir parçası olarak, Power BI Online Service'teki kullanılabilir bir çalışma alanında yayımlamak için bir hedef seçmeniz gerekir.

## <a name="related-content"></a>İlgili içerik

[Kullanım analizi hakkında](usage-analytics.md) </br>
[Kullanım analizinin en son sürümünü edinme](get-the-latest-version-of-usage-analytics.md) </br>
[Microsoft 365 kullanım analizinde raporlarda gezinme ve bunları kullanma](navigate-and-utilize-reports.md) </br>