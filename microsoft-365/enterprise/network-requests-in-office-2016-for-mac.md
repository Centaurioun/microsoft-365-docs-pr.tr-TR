---
title: Mac için Office'te ağ istekleri
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 11/9/2018
audience: ITPro
ms.topic: conceptual
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- scotvorg
- Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365_Setup
- seo-marvel-apr2020
search.appverid: MOM160
ms.assetid: afdae969-4046-44b9-9adb-f1bab216414b
description: Bu makalede, uygulamaların Office Mac hangi uç noktalara ve URL'lere erişmeye çalıştığı ve sağlanan hizmetler açıklanmaktadır.
ms.openlocfilehash: e42f5c8f9878ebd3e4ac40d77f96aa115c875e54
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68189769"
---
# <a name="network-requests-in-office-for-mac"></a>Mac için Office'te ağ istekleri

Office Mac uygulamaları, macOS platformunda yerel bir uygulama deneyimi sağlar. Her uygulama, ağ erişimi olmadığı durumlar da dahil olmak üzere çeşitli senaryolarda çalışacak şekilde tasarlanmıştır. Bir makine bir ağa bağlandığında, uygulamalar gelişmiş işlevsellik sağlamak için bir dizi web tabanlı hizmete otomatik olarak bağlanır. Aşağıdaki bilgiler, uygulamaların erişmeye çalıştığı uç noktaları ve URL'leri ve sağlanan hizmetleri açıklar. Bu bilgiler, ağ yapılandırma sorunlarını giderirken ve ağ proxy sunucuları için ilkeler ayarlarken yararlıdır. Bu makaledeki ayrıntılar, Microsoft Windows çalıştıran bilgisayarlar için uç noktaları içeren [Office 365 URL ve adres aralıkları makalesini](urls-and-ip-address-ranges.md) tamamlamaya yöneliktir. Not edilmediği sürece, bu makaledeki bilgiler bir perakende mağazasından veya toplu lisanslama sözleşmesi aracılığıyla tek seferlik satın alma olarak kullanılabilen Mac için Office 2019 ve Office Mac 2016 için de geçerlidir. 

  
Bu makalenin çoğu ağ URL'lerini, türünü ve bu uç nokta tarafından sağlanan hizmetin veya özelliğin açıklamasını açıklayan tablolardır. Office uygulamalarının her biri hizmet ve uç nokta kullanımı açısından farklılık gösterebilir. Aşağıdaki tablolarda aşağıdaki uygulamalar tanımlanmıştır:
  
- W: Word
- P: PowerPoint
- X: Excel
- O: Outlook
- N: OneNote
   
URL türü aşağıdaki gibi tanımlanır:
  
- ST: Statik - URL, istemci uygulamasına sabit olarak kodlanmıştır.
    
- SS: Semi-Static - URL bir web sayfasının veya yeniden yönlendiricinin bir parçası olarak kodlanmıştır.
    
- CS: Yapılandırma Hizmeti - URL, Office Yapılandırma Hizmeti'nin bir parçası olarak döndürülür.

    
## <a name="office-for-mac-default-configuration"></a>Varsayılan yapılandırmayı Office Mac

 **Yükleme ve güncelleştirmeler**
  
Microsoft Content Delivery Network'ten (CDN) Office Mac yükleme programını indirmek için aşağıdaki ağ uç noktaları kullanılır.
  
|**Url**|**Tür**|**Açıklama**|
|:-----|:-----|:-----|
|```https://go.microsoft.com/fwlink/```  <br/> |St  <br/> |Microsoft 365 Yükleme Portalı en son yükleme paketlerine bağlantı iletme hizmeti.  <br/> |
|```https://officecdn-microsoft-com.akamaized.net/```  <br/> |Ss  <br/> |Content Delivery Network'te yükleme paketlerinin konumu.  <br/> |
|```https://officecdn.microsoft.com/```  <br/> |Ss  <br/> |Content Delivery Network'te yükleme paketlerinin konumu.  <br/> |
|```https://officeci-mauservice.azurewebsites.net/```  <br/> |St  <br/> |Microsoft AutoUpdate için Yönetim Denetimi uç noktası  <br/> |
   
 **İlk uygulama başlatma**
  
