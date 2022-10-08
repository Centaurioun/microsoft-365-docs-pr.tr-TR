---
title: Microsoft 365 kullanım analizinde raporları özelleştirme
f1.keywords:
- NOCSH
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9b76065f-29b9-4b89-8059-c5f9db9ddbf6
description: Raporları tarayıcıda özelleştirmeyi ve Power BI Desktop öğrenin.
ms.openlocfilehash: 97ff462478b7172382aa797e8c4acb3a863bbe3f
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68193531"
---
# <a name="customize-the-reports-in-microsoft-365-usage-analytics"></a>Microsoft 365 kullanım analizinde raporları özelleştirme

Microsoft 365 kullanım analizi, Power BI'da kullanıcıların Microsoft 365'i nasıl benimsediği ve kullandığına ilişkin içgörüler sunan bir pano sağlar. Pano, kullanım verileriyle etkileşim kurmak için yalnızca bir başlangıç noktasıdır. Raporlar, daha kişiselleştirilmiş öngörüler edinmek için özelleştirilebilir.

Ayrıca, Power BI masaüstü uygulaması sayesinde, işletmeniz hakkında daha zengin öngörüler edinmek için raporlarınızı başka veri kaynaklarına bağlayarak raporlarınızı daha da özelleştirebilirsiniz.

## <a name="customizing-reports-in-the-browser"></a>Raporları tarayıcıda özelleştirme

Aşağıdaki iki örnekte, mevcut bir görselin nasıl değiştirileceği ve nasıl yeni görsel oluşturulacağı gösterilmiştir.

### <a name="modify-an-existing-visual"></a>Mevcut bir görseli değiştirme

Bu örnekte Etkinleştirme **/Lisanslama** raporu içindeki **Etkinleştirme** sekmesinin nasıl değiştirileceği gösterilmektedir.

1. **Etkinleştirme/Lisanslama** raporunda **Etkinleştirme** sekmesini seçin.

