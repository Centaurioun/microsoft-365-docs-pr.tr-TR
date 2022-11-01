---
title: Diğer Microsoft 365 Hizmetleri için Data Residency
description: Diğer Microsoft 365 Hizmetleri için Data Residency hakkında bilgi edinin
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.service: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.date: ''
ms.reviewer: dmwmsft
ms.custom:
- it-pro
ms.collection:
- M365-subscription-management
ms.openlocfilehash: 0c8cb3f31d2b4a553c190cd384978d30d7802ec4
ms.sourcegitcommit: 0c72639cc3dc74667a6b14343d303f318e70d457
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/01/2022
ms.locfileid: "68806309"
---
# <a name="data-residency-for-other-microsoft-365-services"></a>Diğer Microsoft 365 Hizmetleri için Data Residency

## <a name="data-residency-commitments-available"></a>Data Residency taahhütleri kullanılabilir

Verilerinizin nerede bulunduğunu belirlemek için aşağıdaki kılavuzu kullanın. Lütfen _kiracınızın_ _Varsayılan Coğrafyası'ne_ başvurun.

### <a name="azure-active-directory-aad"></a>Azure Active Directory (AAD)

Lütfen [Azure Active Directory Veri Konumları'na](https://aka.ms/aaddatamap) bakın.

### <a name="forms"></a>Forms
AB üyesi Ülkelerdeki kiracılar _Verileri Makro Bölgesi Coğrafya 1 – EMEA'da_ tutar. Diğer tüm kiracılarda müşteri verileri Birleşik Devletler depolanır.

### <a name="intune"></a>Intune
Bkz. endpoint.microsoft.com, Kiracı Yönetimi | Mevcut kiracılar için Kiracı Durumu. Mevcut bir kiracınız yoksa, bir deneme kiracısı oluşturun ve Intune sağlayın.

- Microsoft, aşağıdaki durumlar dışında Intune müşteri verilerini belirtilen coğrafi konumun dışında depolamaz:
- Microsoft'un müşteri desteği sağlaması, hizmetle ilgili sorunları gidermesi veya yasal gereksinimlere uyması gerekir.
- Müşteri, aşağıdakilerin kullanımı da dahil olmak üzere müşteri verilerinin böyle bir şekilde depolanmasını etkinleştirmek için bir hesap yapılandırıyor:
- Küresel önbelleğe alma hizmeti sağlayan ve müşteri verilerini dünyanın dört bir yanındaki uç konumlarda depolayan Content Delivery Network (CDN) gibi genel olarak çalışacak şekilde tasarlanmış özellikler.
- Azure Active Directory için: Lütfen [Azure Active Directory Veri Konumları'na](https://aka.ms/aaddatamap) bakın.
- Müşteri verilerini genellikle Birleşik Devletler depolayan ancak genel olarak depolayan önizleme, beta veya diğer yayın öncesi hizmetler. Ne olursa olsun, Microsoft müşterilerin veya son kullanıcılarının müşteri verilerine erişebileceği Coğrafi verileri denetlemez veya sınırlamaz. Benzer şekilde, diğer hizmetlerdeki müşteri verileri daha sonra Intune tümleştirildiğinde, kaynak müşteri verileri diğer hizmetin kendi Coğrafi taahhütlerine (varsa) bağlı olarak depolanmaya devam eder; yalnızca Intune tümleştirilmiş müşteri verilerinin kopyası Intune için belirtilen Coğrafi Bölgede depolanır.

### <a name="office-for-mobile"></a>Mobil cihazlar için Office
Bu hizmetin müşteri verileri Exchange Online ve SharePoint Online gibi diğer hizmetlerden gelir. Mobil cihaz dışında bu hizmetlerin dışında depolanan müşteri verileri yoktur.

### <a name="onenote-services"></a>OneNote Hizmetleri
OneNote, müşteri verilerini OneDrive İş depolar. Bununla birlikte, kalıcı önbelleklerin OneDrive İş müşteri verilerini depoladığı Coğrafya dışında yapılmasına neden olabilecek bir API'sine sahiptir.

### <a name="planner"></a>Planner
[Belirli iş yükleri için statik veri konumu bilgileri](#static-data-location-information-for-select-workloads) bölümüne bakın.

### <a name="power-apps-for-microsoft-365"></a>Microsoft 365 için Power Apps
Lütfen [Dynamics 365 kullanılabilirliği ve veri konumları | Microsoft Learn](/dynamics365/get-started/availability).

### <a name="stream"></a>Stream
Bu bilgileri Stream kullanıcı arabirimindeki "?" seçeneğinden bulabilir ve ardından "Microsoft Stream Hakkında" seçeneğine tıklayıp verilerinizin nerede depolandığını görebilirsiniz. Gerekirse bir deneme kiracısı oluşturun.

### <a name="viva-insights--advanced-mgr-leader"></a>Viva Insights – Gelişmiş, Mgr, Lider
[Belirli iş yükleri için statik veri konumu bilgileri](#static-data-location-information-for-select-workloads) bölümüne bakın.  Yönetici/Öncü ve Gelişmiş için veri bölgesi, tek tek kullanıcılara değil _kiracının_ _Varsayılan Coğrafyası'na_ göre belirlenir.

### <a name="viva-insights--personal"></a>Viva Insights – Kişisel
Müşteri verileri işlenir ve çalışanın Exchange Online posta kutusunda depolanır. Viva Insights'daki Kişisel içgörüler için veri yerleşimi, çalışanın posta kutusu konumunu temel alır. Daha fazla bilgi için bkz. [Yöneticiler için gizlilik kılavuzu Viva Insights kişisel içgörüler](/viva/insights/personal/overview/privacy-guide-admins?branch=main#summary-of-key-points).

### <a name="viva-learning"></a>Viva Learning
[Belirli iş yükleri için statik veri konumu bilgileri](#static-data-location-information-for-select-workloads) bölümüne bakın.

### <a name="whiteboard"></a>Tahta
Lütfen [Microsoft Whiteboard için verileri yönetme | bakın Microsoft Learn](/whiteboard/manage-data-organizations).

### <a name="yammer"></a>Yammer
Lütfen [Data Residency - Yammer | Microsoft Learn](/yammer/manage-security-and-compliance/data-residency).

## <a name="static-data-location-information-for-select-workloads"></a>Belirli iş yükleri için statik veri konumu bilgileri

1. Makro Bölge Coğrafyası 1 – EMEA / Avrupa Birliği
1. Makro Bölgesi Coğrafya 2 - Asya Pasifik
1. Makro Bölgesi Coğrafya 3 – Amerika
1. Avustralya
1. Kanada
1. Japonya

| Ülke Kodu | Ülke Adı | gelişmiş Viva Insights | Viva Learning | Planner |
| --- | --- | --- | --- | --- |
| Af | Afganistan | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Ax | Aland Adaları | APC<sup>2</sup>| AMER<sup>3</sup>| <sup>1</sup> EUR|
| AL | Arnavutluk | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Dz | Cezayir | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Olarak | Amerikan Samoası | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Reklam | Andorra | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Ao | Angola | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Aı | Anguilla | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Aq | Antarktika | AMER<sup>3</sup>| <sup>1</sup> EUR| AMER<sup>3</sup>|
| Ag | Antigua ve Barbuda | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Ar | Arjantin | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| AM | Ermenistan | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| AW | Aruba | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Au | Avustralya | APC<sup>2</sup>| AUS<sup>4</sup>| AUS<sup>4</sup>|
| AT | Avusturya | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Az | Azerbaycan | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Bs | Bahamalar | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| BH | Bahreyn | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Bd | Bangladeş | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Bb | Barbados | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Tarafından | Belarusça | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| BE | Belçika | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Bz | Belize | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Bj | Benin | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| BM | Bermuda | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Bt | Butan | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Bo | Bolivya | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Bq | Bonaire | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Ba | Bosnia and Herzegovina (Bosna i Hercegovina) | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Bw | Botsvana | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Bv | Bouvet Adası | AMER<sup>3</sup>| <sup>1</sup> EUR| AMER<sup>3</sup>|
| Br | Brezilya | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Io | İngiliz Hint Okyanusu Bölgesi | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Vg | Britanya Virjin Adaları | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Bn | Brunei Darüsselam | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Bg | Bulgaristan | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Bf | Burkina Faso | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Bı | Burundi | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Kaya | Kamboçya | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Cm | Kamerun | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Ca | Kanada | AMER<sup>3</sup>| AMER<sup>3</sup>| CAN<sup>5</sup>|
| Cv | Cabo Verde | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Ky | Cayman Islands | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Cf | Orta Afrika Cumhuriyeti | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Td | Çad | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Cl | Şili | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Cn | Çin | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Cx | Christmas Adası | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Cc | Cocos (Keeling) Adaları | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Co | Kolombiya | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Km | Komorolar | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Cg | Kongo (Brazzaville) | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Cd | Kongo, (Kinshasa) | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Ck | Cook Adaları | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Cr | Costa Rica | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Cı | Côte d'Ivoire | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Hr | Hırvatistan | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Cw | Curaçao | AMER<sup>3</sup>| <sup>1</sup> EUR| AMER<sup>3</sup>|
| Cy | Kıbrıs | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Cz | Çek Cumhuriyeti | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Dk | Danimarka | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Dj | Cibuti | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Dm | Dominika | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| DO | Dominican Republic (República Dominicana) | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Ec | Ekvador | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Örneğin | Mısır | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Sv | El Salvador | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Gq | Ekvator Ginesi | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| ER | Eritre | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| EE | Estonya | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| ET | Etiyopya | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Fk | Falkland Adaları (Malvinas) | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Fo | Faroe Islands | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Fm | Mikronezya Federasyon Durumları | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Fj | Fiji | APC<sup>2</sup>| APC<sup>2</sup>| AUS<sup>4</sup>|
| Fi | Finlandiya | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Fr | Fransa | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Gf | Fransızca Guyanası | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Pf | Fransız Polinezyası | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Tf | Fransız Güney Bölgeleri | AMER<sup>3</sup>| <sup>1</sup> EUR| AMER<sup>3</sup>|
| Ga | Gabon | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Gm | Gambiya | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Ge | Gürcistan | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| DE | Almanya | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| GH | Gana | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Gı | Cebelitarık | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Gr | Yunanistan | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Gl | Grönland | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Gd | Grenada | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Gp | Guadeloupe | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Gu | Guam | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Gt | Guatemala | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Gg | Guernsey | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Gn | Gine | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Gw | Guinea-Bissau | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Gy | Guyana | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Ht | Haiti | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Hm | Heard ve Mcdonald Adaları | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Va | Kutsal Manzara (Vatikan Şehir Devleti) | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Hn | Honduras  | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Hk | Hong Kong, ÇIN ÖİB | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Hu | Macaristan | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| IS | İzlanda | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Inç | Hindistan | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Kimlik | Endonezya | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Iq | Irak | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| IE | İrlanda | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Im | Man Adası | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Il | İsrail | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| IT | İtalya | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Jm | Jamaika | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Jp | Japonya | APC<sup>2</sup>| APC<sup>2</sup>| JPN<sup>6</sup>|
| Je | Jersey | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| JO | Ürdün | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Kz | Kazakistan | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Ke | Kenya | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| KI | Kiribati | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| KP | Kore (Kuzey) | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| KR | Kore (Güney) | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Xk | Arnavutluk | <sup>1</sup> EUR| AMER<sup>3</sup>| <sup>1</sup> EUR|
| Kw | Kuveyt | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Kg | Kırgızistan | <sup>1</sup> EUR| APC<sup>2</sup>| <sup>1</sup> EUR|
| La | Lao PDR | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Lv | Letonya | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Lb | Lübnan | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Ls | Lesotho | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Lr | Liberya | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| LY | Libya | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Li | Liechtenstein | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Teğmen | Litvanya | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Lu | Lüksemburg | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Mo | Macao, ÇIN ÖİB | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Mg | Madagaskar | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Mw | Malavi | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Benim | Malezya | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Mv | Maldivler | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Ml | Mali | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Mt | Malta | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Mh | Marshall Adaları | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Mq | Martinik | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Bay | Moritanya | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| MU | Mauritius | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Yt | Mayotte | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| MX | Meksika | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Mc | Monako | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| MD | Moldova | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Mn | Moğolistan | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Beni | Karadağ | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Bayan | Montserrat | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| MA | Fas | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Mz | Mozambik | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Mm | Myanmar | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Na | Namibya | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Nr | Nauru | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Np | Nepal | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Nl | Hollanda | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Bir | Hollanda Antilleri | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Nc | Yeni Kaledonya | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Nz | Yeni Zelanda | APC<sup>2</sup>| APC<sup>2</sup>| AUS<sup>4</sup>|
| NI | Nikaragua | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| NE | Nijer | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Ng | Nijerya | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Nu | Niue | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Nf | Norfolk Adası | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Mp | Kuzey Mariana Adaları | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| HAYIR | Norveç | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Om | Umman | <sup>1</sup> EUR| APC<sup>2</sup>| <sup>1</sup> EUR|
| Pk | Pakistan | <sup>1</sup> EUR| APC<sup>2</sup>| <sup>1</sup> EUR|
| Pw | Palau | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Ps | Palestinian Authority | APC<sup>2</sup>| <sup>1</sup> EUR| APC<sup>2</sup>|
| Pa | Panama | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Sayfa | Papua Yeni Gine | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| PY | Paraguay | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Pe | Peru | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Ph | Filipinler | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Pn | Pitcairn | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Pl | Polonya | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Pt | Portekiz | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Pr | Porto Riko | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Qa | Qator | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Mk | Makedonya Cumhuriyeti | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Re | Réunion | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Ro | Romanya | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Ru | Rusya Federasyonu | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Rw | Ruanda | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| SH | Saint Helena | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| KN | Saint Kitts ve Nevis | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Lc | Saint Lucia | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Pm | Saint Pierre ve Miquelon | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Vc | Saint Vincent ve Grenadines | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Bl | Saint-Barthélemy | AMER<sup>3</sup>| <sup>1</sup> EUR| AMER<sup>3</sup>|
| Mf | Saint-Martin (Fransızca bölümü) | AMER<sup>3</sup>| <sup>1</sup> EUR| AMER<sup>3</sup>|
| Ws | Samoa | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Sm | San Marino | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| St | Sao Tome ve Principe | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Sa | Saudi Arabia (المملكة العربية السعودية) | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| SN | Senegal | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| RS | Sırbistan | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Sc | Seyşeller | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| SL | Sierra Leone | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Sg | Singapur | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Sx | Sint Maarten | AMER<sup>3</sup>| <sup>1</sup> EUR| AMER<sup>3</sup>|
| SK | Slovakya | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Si | Slovenya | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Sb | Solomon Adaları | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| SO | Somali | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| ZA | South Africa | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Gs | Güney Georgia ve Güney Sandwich Adaları | AMER<sup>3</sup>| <sup>1</sup> EUR| AMER<sup>3</sup>|
| Ss | Güney Sudan | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Es | İspanya | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Lk | Sri Lanka | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Sr | Surinam | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Sj | Svalbard ve Jan Mayen Adaları | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Sz | Svaziland | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| SE | İsveç | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Caner | İsviçre | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Tw | Tayvan, Çin Cumhuriyeti | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| TJ | Tacikistan | <sup>1</sup> EUR| APC<sup>2</sup>| <sup>1</sup> EUR|
| TH | Tayland | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Tl | Timor-Leste | APC<sup>2</sup>| <sup>1</sup> EUR| APC<sup>2</sup>|
| Tg | Togo | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Tk | Tokelau | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Hedef | Tonga | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| TT | Trinidad ve Tobago | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Tn | Tunus | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| TR | Türkiye | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Tm | Türkmenistan | <sup>1</sup> EUR| APC<sup>2</sup>| <sup>1</sup> EUR|
| Tc | Turks ve Caicos Adaları | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Tv | Tuvalu | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Ug | Uganda | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Ua | Ukrayna | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Ae | Birleşik Arap Emirlikleri | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Gb | Birleşik Krallık | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Tz | Tanzanya Birleşik Cumhuriyeti | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| US | Amerika'nın Birleşik Devletler | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Uslu | Uruguay | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| UM | ABD Küçük Dış Adaları | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Uz | Özbekistan | <sup>1</sup> EUR| APC<sup>2</sup>| <sup>1</sup> EUR|
| Vu | Vanuatu | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| VE | Venezuela (Bolivarcı Cumhuriyeti) | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Vn | Vietnam | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| Vı | Virgin Islands, US | AMER<sup>3</sup>| AMER<sup>3</sup>| AMER<sup>3</sup>|
| Wf | Wallis ve Futuna Adaları | APC<sup>2</sup>| APC<sup>2</sup>| APC<sup>2</sup>|
| EH | Batı Sahra | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| YE | Yemen | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Zm | Zambiya | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
| Zw | Zimbabve | <sup>1</sup> EUR| <sup>1</sup> EUR| <sup>1</sup> EUR|
