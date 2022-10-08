---
title: Microsoft 365 kullanım analizini etkinleştirme
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
- admindeeplinkMAC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9db96e9f-a622-4d5d-b134-09dcace55b6a
description: Power BI'daki Microsoft 365 Kullanım Analizi şablon uygulamasını kullanarak kiracınız için veri toplamaya nasıl başlayacağınızı öğrenin.
ms.openlocfilehash: ff1bc0e30c2f9a79bbada94672315a14df6daae5
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68190187"
---
# <a name="enable-microsoft-365-usage-analytics"></a>Microsoft 365 kullanım analizini etkinleştirme

Microsoft 365 US Government Community Cloud (GCC) kiracısında Microsoft 365 kullanım analizini etkinleştirmek için bkz. [Kullanım Analizi ile Microsoft 365 Kamu Topluluk Bulutu (GCC) verilerine bağlanma](connect-to-gcc-data-with-usage-analytics.md).

## <a name="before-you-begin"></a>Başlamadan önce

Microsoft 365 kullanım analizini kullanmaya başlamak için önce verileri <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 yönetim merkezi</a> kullanılabilir hale getirmeniz ve ardından şablon uygulamasını Power BI'da başlatmanız gerekir.

## <a name="get-power-bi"></a>Power BI'ı alma

Henüz Power BI'nız yoksa [Power BI Pro kaydolabilirsiniz](https://go.microsoft.com/fwlink/p/?linkid=845347). Deneme sürümüne kaydolmak için **Ücretsiz deneyin'i** veya Power BI Pro almak için **Şimdi satın alın'ı** seçin.


Ayrıca, Power BI'ın bir sürümünü satın almak için **Ürünler**'i de genişletebilirsiniz.

> [!NOTE]
> Şablon uygulamasını yüklemek, özelleştirmek ve dağıtmak için Power BI Pro lisansına ihtiyacınız vardır. Daha fazla bilgi için bkz [. Önkoşullar](/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).

Verilerinizi paylaşmak için hem sizin hem de verileri paylaştığınız kişilerin Power BI Pro lisansına sahip olması veya içeriğin [Power BI premium hizmetindeki](/power-bi/service-premium-what-is) bir çalışma alanında olması gerekir.

## <a name="enable-the-template-app"></a>Şablon uygulamasını etkinleştirme

Şablon uygulamasını etkinleştirmek için **bir Genel yönetici** olmanız gerekir.

Daha fazla bilgi için [yönetici rolleri hakkında](../add-users/about-admin-roles.md) bilgi edinin.

1. Yönetim merkezinde **Ayarlar** \> **Kuruluş ayarları** \> **Hizmetler** sekmesine gidin.

2. **Hizmetler** sekmesinde **Raporlar'ı** seçin.

3. Açılan Raporlar panelinde **Rapor verilerini Power BI için Microsoft 365 kullanım analizinde kullanılabilir hale getir** seçeneğini **KaydetmeDe** \> olarak ayarlayın.

Veri toplama işlemi, kiracınızın boyutuna bağlı olarak iki ile 48 saat içinde tamamlanır. Veri toplama tamamlandığında **Power BI'a Git** düğmesi etkinleştirilir (artık gri olmaz). İşlem tamamlandıktan sonra uygulama, kuruluşunuz düzeyinde geçmiş kullanım verileri sağlar. 

> [!NOTE]
> **"Kullanıcı Etkinliği"** sekmesinin verileri yalnızca geçerli ayın on beşinci gününden ve sonraki ayın ilk gününden sonra yenilenir, bu nedenle ilk yenileme tamamlanana kadar başlangıçta boş kalır.

## <a name="start-the-template-app"></a>Şablon uygulamasını başlatma

Şablon uygulamasını başlatmak için **genel yönetici**, **rapor okuyucu**, **Exchange yöneticisi**, **Skype Kurumsal yöneticisi** veya **SharePoint yöneticisi olmanız gerekir**.

1. Kiracı kimliğini kopyalayın ve **Power BI'a git'i** seçin.