Bir Office uygulamasının ilk başlatılmasında aşağıdaki ağ uç noktalarıyla bağlantı kurulmaktadır. Bu uç noktalar kullanıcılar için gelişmiş Office işlevselliği sağlar ve lisans türüne bakılmaksızın URL'lerle bağlantı kurulmaktadır (Toplu Lisans yüklemeleri dahil).
  
|**Url**|**Apps**|**Tür**|**Açıklama**|
|:-----|:-----|:-----|:-----|
|```https://config.edge.skype.com/```  <br/> |WXPON  <br/> |St  <br/> |'Uçuş' Yapılandırması - Özelliğin ışıklandırmasına ve denemesine olanak tanır.  <br/> |
|```https://ocos-office365-s2s.msedge.net/```  <br/> |WXPON  <br/> |St  <br/> |'Uçuş' Ağ Yapılandırma Testi  <br/> |
|```https://client-office365-tas.msedge.net/```  <br/> |WXPON  <br/> |St  <br/> |'Uçuş' Ağ Yapılandırma Testi  <br/> |
|```https://officeclient.microsoft.com/```  <br/> |WXPON  <br/> |St  <br/> |Office Yapılandırma Hizmeti - Hizmet uç noktalarının ana listesi.  <br/> |
|```https://nexusrules.officeapps.live.com/```  <br/> |WXPON  <br/> |St  <br/> |Office Kuralları Telemetrisini indirme - İstemciyi telemetri hizmetine yüklenecek veriler ve olaylar hakkında bilgilendirmektedir.  <br/> |
|```https://mobile.pipe.aria.microsoft.com/```  <br/> |N  <br/> |Cs  <br/> |OneNote Telemetri Hizmeti  <br/> |
|```https://nexus.officeapps.live.com/```  <br/> |WXPON  <br/> |St  <br/> |Office Telemetrisi Karşıya Yükleme Raporlaması - İstemcide gerçekleşen "Heartbeart" ve hata olayları telemetri hizmetine yüklenir.  <br/> |
|```https://templateservice.office.com/```  <br/> |WXP  <br/> |Cs  <br/> |Office Şablon Hizmeti - Kullanıcılara çevrimiçi belge şablonları sağlar.  <br/> |
|```https://omextemplates.content.office.net/```  <br/> |WXP  <br/> |Cs  <br/> |Office Şablonları İndirmeleri - PNG şablon görüntülerinin depolanması.  <br/> |
|```https://store.office.com/```  <br/> |WXP  <br/> |Cs  <br/> |Office uygulamaları için depolama yapılandırması.  <br/> |
|```https://odc.officeapps.live.com/```  <br/> |WXPN  <br/> |Cs  <br/> |Office Belge Tümleştirme Hizmetleri Kataloğu (hizmetlerin ve uç noktaların listesi) ve Ev Bölgesi Bulma.  <br/> |
|```https://cdn.odc.officeapps.live.com/```  <br/> |WXPON  <br/> |Cs  <br/> |Ev Bölgesi Bulma v2 (15.40 ve üzeri) kaynakları  <br/> |
|```https://officecdn.microsoft.com/```  <br/> |WXPON  <br/> |St  <br/> |Microsoft AutoUpdate Bildirimleri - Kullanılabilir güncelleştirme olup olmadığını denetler  <br/> |
|```https://ajax.aspnetcdn.com/```  <br/> |WXPO  <br/> |Ss  <br/> |Microsoft Ajax JavaScript Kitaplığı  <br/> |
|```https://wikipedia.firstpartyapps.oaspapps.com/```  <br/> |W  <br/> |Ss  <br/> |Office yapılandırması ve kaynakları için Wikipedia uygulaması.  <br/> |
|```https://excelbingmap.firstpartyapps.oaspapps.com/```  <br/> |X  <br/> |Ss  <br/> |Office yapılandırması ve kaynakları için Bing Eşleme uygulaması.  <br/> |
|```https://peoplegraph.firstpartyapps.oaspapps.com/```  <br/> |X  <br/> |Ss  <br/> |Office yapılandırması ve kaynakları için Graph uygulamasını Kişiler.  <br/> |
|```https://www.onenote.com/```  <br/> |N  <br/> |St  <br/> |OneNote'un Yeni içeriği.  <br/> |
|```https://site-cdn.onenote.net/```  <br/> |N  <br/> |St  <br/> |OneNote için yeni içerik.  <br/> |
|```https://site-cdn.onenote.net/```  <br/> |N  <br/> |Ss  <br/> |OneNote'un Yeni görüntüleri.  <br/> |
|```https://acompli.helpshift.com/```  <br/> |O  <br/> |St  <br/> |Uygulama içi Destek Hizmeti.  <br/> |
|```https://prod-global-autodetect.acompli.net/```  <br/> |O  <br/> |St  <br/> |Hesap Algılama Hizmeti'ne Email.  <br/> |
|```https://autodiscover-s.outlook.com/```  <br/> |WXPO  <br/> |St  <br/> |Outlook Otomatik Bulma  <br/> |
|```https://outlook.office365.com/```  <br/> |WXPO  <br/> |St  <br/> |Microsoft 365 hizmeti için Outlook uç noktası.  <br/> |
|```https://r1.res.office365.com/```  <br/> |O  <br/> |St  <br/> |Outlook eklentilerinin simgeleri.  <br/> |
   
