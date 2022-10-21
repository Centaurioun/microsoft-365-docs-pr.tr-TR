---
title: Microsoft Syntex'i ayarlama
ms.author: mikeplum
author: MikePlumleyMSFT
ms.reviewer: ssquires
manager: serdars
audience: admin
ms.topic: article
ms.service: microsoft-syntex
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.custom:
- admindeeplinkMAC
search.appverid: MET150
ms.localizationpriority: high
description: Microsoft Syntex'i ayarlayın.
ms.openlocfilehash: b6a7309e9ae833f643930d9f308c1b748afeb0f5
ms.sourcegitcommit: 87283bb02ca750286f7c069f811b788730ed5832
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2022
ms.locfileid: "68659597"
---
# <a name="set-up-microsoft-syntex"></a>Microsoft Syntex'i ayarlama

Yöneticiler, Microsoft Syntex'i ayarlamak için <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 yönetim merkezi</a> kullanabilir. 

Başlamadan önce aşağıdakileri göz önünde bulundurun:

- Belge işlemeyi hangi SharePoint sitelerinde etkinleştireceksiniz? Bunların tümü, bazıları veya belirli siteler mi?
- Varsayılan içerik merkezinize ne ad vereceksiniz?

İlk kurulumdan sonra <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 yönetim merkezi</a> ayarlarınızı değiştirebilirsiniz.

Kurulumdan önce ortamınızda içerik anlama özelliğini ayarlamanın ve yapılandırmanın en iyi yolunu planladığınızdan emin olun. Örneğin, aşağıdaki kararları vermeniz gerekir:

- Belge işlemeyi etkinleştirmek istediğiniz SharePoint siteleri - bunların tümü, bazıları veya seçili siteler
- İçerik merkezinizin adı ve yöneticileri

## <a name="requirements"></a>Gereksinimler 

> [!NOTE]
> Microsoft 365 yönetim merkezi erişebilmek ve Syntex'i ayarlamak için Genel yönetici veya SharePoint yönetici izinlerine sahip olmanız gerekir.

Yönetici olarak, kurulumdan sonra istediğiniz zaman ve <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 yönetim merkezi</a> içerik anlama yönetimi ayarları boyunca seçtiğiniz ayarlarda değişiklik yapabilirsiniz.

### <a name="custom-power-platform-environments"></a>Özel Power Platform ortamları

