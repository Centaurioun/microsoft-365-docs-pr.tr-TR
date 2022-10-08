---
title: SharePoint 2013'ten yükseltme
ms.author: serdars
author: serdarsoysal
manager: serdars
ms.date: 11/10/2021
audience: ITPro
ms.topic: conceptual
ms.service: microsoft-365-enterprise
ms.collection:
- scotvorg
- Ent_O365
search.appverid:
- MET150
f1.keywords:
- NOCSH
description: SharePoint Server 2013 ve SharePoint Foundation 2013'ten yükseltecek bilgileri ve kaynakları bulun. Her iki destek de 11 Nisan 2023'de sona erer.
ms.openlocfilehash: cd2c9b233685aeeee329b5ebeafcb3ff3a27f4b3
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68193289"
---
# <a name="upgrading-from-sharepoint-2013"></a>SharePoint 2013'ten yükseltme

Hem Microsoft SharePoint Server 2013 hem de SharePoint Foundation 2013 **, 11 Nisan 2023'te** destek sonuna ulaşacaktır. Bu makale, mevcut SharePoint Server verilerinizi Microsoft 365'te SharePoint Online'a geçirmenize veya şirket içi SharePoint 2013 ortamınızı yükseltmenize yardımcı olacak kaynaklar sağlar. Bu makalenin geri kalanında, SharePoint Server 2013 ve SharePoint Foundation 2013'e başvurmak için SharePoint 2013'i kullanacağız.

## <a name="what-is-end-of-support"></a>*Destek sonu* nedir?

Microsoft ürünlerinin çoğu, yeni özellikler, hata düzeltmeleri, güvenlik düzeltmeleri vb. alan bir destek yaşam döngüsüne sahiptir. Destek sonu tarihinden sonra ürün çalışmayı durdurmaz, ancak Microsoft artık şunları sağlamaz:

- Oluşabilecek sorunlar için teknik destek.

- Sunucunun kararlılığını ve kullanılabilirliğini etkileyebilecek sorunlar için hata düzeltmeleri.

- Sunucuyu güvenlik ihlallerine açık hale getirebilecek güvenlik açıklarına yönelik güvenlik düzeltmeleri.

- Saat dilimi güncelleştirmeleri.

Bu, ürün için başka güncelleştirme, düzeltme eki veya düzeltme olmayacağı anlamına gelir (güvenlik düzeltme ekleri/düzeltmeler dahil). Microsoft Desteği destek çalışmalarını daha yeni sürümlere tamamen kaydırmış olacak.

> [!NOTE]
> Yazılım yaşam döngüsü genellikle ilk sürümden itibaren beş yıllık temel destek ve potansiyel olarak 5 yıla kadar genişletilmiş destek sürer. [Microsoft çözüm sağlayıcıları](https://go.microsoft.com/fwlink/?linkid=841249) , yazılımın sonraki sürümüne yükseltmenize veya Microsoft 365'e (veya her ikisine) geçmenize yardımcı olabilir. Özellikle SharePoint ile kullandığınız Microsoft SQL Server sürümü için kritik temel teknolojiler için destek sonu tarihlerini bildiğinizden emin olun. Daha fazla bilgi için bkz [. Sabit Yaşam Döngüsü İlkesi](https://support.microsoft.com/help/14085).

## <a name="plan-ahead"></a>Önceden planlayın

[SharePoint Server 2013 ve SharePoint Foundation 2013](/lifecycle/products/sharepoint-server-2013) için Ürün Yaşam Döngüsü sitesinde desteğin sona erdiğini denetleyin.[](/lifecycle/products/sharepoint-foundation-2013) Bu tarihleri göz önünde bulundurarak yükseltmelerinizi veya geçişlerinizi planlayın. Ürününüzün listelenen tarihte *çalışmayı durdurmayacağını* unutmayın. Ancak bu tarihten sonra yüklemenize artık düzeltme eki uygulanmayacağından ürünün sonraki sürümüne sorunsuz bir geçiş planlamak istersiniz. Aşağıdaki tabloda kullanabileceğiniz seçenekler listelenmiştir.

|Destek sonu ürünü|İyi|Iyi|En iyi|
|---|---|---|---|
|SharePoint Server 2013<BR>SharePoint Foundation 2013|SharePoint Server 2016 veya 2019'a yükseltme|SharePoint Server Abonelik Sürümü yükseltme|Microsoft 365'te SharePoint'e geçiş

## <a name="whats-next"></a>Sırada ne var?

Microsoft 365'teki en son işbirliği, zeka ve güvenlik çözümlerinden yararlanmak için Microsoft 365'te SharePoint'e geçiş yapmanızı öneririz. Microsoft 365'teki modern deneyim özellikleri cazip, esnek ve performanslı olacak şekilde tasarlanmıştır.

Şirket içi SharePoint dağıtımını sürdürmeniz gerekiyorsa, Microsoft 365'te SharePoint'e olabildiğince çok SharePoint işlevselliği geçirmenizi sağlayacak karma bir dağıtım öneririz. Karma uygulama hakkında bilgi edinmek ve planlamak için bkz. [SharePoint](/sharepoint/hybrid/hybrid) karma.

### <a name="migrate-to-sharepoint-in-microsoft-365"></a>Microsoft 365'te SharePoint'e geçiş

Sitelerinizi ve içeriğinizi Microsoft 365'te SharePoint'e geçirmek için SharePoint Geçiş Aracı'nı (SPMT) kullanabilirsiniz. Önceden planlama yapmanıza, geçişinizi gerçekleştirmenize ve karşılaşabileceğiniz sorunları gidermenize yardımcı olabilecek kapsamlı bir içerik kitaplığımız var. [SharePoint Geçiş Aracı'na genel bakış](/sharepointmigration/introducing-the-sharepoint-migration-tool) , başlamak için iyi bir yerdir.