> [!NOTE]
> Office Yapılandırma Hizmeti, yalnızca Mac için değil, tüm Microsoft Office istemcileri için otomatik bulma hizmeti işlevi görür. Yanıtta döndürülen uç noktalar yarı statiktir, bu değişiklik çok seyrek olsa da yine de mümkündür. 
  
 **Oturum aç**
  
Bulut tabanlı depolamada oturum açarken aşağıdaki ağ uç noktalarıyla bağlantı kurulur. Hesap türünüze bağlı olarak farklı hizmetlerle iletişim kurulabilir. Örneğin:
  
- **MSA: Microsoft Hesabı** - genellikle tüketici ve perakende senaryoları için kullanılır 
    
- **OrgID: Kuruluş Hesabı** - genellikle ticari senaryolar için kullanılır 
    
|**Url**|**Apps**|**Tür**|**Açıklama**|
|:-----|:-----|:-----|:-----|
|```https://login.windows.net/```  <br/> |WXPON  <br/> |St  <br/> |Windows Yetkilendirme Hizmeti  <br/> |
|```https://login.microsoftonline.com/```  <br/> |WXPON  <br/> |St  <br/> |Microsoft 365 Oturum Açma Hizmeti (OrgID)  <br/> |
|```https://login.live.com/```  <br/> |WXPON  <br/> |St  <br/> |Microsoft Hesabı Oturum Açma Hizmeti (MSA)  <br/> |
|```https://auth.gfx.ms/```  <br/> |WXPON  <br/> |Cs  <br/> |Microsoft Hesabı Oturum Açma Hizmeti Yardımcısı (MSA)  <br/> |
|```https://secure.aadcdn.microsoftonline-p.com/```  <br/> |WXPON  <br/> |Ss  <br/> |Microsoft 365 Oturum Açma Markası (OrgID)  <br/> |
|```https://ocws.officeapps.live.com/```  <br/> |WXPN  <br/> |Cs  <br/> |Belge ve Yer Depolama Bulucu  <br/> |
|```https://roaming.officeapps.live.com/```  <br/> |WXPN  <br/> |Cs  <br/> |En Son Kullanılan (MRU) belge hizmeti  <br/> |
   
