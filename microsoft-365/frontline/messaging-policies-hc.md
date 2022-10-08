---
title: Microsoft Teams kullanan sağlık kuruluşları için Güvenli Mesajlaşma
author: samanro
ms.author: samanro
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: microsoft-365-frontline
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
ms.localizationpriority: high
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
- m365-frontline
- highpri
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
ms.reviewer: ''
description: Microsoft Teams için okundu bilgileri ve öncelik bildirimleri içerebilen bir Güvenli Mesajlaşma ilkesini özelleştirmeyi öğrenin.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 59e6690e7ff9eb36e531d4a1254503ba98bb07e6
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68057271"
---
# <a name="secure-messaging-for-healthcare-organizations"></a>Sağlık kuruluşları için Güvenli Mesajlaşma

Mesajlaşma ilkeleri, Microsoft Teams'de kullanıcıların kullanabileceği sohbet ve kanal mesajlaşması özelliklerini denetlemek için kullanılır ve Hastaneler, klinikler veya doktor ofisleri gibi sağlık kuruluşları için Güvenli Mesajlaşma'nın genel dağıtımının bir parçasıdır. Burada, kritik iletilerin ne zaman okunduğu konusunda bilgi sahibi olmak çok önemlidir.

Genel (Kuruluş genelinde varsayılan) ilkesini kullanabilir veya kuruluşunuzdaki kişiler için bir veya daha fazla özel mesajlaşma ilkesi oluşturabilirsiniz. Özel ilke oluşturup atamadığınız sürece kuruluşunuzdaki kullanıcılar genel ilkeyi otomatik olarak alır. Özel bir ilke oluşturduktan sonra, bu ilkeye bir kullanıcı veya kuruluşunuzdaki kullanıcı grupları atayın. Örneğin, daha sınırlı bir özellik kümesi elde etmek için yalnızca belirli iş rollerinin bu özellikleri (belki de yalnızca doktorlar ve hemşireler) ve diğer çalışanları (janitorial veya mutfak personeli gibi) kullanmasına izin vermeyi seçebilirsiniz. Kuruluşunuzun neye ihtiyaç duyduğuna kendiniz karar verin. Buradaki kılavuz en çok bir öneridir.

İlkeler, yönetici kimlik bilgileriyle oturum açıp sol gezinti bölmesinde **Mesajlaşma ilkeleri'ni** seçerek [Microsoft Teams yönetim merkezinde](https://admin.teams.microsoft.com) kolayca yönetilebilir.

 :::image type="content" source="media/hc-messaging-policy-admin-center-new.png" alt-text="Mesajlaşma ilkeleri sayfasının ekran görüntüsü." lightbox="media/hc-messaging-policy-admin-center-new.png":::
 
 Kuruluşunuz için mevcut varsayılan Mesajlaşma ilkesini düzenlemek için **Genel (Kuruluş genelinde varsayılan)** seçeneğine tıklayın ve değişikliklerinizi yapın. Yeni bir özel mesajlaşma ilkesi oluşturmak için **Ekle'ye** tıklayın ve ayarlarınızı seçin. İşiniz bittiğinde **Kaydet'i** seçin.

![Mesajlaşma ilkesi ayarlarının ekran görüntüsü.](media/hc-messaging-policy.png)

Aşağıdaki ayarlar Healthcare uygulamaları için özel ilgi çekicidir ve Healthcare alanında kullanılan özel bir ilke tasarlarken dikkate alınmalıdır:

## <a name="read-receipts"></a>Okundu bilgileri

Okundu bilgileri, sohbet iletisini gönderenin iletinin alıcı tarafından 1:1'de ne zaman okundığını ve 20 veya daha az kişinin grup sohbeti yapmasını sağlar. Okundu bilgilerinin kullanıcı tarafından denetlenip denetlenmeyeceğini, herkes için açık veya herkes için kapalı olduğunu belirtmek için bu ayarı kullanın. İleti okundu bilgileri Healthcare kuruluşlarında önemlidir çünkü bir iletinin okunup okunmadığı konusunda belirsiz bir şekilde kaldırılır.

Sağlık uygulamaları için **, herkes için Kullanıcı tarafından denetlenen** veya **Açık'ı** seçin. **Herkes için Açık** ayarını kullanırken, kiracının tamamı için alındı bilgilerini ayarlamanın tek yolunun tüm kiracı için yalnızca bir mesajlaşma ilkesine ("Genel (Kuruluş Genelinde Varsayılan)" adlı varsayılan ilke) sahip olmak veya kiracıdaki tüm mesajlaşma ilkelerinin makbuzlar için aynı ayarları kullanmasını sağlamak olduğunu unutmayın. Okundu bilgileri özelliği en çok özellik **herkes için Açık** olarak etkinleştirildiğinde etkilidir.

