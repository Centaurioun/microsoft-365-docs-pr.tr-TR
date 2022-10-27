---
title: Microsoft 365 kullanım raporlarında etkin kullanıcı
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- Tier2
- scotvorg
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 093a6d0d-890b-489e-9f46-b15687d3fe4f
description: Microsoft 365 kullanım analizi, etkinlik raporları ve benimseme ölçümlerinin etkin kullanıcısı hakkında bilgi edinin.
ms.openlocfilehash: 5d97422603461ba0ae5334fc7064f287a807a971
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2022
ms.locfileid: "68732217"
---
# <a name="active-user-in-microsoft-365-usage-reports"></a>Microsoft 365 kullanım raporlarında etkin kullanıcı

## <a name="active-user-in-usage-reports"></a>Kullanım raporlarında etkin kullanıcı

Microsoft 365 [kullanım analizi için Microsoft 365](usage-analytics.md) ürünlerinin etkin kullanıcısı ve [yönetim merkezindeki Etkinlik Raporları](../activity-reports/activity-reports.md) aşağıdaki gibi tanımlanır. 
  
|**Ürün**|**Etkin kullanıcı tanımı**|**Notlar**|
|:-----|:-----|:-----|
|Exchange Online  <br/> |Aşağıdaki eylemlerden herhangi birini gerçekleştiren tüm kullanıcılar: Okundu olarak işaretleyin, ileti gönderin, randevu oluşturun, toplantı istekleri gönderin, toplantı isteklerini kabul edin (belirsiz olarak) veya reddedin, toplantıları iptal edin.  <br/> |Takvim bilgileri temsil edilmemektedir; bu özellik yakında çıkacak bir güncelleştirmeyle eklenecektir.  <br/> |
|SharePoint Online  <br/> |Oluşturma, değiştirme, görüntüleme, silme, şirket içinde veya dışında paylaşma ya da herhangi bir sitedeki istemcilerle eşitleme yoluyla dosya etkileşimi gerçekleştirmiş veya herhangi bir sitede bir sayfayı görüntülemiş tüm kullanıcılar.  <br/> |Microsoft 365 Kullanım Analizi şablon uygulamasındaki SharePoint Online için etkin kullanıcı ölçümleri yalnızca SharePoint Team sitesinde veya Grup sitesinde dosya etkinliği yapan kullanıcıları yansıtır. Şablon uygulaması, tanımı yönetim merkezindeki kullanım raporlarındakiyle aynı şekilde eşitleyecek şekilde güncelleştirilir.  <br/> |
|OneDrive İş  <br/> |Oluşturma, değiştirme, görüntüleme, silme, şirket içinde veya dışında paylaşma ya da istemcilerle eşitleme yoluyla dosya etkileşimi gerçekleştirmiş tüm kullanıcılar.  <br/> ||
|Yammer  <br/> |Yammer'da ileti okuyan, gönderen veya beğenen tüm kullanıcılar.  <br/> ||
|Skype Kurumsal  <br/> |Eşler arası bir oturuma (anlık mesajlaşma, sesli ve görüntülü aramalar, uygulama paylaşımı ve dosya aktarımları dahil) katılmış ya da bir konferans düzenlemiş veya konferansa katılmış tüm kullanıcılar.  <br/> ||
|Office  <br/> |Microsoft 365 Pro Plus, Visio Pro veya Project Pro aboneliğini en az bir cihazda etkinleştiren tüm kullanıcılar.  <br/> ||
|Microsoft 365 Grupları  <br/> |Posta kutusu etkinliği olan tüm grup üyeleri (gruba bir ileti gönderilmişse)  <br/> |Bu tanım, grup sitesi dosya etkinliği ve Yammer grup etkinliği (grup sitesindeki dosya etkinliği ve grupla ilişkilendirilmiş Yammer grubuna gönderilen ileti) ile geliştirilecektir. Bu veriler şu anda Microsoft 365 Kullanım Analizi şablon uygulamasında kullanılamıyor  <br/> |
|Microsoft Teams  <br/> |Sohbet iletilerine, özel sohbet iletilerine, aramalara, toplantılara veya diğer etkinliklere katılan tüm kullanıcılar. Diğer etkinlikler, kullanıcı tarafından bazıları dahil ve bunlarla sınırlı olmayan diğer ekip etkinliklerinin sayısı olarak tanımlanır: iletileri beğenme, uygulamalar, dosyalar üzerinde çalışma, arama, ekipleri ve kanalı takip etme ve bunları favorilere ayırma.  <br/> ||
   
## <a name="adoption-metrics"></a>Benimseme Ölçümleri

[Microsoft 365 kullanım analizi](usage-analytics.md) , zaman içinde ürünlerin benimsenmesini göstermek için etkin kullanıcılarla ilgili daha fazla benimseme ölçümü içerir. Bu ölçümler seçilen ay, yıl ve ürün için geçerlidir ve aşağıdaki gibi tanımlanır. 
  
|**Metrik**|**Açıklama**|
|:-----|:-----|
|EnabledUsers  <br/> |Ay içinde ürünü kullanmak için etkinleştirilen kullanıcı sayısı.  <br/> |
|ActiveUsers  <br/> |Ay içinde etkin olan kullanıcı sayısı.  <br/> |
|MoMReturningUsers  <br/> |Önceki ay da etkin olan ay içinde etkin olan kullanıcı sayısı.  <br/> |
|FirstTimeUsers  <br/> |Hizmeti daha önce hiç kullanmamış olan ayda etkin olan kullanıcı sayısı.  <br/> |
|KümülatifActiveUsers  <br/> |Ay içinde etkin olan kullanıcı sayısı ve önceki aylar.  <br/> |
|ActiveUsers(%)  <br/> |Ayın en yakın onuncu gününe yuvarlanan kullanıcıların yüzdesi, o ayda etkinleştirilen kullanıcı sayısına kıyasla etkindir.  <br/> |
|MoMReturningUsers(%)  <br/> |Etkin kullanıcı sayısına kıyasla, önceki ayda da etkin olan ayın en yakın onuncu gününe yuvarlanan kullanıcıların yüzdesi.  <br/> |
   
MoMReturningUsers, FirstTimeUsers, &amp; CumulativeActiveUsers 1 Ocak 2018'den itibaren Microsoft Teams'in eklenmesiyle sıfırlandı.
  