> [!NOTE]
> Abonelik tabanlı ve perakende lisanslarda oturum açmak hem ürünü etkinleştirir hem de OneDrive gibi bulut kaynaklarına erişim sağlar. Toplu Lisans yüklemelerinde kullanıcılardan hala oturum açmaları istenir (varsayılan olarak), ancak ürün zaten etkinleştirildiğinden bu yalnızca bulut kaynaklarına erişim için gereklidir. 
  
 **Ürün etkinleştirme**
  
Aşağıdaki ağ uç noktaları Microsoft 365 Aboneliği ve Perakende Lisansı etkinleştirmeleri için geçerlidir. Özel olarak, bu Toplu Lisans yüklemeleri için GEÇERLI OLMAZ.
  
|**Url**|**Apps**|**Tür**|**Açıklama**|
|:-----|:-----|:-----|:-----|
|```https://ols.officeapps.live.com/```  <br/> |WXPON  <br/> |Cs  <br/> |Office Lisanslama Hizmeti  <br/> |
   
 **Yenilikler içeriği**
  
Aşağıdaki ağ uç noktaları yalnızca Microsoft 365 Aboneliği için geçerlidir.
  
|**Url**|**Apps**|**Tür**|**Açıklama**|
|:-----|:-----|:-----|:-----|
|```https://contentstorage.osi.office.net/```  <br/> |WXPO  <br/> |Ss  <br/> |Yenilikler JSON sayfası içeriği.  <br/> |
   
 **Araştırmacı**
  
Aşağıdaki ağ uç noktaları yalnızca Microsoft 365 Aboneliği için geçerlidir.
  
|**Url**|**Apps**|**Tür**|**Açıklama**|
|:-----|:-----|:-----|:-----|
|```https://entity.osi.office.net/```  <br/> |W  <br/> |Cs  <br/> |Araştırmacı Web Hizmeti  <br/> |
|```https://cdn.entity.osi.office.net/```  <br/> |W  <br/> |Cs  <br/> |Araştırmacı Statik İçeriği  <br/> |
|```https://www.bing.com/```  <br/> |W  <br/> |Cs  <br/> |Araştırmacı İçerik Sağlayıcısı  <br/> |
   
 **Akıllı Arama**
  
Aşağıdaki ağ uç noktaları hem Microsoft 365 Aboneliği hem de Perakende/Toplu Lisans etkinleştirmeleri için geçerlidir.
  
|**Url**|**Apps**|**Tür**|**Açıklama**|
|:-----|:-----|:-----|:-----|
|```https://uci.officeapps.live.com/```  <br/> |WXPN  <br/> |Cs  <br/> |İçgörüler Web Hizmeti  <br/> |
|```https://ajax.googleapis.com/```  <br/> |WXPN  <br/> |Cs  <br/> |JQuery Kitaplığı  <br/> |
|```https://cdnjs.cloudflare.com/```  <br/> |WXPN  <br/> |Cs  <br/> |JavaScript Kitaplığını Destekleme  <br/> |
|```https://www.bing.com/```  <br/> |WXPN  <br/> |Cs  <br/> |İçgörüler İçerik Sağlayıcısı  <br/> |
|```https://tse1.mm.bing.net/```  <br/> |WXPN  <br/> |Cs  <br/> |İçgörüler İçerik Sağlayıcısı  <br/> |
   
 **PowerPoint Tasarımcısı**
  
Aşağıdaki ağ uç noktaları yalnızca Microsoft 365 Aboneliği için geçerlidir.
  
|**Url**|**Apps**|**Tür**|**Açıklama**|
|:-----|:-----|:-----|:-----|
|```https://pptsgs.officeapps.live.com/```  <br/> |P  <br/> |Cs  <br/> |PowerPoint Designer web hizmeti  <br/> |
   
 **PowerPoint Hızlı Başlangıç**
  
