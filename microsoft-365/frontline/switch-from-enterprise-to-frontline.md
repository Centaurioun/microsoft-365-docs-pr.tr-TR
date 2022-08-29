---
title: Microsoft 365 E planından Microsoft 365 F planına geçiş
author: LanaChin
ms.author: v-lanachin
ms.reviewer: ''
manager: samanro
ms.topic: article
audience: admin
ms.service: microsoft-365-frontline
search.appverid: MET150
description: Bazı kullanıcılarınızı Microsoft 365 E planından Microsoft 365 F planına geçiyorsanız dikkate almanız gerekenler ve hazırlanma hakkında bilgi edinin.
ms.localizationpriority: high
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- m365-frontline
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
ms.openlocfilehash: 81ebf6305ca4e60a33eb262fc277efe298d19c43
ms.sourcegitcommit: 217108c59be41b01963a393b4f16d137636fe6a8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/12/2022
ms.locfileid: "67331851"
---
# <a name="changing-from-a-microsoft-365-e-plan-to-a-microsoft-365-f-plan"></a>Microsoft 365 E planından Microsoft 365 F planına geçiş

Kullanıcılarınızdan bazılarını bir Microsoft 365 E planından Microsoft 365 [F3](https://www.microsoft.com/microsoft-365/enterprise/f3) veya [F1](https://www.microsoft.com/microsoft-365/enterprise/f1) planına geçirmeyi düşünüyorsanız, bu makalede kuruluşunuzu değişikliğe hazırlamanıza yardımcı olacak yönergeler sağlanır. E planından F planına geçmek, kullanıcıların erişimi olan hizmetleri ve özellikleri etkiler.

E planları bilgi çalışanlarına (genellikle masada çalışan çalışanlar) ve F planları ön cephe çalışanlarına (harekette olan, genellikle mobil cihazlarda çalışan ve doğrudan müşterilerle veya genel halkla çalışan çalışanlar) yöneliktir. Her plan zaman içinde gelişmeye devam ederek sırasıyla bilgi çalışanları ve cephe çalışanları için daha uyarlanabilir hale gelebilir. Daha fazla bilgi edinmek için bkz. [Ön çalışan kullanıcı türlerini ve lisanslamayı anlama](flw-licensing-options.md).

Kullanıcılar bir F planına geçtiğinde neler bekleyebileceğinize, değişikliğe nasıl hazırlanabileceğinize ve kuruluşunuzdaki ön cephe çalışanlarını geçiş planlarına geçtikten sonra neler yapabileceğinize ilişkin genel bir bakış elde edersiniz.

## <a name="understand-the-key-differences-between-e-and-f-plans"></a>E ve F planları arasındaki önemli farkları anlama

İlk olarak hizmet ve planlar arasındaki özellik farklarını tanıyın.

Bazı önemli farklar şunlardır:

- F planları Office masaüstü uygulamalarını veya Outlook masaüstü uygulamasını içermez.
- F planları, Office mobil uygulamalarında 10,1 inçten küçük tümleşik ekranlara sahip cihazlarla sınırlıdır.
- F, Microsoft Teams'de Walkie Talkie, Görevler, Vardiyalar ve Onaylar gibi [ön çalışan uygulamalarını varsayılan olarak sabitler](pin-teams-apps-based-on-license.md) .

Bu bölümde, bu önemli farklar hakkında daha fazla bilgi eklemiş ve dikkate alınacak bazı ek farkları vurgulayacağız. Bunun kapsamlı bir liste olmadığını unutmayın. Daha fazla bilgi edinmek için:

- E ve F planlarına dahil edilenlerin ayrıntılı karşılaştırması için bkz. [Modern iş planı](https://go.microsoft.com/fwlink/p/?linkid=2139145) karşılaştırması.
- E ve F planlarının [hizmet](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options#service-availability-within-each-microsoft-365-and-office-365-plan) ve [özellik kullanılabilirliği](/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description#feature-availability-across-some-plans) listesi için bkz. Planlar arasında hizmet kullanılabilirliği ve özellik kullanılabilirliği.

### <a name="office-apps"></a>Office uygulamaları

Office masaüstü uygulamaları F3 ve F1 planlarında yer almaz. Ön cephe çalışanlarınız işleri halletmek için Web için Office ve Office mobil uygulamalarını kullanabilir. F3 kullanıcılarının Web için Office belgelere tam erişimi olduğunu ve F1 kullanıcılarının salt okunur erişime sahip olduğunu unutmayın.

|Hizmet veya özellik|Microsoft 365 E3/E5  |Microsoft 365 F3|Microsoft 365 F1|
|---------|---------|---------|---------|
|Office masaüstü uygulamaları (Word, Excel, OneNote, PowerPoint, Access, Publisher)|Evet|Hayır|Hayır|
|Web için Office (Word, Excel, OneNote, PowerPoint)|Evet|Evet|Salt okunur|
|Office mobil uygulamaları (Word, Excel, PowerPoint, Outlook, OneNote)|Evet|Evet&sup1;|Salt okunur|

&sup1; 10,1 inçten küçük tümleşik ekranlara sahip cihazlarda desteklenen dosyaları düzenleme.

#### <a name="office-for-the-web"></a>Web için Office

Web için Office ile ön cephe çalışanlarınız Word, Excel, OneNote ve PowerPoint dosyalarını açmak için bir web tarayıcısı kullanır.

Web için Office kullanırken dikkat etmeniz gereken bazı farklılıklar şunlardır. Web için Office ve Office masaüstü uygulamaları arasında ayrıntılı bir özellik karşılaştırması için bkz. [hizmet açıklaması Web için Office](/office365/servicedescriptions/office-online-service-description/office-online-service-description).

|Hizmet veya özellik|Bazı farklılıklar |Daha fazla bilgi|
|---------|---------|---------|
|**Web için Word**|<ul><li> Makro etkin belgeleri (.docm) ve şablonları (.dotm) açabilir ve düzenleyebilir, ancak makrolar çalışmaz.</li><li>Kullanıcı Tanımlı İzin (UDP) Bilgi Hakları Yönetimi (IRM) korumalı belgeleri açabilir ancak düzenleyemez.</li></ul>|<ul><li>[Web hizmeti için Word açıklaması](/office365/servicedescriptions/office-online-service-description/word-online)</li><li>[Tarayıcıda ve Word'de belge kullanma arasındaki farklar](https://support.microsoft.com//office/differences-between-using-a-document-in-the-browser-and-in-word-3e863ce3-e82c-4211-8f97-5b33c36c55f8)</li></ul>|
|**Web için Excel**|<ul><li>Makro etkin çalışma kitaplarını (.xlsm) açabilir ve düzenleyebilir, ancak makrolar çalışmaz.</li><li>[Dosya boyutu sınırlamaları](https://support.microsoft.com/office/file-size-limits-for-workbooks-in-sharepoint-9e5bc6f8-018f-415a-b890-5452687b325e)<ul><li>SharePoint Online'da depolanan bir çalışma kitabını görüntülemek veya çalışma kitabıyla etkileşimde bulunabilmek için, çalışma kitabının 100 MB'tan az olması gerekir. </li><li>E-posta iletisine eklenmiş bir çalışma kitabını Web üzerinde Outlook açmak için çalışma kitabının 10 MB'tan az olması gerekir.</li></ul></ul>|<ul><li>[hizmet açıklamasını Web için Excel](/office365/servicedescriptions/office-online-service-description/excel-online)</li><li>[Çalışma kitabını tarayıcıda ve Excel'de kullanma arasındaki farklar](https://support.microsoft.com/office/differences-between-using-a-workbook-in-the-browser-and-in-excel-f0dc28ed-b85d-4e1d-be6d-5878005db3b6)</li><li>Çoğu Excel işlevi, Excel'de olduğu gibi tarayıcıda da çalışır. Özel durumların listesi için bkz[. Excel'de ve Web için Excel'de İşlevler](https://support.microsoft.com/office/differences-between-using-a-workbook-in-the-browser-and-in-excel-f0dc28ed-b85d-4e1d-be6d-5878005db3b6#__functions).</li></ul>|
|**Web için OneNote**|<ul><li>Arama geçerli bölümle sınırlıdır.</li><li>Yakınlaştırma ve uzaklaştırma kullanılamaz. Bunun yerine, kullanıcılar tarayıcılarının yakınlaştırma özelliğini kullanabilir.</li></ul>|<ul><li>[hizmet açıklamasını Web için OneNote](/office365/servicedescriptions/office-online-service-description/onenote-online)</li><li>[Not defterini tarayıcıda ve OneNote'ta kullanma arasındaki farklar](https://support.microsoft.com/office/differences-between-using-a-notebook-in-the-browser-and-in-onenote-a3d1fc13-ac74-456b-b391-b633a62aa83f)</li></ul>|
|**Web için PowerPoint**|<ul><li>2 GB'a kadar olan dosyaları açabilir.</li><li>Makro etkin sunuları (.pptm, .potm, .ppsm) açabilir ve düzenleyebilir, ancak makrolar çalışmaz.</li></ul>|<ul><li>[hizmet açıklamasını Web için PowerPoint](/office365/servicedescriptions/office-online-service-description/powerpoint-online)</li><li>[Web tabanlı PowerPoint'te belirli özelliklerin davranışı](https://support.microsoft.com/office/how-certain-features-behave-in-web-based-powerpoint-a931f0c8-1305-4428-8f7c-9cfa00ef28c5)</li></ul>|

#### <a name="office-mobile"></a>Office mobile

Ön cephe çalışanlarınız Office'i mobil cihazlarına iki şekilde alabilir:

- Word, Excel ve PowerPoint'i birleştiren Office mobil uygulamasını yükleyin.
- Word, Excel, PowerPoint ve OneNote için tek tek Office mobil uygulamalarını yükleyin.

Daha fazla bilgi edinmek için bkz. [Android'de Office'i yükleme ve ayarlama](https://support.microsoft.com/office/install-and-set-up-office-on-an-android-cafe9d6f-8b0c-4b03-b20a-12438a82a22d) ve [iPhone veya iPad'de Office'i yükleme ve ayarlama](https://support.microsoft.com/office/install-and-set-up-office-on-an-iphone-or-ipad-9df6d10c-7281-4671-8666-6ca8e339b628).

Office mobile'da kullanılabilen özellikler hakkında daha fazla bilgi için bkz. [Microsoft 365 aboneliğine sahip mobil cihazlardaki Office uygulamalarında yapabilecekler](https://support.microsoft.com/office/what-you-can-do-in-the-office-apps-on-mobile-devices-with-a-microsoft-365-subscription-9ef8b63a-05fd-4f9c-bac5-29da046833ea).

#### <a name="email"></a>E-posta

F3 kullanıcılarının Web üzerinde Outlook üzerinden erişebilecekleri 2 GB'lık bir posta kutusu vardır. Web üzerinde Outlook ile Outlook masaüstü uygulaması arasında özellik karşılaştırması için bkz. [Pc için Outlook, Web üzerinde Outlook ve iOS için Outlook & Android'i karşılaştırma](https://support.microsoft.com/office/compare-outlook-for-pc-outlook-on-the-web-and-outlook-for-ios-android-b26a7bf5-0ac7-48ba-97af-984e0645dde5).

F1 kullanıcılarının posta kutusu hakları yoktur. Kullanıcılar için Exchange Bilgi Noktası planı aracılığıyla bir posta kutusu sağlansa da, bu posta kutusunu kullanma hakkına sahip değildirler. F1 kullanıcıları için [Web üzerinde Outlook devre dışı bırakmanızı](/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-outlook-web-app) öneririz.

|Hizmet veya özellik|Microsoft 365 E3/E5|Microsoft 365 F3|Microsoft 365 F1|
|---------|---------|---------|---------|
|Exchange Online posta kutusu|Evet (100 GB posta kutusu)|Evet (2 GB posta kutusu)|&yok1;|
|Outlook masaüstü uygulaması|Evet|Hayır|Hayır|
|Arşiv posta kutusu|Evet|Hayır|Hayır|
|Temsilci erişimi|Evet|Hayır|Hayır|

&sup1; F1, yalnızca Teams takvimini etkinleştirmek için Exchange Bilgi Noktası planını içerir ve posta kutusu haklarını içermez.

Daha fazla bilgi için bkz. [Exchange Online hizmet açıklaması](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description).

#### <a name="teams"></a>Teams

F3 ve F1 planları teams masaüstü uygulamasını, mobil uygulamayı ve ön cephe çalışanı iletişimi ve işbirliği için web uygulamasını içerir. Ön cephe çalışanlarınızın toplantılar, sohbet, kanallar, içerik ve uygulamalar gibi Teams özelliklerine erişimi vardır. Ancak canlı etkinlikler ve web seminerleri oluşturamaz veya Teams Phone özelliklerini kullanamaz.

|Hizmet veya özellik|Microsoft 365 E3/E5|Microsoft 365 F3|Microsoft 365 F1|
|---------|---------|---------|---------|
|Canlı etkinlikler|Evet|Hayır|Hayır|
|Webinars|Evet|Hayır|Hayır|
|Teams Phone|Evet|Hayır|Hayır|

#### <a name="sharepoint"></a>SharePoint

F3 ve F1 kullanıcıları belgeler üzerinde işbirliği yapabilir ve SharePoint'te depolanan eğitim malzemeleri gibi kuruluş genelindeki kaynaklara erişebilir. F3 ve F1 planlarının site posta kutularını veya kişisel siteleri içermediğini unutmayın.

|Hizmet veya özellik|Microsoft 365 E3/E5|Microsoft 365 F3|Microsoft 365 F1|
|---------|---------|---------|---------|
|Site posta kutusu|Evet|Hayır|Hayır|
|Kişisel site|Evet|Hayır|Hayır|

SharePoint sınırları hakkında daha fazla bilgi edinmek için bkz. [SharePoint sınırları](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits).

#### <a name="content-services"></a>İçerik hizmetleri

F3 ve F1 kullanıcılarının dosyaları depolamak ve paylaşmak için 2 GB OneDrive depolama alanı vardır. Daha fazla bilgi için bkz. [OneDrive hizmet açıklaması](/office365/servicedescriptions/onedrive-for-business-service-description).

|Hizmet veya özellik|Microsoft 365 E3/E5|Microsoft 365 F3|Microsoft 365 F1|
|---------|---------|---------|---------|
|OneDrive|Sınırsız depolama&sup1;|2 GB depolama alanı|2 GB depolama alanı|
|Microsoft Stream|Evet|Evet&sup2;|Evet&sup2;|
|Sway|Evet|Evet|Hayır|
|Web için Visio|Evet|Evet|Salt okunur|
|Doğan|Evet|Hayır|Hayır|

&sup1; Beşten fazla kullanıcısı olan abonelikler için kiracının [varsayılan kotasına](/onedrive/set-default-storage-space) göre kullanıcı başına 5 TB'a kadar ilk OneDrive depolama alanı. Daha fazla depolama alanı istenebilir.</br>
&sup2; Kullanıcılar toplantıları kaydedebilir ve Stream içeriğini kullanabilir ancak Stream'de yayımlayamaz veya paylaşamaz.

#### <a name="insights-and-analytics"></a>İçgörüler ve analiz

|Hizmet veya özellik|Microsoft 365 E3/E5|Microsoft 365 F3|Microsoft 365 F1|
|---------|---------|---------|---------|
|Viva Analizler|Evet|Hayır|Hayır|
|Power BI|Evet|Hayır|Hayır|

#### <a name="work-management-and-automation"></a>İş yönetimi ve otomasyon

|Hizmet veya özellik|Microsoft 365 E3/E5|Microsoft 365 F3|Microsoft 365 F1|
|---------|---------|---------|---------|
|Power Apps|Evet|Evet|Hayır|
|Power Automate|Evet|Evet|Hayır|
|Power Virtual Agents|Evet|Evet|Hayır|
|Teams için Dataverse|Evet|Evet|Hayır|
|Microsoft Forms|Evet&sup1;|Evet&sup1;|Hayır|
|Microsoft To Do|Evet|Evet|Hayır|

&sup1; Lisanslı kullanıcılar form oluşturabilir, paylaşabilir ve yönetebilir. Formu tamamlamak veya formu yanıtlamak için lisans gerekmez.

#### <a name="windows"></a>Windows

|Hizmet veya özellik|Microsoft 365 E3/E5|Microsoft 365 F3|Microsoft 365 F1|
|---------|---------|---------|---------|
|Windows 11 Enterprise|Evet|Evet&sup1;|Hayır|

&sup1; Long-Term Bakım Kanalı (LTSC) veya Microsoft Masaüstü İyileştirme Paketi (MDOP) yok. Sanal masaüstü altyapısı (VDI) yalnızca Hizmet Kalitesine (QoS) sahip paylaşılan bir cihazın lisanslı kullanıcıları için (Azure Sanal Masaüstü hariç).

## <a name="what-to-expect"></a>Bekleyebileceğiniz şeyler

Aşağıdaki tabloda dikkate alınması gereken önemli noktalar ve değişiklik işlemi sırasında yapılması önerilen eylemler listelenmiştir. Anahtardan önce yapmanız gerekenleri ve anahtar tamamlandıktan sonra neleri planlayabileceğinizi belirlemenize yardımcı olması için bu bilgileri kullanın. 

Bu makalenin sonraki bölümlerinde bu tabloya değineceğiz.

|Hizmet veya özellik |Anahtardan önce|Anahtardan sonra|
|---------|---------|---------|
|Office uygulamaları| <ul><li>Kullanıcıların yerel bilgisayarlarında depolanan dosyaları belirleyin ve kullanıcıların bunları OneDrive'larına taşımasına yardımcı olun.</li><li>F planına geçtikten sonra Office masaüstü uygulamalarının sınırlı işlevsellik moduna geçeceğini unutmayın. Geçiş sonrasında Office masaüstü uygulamalarını kaldırmaya hazır olun.</li></ul>| Kullanıcı:</br> <ul><li>Web için Office erişmek için [office.com](https://www.office.com) oturum açın.</li><li>[Office mobil uygulamalarını yükleyin ve kullanın](https://support.microsoft.com/office/set-up-office-apps-and-email-on-a-mobile-device-7dabb6cb-0046-40b6-81fe-767e0b1f014f) (henüz yüklü değilse).</li><li>Kullanıcılar ayrıca SharePoint belge kitaplıkları, OneDrive, Teams ve Yammer'dan belgeler üzerinde doğrudan işbirliği yapabilir.</li></ul>Yöneticiler:<ul><li>Kullanıcıların bilgisayarlarından Office masaüstü uygulamalarını kaldırın.</li></ul>      |
|Email, Exchange, Outlook|<ul><li>[Get-MailboxStatistics](/powershell/module/exchange/get-mailboxstatistics?view=exchange-ps) Exchange PowerShell cmdlet'ini kullanarak 2 GB'ın üzerindeki kullanıcı posta kutularını tanımlayın ve sonra gerektiğinde posta kutusu boyutunu küçültün. Daha fazla bilgi için bkz. [Web üzerinde Outlook'de posta kutusu depolama sınırları](https://support.microsoft.com/office/mailbox-storage-limits-in-outlook-on-the-web-f170fe90-b859-4034-bcda-e186fc6a26f5).</li><li>Kullanıcıların arşiv posta kutusu varsa:</li><ul><li>Arşiv posta kutusu içeriğini kullanıcının posta kutusuna geri taşıyın.</li><li>PowerShell cmdlet'ini [Exchange Online Get-EXOMailbox](/powershell/module/exchange/get-exomailbox?view=exchange-ps) kullanarak iletilerin yaşına göre e-postayı otomatik olarak taşıyabilecek arşiv ilkelerini denetleyin.</li></ul> <li>Site posta kutusu erişimini ve kullanımını belirleme.</li><li>Outlook masaüstü uygulaması, verileri ve yapılandırması:</li><ul><li>Outlook veri (.pst) dosyalarını kullanan kullanıcıları ve bilgisayarları tanımlayın.</li><li>Var olan Outlook yalnızca istemci kurallarını tanımlama ve belgele.</li><li>E-posta imzalarını dışarı aktarın.</li></ul></ul>|Kullanıcı:</br><ul><li>Web üzerinde Outlook erişmek için [office.com](https://www.office.com) oturum açın.</li><li>[Mobil cihazlarda (henüz değilse) e-postayı ayarlayın](https://support.microsoft.com/office/set-up-office-apps-and-email-on-a-mobile-device-7dabb6cb-0046-40b6-81fe-767e0b1f014f) .</li><li>Posta imzalarını denetleyin ve güncelleştirin.</li><li>Posta kutusu kurallarını denetleyin ve güncelleştirin.</li></ul>Yöneticiler:<ul><li> F1 kullanıcıları için [Web üzerinde Outlook devre dışı bırakın](/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-outlook-web-app) ve başka yöntemlerle posta kutusuna erişmemelerini isteyin.</li></ul>|
|Teams | <ul><li>Canlı etkinliklerin ve web seminerlerinin kullanımını belirleme.</li><li>Teams Phone'un etkinleştirildiği kullanıcıları belirleyin. Kullanıcılar bu özelliği kullanıyorsa, F planına geçiş için uygun kullanıcı kümesi olmayabilir.</li></ul>      ||
|OneDrive | <ul><li>2 GB'tan fazla veya 2 GB'a yakın depolama alanı kullanan kullanıcıları belirleyin. (OneDrive, F planına geçtikten sonra 2 GB sınırını aşan kullanıcılar için salt okunur hale gelir.)</li><li>Kullanıcıların OneDrive'da depolanan dosya sayısını ve kullanılan genel depolama miktarını azaltmasını sağlayın.</li><li>Tüm dosyaların kullanıcıların bilgisayarlarından OneDrive'a tam olarak eşitlenmiş olduğundan emin olun.</li></ul>| |

## <a name="prepare-to-switch-plans"></a>Plan değiştirmeye hazırlanma

### <a name="create-a-change-management-strategy"></a>Değişiklik yönetimi stratejisi oluşturma

En uygun değişiklik yönetimi stratejisi, kullanıcılarınızı bir F planına geçirmeden önce ve sonra nasıl iletişim kurabileceğinizi, eğittiğinizi ve destekleyeceksiniz. Örneğin, dikkat edilmesi gereken birkaç şey şunlardır:

- Kullanıcılar anahtardan nasıl haberdar olacak?
- Kullanıcılar hizmet ve özelliklerdeki farklarda gezinmeyi nasıl öğrenecek? F planına geçiş, davranış değişikliği gerektirdiğinden eğitimde daha fazla çaba gerektirebilir.
- Kullanıcılar nasıl yardım ve destek alacak?

Stratejinizi oluştururken iletişim ve eğitim tercihlerini göz önünde bulundurun. Başarılı bir geçiş sağlamaya yardımcı olmak için mesajlaşma, eğitim ve desteğinizi ön cephe çalışanlarınızın ve şirket kültürünüzün belirli gereksinimlerine göre özelleştirin.

Stratejinizi planlamanıza yardımcı olacak bazı fikirler aşağıdadır.

|İletişim|Eğitim|Destek|
|---------|---------|---------|
|<ul><li>E-posta</li><li>Departman veya mağaza yöneticileri</li><li>Şampiyonlar</li><li>Ekipler ve kanallar</li><li>Yammer toplulukları</li></ul> |<ul><li>Microsoft çevrimiçi yardım, eğitim ve video kaynakları</li><li>Şirket içi eğitim</li></ul>|<ul><li>Şirket içi yardım masası</li><li>Self servis intranet sitesi</li><li>Microsoft çevrimiçi yardım, eğitim ve video kaynakları</li><li>Yerde yürüyenler ve şampiyonlar</li></ul>         |

Kullanıcılarınızla etkileşim kurmanıza ve eğitmenize yardımcı olması için bu benimseme kaynaklarını da gözden geçirmek isteyebilirsiniz:

- [Microsoft 365 – Microsoft Benimseme](https://adoption.microsoft.com/microsoft-365/)
- [Ön cephe çalışanları için Teams – Microsoft Benimseme](https://adoption.microsoft.com/microsoft-teams/frontline-workers/)

### <a name="back-up-or-prepare-data"></a>Verileri yedekleme veya hazırlama

Kullanıcıların saklamak istediği verileri belirleyin ve yedekleyin veya hazırlayın. Bu makalenin önceki bölümlerindeki [Beklenecekler](#what-to-expect) bölümündeki yönergeleri izleyin ve aşağıdaki bileşenlerin her biri için tablonun Switch sütunundan **önce** bölümündeki önerilen eylemleri tamamlayın:

- Office uygulamaları
- Email, Exchange, Outlook
- Teams
- OneDrive

Daha fazla bilgi için bkz. [Plan değiştirmeden önce verileri yedekleme](/microsoft-365/commerce/subscriptions/move-users-different-subscription).

## <a name="switch-users-to-a-microsoft-365-f-plan"></a>Kullanıcıları Microsoft 365 F planına değiştirme

PowerShell cmdlet'leri aracılığıyla planları veya betikli yaklaşımı el ile değiştirmek için Microsoft 365 yönetim merkezi kullanabilirsiniz. Hangi yöntemi seçerseniz seçin, lisans değişikliği atamasını tek bir işlemde tamamlamak önemlidir. Başka bir deyişle, aynı işlemde bir F lisansı atayarak mevcut bir E lisansını kaldırın ve değiştirin.

Bir kullanıcı için mevcut lisansı kaldırmaktan ve daha sonra yeni bir lisans atamaktan kaçının. Bunu yapmak kullanıcının verilerini etkileyebilir. Daha fazla bilgi edinmek için bkz. [Lisansını kaldırdığınızda kullanıcının verilerine ne olur?](/microsoft-365/admin/manage/remove-licenses-from-users?view=o365-worldwide#what-happens-to-a-users-data-when-you-remove-their-license).

Microsoft yönetim merkezinde planları değiştirme hakkında adım adım yönergeler için bkz. [Microsoft planlarını el ile değiştirme](/microsoft-365/commerce/subscriptions/change-plans-manually).

## <a name="what-to-do-after-switching-plans"></a>Planlar değiştirildikten sonra yapılması gerekenler

Bu makalenin önceki bölümlerinde yer alan [Beklenecekler](#what-to-expect) bölümündeki yönergeleri izleyin ve aşağıdaki bileşenlerin her biri için tablonun **Switch** sütununda önerilen eylemleri tamamlayın:

- Office uygulamaları
- Email, Exchange, Outlook
- Teams
- OneDrive

Kullanıcılarınıza değişikliğin tamamlandığını bildirin ve değişiklik yönetimi stratejinizde tanımlandığı gibi nasıl yardım alacaklarını bildirin. Geçişte bunları desteklemek için [yardım ve öğrenme kaynaklarının](#user-setup-help-and-learning-resources) bağlantılarını eklemek isteyebilirsiniz.

## <a name="user-setup-help-and-learning-resources"></a>Kullanıcı kurulumu, yardım ve öğrenme kaynakları

Eğitim ve destek için ön cephe çalışanlarınızla paylaşabileceğiniz kurulum, yardım ve öğrenme kaynaklarının bazı bağlantıları aşağıdadır.

|Uygulama|Bağlantılar |
|---------|---------|
|Web için Office|<ul><li>[Web için Office eğitimi](https://support.microsoft.com/office/office-for-the-web-training-e315b031-2bd5-40a1-99ca-264ebf2c8f96)</li><li>[Microsoft 365'te Web için Office kullanmaya başlama](https://support.microsoft.com/office/get-started-with-office-for-the-web-in-microsoft-365-5622c7c9-721d-4b3d-8cb9-a7276c2470e5)</li></ul>|
|Web üzerinde Outlook|<ul><li>[Web üzerinde Outlook tanımaya başlayın](https://support.microsoft.com/office/get-to-know-outlook-on-the-web-3f1a229b-0d60-438f-b515-dd7a28026bc1)</li><li>[Web üzerinde Outlook ile ilgili yardım alma](https://support.microsoft.com/office/get-help-with-outlook-on-the-web-cf659288-35cc-4c6c-8c75-e8e4317fda11)</li><li>[videoları Web üzerinde Outlook](https://support.microsoft.com/office/learn-more-about-outlook-on-the-web-adbacbab-fe59-4259-a550-6cb7f85f19ec)</li></ul>|
|Office mobile|Kurulum:</br><ul><li>[Android'de Office uygulamalarını ve e-postayı ayarlama](https://support.microsoft.com/office/set-up-office-apps-and-email-on-android-6ef2ebf2-fc2d-474a-be4a-5a801365c87f)</li><li>[iOS cihazlarında Office uygulamalarını ve e-postayı ayarlama](https://support.microsoft.com/office/set-up-the-office-app-and-outlook-on-ios-devices-0402b37e-49c4-4419-a030-f34c2013041f)</li></ul>Office mobil uygulaması yardımı:<ul><li>[Android için Office mobil uygulaması yardımı](https://support.microsoft.com/office/microsoft-office-app-for-android-0383d031-a1c6-46c9-b734-53cd1d22765b)</li><li>[iOS için Office uygulaması yardımı](https://support.microsoft.com/office/microsoft-office-app-for-ios-c8880c05-883a-46b6-ad32-9bffa31228d0)</li></ul>Bireysel Office mobil uygulaması yardımı:<ul><li>[Android için Word Telefonlar](https://support.microsoft.com/office/word-for-android-phones-help-764afb31-ad50-4645-8f51-820ecf731d8f), [Android için Word tabletler](https://support.microsoft.com/office/word-for-android-tablets-help-8a0dcd56-fb32-4e0d-95d8-997c066125c8), [iPhone için Word](https://support.microsoft.com/office/word-for-iphone-help-d41a5299-f6fa-4cca-b529-46a8069c5796)[, iPad için Word](https://support.microsoft.com/office/word-for-ipad-help-6567cf2a-c949-4213-912d-f7a14f6264c5)</li><li>[Android için Excel Telefonlar](https://support.microsoft.com/office/excel-for-android-phones-help-f818cb37-bfac-485d-8480-363b3da40596), [Android için Excel Tabletler](https://support.microsoft.com/office/word-for-android-tablets-help-8a0dcd56-fb32-4e0d-95d8-997c066125c8), [iPhone için Excel](https://support.microsoft.com/office/excel-for-iphone-help-b367819b-05b4-4a56-ab1c-678da62e1fd3)[, iPad için Excel](https://support.microsoft.com/office/excel-for-ipad-help-6b5dc2e1-a8e4-48e6-bb69-cb9a3964bc91)</li><li>[Android için PowerPoint Telefonlar](https://support.microsoft.com/office/powerpoint-for-android-phones-help-f6714e00-0ee2-48d1-bd3d-e1997565861f), [Android için PowerPoint Tabletler](https://support.microsoft.com/office/powerpoint-for-android-tablets-help-2ada1d22-3784-4943-bc47-9d1ede42875c), [iPhone için PowerPoint](https://support.microsoft.com/office/powerpoint-for-iphone-help-754fcb37-783b-4e8a-afca-edb900221b8b) [iPad için PowerPoint](https://support.microsoft.com/office/powerpoint-for-ipad-help-b75ce3bb-03e3-46df-a792-647573fef84a)</li><li>[Android için OneNote](https://support.microsoft.com/office/microsoft-onenote-for-android-46b4b49d-2bef-4746-9c30-6abb5e20b688), [iPhone için OneNote](https://support.microsoft.com/office/microsoft-onenote-for-iphone-b93a0ea8-1285-4d31-a7c5-86a849731902) [iPad için OneNote](https://support.microsoft.com/office/microsoft-onenote-help-ipad-f44e5bcd-5203-4553-9de4-0c56e6500825)</li></ul>
|Teams|<ul><li>[Teams video eğitimi](https://support.microsoft.com/office/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7)</li><li>[Teams öğrenme & yardımcı olur](https://support.microsoft.com/teams)</li></ul>|