2. Power BI'a ulaştığınızda oturum açın. Ardından gezinti **menüsünden Uygulamalar Uygulama**->**al'ı** seçin.

3. **Uygulamalar** sekmesinde arama kutusuna Microsoft 365 yazın ve ardından **Microsoft 365 kullanım analizi**\> **Şimdi edinin**'i seçin.

    [![Şimdi edinin'i seçin.](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)

4. Uygulama yüklendikten sonra. Kutucuğu seçerek açın.

5. Uygulamayı örnek verilerle görüntülemek için Uygulamayı **keşfet'i** seçin. Uygulamayı kuruluşunuzun verilerine bağlamak için **Bağlan'ı** seçin.

6. **Bağlan'ı** seçin, **Microsoft 365 kullanım analizine bağlan** ekranında, adım (1) içinde kopyaladığınız kiracı kimliğini (tireler olmadan) yazın ve **İleri'yi** seçin.

7. Sonraki ekranda, **Oturum açma Kimlik Doğrulama yöntemi** \> olarak **OAuth2'yi** seçin. Başka bir kimlik doğrulama yöntemi seçerseniz şablon uygulamasına bağlantı başarısız olur.

    ![Kimlik doğrulama yöntemi olarak Microsoft hesabı'nı seçin.](../../media/ab6f0463-c3f7-4088-a605-67c699fa86adnew.png)

8. Şablon uygulaması örneği açıldıktan sonra Microsoft 365 kullanım analizi panosu web üzerinde Power BI'da kullanılabilir. Panonun ilk yüklemesi 2-30 dakika arasında sürer.

Kiracı düzeyi toplamları, kabul ettikten sonra tüm raporlarda kullanılabilir. **Kullanıcı düzeyi ayrıntıları, kabul ettikten sonra yalnızca bir sonraki takvim ayının 5'inde kullanılabilir duruma gelir**. Bu, Kullanıcı Etkinliği altındaki tüm raporları etkiler (Bu raporları görüntüleme ve kullanma hakkında ipuçları için bkz. [Microsoft 365 kullanım analizinde raporlarda gezinme](navigate-and-utilize-reports.md) ve bunları kullanma).

## <a name="make-the-collected-data-anonymous"></a>Toplanan verilerin anonim olmasını sağlama

Raporlar, kuruluşunuzun kullanım verileri hakkında bilgi sağlar. Varsayılan olarak, raporlar kullanıcılar, gruplar ve siteler için tanımlanabilir adlarla bilgileri görüntüler. 1 Eylül 2021'den itibaren, şirketlerin yerel gizlilik yasalarını desteklemesine yardımcı olmak için devam eden taahhüdümüzün bir parçası olarak tüm raporlar için kullanıcı bilgilerini varsayılan olarak gizleyeceğiz.
  
Genel yöneticiler, kiracıları için bu değişikliği geri alabilir ve kuruluşlarının gizlilik uygulamaları izin verirse tanımlanabilir kullanıcı bilgilerini gösterebilir. Bu, aşağıdaki adımları izleyerek Microsoft 365 yönetim merkezi elde edilebilir:
  
1. Yönetim merkezinde **Ayarlar** \> **Kuruluş Ayarları** \> **Hizmetleri** sayfasına gidin.

2. **Raporlar**'ı seçin. 
  
3. Deyimin işaretini kaldırın **Tüm raporlarda, kullanıcılar, gruplar ve siteler için kimliği kaldırılmış adları görüntüleyin ve** değişikliklerinizi kaydedin.  
  
Bu değişikliklerin etkili olması birkaç dakika sürer. Tanımlanabilir kullanıcı bilgilerini göstermek, Microsoft Purview uyumluluk portalı denetim günlüğünde günlüğe kaydedilen bir olaydır.   

## <a name="related-content"></a>İlgili içerik

[Kullanım analizi hakkında](usage-analytics.md) (makale)\
[Kullanım analizinin en son sürümünü alma](get-the-latest-version-of-usage-analytics.md) (makale)\
[Microsoft 365 kullanım analizinde raporlarda gezinme ve bunları kullanma](navigate-and-utilize-reports.md) (makale)
