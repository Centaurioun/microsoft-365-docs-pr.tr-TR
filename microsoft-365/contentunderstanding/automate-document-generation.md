---
title: SharePoint Syntex ve Power Automate ile belge oluşturmayı otomatikleştirme (önizleme)
ms.author: chucked
author: chuckedmonson
manager: pamgreen
audience: admin
ms.reviewer: anrasto, shrganguly
ms.topic: article
ms.service: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.localizationpriority: medium
description: SharePoint Syntex ve Power Automate kullanarak otomatik olarak belge ve diğer içerik oluşturmayı öğrenin.
ms.openlocfilehash: 7ed0756b4aaed2ef564dd4796368e25d7f78dd97
ms.sourcegitcommit: d3ef9391f621e8f4ca70661184b3bb82c6cbda94
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/02/2022
ms.locfileid: "67876499"
---
# <a name="automate-document-generation-with-sharepoint-syntex-and-power-automate-preview"></a>SharePoint Syntex ve Power Automate ile belge oluşturmayı otomatikleştirme (önizleme)

power automate ile birlikte SharePoint Syntex içerik derlemesini kullanarak, modern şablonları kullanarak belge oluşturmayı otomatikleştirebilirsiniz. 

Bu önizleme sürümü, SharePoint bağlayıcısında bir Power Automate eylemidir. Eylem "SharePoint Syntex kullanarak belge oluşturma (önizleme)" olarak adlandırılır ve önizleme için sınırlı özelliklere sahiptir. 

## <a name="scope-of-the-preview"></a>Önizlemenin kapsamı 

Önizlemenin geçerli kapsamı şunları yapmanızı sağlar:  

- Belge oluşturma için başlangıç noktası olarak bir SharePoint listesi seçin. Başka bir ifadeyle, listedeki bir öğe eklendikten, değiştirildikten veya silindikten sonra SharePoint listesindeki değerler kullanılarak bir belge oluşturulmasını istiyorsunuz. 

- Modern bir şablon seçin ve alanlarını seçilen SharePoint listesindeki sütunlarla ilişkilendirin. 

Önizleme, SharePoint Bağlayıcısı'nda aşağıdaki üç tetikleyici için çalışacak şekilde oluşturulur ve test edilir:

- Öğe oluşturulduğunda
- Öğe oluşturulduğunda veya değiştirildiğinde
- Bir öğe silindiğinde

## <a name="automate-document-generation"></a>Belge oluşturmayı otomatikleştirme 

Modern bir şablon ve Power Automate kullanarak otomatik olarak belge oluşturmak için bu adımları izleyin. 

1. Power Automate'te oturum açın.

2. Sol panelde **Bağlayıcılar'ı** seçin. Arama kutusunda *SharePoint'i* arayın ve **sharepoint** bağlayıcısını seçin.

3. SharePoint bağlayıcısı sayfasında, otomatik belge oluşturma işlemini başlatmak için kullanmak istediğiniz tetikleyiciyi seçin. 

    Aşağıdaki üç tetikleyiciden biriyle başlamanızı öneririz:

    - Öğe oluşturulduğunda
    - Öğe oluşturulduğunda veya değiştirildiğinde
    - Bir öğe silindiğinde

4. Ardından, SharePoint site adresini ve SharePoint listesinin adını girerek tetikleyiciyi ayarlayın. **Yeni adım'ı** seçin. 

   ![Örnek site adresini ve site adını gösteren Belge oluşturulduğunda veya değiştirildiğinde tetikleyicisinin ekran görüntüsü.](../media/content-understanding/document-generation-trigger.png)

5. SharePoint bağlayıcısını yeniden seçin. Arama kutusunda **SharePoint Syntex kullanarak belge oluştur (önizleme)** eylemini arayın ve seçin.

   ![SharePoint Syntex (önizleme) eylemini kullanarak belge oluştur eylemini gösteren SharePoint bağlayıcısı Eylemleri sekmesinin ekran görüntüsü.](../media/content-understanding/document-generation-action.png) 

6. Site bilgilerini girin ve modern şablonu içeren belge kitaplığını seçin. 

7. Şablon seçildikten sonra şablon alanlarını görmeye başlarsınız. Alanları listedeki sütunlarla ilişkilendirin. 

    > [!NOTE]
    >Şablondaki veri eşlemesi bu önizlemede desteklenmez. Örneğin, şablonunuzdaki bir alanı yönetilen meta veri sütunuyla ilişkilendirdiyseniz, otomatik oluşturma sırasında bu alanı listedeki bir sütunla ilişkilendirebilirsiniz. 

8. İşiniz bittiğinde, akışı kaydetmek için **Kaydet'i** seçin. 

    > [!NOTE]
    > Kullanıcıların belge oluşturma için el ile değer eklemesine gerek duymadan şablonları kullanmanızı öneririz. Şablon bir alan için el ile girişe ihtiyaç duyuyorsa, bu değeri bir SharePoint liste sütununa eşlemek yerine alana göre belirtebilirsiniz.<br><br> Şu anda bu eylem kullanılarak yalnızca Word belgeleri (.Docx) desteklenmektedir.  

## <a name="see-also"></a>Ayrıca bkz.

 [SharePoint Syntex'da içerik derlemesi kullanarak belge oluşturma](content-assembly.md)