Aşağıdaki ağ uç noktaları yalnızca Microsoft 365 Aboneliği için geçerlidir.
  
|**Url**|**Apps**|**Tür**|**Açıklama**|
|:-----|:-----|:-----|:-----|
|```https://pptcts.officeapps.live.com/```  <br/> |P  <br/> |Cs  <br/> |PowerPoint Hızlı Başlangıç web hizmeti  <br/> |
   
 **Gülümseme/Kaş Çatma Gönder**
  
Aşağıdaki ağ uç noktaları hem Microsoft 365 Aboneliği hem de Perakende/Toplu Lisans etkinleştirmeleri için geçerlidir.
  
|**Url**|**Apps**|**Tür**|**Açıklama**|
|:-----|:-----|:-----|:-----|
|```https://sas.office.microsoft.com/```  <br/> |WXPON  <br/> |Cs  <br/> |Gülümseme Hizmeti Gönder  <br/> |
   
 **Desteğe Başvurun**
  
Aşağıdaki ağ uç noktaları hem Microsoft 365 Aboneliği hem de Perakende/Toplu Lisans etkinleştirmeleri için geçerlidir.
  
|**Url**|**Apps**|**Tür**|**Açıklama**|
|:-----|:-----|:-----|:-----|
|```https://powerlift-frontdesk.acompli.net/```  <br/> |O  <br/> |Cs  <br/> |Destek Hizmeti ile iletişime geçin  <br/> |
|```https://acompli.helpshift.com/```  <br/> |O  <br/> |Cs  <br/> |Uygulama İçi Destek Hizmeti  <br/> |
   
 **PDF Olarak Kaydet**
  
Aşağıdaki ağ uç noktaları hem Microsoft 365 Aboneliği hem de Perakende/Toplu Lisans etkinleştirmeleri için geçerlidir.
  
|**Url**|**Apps**|**Tür**|**Açıklama**|
|:-----|:-----|:-----|:-----|
|```https://wordcs.officeapps.live.com/```  <br/> |W  <br/> |Cs  <br/> |Word belge dönüştürme hizmeti (PDF)  <br/> |
   
 **Office Uygulamaları (diğer adıyla eklentiler)**
  
Office Uygulaması eklentilerine güvenildiğinde, aşağıdaki ağ uç noktaları hem Microsoft 365 Aboneliği hem de Perakende/Toplu Lisans etkinleştirmeleri için geçerlidir.
  
