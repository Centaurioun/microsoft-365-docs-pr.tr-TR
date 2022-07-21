---
title: Etkinlik gezgininde bildirilen etiketleme eylemleri
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Etkinlik gezgininde kullanılabilen etiketleme etkinliklerinin listesi.
ms.openlocfilehash: 27a6bb3f0fe4293d5904c7e1661ef1e422fbac5b
ms.sourcegitcommit: 24827a509b3e78959ce67679646e572a0c996282
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66917895"
---
# <a name="labeling-activities-that-are-available-in-activity-explorer"></a>Etkinlik gezgininde kullanılabilen etiketleme etkinlikleri

## <a name="sensitivity-label-applied"></a>Duyarlılık etiketi uygulandı

Etiketlenmemiş bir belge etiketlendiğinde veya duyarlılık etiketiyle bir e-posta gönderildiğinde bu olay oluşturulur.

- Office yerel uygulamalarında ve web uygulamalarında kaydetme sırasında yakalanır.
- Azure Information Protection (AIP) birleşik etiketleme istemcisi için oluşum sırasında yakalanır.
- Etiketleri yükseltme ve düşürme eylemleri Etiket *olay türü* alanı ve filtresi aracılığıyla da izlenebilir.

|Kaynak  |Etkinlik gezgininde bildirildi | Not  |
|---------|---------|---------|
| Word, Excel, PowerPoint|Evet |
|Outlook| Evet | |
|SharePoint online, OneDrive|Evet | |
|Exchange        |Evet         | |
|Azure Information Protection (AIP) birleşik istemcisi ve AIP birleşik tarayıcısı |Evet |AIP *yeni etiket* eylemi Etkinlik gezgininde *uygulanan etiketle* eşlenir   |
|Microsoft Bilgi Koruması (MIP) SDK         |Evet|AIP *yeni etiket* eylemi Etkinlik gezgininde *uygulanan etiketle* eşlenir|
|Rights Management Service (RMS)         |Geçerli değil         | |
|Power BI desktop ve web        | Hayır| Microsoft 365 denetim günlüklerinde erişilebilir         |
|Bulut Uygulamaları için Microsoft Defender         |Hayır|         |

## <a name="sensitivity-label-changed"></a>Duyarlılık etiketi değiştirildi

Bu olay, belgede veya e-postada duyarlılık etiketi her güncelleştirildiğinde oluşturulur.

- AIP birleşik istemcisi, AIP birleşik tarayıcısı ve MIP SDK kaynakları için, AIP *yükseltme etiketi* ve *aşağı sürüme düşürme etiketi* eylemi Etkinlik gezgini *etiketiyle eşleşiyor değiştirildi*

- Office yerel uygulamalarında ve web uygulamalarında kaydetme noktasında yakalanır.
- AIP birleşik etiketleme istemcisi ve tarayıcı zorlamaları için oluşum sırasında yakalanır
- Etiketleri yükseltme ve düşürme eylemleri Etiket *olay türü* alanı ve filtresi aracılığıyla da izlenebilir. *Gerekçe metni*, SharePoint Online ve OneDrive dışında da yakalanır.
- Outlook'taki Office yerel uygulamalarında yapılan duyarlılık etiketlemesi, dosya kaydetme/e-posta gönderme eylemleri öncesinde oluşturulan son eylemi toplar. Örneğin, kullanıcı e-postadaki etiketi göndermeden önce birden çok kez değiştirirse, e-posta gönderildiğinde bulunan son etiket denetim günlüğünde yakalanır ve etkinlik gezgininde bildirilir.

|Kaynak  |Etkinlik gezgininde bildirildi|Not  |
|---------|---------|---------|
|Word, Excel, PowerPoint         |Evet         |
|Outlook         |Evet         |
|SharePoint Online, OneDrive         |Evet         |
|Exchange         |Evet         |
|AIP birleşik istemcisi         |Evet         |
|AIP birleşik tarayıcısı         |Evet         |
|MIP SDK'sı         |Evet         |
|RMS hizmeti         |Geçerli değil         |
|Power BI desktop ve Web         |Hayır         |Microsoft 365 denetim günlüklerinde erişilebilir |
|Bulut Uygulamaları için Microsoft Defender     |Hayır         |         |