Özel bir Power Platform ortamı kullanmayı planlıyorsanız, bu ortamda *Cortex Projesi için AI Builder* uygulamasını yüklemeniz gerekir. Ayrıntılar için [bkz. Dynamics 365 uygulamalarını yönetme](/power-platform/admin/manage-apps#install-an-app-in-the-environment-view) ve Dynamics 365 uygulamaları listesinde *Cortex Projesi için AI Builder* uygulamasını arama.

Ayrıca, belge işleme modelleri oluşturabilmeniz için önce özel ortama [AI Builder kredileri ayırmanız](/power-platform/admin/capacity-add-on) gerekir. 

Özel bir ortam kullanırken, model oluşturuculara Ortam Oluşturucu güvenlik rolü atanmalı ve model kullanıcılarına Temel Kullanıcı güvenlik rolü atanmalıdır. Daha fazla bilgi için bkz. [Kullanıcıya güvenlik rolü atama](/power-platform/admin/assign-security-roles) .

[İçerik merkezi sitesinde](/microsoft-365/contentunderstanding/create-a-content-center) model oluşturan kullanıcıların site üyesi olması gerekir. İçerik merkezi dışında yerel olarak model oluşturan kullanıcıların bu sitelerin site sahipleri olması gerekir.

### <a name="licensing"></a>Lisanslama

Syntex'i kullanmak için kuruluşunuzun Syntex aboneliğine ve her kullanıcıya atanmış bir lisansa sahip olması gerekir. Syntex lisansları, tümü atanması gereken aşağıdaki uygulamaları içerir:

- Syntex
- Syntex - SPO türü
- Syntex için Common Data Service

Yapılandırılmış belge işleme veya serbest biçimli belge işleme modellerini kullanmak için AI Builder kredilerine de ihtiyacınız vardır. Syntex'in lisanslı her kullanıcısı için her ay bir AI Builder kredisi ayırması sağlanır.

Syntex lisanslama hakkında ayrıntılı bilgi için bkz. [Microsoft Syntex lisansı](syntex-licensing.md)

## <a name="to-set-up-syntex"></a>Syntex'i ayarlamak için

1. Microsoft 365 yönetim merkezi <a href="https://go.microsoft.com/fwlink/p/?linkid=2171997" target="_blank">**Kurulum'u**</a> seçin ve ardından **Dosyalar ve içerik** bölümünü görüntüleyin.

2. **Dosyalar ve içerik** bölümünde **İçerik anlama işlemini otomatikleştir'i** seçin. Geçerli AI Builder kredi kullanılabilirliğinizin **Bir bakışta** bölümünde gösterildiğini unutmayın.<br/>

3. **İçerik anlama işlemini otomatikleştir** sayfasında, Kurulum işleminde izlenmek için **Başlarken'e** tıklayın. <br/>

    > [!div class="mx-imgBorder"]
    > ![Kurulumu başlatın.](../media/content-understanding/admin-content-understanding-get-started.png)</br>

4. **Form İşlemeyi Yapılandır** sayfasında, kullanıcıların belirli SharePoint belge kitaplıklarında belge işleme modelleri oluşturmasına izin vermek isteyip istemediğinizi seçebilirsiniz. Belge kitaplığı şeridinde, etkin olduğu SharePoint belge kitaplıklarında **form işleme modeli oluşturma** seçeneği sağlanacaktır.
 
     **Form işleme modeli oluşturma seçeneği hangi SharePoint kitaplıkları tarafından gösterilmelidir**? için şunları seçebilirsiniz:</br>
      - **Kuruluşunuzdaki tüm SharePoint kitaplıklarının** kullanımına açmak için tüm SharePoint sitelerindeki kitaplıklar.</br>
      - **Seçili SharePoint sitelerindeki kitaplıklar** ve kullanılabilir hale getirmek istediğiniz siteleri seçin veya en fazla 50 sitenin listesini karşıya yükleyin.</br>
      - Herhangi bir sitenin kullanımına açmak istemiyorsanız **SharePoint kitaplığı** yok (kurulumdan sonra bunu değiştirebilirsiniz).

   > [!div class="mx-imgBorder"]
   > ![Belge işleme sitesi seçeneklerini yapılandırın.](../media/content-understanding/admin-configforms.png)

   > [!Note]
   > Site eklendikten sonra sitenin kaldırılması, o sitedeki kitaplıklara uygulanan mevcut modelleri veya bir kitaplığa yapılandırılmamış belge işleme modelleri uygulama özelliğini etkilemez. 
    
    Birden çok Power Platform ortamı yapılandırdıysanız, belge işleme için hangisini kullanmak istediğinizi seçebilirsiniz. (Yalnızca bir ortamınız varsa bu seçenek görünmez.)

    ![Belge işleme Power Platform seçeneklerini yapılandırın.](../media/content-understanding/setup-power-platform-env.png)

    **Power Platform ortamı** için şunları seçebilirsiniz:
    - Varsayılan Power Platform **ortamınızı** kullanmak için varsayılan ortamı kullanın.
    - **Özel ortam** kullanmak için özel bir ortam kullanın. Listeden kullanmak istediğiniz ortamı seçin. ([Özel ortam gereksinimlerine bakın](/microsoft-365/contentunderstanding/set-up-content-understanding#requirements)).

    **İleri**'ye tıklayın.

5. **İçerik Merkezi Oluştur** sayfasında, kullanıcılarınızın yapılandırılmamış belge işleme modelleri oluşturup yönetebileceği bir SharePoint içerik merkezi sitesi oluşturabilirsiniz. Daha önce SharePoint yönetim merkezinden bir içerik merkezi oluşturduysanız, bu bilgiler burada görüntülenir ve **İleri'yi** seçebilirsiniz.

    1. **Site adı** alanına, içerik merkezi sitenize vermek istediğiniz adı yazın.
    
    1. **Site adresi**, site adı için seçtiklerinize bağlı olarak sitenizin URL'sini gösterir. Değiştirmek istiyorsanız **Düzenle'ye** tıklayın.

       > [!div class="mx-imgBorder"]
       > ![İçerik merkezi oluşturma.](../media/content-understanding/admin-cu-create-cc.png)</br>

       **İleri**'yi seçin.

6. **Gözden geçir ve bitir** sayfasında, seçtiğiniz ayara bakabilir ve değişiklik yapmayı seçebilirsiniz. Seçimlerinizden memnunsanız **Etkinleştir'i** seçin.

7. Onay sayfasında **Bitti'ye** tıklayın.

8. **Otomatik içerik anlama** sayfanıza geri dönersiniz. Bu sayfada **Yönet'i** seçerek yapılandırma ayarlarınızda herhangi bir değişiklik yapabilirsiniz. 

## <a name="assign-licenses"></a>Lisans atama

Syntex'i yapılandırdıktan sonra, syntex özelliklerini kullanacak kullanıcılar için lisans atamanız gerekir.

Lisans atamak için:

1. Microsoft 365 yönetim merkezi, **Kullanıcılar'ın** altında <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">**Etkin kullanıcılar'ı**</a> seçin.

2. Lisanslamak istediğiniz kullanıcıları seçin ve **Ürün lisanslarını yönet'i** seçin.

3. Açılan menüden **Uygulamalar'ı** seçin.

4. **Syntex için uygulamaları göster'i** seçin. **Uygulamalar'ın** altında **Syntex, Syntex ve Syntex için Common Data Service** **- SPO türünün** tümünün seçili olduğundan emin olun. 

    > [!div class="mx-imgBorder"]
    > ![Microsoft 365 yönetim merkezi syntex lisansları.](../media/content-understanding/sharepoint-syntex-licenses.png)

5. **Değişiklikleri kaydet**’e tıklayın.

## <a name="see-also"></a>Ayrıca bkz.

[AI Builder'da belge işleme modeline genel bakış](/ai-builder/form-processing-model-overview)

[Power Platform yönetim merkezinde ortam oluşturma ve yönetme](/power-platform/admin/create-environment)