|**Url**|**Apps**|**Tür**|**Açıklama**|
|:-----|:-----|:-----|:-----|
|```https://store.office.com/```  <br/> |WXPO  <br/> |Cs  <br/> |Office uygulama mağazası yapılandırması  <br/> |
|```https://wikipedia.firstpartyapps.oaspapps.com/```  <br/> |W  <br/> |Ss  <br/> |Wikipedia uygulama kaynakları  <br/> |
|```https://excelbingmap.firstpartyapps.oaspapps.com/```  <br/> |X  <br/> |Ss  <br/> |Bing Eşleme uygulaması kaynakları  <br/> |
|```https://peoplegraph.firstpartyapps.oaspapps.com```  <br/> |X  <br/> |Ss  <br/> |graph uygulama kaynaklarını Kişiler  <br/> |
|```https://o15.officeredir.microsoft.com/```  <br/> |WPX  <br/> |Ss  <br/> |Office Yeniden Yönlendirme Hizmeti  <br/> |
|```https://appsforoffice.microsoft.com/```  <br/> |WXP  <br/> |Ss  <br/> |Office JavaScript Kitaplıkları  <br/> |
|```https://telemetry.firstpartyapps.oaspapps.com/```  <br/> |Wx  <br/> |Ss  <br/> |Office uygulamaları için Telemetri ve Raporlama Hizmeti  <br/> |
|```https://ajax.microsoft.com/```  <br/> |W  <br/> |Ss  <br/> |Microsoft Ajax JavaScript Kitaplığı  <br/> |
|```https://ajax.aspnetcdn.com/```  <br/> |X  <br/> |Ss  <br/> |Microsoft Ajax JavaScript Kitaplığı  <br/> |
|```https://c.microsoft.com/```  <br/> |WPXO  <br/> |Ss  <br/> |Office JavaScript Kitaplıkları  <br/> |
|```https://c1.microsoft.com/```  <br/> |WPXO  <br/> |Ss  <br/> |Destek kaynakları  <br/> |
|```https://cs.microsoft.com/```  <br/> |WPXO  <br/> |Ss  <br/> |Destek kaynakları  <br/> |
|```https://c.bing.com/```  <br/> |WPXO  <br/> |Ss  <br/> |Destek kaynakları  <br/> |
|```https://*.cdn.optimizely.com/```  <br/> |WPXO  <br/> |Ss  <br/> |JavaScript kitaplığı  <br/> |
|```https://errors.client.optimizely.com/```  <br/> |WPX  <br/> |Ss  <br/> |Hata raporlama  <br/> |
|```https://*-contentstorage.osi.office.net/```  <br/> |WPXO  <br/> |Ss  <br/> |Yazı tipi kaynakları  <br/> |
|```https://nexus.ensighten.com/```  <br/> |WPXO  <br/> |Ss  <br/> |Telemetri Hizmeti  <br/> |
|```https://browser.pipe.aria.microsoft.com/```  <br/> |WPXO  <br/> |Ss  <br/> |Telemetri Raporlama  <br/> |
|```https://*.vo.msecnd.net/```  <br/> |WPXO  <br/> |Ss  <br/> |Microsoft Store Varlık Kitaplığı  <br/> |
|```https://*.wikipedia.org/```  <br/> |W  <br/> |Ss  <br/> |Wikipedia sayfası kaynakları  <br/> |
|```https://upload.wikimedia.org/```  <br/> |W  <br/> |Ss  <br/> |Wikipedia medya kaynakları  <br/> |
|```https://wikipedia.firstpartyappssandbox.oappseperate.com/```  <br/> |W  <br/> |Ss  <br/> |Wikipedia korumalı alan çerçevesi  <br/> |
|```https://*.virtualearth.net/```  <br/> |X  <br/> |Ss  <br/> |Harita şablonları  <br/> |
   
 **Güvenli Bağlantılar**
  
Aşağıdaki ağ uç noktası yalnızca Microsoft 365 Aboneliği için tüm Office uygulamaları için geçerlidir.
  
|**Url**|**Tür**|**Açıklama**|
|:-----|:-----|:-----|
|```https://*.oscs.protection.outlook.com/```  <br/> |Cs  <br/> |Microsoft Güvenli Bağlantı Hizmeti  <br/> |
   
 **Kilitlenme raporlama**
  
Aşağıdaki ağ uç noktası hem Microsoft 365 Aboneliği hem de Perakende/Toplu Lisans etkinleştirmeleri için tüm Office uygulamaları için geçerlidir. Bir işlem beklenmedik bir şekilde kilitlendiğinde, bir rapor oluşturulur ve Watson hizmetine gönderilir.
  
|**Url**|**Tür**|**Açıklama**|
|:-----|:-----|:-----|
|```https://watson.microsoft.com/```  <br/> |St  <br/> |Microsoft Hata Raporlama Hizmeti  <br/> |
|```https://officeci.azurewebsites.net/```  <br/> |St  <br/> |Office İşbirliğine Dayalı İçgörüler Hizmeti  <br/> |
   
## <a name="options-for-reducing-network-requests-and-traffic"></a>Ağ isteklerini ve trafiği azaltma seçenekleri