## <a name="sensitivity-label-removed"></a>Duyarlılık etiketi kaldırıldı

Bu olay, bir dosyadan veya belgeden her duyarlılık etiketi kaldırıldığında oluşturulur.

- Bu olay, Office yerel uygulamalarında ve web uygulamalarında kaydetme sırasında yakalanır.
- Azure Information Protection (AIP) birleşik etiketleme istemcisi için oluşum sırasında yakalanır.
- Outlook'ta Office'in yerleşik etiketleriyle duyarlılık etiketlemesi, dosya kaydetme/e-posta gönderme eylemleri öncesinde oluşturulan son etiketleme olayını toplar.

|Kaynak  |Etkinlik gezgininde bildirildi | Not  |
|---------|---------|---------|
|Word, Excel, PowerPoint         |Evet         |
|Outlook         |Evet         ||
|SharePoint Online, OneDrive         |Evet         |
|Exchange         |Evet         |
|AIP birleşik istemcisi         |Evet         |AIP *etiketi kaldır* eylemi Etkinlik gezgininde *etiket kaldırılan* eylemle eşlenir|
|AIP birleşik tarayıcısı         |Evet         |AIP *etiketi kaldır* eylemi Etkinlik gezgininde *etiket kaldırılan* eylemle eşlenir |
|MIP SDK'sı         |Evet         |AIP *etiketi kaldır* eylemi Etkinlik gezgininde *etiket kaldırılan* eylemle eşlenir |
|RMS hizmeti         |Geçerli değil         |
|Power BI desktop ve Web         |Hayır         |Microsoft 365 denetim günlüklerinde erişilebilir |
|Bulut Uygulamaları için Microsoft Defender     |Hayır         |         |

## <a name="sensitivity-label-file-read"></a>Duyarlılık etiketi dosyası okundu

Bu olay, etiketlenmiş veya korumalı bir belge her açıldığında oluşturulur.

|Kaynak  |Etkinlik gezgininde bildirildi | Not  |
|---------|---------|---------|
|Word, Excel, PowerPoint         |Evet         |
|Outlook         |Hayır         |
|SharePoint Online, OneDrive         |Hayır         |
|Exchange         |Hayır         |
|AIP birleşik istemcisi         |Evet         |AIP *erişim* eylemi Etkinlik gezginindeki *dosya okuma* eylemiyle eşlenir|
|AIP birleşik tarayıcısı         |Evet         |AIP *erişim* eylemi Etkinlik gezginindeki *dosya okuma* eylemiyle eşlenir|
|MIP SDK'sı         |Evet         |AIP *erişim* eylemi Etkinlik gezginindeki *dosya okuma* eylemiyle eşlenir|
|RMS hizmeti         |Evet         |*Erişim* eylemi Etkinlik gezginindeki *dosya okuma* eylemiyle eşlenir |
|Power BI desktop ve Web         |Hayır         |Microsoft 365 denetim günlüklerinde erişilebilir |
|Bulut Uygulamaları için Microsoft Defender     |Hayır         |         |

## <a name="files-discovered"></a>Bulunan dosyalar

Bu olay, AIP tarayıcısı çeşitli konumlardaki hassas verileri taramak için kullanıldığında ve dosyaları bulduğunda dosyalar her keşfedildiğinde oluşturulur.