*Okundu bilgisi olmayan kullanım örneği:* Yüksek riskli bir hasta olan Jakob Roth hastaneye kabul edilir.  Sofia Krause, farklı uzmanlar da dahil olmak üzere sağlık çalışanlarının disiplinler arası ekibinin (IDT) bir parçası olarak çalışan bir hemşire, bu hastadan sorumlu birincil bakım koordinatörü olarak atandı.  Sofya, çeşitli mesajlaşma istemcileri ve uygulamaları kullanan hemşire ve doktor gruplarına e-postalar ve diğer anlık iletiler gönderiyor ve çoğu zaman ekip üyeleri tarafından okunup okunmadığına dair bir yanıt veya gösterge almıyor. Karmaşık iletişim süreçleri nedeniyle Jakob'un ilaçları yanlış uygulanıyor ve hastanede kalış süresi uzatılıyor.

*Okundu bilgileri içeren kullanım örneği:* Yüksek riskli bir hasta olan Jakob Roth hastaneye kabul edilir.  Sofia Krause, farklı uzmanlar da dahil olmak üzere sağlık çalışanlarının disiplinler arası ekibinin (IDT) bir parçası olarak çalışan bir hemşire, bu hastadan sorumlu birincil bakım koordinatörü olarak atandı.  Sofia, bakımı koordine etmek için hastayla birlikte çalışacak bir dizi doktor ve diğer hemşirelerle grup sohbeti başlatıyor ve acil bir triyaj başlatıyor.  Hemşireler ve doktorlar, bakım koordinasyon süreci boyunca hastanın bakım planı üzerinde iletişim kurar ve işbirliği kurar.  Önemli ve acil iletiler 1:1 ve grup sohbeti konuşmaları üzerinden gönderilir. Sofya, destek isteyen gönderilen iletilerin hedeflenen hekimler veya hemşireler tarafından teslim ve okunup okunmadığını belirlemek için okundu bilgileri işlevini kullanıyor. Jakob'ın hasta sonuçları neredeyse en iyi duruma geldi ve sağlık ekibi sorunsuz iletişim kurarak eve daha erken gidiyor.

## <a name="send-urgent-messages-using-priority-notifications"></a>Öncelik bildirimlerini kullanarak acil iletiler gönderme

Kullanıcı, diğer kullanıcılara sohbet iletileri gönderirken iletiyi *acil* olarak işaretleyebilir. Bu özellik, kritik bir olayın dikkate alınması gerektiğinde hastane personelinin birbirleri için uyarı vermelerine yardımcı olur. Normal *önemli* iletilerden farklı olarak, [öncelik bildirimleri](https://support.microsoft.com/article/mark-a-message-as-important-or-urgent-in-teams-ea99d5b6-1317-4550-8d75-86ff14cd4462) kullanıcılara 20 dakikaya kadar veya ileti alıcı tarafından alınıp okunana kadar iki dakikada bir uyarır ve iletinin zamanında işlem yapma olasılığını en üst düzeye çıkarır.

Bir yönetici, bu ilkeye atanan kullanıcıların öncelik bildirimleri gönderme özelliğini etkinleştirebilir veya devre dışı bırakabilir. Bu özellik varsayılan olarak açıktır. Öncelik iletisinin alıcısı aynı mesajlaşma ilkesine sahip olmayabilir ve öncelikli iletileri almayı devre dışı bırakma seçeneğine sahip olmayabilir. Healthcare uygulamaları için özelliği en az bazı kullanıcılar için etkinleştirmenizi öneririz, ancak hangilerini belirlemeniz gerekir.

*Kullanım örneği:* Sofia Krause, yüksek riskli bir hasta olan Jakob Roth'u hazır bekliyor. Manuela Carstens, bir doktor, bu hastanın birincil bakım doktoru.  Sofia, Jakob'un önceliklendirmesi konusunda acil yardım isteyen bir öncelik bildirimi kullanarak Manuela'ya bir mesaj gönderiyor.  Manuela'nın telefonu iletiyi alır ancak Manuela telefonun titreşimini hissetmedi ve yanıt vermiyor. Teams Manuela'ya yeniden bildirim gönderir ve iletiyi okuyana kadar kalıcı olarak yeniden bildirimde bulunmaya devam eder. Okundu bilgileri de etkinleştirilirse Sofia, Manuela nasıl yanıt vereceğine karar vermeden önce bile mesajın Manuela tarafından okunduğunu fark edebilir.

## <a name="related-topics"></a>İlgili konular

- [Teams'de mesajlaşma ilkelerini yönetme](/microsoftteams/messaging-policies-in-teams)
- [Sağlık kuruluşları için Teams'i kullanmaya başlama](teams-in-hc.md)