Office Mac varsayılan yapılandırması, hem işlevsellik hem de makineyi güncel tutma açısından en iyi kullanıcı deneyimini sağlar. Bazı senaryolarda, uygulamaların ağ uç noktalarıyla iletişim kurmasını engellemek isteyebilirsiniz. Bu bölümde bunu yapma seçenekleri açıklanmaktadır.
  
 ### <a name="disabling-cloud-sign-in-and-office-add-ins"></a>Bulut Sign-In ve Office Add-Ins devre dışı bırakma
  
Toplu Lisans müşterileri, belgeleri bulut tabanlı depolamaya kaydetme konusunda katı ilkelere sahip olabilir. Aşağıdaki uygulama başına tercih, MSA/OrgID Oturum Açma'yı devre dışı bırakmak ve Office Eklentileri'ne erişimi devre dışı bırakmak için ayarlanabilir.
  
- ```defaults write com.microsoft.Word UseOnlineContent -integer 0```

- ```defaults write com.microsoft.Excel UseOnlineContent -integer 0```

- ```defaults write com.microsoft.Powerpoint UseOnlineContent -integer 0```

Kullanıcılar Sign-In işlevine erişmeye çalışırsa, ağ bağlantısının mevcut olmadığını belirten bir hata görürler. Bu tercih çevrimiçi ürün etkinleştirmeyi de engellediğinden, yalnızca Toplu Lisans yüklemeleri için kullanılmalıdır. Özellikle, bu tercihin kullanılması Office uygulamalarının aşağıdaki uç noktalara erişmesini engeller:
  
- ```https://odc.officeapps.live.com```
    
- ```https://*.firstpartyapps.oaspapps.com```
    
- Yukarıdaki 'Oturum Aç' bölümünde listelenen tüm uç noktalar.
    
- Yukarıdaki 'Akıllı Arama' bölümünde listelenen tüm uç noktalar.
    
- Yukarıdaki 'Ürün Etkinleştirmesi' bölümünde listelenen tüm uç noktalar.
    
- Yukarıdaki 'Office Uygulamaları (diğer adıyla eklentiler)' bölümünde listelenen tüm uç noktalar.
    
Kullanıcının tam işlevselliğini yeniden oluşturmak için tercihi '2' olarak ayarlayın veya kaldırın.
  
> [!NOTE]
> Bu tercih için Office Mac derleme 15.25 [160726] veya üzeri gerekir. 
  
### <a name="telemetry"></a>Telemetri 
  
Office Mac düzenli aralıklarla telemetri bilgilerini Microsoft'a geri gönderir. Veriler 'Nexus' uç noktasına yüklenir. Telemetri verileri, mühendislik ekibinin her Office uygulamasının durumunu ve beklenmeyen davranışlarını değerlendirmesine yardımcı olur. Telemetrinin iki kategorisi vardır:
  
- **Sinyal** sürüm ve lisans bilgilerini içerir. Bu veriler uygulama başlatıldığında hemen gönderilir. 
    
- **Kullanım** , uygulamaların nasıl kullanıldığı ve önemli olmayan hatalar hakkında bilgi içerir. Bu veriler her 60 dakikada bir gönderilir. 
    
Microsoft gizliliğinizi çok ciddiye alır. Microsoft'un veri toplama ilkesi hakkındaki bilgileri adresinden [https://privacy.microsoft.com](https://privacy.microsoft.com)okuyabilirsiniz. Uygulamaların 'Kullanım' telemetrisi göndermesini önlemek için **SendAllTelemetryEnabled** tercihi ayarlanabilir. Tercih uygulama başınadır ve macOS Yapılandırma Profilleri aracılığıyla veya Terminal'den el ile ayarlanabilir: 
  
```defaults write com.microsoft.Word SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.Excel SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.Powerpoint SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.Outlook SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.onenote.mac SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.autoupdate2 SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.Office365ServiceV2 SendAllTelemetryEnabled -bool FALSE```

