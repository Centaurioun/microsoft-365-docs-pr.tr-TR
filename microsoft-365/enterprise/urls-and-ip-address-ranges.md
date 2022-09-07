---
title: Office 365 URL’leri ve IP adresi aralıkları
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 08/29/2022
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: high
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- MOM160
- BCS160
ms.assetid: 8548a211-3fe7-47cb-abb1-355ea5aa88a2
description: 'Özet: Office 365 için internet bağlantısı gerekir. Government Community Cloud (GCC) dahil olmak üzere Office 365 planlarını kullanan müşteriler aşağıdaki uç noktalara erişebilmelidir.'
hideEdit: true
ms.openlocfilehash: c473fdd8c15568ea6f7e58d2570b8d8bad053783
ms.sourcegitcommit: 651610ca73bfd1d008d97311b59782790df664fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2022
ms.locfileid: "67613307"
---
# <a name="office-365-urls-and-ip-address-ranges"></a>Office 365 URL’leri ve IP adresi aralıkları

Office 365 için internet bağlantısı gerekir. Government Community Cloud (GCC) dahil olmak üzere Office 365 planlarını kullanan müşteriler aşağıdaki uç noktalara erişebilmelidir.
  
*Office 365 Dünya Çapında (+GCC)* \| [Office 365 21 Vianet tarafından sağlanan](urls-and-ip-address-ranges-21vianet.md) \| [Office 365 ABD Hükümeti DoD](microsoft-365-u-s-government-dod-endpoints.md) \| [Office 365 ABD Hükümeti GCC High](microsoft-365-u-s-government-gcc-high-endpoints.md) \|