2. Power BI'da Daha fazla sayfa düğmesi aracılığıyla ![üst kısımdaki **Düzenle** düğmesini seçerek düzenleme moduna girin.](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) düğmesi.

    ![Sağ üst gezinti bölmesinde Raporu düzenle'ye tıklayın.](../../media/e2c16663-1fbd-4d7f-887c-0cbb891d3b3d.png)

3. Sağ üst kısımda **Bu sayfayı çoğalt'ı** seçin.

    ![Bu sayfayı çoğalt'ı seçin.](../../media/b2d18dcd-6b82-4ce7-ab79-1b24e3721309.png)

4. Sağ alt kısımda Android, iOS, Mac gibi işletim sistemine göre etkinleştirilen kullanıcıların sayısını gösteren çubuk grafiklerden herhangi birini seçin.

5. Sağ tarafta **bulunan Görselleştirmeler** alanında, **mac sayısını** görselden kaldırmak için yanındaki **X** işaretini seçin.

    ![Mac Sayısını kaldırın.](../../media/ce3d8358-df57-4f64-bd25-ac5be7fc8713.png)

### <a name="create-a-new-visual"></a>Yeni görsel oluşturma

Aşağıdaki örnekte, yeni Yammer kullanıcılarının aylık olarak izlenmesi için nasıl yeni bir görsel oluşturulacağı gösterilmiştir.

1. Sol gezintiyi kullanarak **Ürün Kullanımı** raporuna gidin ve **Yammer** sekmesini seçin.

2. Power BI'da Diğer sayfa düğmesini seçerek ![düzenleme moduna geçin.](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) ve **Düzenle'yi seçin**.

3. Sayfanın en altında, ![Power BI'da sayfa ekle düğmesi.](../../media/d3b8c117-17d4-4f53-b078-8fefc2155b24.png) yeni bir sayfa oluşturmak için.

4. Sağ taraftaki **Görselleştirmeler** alanında **Yığılmış çubuk grafiğini** (soldan ilk satır) seçin.

    ![Çubuk Grafik'i seçin.](../../media/214c3fed-6eae-43e6-83fb-708a2d74406e.png)

5. Görselleştirmenin sağ alt kısmını seçin ve büyütmek için sürükleyin.

6. Sağdaki **Alanlar** alanında **Takvim** tablosunu genişletin.

7. **MonthName** öğesini, alanlar bölümünde yer alan **Görselleştirmeler** alanındaki **Eksen** başlığının hemen altına sürükleyin.

    ![Ay Adını sürükleyin.](../../media/bff99987-8c4b-4618-89fd-47df557b0ed7.png)

8. Sağdaki **Alanlar** bölümünde **TenantProductUsage** tablosunu genişletin.

9. **FirstTimeUsers** öğesini alanlar bölümündeki **Değer** başlığının hemen altına sürükleyin.

10. **Ürün** öğesini **Filtreler** alanındaki **Görsel düzey filtreleri** başlığının hemen altına sürükleyin.

11. Görünen **Filtre Türü** alanında **Yammer** onay kutusunu seçin.

    ![Yammer onay kutusunu seçin.](../../media/82e99730-0de9-42da-928a-76aab0c3e609.png)

12. Görselleştirme listesinin hemen altında, Power BI Görselleri'nde **Biçim** simgesi ![Biçim simgesini seçin.](../../media/ee0602f3-3df5-4930-b862-db1d90ae4ae2.png)

13. Başlığı genişletin ve **Başlık Metni** değerini **Aya Göre Yammer'ı İlk Kez Kullananlar** olarak değiştirin.

14. **Metin Boyutu** değerini **12** olarak değiştirin.

15. Sağ alttaki sayfanın adını düzenleyerek yeni sayfanın başlığını değiştirin.

16. En üstte **Okuma Görünümü'ne** ve ardından **Kaydet'e** tıklayarak raporu kaydedin.

## <a name="customizing-the-reports-in-power-bi-desktop"></a>Power BI Masaüstü'nde raporları özelleştirme

For most customers modifying the reports and chart visuals in Power BI web will be sufficient. For some however, there may be a need to join this data with other data sources to gain richer insights contextual to their own business, in which case they can customize and build additional reports using Power BI Desktop. You can download [Power BI Desktop](https://go.microsoft.com/fwlink/p/?linkid=849797) for free.

### <a name="use-the-reporting-apis"></a>Raporlama API'lerini kullanma

Bu raporları destekleyen Microsoft 365'ten ODATA raporlama API'lerine doğrudan bağlanarak işe başlayabilirsiniz.

1. **Veri al** \> **Diğer** \> **ODATA Akışı** \> **Bağlan** bölümüne gidin.

2. URL penceresine "https://<i></i> reports.office.com/pbi/v1.0/\<tenantid\>" yazın

    **NOT:** Raporlama API'leri önizleme aşamasındadır ve üretim aşamasına geçinceye kadar değiştirilebilir.

    ![Power BI desktop için OData akışı URL'si.](../../media/c0ef967e-a454-4eba-bc8e-61e113170053.png)

3. İstendiğinde Microsoft 365'e kimlik doğrulaması yapmak için Microsoft 365 (kuruluş veya okul) yönetici kimlik bilgilerinizi girin.

    Microsoft 365 Benimseme şablonu uygulama raporlarına kimlerin erişmesine izin verilenler hakkında daha fazla bilgi için [SSS](usage-analytics.md#faq) bölümüne bakın.

4. Bağlantı yetkilendirildiğinde, bağlanılabilecek veri kümelerini gösteren Gezgin penceresini görürsünüz.

    Tümünü seçin ve **Yükle'yi** seçin.

    Bunu yaptığınızda, veriler Power BI Masaüstünüze indirilir. Bu dosyayı kaydettikten sonra ihtiyacınız olan raporları oluşturmaya başlayabilirsiniz.

    ![Raporlama API'sinde bulunan ODATA değerleri.](../../media/545b4d17-dbbd-4cfc-b75a-a8b27283d438.png)

### <a name="use-the-microsoft-365-usage-analytics-template"></a>Microsoft 365 kullanım analizi şablonunu kullanma

You can also use the Power BI template file that corresponds to the Microsoft 365 usage analytics reports as a starting point to connect to the data. The advantage of using the pbit file is that it has the connection string already established. You can also take advantage of all the custom measures that are created, on top of the data that the base schema returns and build on it further.

Power BI şablon dosyasını [Microsoft İndirme Merkezi'nden](https://download.microsoft.com/download/7/8/2/782ba8a7-8d89-4958-a315-dab04c3b620c/Microsoft%20365%20Usage%20Analytics.pbit) indirebilirsiniz. Power BI şablon dosyasını indirdikten sonra başlamak için şu adımları izleyin:

1. Pbit dosyasını açın.

2. İletişim kutusuna kiracı kimliğinizi girin.

    ![Pbit dosyasını açmak için kiracı kimliğinizi girin.](../../media/071ed0bf-8b9d-49c6-81fc-fd4c6cc85bd3.png)

3. İstendiğinde Microsoft 365'e kimlik doğrulaması yapmak için yönetici kimlik bilgilerinizi girin.

     Microsoft 365 kullanım analizi raporlarına erişmesine izin verilen kişiler hakkında daha fazla bilgi için.

    Yetki sağlandıktan sonra Power BI dosyasındaki veriler yenilenir.

    Verilerin yüklenmesi biraz zaman alabilir. Yükleme tamamlandığında, dosyayı bir .pbix dosyası olarak kaydedebilir ve raporları özelleştirmeye devam edebilir ya da bu rapora başka bir veri kaynağı ekleyebilirsiniz.

4. Follow [Getting started with Power BI](/power-bi/fundamentals/desktop-getting-started) documentation to understand how to build reports, publish them to the Power BI service, and share with your organization. Following this path for customization and sharing may require additional Power BI licenses. See Power BI [licensing guidance](https://go.microsoft.com/fwlink/p/?linkid=849803) for details.
