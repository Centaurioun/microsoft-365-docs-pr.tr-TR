---
title: İçerik için arama yapma
description: Exchange posta kutularında e-postayı, SharePoint sitelerindeki ve OneDrive konumlarındaki belgeleri ve Skype Kurumsal anlık ileti konuşmalarını hızla bulmak için Microsoft Purview uyumluluk portalı İçerik arama eBulma aracını kullanın.
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- highpri
- tier1
- purview-compliance
- content-search
ms.openlocfilehash: 68adc95f2839d1e45957f0ac98cbcf19f9985807
ms.sourcegitcommit: e7dbe3b0d97cd8c64b5ae15f990d5e4b1dc9c464
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2022
ms.locfileid: "68687915"
---
# <a name="search-for-content-using-the-content-search-tool"></a>İçerik arama aracını kullanarak içerik arama

Exchange posta kutularında e-postayı, SharePoint sitelerindeki ve OneDrive konumlarındaki belgeleri ve Skype Kurumsal anlık ileti konuşmalarını hızla bulmak için Microsoft Purview uyumluluk portalı İçerik arama aracını kullanın. Microsoft Teams ve Microsoft 365 Grupları gibi işbirliği araçlarında e-posta, belge ve anlık ileti konuşmalarını aramak için içerik arama aracını kullanabilirsiniz.
  
[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="search-for-content"></a>İçerik için arama yapma

İlk adım, arama yapılacak içerik konumlarını seçmek için İçerik arama aracını kullanmaya başlamak ve belirli öğeleri aramak için bir anahtar sözcük sorgusu yapılandırmaktır. Ya da sorguyu boş bırakıp hedef konumlardaki tüm öğeleri döndürebilirsiniz.

- İçerik araması [oluşturun ve çalıştırın](content-search.md).
- [Arama sorgularını oluşturun ve](keyword-queries-and-search-conditions.md) aramanızı daraltmak için koşulları kullanın.
- İçerik araması için [özellik başvurusu](content-search-reference.md).
- EBulma yöneticisinin kuruluşunuzdaki posta kutularının veya sitelerin yalnızca alt kümesini aramasını sağlayan [arama izinleri filtrelemesini yapılandırın](permissions-filtering-for-content-search.md).
- Microsoft 365'te şirket içi kullanıcılar için [bulut tabanlı posta kutularında arama](search-cloud-based-mailboxes-for-on-premises-users.md).
- Arama sonuçlarının [anahtar sözcük istatistiklerini görüntüleyin](view-keyword-statistics-for-content-search.md) ve gerekirse sorguyu daraltın.
- Kuruluşunuzun Microsoft 365'e aktardığı [üçüncü taraf verileri arayın](use-content-search-to-search-third-party-data-that-was-imported.md).
- [Gizli alıcıları](/exchange/policy-and-compliance/holds/preserve-bcc-recipients-and-group-members) aramanız için koruyun.

## <a name="perform-actions-on-content-you-find"></a>Bulduğunuz içerik üzerinde eylemler gerçekleştirme

Bir aramayı çalıştırdıktan ve gerektiği gibi daraltdıktan sonra, sonraki adım arama tarafından döndürülen sonuçlarla bir şeyler yapmaktır. Sonuçları yerel bilgisayarınıza aktarıp indirebilirsiniz veya kuruluşunuza yönelik bir e-posta saldırısı söz konusu olduğunda, kullanıcı posta kutularından arama sonuçlarını silebilirsiniz.

- [İçerik aramasının sonuçlarını dışarı aktarın](export-search-results.md) ve yerel bilgisayarınıza indirin..
- Virüs içeren iletiler, tehlikeli ekler veya kimlik avı [iletileri gibi e-posta iletilerini arayın ve silin](search-for-and-delete-messages-in-your-organization.md).
- Gerçek sonuçları dışarı aktarmadan içerik aramasının sonuçlarıyla ilgili bir [raporu](export-a-content-search-report.md) dışarı aktarın.

## <a name="learn-more-about-content-search"></a>İçerik arama hakkında daha fazla bilgi edinin

İçerik aramanın kullanımı kolaydır, ancak aynı zamanda güçlü bir araçtır. Sahne arkası, çok şey oluyor. Ne kadar çok bilgi edinip davranışını ve sınırlamalarını anlarsanız, kuruluşunuzun arama ve araştırma gereksinimleri için o kadar başarılı olursunuz.
  
- [bir](limits-for-content-search.md) kerede çalıştırabileceğiniz arama sayısı üst sınırı ve tek bir aramaya ekleyebileceğiniz maksimum içerik konumu sayısı gibi içerik arama sınırları.
- [Tahmini ve gerçek arama sonuçları ile arama sonuçlarını](differences-between-estimated-and-actual-ediscovery-search-results.md) dışarı aktarıp indirirken aralarında farklılıklar olmasının nedenleri.
- [Exchange ve SharePoint'te kısmen dizine alınmış öğeler](partially-indexed-items-in-content-search.md) ve arama sonuçlarını dışarı aktarıp indirirken bunları dahil etme veya dışlama.
- [Kısmen dizine alınan öğeleri araştırın](investigating-partially-indexed-items-in-ediscovery.md) ve kuruluşunuzun bunlara maruz kalmasını belirleyin.
- [Arama sonuçları olan e-posta](de-duplication-in-ediscovery-search-results.md) iletilerini dışarı aktarırken etkinleştirebileceğiniz arama sonuçlarında yinelenenleri kaldırma.

## <a name="use-scripts-for-advanced-scenarios"></a>Gelişmiş senaryolar için betikleri kullanma

Bazen daha gelişmiş, karmaşık ve yinelenen içerik arama görevleri gerçekleştirmeniz gerekir. Bu gibi durumlarda [, Güvenlik & Uyumluluk PowerShell'deki](/powershell/exchange/scc-powershell) komutları kullanmak daha kolay ve daha hızlıdır.

Bunu kolaylaştırmaya yardımcı olmak için, içerik aramayla ilgili karmaşık görevleri tamamlamanıza yardımcı olmak için çeşitli Güvenlik & Uyumluluğu PowerShell betikleri oluşturduk.

- Bir servis talebine yanıt veren öğelerin söz konusu klasörde bulunduğundan emin olduğunuzda [belirli posta kutusu ve site klasörlerinde](use-content-search-for-targeted-collections.md) (*hedeflenen* koleksiyon olarak adlandırılır) arama yapın.
- Kullanıcı listesi için [posta kutusunda ve OneDrive konumunda arama](search-the-mailbox-and-onedrive-for-business-for-a-list-of-users.md).
- Arama verilerini hızlı ve verimli bir şekilde tanımlamak [ve silmek için birden çok arama oluşturun, rapor](create-report-on-and-delete-multiple-content-searches.md) edin ve silin.
- [bir içerik aramasını kopyalayıp aynı içerik](clone-a-content-search.md) konumlarında çalıştırılacak farklı anahtar sözcük arama sorgularının sonuçlarını hızla karşılaştırın; veya yeni bir arama oluştururken çok sayıda içerik konumunu yeniden girmek zorunda kalmadan zaman kazanmak için betiği kullanın.