### <a name="upgrade-to-sharepoint-server-subscription-edition"></a>SharePoint Server Abonelik Sürümü yükseltme

SharePoint 2013'ten Subscription Edition'a yükseltmenin doğrudan bir yolu olmasa da, bu yine de ikinci en iyi seçenektir. Birincil neden, SharePoint Server Abonelik Sürümü devam eden SharePoint Server'ın yeni ana sürümlerini yayınlama gereksinimini ortadan kaldıran sürekli bir güncelleştirme modeli sunmasıdır.

Subscription Edition'a yükseltmek için SharePoint Server 2016 veya 2019 çalıştırıyor olmanız gerekir. SharePoint 2013'ten 2019'a doğrudan bir yol olmadığından, en iyi seçeneğiniz önce 2016'ya yükseltmek ve ardından Subscription Edition'a yükseltmektir. Subscription Edition'a yükseltmenizi planlama ve hakkında daha fazla bilgi edinmek için aşağıdaki bağlantılara bakın:

- [SharePoint Server 2016'ya yükseltme](/sharepoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)
- [SharePoint Server Abonelik Sürümü yükseltme](/sharepoint/upgrade-and-update/upgrade-to-sharepoint-server-subscription-edition)

Şirket içi SharePoint dağıtımını sürdürmeniz gerekse bile, Microsoft 365'teki modern işbirliği deneyimlerinden, güvenlik ve uyumluluk özelliklerinden yararlanmaya başlamak için sitelerinizin veya içeriğinizin bölümlerini [SharePoint karma](/sharepoint/hybrid/hybrid) uygulamasıyla Microsoft 365'e geçirmenizi öneririz.  

### <a name="upgrade-to-sharepoint-server-2016-or-2019"></a>SharePoint Server 2016 veya 2019'a yükseltme

Şirket içi SharePoint dağıtımınızı 2013 desteğinin sonuna kadar sürdürmeyi planlıyorsanız hem SharePoint Server 2016 hem de 2019 desteklenen platformlardır. Ancak **her iki sürüm de 14 Temmuz 2026'da destek sonuna ulaşacaktır**. Bu, 2013 için destek sonu tarihinden sonra 3 yıl içinde başka bir yükseltme planlamanız gerektiği anlamına gelir. Her iki ürünün de destek yaşam döngüsü sayfaları şunlardır:

- [SharePoint Server 2016 destek yaşam döngüsü tarihleri](/lifecycle/products/sharepoint-server-2016)
- [SharePoint Server 2019 destek yaşam döngüsü tarihleri](/lifecycle/products/sharepoint-server-2019)

Daha fazla bilgi edinmek ve yükseltmenizi planlamak için aşağıdaki makalelere bakın:

- [SharePoint Server 2016'ya yükseltme](/sharepoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)
- [SharePoint Server 2019 yükseltme](/sharepoint/upgrade-and-update/upgrade-to-sharepoint-server-2019)

Şirket içi SharePoint dağıtımını sürdürmeniz gerekse bile, Microsoft 365'teki modern işbirliği deneyimlerinden, güvenlik ve uyumluluk özelliklerinden yararlanmaya başlamak için sitelerinizin veya içeriğinizin bölümlerini [SharePoint karma](/sharepoint/hybrid/hybrid) uygulamasıyla Microsoft 365'e geçirmenizi öneririz.  
