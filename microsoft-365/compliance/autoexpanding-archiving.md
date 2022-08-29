---
title: Otomatik genişleyen arşivleme hakkında daha fazla bilgi edinme
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 37cdbb02-a24a-4093-8bdb-2a7f0b3a19ee
description: Exchange Online posta kutuları için ek arşiv depolama alanı sağlayan arşivlemeyi otomatik olarak genişletme hakkında bilgi edinin.
ms.openlocfilehash: 1eb2aaf2593e9b5d2c1e254f7fa8e207cbc848d4
ms.sourcegitcommit: 23c7e96d8ec31c676c458e7c71f1cc8a1e40a0e4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/16/2022
ms.locfileid: "67359985"
---
# <a name="learn-about-auto-expanding-archiving"></a>Otomatik genişleyen arşivleme hakkında daha fazla bilgi edinme

>*[Güvenlik & uyumluluğu için Microsoft 365 lisanslama kılavuzu](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

Microsoft Purview'daki arşiv posta kutuları, kullanıcılara ek posta kutusu depolama alanı sağlar. Kullanıcının arşiv posta kutusu etkinleştirildikten sonra 100 GB'a kadar ek depolama alanı kullanılabilir hale gelir.

Microsoft Purview'daki bu arşivleme özelliği ( *otomatik genişletme arşivleme* olarak adlandırılır), arşiv posta kutularında 1,5 TB'a kadar ek depolama alanı sağlar. Arşiv posta kutusunda depolama kotası ulaşıldığında, Arşiv posta kutusu 1,5 TB'a ulaşana kadar Microsoft Purview otomatik olarak (ve artımlı olarak) arşivin boyutunu artırır.

Otomatik genişletme arşivlemeyi açmayla ilgili adım adım yönergeler için bkz. [Otomatik genişletme arşivlemeyi etkinleştirme](enable-autoexpanding-archiving.md).

> [!NOTE]
> Otomatik genişletme arşivleme, paylaşılan posta kutularını da destekler.

## <a name="how-auto-expanding-archiving-works"></a>Otomatik genişletme arşivleme nasıl çalışır?

Giriş bölümünde açıklandığı gibi, kullanıcının arşiv posta kutusu etkinleştirildiğinde ek posta kutusu depolama alanı oluşturulur. Otomatik genişletme arşivleme etkinleştirildiğinde, Microsoft Purview arşiv posta kutusunun boyutunu düzenli aralıklarla denetler. Arşiv posta kutusu depolama sınırına yaklaştığında, arşiv için otomatik olarak ek depolama alanı oluşturulur. Kullanıcının bu ek depolama alanı biterse, kullanıcının arşivine otomatik olarak daha fazla depolama alanı eklenir. Bu işlem, kullanıcının arşivi 1,5 TB boyuta ulaşana kadar devam eder. Bu işlem otomatik olarak gerçekleşir; bu da yöneticilerin ek arşiv depolama alanı istemesi veya otomatik genişletme arşivlemeyi yönetmesi gerekmeyecek anlamına gelir.

bu işlemle ilgili hızlı bir genel bakış aşağıda verilmiştir.

![Otomatik genişletme arşivleme işlemine genel bakış.](../media/74355385-d990-44fe-8a87-6c3639d1f63f.png)

1. Arşivleme, kullanıcı posta kutusu veya paylaşılan posta kutusu için etkinleştirilir. 100 GB depolama alanı olan bir arşiv posta kutusu oluşturulur ve arşiv posta kutusu için uyarı kotası 90 GB olarak ayarlanır.

2. Yönetici, posta kutusu için arşivlemenin otomatik olarak genişletilmesine olanak tanır. Posta kutusuna bir saklama veya saklama ilkesi uygulanmışsa, arşiv posta kutusunun depolama kotası 110 GB'a, arşiv uyarı kotası ise 100 GB'a yükseltilir.
    
    Ardından arşiv posta kutusu (Kurtarılabilir Öğeler klasörü dahil) depolama kotasına ulaştığında, arşiv posta kutusu otomatik olarak genişletilen bir arşive dönüştürülür. Maksimum 1,5 TB boyuta ulaşana kadar ek depolama alanı eklenir. Ek depolama alanının sağlanması 30 güne kadar sürebilir.

3. Microsoft Purview gerektiğinde otomatik olarak daha fazla depolama alanı ekler.

> [!IMPORTANT]
> Otomatik genişletme arşivleme yalnızca tek tek kullanıcılar (veya paylaşılan posta kutuları) için kullanılan ve günlük 1 GB'ı aşmayan büyüme hızına sahip posta kutuları için desteklenir. Kullanıcının arşiv posta kutusu yalnızca o kullanıcıya yöneliktir. İletileri arşiv posta kutusuna kopyalamak için günlüğe kaydetme, taşıma kuralları veya otomatik iletme kurallarının kullanılmasına izin verilmez. Microsoft, kullanıcının arşiv posta kutusunun diğer kullanıcıların arşiv verilerini depolamak için kullanıldığı durumlarda veya uygunsuz kullanım durumunda ek arşivlemeyi reddetme hakkını saklıdır.

## <a name="what-gets-moved-to-the-additional-archive-storage-space"></a>Ek arşiv depolama alanına ne taşınır?

Otomatik olarak genişleten arşiv depolama alanını verimli bir şekilde kullanmak için klasörler taşınabilir. Microsoft Purview, arşive ek depolama alanı eklendiğinde hangi klasörlerin taşındığını belirler. Bazen bir klasör taşındığında, bir veya daha fazla alt klasör otomatik olarak oluşturulur ve taşıma işlemini kolaylaştırmak için özgün klasördeki öğeler bu klasörlere dağıtılır. Outlook'ta klasör listesinin arşiv bölümünü görüntülerken, bu alt klasörler özgün klasörün altında görüntülenir. Microsoft 365'in bu alt klasörleri adlandırmak **\<folder name\>için kullandığı adlandırma kuralı _yyyy (Mmm dd, yy h_mm üzerinde oluşturulur)**; burada:

- **yyyy** , klasördeki iletilerin alındığı yıldır.

- **mmm dd, yyyy h_m**, kullanıcının Outlook'taki saat dilimi ve bölgesel ayarlarına bağlı olarak alt klasörün Office 365 tarafından UTC biçiminde oluşturulduğu tarih ve saattir.

Aşağıdaki ekran görüntülerinde, iletiler otomatik genişletilmiş arşive taşınmadan önce ve sonra bir klasör listesi gösterilir.

 **Ek depolama eklenmeden önce**

![Arşivi otomatik olarak genişletmeden önce arşiv posta kutusunun klasör listesi sağlanır.](../media/5d6d6420-e562-4912-aaab-1c111762b3f6.png)

 **Ek depolama eklendikten sonra**

![Arşiv otomatik genişletildikten sonra arşiv posta kutusunun klasör listesi sağlanır.](../media/c03c5f51-23fa-4fc2-b887-7e7e5cce30da.png)

> [!NOTE]
> Daha önce açıklandığı gibi Microsoft Purview, içeriği yardımcı bir arşive dağıtmaya yardımcı olmak için öğeleri alt klasörlere taşır (ve yukarıda açıklanan adlandırma kuralını kullanarak adlandırır). Ancak öğeleri alt klasörlere taşımak her zaman geçerli olmayabilir. Bazen bir klasörün tamamı yardımcı bir arşive taşınabilir. Bu durumda, klasör özgün adını korur. Outlook'taki klasör listesinde klasörün yardımcı bir arşive taşındığı görülmeyecektir.

## <a name="outlook-requirements-for-accessing-items-in-an-auto-expanded-archive"></a>Otomatik genişletilmiş arşivdeki öğelere erişmek için Outlook gereksinimleri

Otomatik genişletilmiş arşivde depolanan iletilere erişmek için kullanıcıların aşağıdaki Outlook istemcilerinden birini kullanması gerekir:

- Kurumlar için Microsoft 365 Uygulamaları (eski adıyla Office 365 ProPlus) bir parçası olarak Outlook

- İş için Microsoft 365 Uygulamaları bir parçası olarak Outlook (eski adıyla Office 365 business)

- Windows için Outlook 2016 veya Outlook 2019

- Birincil posta kutusu şirket içi yerine Exchange Online olduğunda Web üzerinde Outlook

- mac için Outlook 2016 veya Outlook 2019

Otomatik genişletilmiş arşivde depolanan iletilere erişmek için Outlook veya Web üzerinde Outlook kullanırken göz önünde bulundurmanız gereken bazı noktalar şunlardır.

- Arşiv posta kutunuzda, otomatik olarak genişletilmiş depolama alanına taşınanlar da dahil olmak üzere herhangi bir klasöre erişebilirsiniz.

- Arşiv posta kutusunun en az bir otomatik genişletilmiş depolama alanı varsa, bir klasörü arşiv posta kutusundan veya yardımcı arşivden silemezsiniz. Başka bir deyişle, otomatik genişletilmiş bir depolama alanı sağlandıktan sonra arşivdeki hiçbir klasörü silemezsiniz.

- Otomatik olarak genişletilmiş depolama alanındaki öğeleri silebilirsiniz. Ancak, bir posta kutusu için otomatik genişletme arşivleme etkinleştirildikten sonra bir öğeyi kurtarmak için Silinmiş Öğeleri Kurtar özelliğini kullanamazsınız.

- Otomatik genişletilmiş arşivleme araması web için Outlook'ta (OWA) kullanılabilir. Çevrimiçi Arşiv'e benzer şekilde, ek bir depolama alanına taşınan öğeleri de arayabilirsiniz. OWA'da arama kapsamı olarak arşiv seçildiğinde, tüm arşivler (otomatik genişletilmiş arşivler dahil) ve bunlara karşılık gelen alt klasörler aranacaktır.

- Otomatik genişletilmiş arşiv araması, Windows için Outlook'ta Aylık Kurumsal Kanal'da kullanılabilir. Bu güncelleştirme ile Geçerli Posta Kutusu kapsamı kullanılabilir, böylece otomatik genişletilmiş arşivde arama yapmanızı sağlar. Yalnızca bulutta arşiv durumunda (birincil posta kutusu hala şirket içinde) otomatik genişletilmiş arşiv özelliği için aramanın desteklenmediğini unutmayın. Bu ve diğer Microsoft Search destek özellikleri hakkında daha fazla bilgi için bkz. [Windows için Outlook'un Exchange Online'a bağlı olması Microsoft Search'ün nasıl kullanıldığı](https://techcommunity.microsoft.com/t5/outlook-global-customer-service/how-outlook-for-windows-connected-to-exchange-online-utilizes/ba-p/1715045). 

- Outlook'taki öğe sayıları ve otomatik genişletilmiş arşivdeki Okundu/Okunmadı sayıları (Outlook'ta ve Web üzerinde Outlook) doğru olmayabilir.

## <a name="auto-expanding-archiving-and-other-compliance-features"></a>Arşivleme ve diğer uyumluluk özelliklerini otomatik genişletme

Bu bölümde, otomatik olarak genişleten arşivleme ile diğer uyumluluk ve veri idaresi özellikleri arasındaki işlevler açıklanmaktadır.

- **Ediscovery:** İçerik Arama veya In-Place eBulma gibi bir eBulma aracı kullandığınızda, otomatik genişletilmiş arşivdeki ek depolama alanları da aranıyor.

- **Saklama:** Exchange Online'da Dava Tutma veya eBulma servis talebi saklama ve Microsoft Purview uyumluluk portalı saklama ilkeleri gibi araçları kullanarak posta kutusunu beklemeye aldığınızda, otomatik olarak genişletilmiş arşivde bulunan içerik de beklemeye alınır.

- **Mesajlaşma kayıtları yönetimi (MRM):** Süresi dolmuş posta kutusu öğelerini kalıcı olarak silmek için Exchange Online'da MRM silme ilkelerini kullanırsanız, otomatik genişletilmiş arşivde bulunan süresi dolmuş öğeler de silinir.

- **İçeri aktarma hizmeti:** PST dosyalarını kullanıcının otomatik olarak genişletilmiş arşivine aktarmak için İçeri Aktarma Office 365 hizmetini kullanabilirsiniz. PST dosyalarından kullanıcının arşiv posta kutusuna en fazla 100 GB veri aktarabilirsiniz.

## <a name="next-steps"></a>Sonraki adımlar

Arşivlemenin otomatik olarak genişletilmesi hakkında daha fazla teknik ayrıntı için bkz. [Microsoft 365: Arşivleri Otomatik Genişletme SSS](https://techcommunity.microsoft.com/t5/exchange-team-blog/office-365-auto-expanding-archives-faq/ba-p/607784).

Otomatik genişletme arşivlemeyi etkinleştirmeye hazırsanız bkz. [Otomatik genişletme arşivlemeyi etkinleştirme](enable-autoexpanding-archiving.md).