|Kaynak  |Etkinlik gezgininde bildirildi | Not  |
|---------|---------|---------|
|Word, Excel, PowerPoint         |Geçerli değil         |
|Outlook         |Geçerli değil         |
|SharePoint Online, OneDrive         |Geçerli değil         |
|Exchange         |Geçerli değil         |
|AIP birleşik istemcisi         |Geçerli değil       |
|AIP birleşik tarayıcısı         |Evet         |AIP *bulma* eylemi Etkinlik gezgininde *bulunan dosyalar* eylemiyle eşlenir|
|MIP SDK'sı         |Evet         |AIP *bulma* eylemi, Etkinlik gezgininde *bulunan dosya* eylemiyle eşlenir|
|RMS hizmeti         |Geçerli değil         |
|Power BI desktop ve Web         |Geçerli değil         |
|Bulut Uygulamaları için Microsoft Defender     |Geçerli değil         |         |

## <a name="sensitivity-label-file-renamed"></a>Duyarlılık etiketi dosyası yeniden adlandırıldı

Duyarlılık etiketine sahip bir belge yeniden adlandırıldığı her durumda bu olay oluşturulur.

|Kaynak  | Etkinlik gezgininde bildirildi | Not  |
|---------|---------|---------|
|Word, Excel, PowerPoint         |Evet         |
|Outlook         |Geçerli değil         |
|SharePoint Online, OneDrive         |Hayır        |
|Exchange         |Geçerli değil         |
|AIP birleşik istemcisi         |Hayır         |
|AIP birleşik tarayıcısı         |Hayır         |
|MIP SDK'sı         |Hayır         |
|RMS hizmeti         |Hayır      |
|Power BI desktop ve Web         |Hayır         |
|Bulut Uygulamaları için Microsoft Defender     |Hayır         |         |

## <a name="file-removed"></a>Dosya kaldırıldı

Bu olay, AIP tarayıcısı daha önce taranmış bir dosyanın kaldırıldığını her algıladığından oluşturulur.

|Kaynak  |Etkinlik gezgininde bildirildi | Not  |
|---------|---------|---------|
|Word, Excel, PowerPoint         |Geçerli değil         |
|Outlook         |Geçerli değil         |
|SharePoint Online, OneDrive         |Geçerli değil           |
|Exchange         |Geçerli değil         |
|AIP birleşik istemcisi         |Geçerli değil            |
|AIP birleşik tarayıcısı         |Evet         |
|MIP SDK'sı         |Geçerli değil            |
|RMS hizmeti         |Geçerli değil         |
|Power BI desktop ve Web         |Geçerli değil  |
|Bulut Uygulamaları için Microsoft Defender     |Geçerli değil        |         |

### <a name="protection-applied"></a>Koruma uygulandı

Bu olay, etiketi olmayan bir öğeye ilk kez koruma el ile eklenir oluşturulur.

|Kaynak  |Etkinlik gezgininde bildirildi | Not  |
|---------|---------|---------|
|Word, Excel, PowerPoint         |Hayır         |
|Outlook         |Hayır         |
|SharePoint Online, OneDrive         |Geçerli değil           |
|Exchange         |Hayır       |
|AIP birleşik istemcisi         |Evet            |
|AIP birleşik tarayıcısı         |Geçerli değil         |
|MIP SDK'sı         |Evet            |
|RMS hizmeti         |Geçerli değil         |
|Power BI desktop ve Web         |Geçerli değil            |
|Bulut Uygulamaları için Microsoft Defender     |Geçerli değil        |         |

## <a name="protection-changed"></a>Koruma değiştirildi

Etiketsiz bir belgedeki koruma el ile değiştirildiğinde bu olay oluşturulur.

|Kaynak  |Etkinlik gezgininde bildirildi |
|---------|---------|
|Word, Excel, PowerPoint         |Hayır         |
|Outlook         |Hayır         |
|SharePoint Online, OneDrive         |Geçerli değil           |
|Exchange         |Hayır       |
|AIP birleşik istemcisi         |Evet            |
|AIP birleşik tarayıcısı         |Geçerli değil         |
|MIP SDK'sı         |Evet            |
|RMS hizmeti         |Geçerli değil         |
|Power BI desktop ve Web         |Geçerli değil            |
|Bulut Uygulamaları için Microsoft Defender     |Geçerli değil        |