Sinyal telemetrisi her zaman gönderilir ve devre dışı bırakılamaz.
  
### <a name="crash-reporting"></a>Kilitlenme raporlama
  
Önemli bir uygulama hatası oluştuğunda uygulama beklenmedik şekilde sonlandırılır ve 'Watson' hizmetine bir kilitlenme raporu yüklenir. Kilitlenme raporu, uygulamanın kilitlenmeye yol açan adımların listesi olan bir çağrı yığınından oluşur. Bu adımlar mühendislik ekibinin başarısız olan tam işlevi ve nedenini belirlemesine yardımcı olur.
  
Bazı durumlarda, belgenin içeriği uygulamanın kilitlenmesine neden olur. Uygulama belgeyi neden olarak tanımlarsa, kullanıcıya belgeyi çağrı yığınıyla birlikte göndermenin uygun olup olmadığını sorar. Kullanıcılar bu soruya bilinçli bir seçim yapabilir. BT yöneticileri, belgelerin iletimi konusunda katı gereksinimlere sahip olabilir ve kullanıcı adına hiçbir zaman belge göndermemeye karar verebilir. Belgelerin gönderilmesini önlemek ve kullanıcıya istemi engellemek için aşağıdaki tercih ayarlanabilir:
  
```defaults write com.microsoft.errorreporting IsAttachFilesEnabled -bool FALSE```

> [!NOTE]
> **SendAllTelemetryEnabled** **FALSE** olarak ayarlanırsa, bu işlemin tüm kilitlenme raporlaması devre dışı bırakılır. Kullanım telemetrisi göndermeden kilitlenme raporlamayı etkinleştirmek için aşağıdaki tercih ayarlanabilir: ```defaults write com.microsoft.errorreporting IsMerpEnabled -bool TRUE``` 
  
### <a name="updates"></a>Güncelleştirmeler
  
Microsoft düzenli aralıklarla (genellikle ayda bir kez) güncelleştirmeler Office Mac yayınlar. En son güvenlik düzeltmelerinin yüklendiğinden emin olmak için kullanıcıların ve BT yöneticilerinin makineleri güncel tutmalarını kesinlikle öneririz. BT yöneticilerinin makine güncelleştirmelerini yakından denetlemek ve yönetmek istediği durumlarda, Otomatik Güncelleştirme işleminin ürün güncelleştirmelerini otomatik olarak algılamasını ve sunmasını önlemek için aşağıdaki tercih ayarlanabilir:
  
```defaults write com.microsoft.autoupdate2 HowToCheck -string 'Manual'```

### <a name="blocking-requests-with-a-firewallproxy"></a>Güvenlik Duvarı/Ara Sunucu ile İstekleri Engelleme
  
Kuruluşunuz bir güvenlik duvarı veya ara sunucu aracılığıyla URL'lere yönelik istekleri engelliyorsa, bu belgede listelenen URL'leri izin verilen veya 40X yanıtla listelenen URL'leri (ör. 403 veya 404) yapılandırıldığından emin olun. 40X yanıtı, Office uygulamalarının kaynağa erişememe durumunu düzgün bir şekilde kabul etmelerine olanak tanır ve bağlantıyı bırakmaktan daha hızlı bir kullanıcı deneyimi sağlar ve bu da istemcinin yeniden denemesine neden olur.
  
Proxy sunucunuz kimlik doğrulaması gerektiriyorsa istemciye 407 yanıtı döndürülür. En iyi deneyim için, NTLM ve Kerberos sunucularıyla çalışmaya yönelik belirli düzeltmeler içerdiğinden Office Mac derlemeleri 15.27 veya üzerini kullandığınızdan emin olun.
  
  
## <a name="see-also"></a>Ayrıca bkz.

[Office 365 URL’leri ve IP adresi aralıkları](urls-and-ip-address-ranges.md)