|Notlar|İndir|Kullanım|
|---|---|---|
|**Son güncelleştirme:** 29.08.2022 - ![RSS.](../media/5dc6bb29-25db-4f44-9580-77c735492c4b.png) [Günlük aboneliğini değiştir](https://endpoints.office.com/version/worldwide?allversions=true&format=rss&clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7)|**İndirin:** tüm gerekli ve isteğe bağlı hedeflerin [JSON olarak biçimlendirilmiş](https://endpoints.office.com/endpoints/worldwide?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7) bir listesi.|**Kullanın:** [PAC dosyaları](managing-office-365-endpoints.md#pacfiles) proxy’miz|
|

Bu verileri kullanarak ağ bağlantısını yönetmeye yönelik önerilerimizi anlamak için [Office 365 uç noktalarını yönetme](managing-office-365-endpoints.md) ile başlayın. Uç nokta verileri, etkin olmadan 30 gün önce yayınlanan yeni IP Adresleri ve URL'ler ile her ayın başında gerektiği gibi güncelleştirilir. Bu tempo, henüz otomatik güncelleştirmeleri olmayan müşterilerin, yeni bağlantı gerekmeden önce işlemlerini tamamlamalarına olanak tanır. Destek artışlarını, güvenlik olaylarını veya diğer acil operasyonel gereksinimleri ele almak için gerekirse uç noktalar da ay boyunca güncelleştirilebilir. Aşağıdaki bu sayfada gösterilen verilerin tümü REST tabanlı web hizmetlerinden oluşturulmuştur. Bu verilere erişmek için bir betik veya bir ağ cihazı kullanıyorsanız, doğrudan [Web hizmetine](microsoft-365-ip-web-service.md) gitmelisiniz.

Aşağıdaki uç nokta verileri, bir kullanıcının makinesinden Office 365'e bağlantı için gereksinimleri listeler. Microsoft'tan bir müşteri ağına, bazen karma veya gelen ağ bağlantıları olarak adlandırılan ağ bağlantıları için kullanılan IP adresleri hakkında ayrıntılar ve daha fazla bilgi için bkz. [Ek uç noktalar](additional-office365-ip-addresses-and-urls.md).

Uç noktalar, üç birincil iş yükünü ve bir dizi ortak kaynağı temsil eden dört hizmet alanında gruplandırılmıştır. Gruplar, trafik akışlarını belirli bir uygulamayla ilişkilendirmek için kullanılabilir, ancak özelliklerin genellikle birden çok iş yükündeki uç noktaları tükettiği göz önüne alındığında, bu gruplar erişimi kısıtlamak için etkin bir şekilde kullanılamaz.

Gösterilen veri sütunları şunlardır:

- **Kimlik**: Uç nokta kümesi olarak da bilinen satırın kimlik numarası. Bu kimlik, uç nokta kümesi için web hizmeti tarafından döndürülen kimlikle aynıdır.

- **Kategori**: Uç nokta kümesinin **İyileştir**, **İzin Ver** veya **Varsayılan** olarak kategorize edilip edilmediğini gösterir. Bu sütun ayrıca ağ bağlantısına sahip olmak için hangi uç nokta kümelerinin gerekli olduğunu da listeler. Ağ bağlantısına sahip olması gerekmeyen uç nokta kümeleri için, uç nokta kümesi engellenirse hangi işlevlerin eksik olacağını belirtmek için bu alanda notlar sağlarız. Bir hizmet alanının tamamını dışlarsanız, gerekli olarak listelenen uç nokta kümeleri bağlantı gerektirmez.

   [Yeni Office 365 uç nokta kategorileri](microsoft-365-network-connectivity-principles.md#new-office-365-endpoint-categories) bölümünde bu kategoriler ve bunların yönetimine yönelik yönergeler hakkında bilgi edinebilirsiniz.

- **HATA**: Uç nokta kümesi, Office 365 yol önekleriyle Azure ExpressRoute üzerinden destekleniyorsa bu **Evet**'tir. Gösterilen yol öneklerini içeren BGP topluluğu, listelenen hizmet alanıyla hizalanır. HATA **Hayır** olduğunda, ExpressRoute'un bu uç nokta kümesi için desteklenmediği anlamına gelir.

   Bazı yollar birden fazla BGP topluluğunda tanıtılabilir ve bu da belirli bir IP aralığındaki uç noktaların ER bağlantı hattından geçiş yapmasını mümkün hale getirir, ancak yine de desteklenmez. Her durumda, belirli bir uç nokta kümesinin ER sütununun değerine uyulmalıdır. BGP toplulukları hakkında daha fazla bilgi için bkz. [Office 365 senaryoları için ExpressRoute'ta BGP topluluklarını kullanma](bgp-communities-in-expressroute.md#key-planning-considerations-to-using-bgp-communities).

- **Adresler**: Uç nokta kümesi için FQDN'leri veya joker alan adlarını ve IP adresi aralıklarını listeler. IP adresi aralığının CIDR biçiminde olduğunu ve belirtilen ağda birçok bağımsız IP adresi içerebileceğini unutmayın.

- **Bağlantı Noktaları**: Ağ uç noktasını oluşturmak için listelenen IP adresleriyle birleştirilen TCP veya UDP bağlantı noktalarını listeler. Listelenen farklı bağlantı noktalarının bulunduğu IP adresi aralıklarında bazı yinelemeler görebilirsiniz.

[!INCLUDE [Office 365 worldwide endpoints](../includes/office-365-worldwide-endpoints.md)]

> [!NOTE]
> Yammer IP adresleri ve URL'leriyle ilgili öneriler için, Yammer blogunda [Yammer için sabit kodlanmış IP adreslerinin kullanılması önerilmez](https://techcommunity.microsoft.com/t5/Yammer-Blog/Using-hard-coded-IP-addresses-for-Yammer-is-not-recommended/ba-p/276592) konusuna bakın.

## <a name="related-topics"></a>İlgili Konular

[Office 365 IP Adresi ve URL Web hizmetine dahil olmayan ek uç noktalar](additional-office365-ip-addresses-and-urls.md)

[Office 365 uç noktalarını yönetme](managing-office-365-endpoints.md)

[Genel Microsoft Stream uç noktaları](/stream/network-overview#general-microsoft-stream-endpoints)
  
[Microsoft 365 bağlantısını izleyin](./monitor-connectivity.md)

[Üçüncü taraf uygulama sisteminde Kök CA ve Ara CA paketi](../compliance/encryption-office-365-certificate-chains.md)
  
[İstemci bağlantısı](https://support.office.com/article/client-connectivity-4232abcf-4ae5-43aa-bfa1-9a078a99c78b)
  
[İçerik teslim ağları](https://support.office.com/article/content-delivery-networks-0140f704-6614-49bb-aa6c-89b75dcd7f1f)
  
[Microsoft Azure IP Aralıkları ve Hizmet Etiketleri – Genel Bulut](https://www.microsoft.com/download/details.aspx?id=56519)

[Microsoft Azure IP Aralıkları ve Hizmet Etiketleri – ABD Hükümeti Bulutu](https://www.microsoft.com/download/details.aspx?id=57063)

[Microsoft Azure IP Aralıkları ve Hizmet Etiketleri – Çin Bulutu](https://www.microsoft.com/download/details.aspx?id=57062)
  
[Microsoft Genel IP Alanı](https://www.microsoft.com/download/details.aspx?id=53602)

[Hizmet Adı ve Aktarım Protokolü Bağlantı Noktası Numarası Kayıt Defteri Girişi](https://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xhtml)