## <a name="protection-removed"></a>Koruma kaldırıldı

Etiketsiz bir belgedeki koruma el ile değiştirildiğinde bu olay oluşturulur.

|Kaynak  |Etkinlik gezgininde bildirildi |
|---------|---------|
|Word, Excel, PowerPoint         |Hayır         |
|Outlook         |Hayır         |
|SharePoint Online, OneDrive         |Geçerli değil           |
|Exchange         |Hayır       |
|AIP birleşik istemcisi         |Evet            |
|AIP birleşik tarayıcısı         |Geçerli değil         |
|MIP SDK'sı         |Evet            |
|RMS hizmeti         |Geçerli değil         |
|Power BI desktop ve Web         |Geçerli değil            |
|Bulut Uygulamaları için Microsoft Defender     |Geçerli değil        |

## <a name="dlp-policy-matched"></a>DLP ilkesi eşleştirildi

Bu olay, bir belgede veya e-postada bir DLP ilkesi her eşleştirildiğinde oluşturulur.

|Kaynak  |Etkinlik gezgininde bildirildi |
|---------|---------|
|Exchange         |Evet       |
|SharePoint Online|Evet          |
|OneDrive |Evet|
|Teams |Evet   |
|cihazları Windows 10         |Evet |
|MAC         |Hayır     |
|Şirket içi         |Hayır|
|Bulut Uygulamaları için Microsoft Defender     |Hayır        |

Windows 10 Cihazları (Uç Nokta DLP) olayları şunlardır:

- Dosya silindi
- Dosya oluşturuldu
- Dosya panoya kopyalandı
- Dosya değiştirildi
- Dosya okuma
- Dosya yazdırıldı
- Dosya yeniden adlandırıldı
- Ağ paylaşımına kopyalanan dosya
- İzin verilmeyen uygulama tarafından erişilen dosya

## <a name="retention-label-applied"></a>Bekletme etiketi uygulandı

Etiketlenmemiş bir belge etiketlendiğinde veya bekletme etiketiyle bir e-posta gönderildiğinde bu olay oluşturulur.

- Belge için kaydetme sırasında ve e-posta gönderme sırasında yakalanır.

|Kaynak  |Etkinlik gezgininde bildirildi |
|---------|---------|
|Exchange         |Hayır       |
|SharePoint Online|Evet          |
|OneDrive |Evet|

## <a name="retention-label-changed"></a>Bekletme etiketi değiştirildi

Bu olay, bir belge veya e-postada etiket her güncelleştirildiğinde oluşturulur.

- Belge için kaydetme sırasında ve e-posta gönderme sırasında yakalanır.

|Kaynak  |Etkinlik gezgininde bildirildi |
|---------|---------|
|Exchange         |Hayır       |
|SharePoint Online|Evet          |
|OneDrive |Evet|

## <a name="retention-label-removed"></a>Bekletme etiketi kaldırıldı

Bu olay, bir dosyadan veya belgeden her etiket kaldırıldığında oluşturulur.

- Belge için kaydetme sırasında ve e-posta gönderme sırasında yakalanır.

|Kaynak  |Etkinlik gezgininde bildirildi |
|---------|---------|
|Exchange         |Hayır       |
|SharePoint Online|Evet          |
|OneDrive |Evet|

## <a name="known-issues"></a>Bilinen sorunlar
  
- Önerilen etiket aracı ipucu son kullanıcıya gösterildiğinde yakalanmaz. Ancak kullanıcı önerilen etiketi uygulamayı seçerse, etiket *Nasıl uygulanır* alanında *Önerilen* olarak gösterilir.

- SharePoint ve OneDrive'dan duyarlılık etiketi düşürmesinde gerekçe metni şu anda kullanılamıyor.

- Hassas bilgi türleri şu anda Word, Excel, PowerPoint ve Outlook'un yanı sıra SharePoint Online ve OneDrive'daki otomatik etiketleme etkinlikleri için kullanılamaz.
