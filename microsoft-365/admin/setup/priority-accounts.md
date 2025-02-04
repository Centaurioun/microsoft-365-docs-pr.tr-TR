---
title: Öncelikli hesapları yönetme ve izleme
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- Tier2
- scotvorg
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- admindeeplinkMAC
description: İş etkisi yüksek hesaplara gönderilen veya bu hesaplardan gönderilen başarısız ve gecikmeli e-posta iletilerini izleyin.
ms.openlocfilehash: 5c19164d8460c1722fe5ebec7355c2283d007a54
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2022
ms.locfileid: "68732327"
---
# <a name="manage-and-monitor-priority-accounts"></a>Öncelikli hesapları yönetme ve izleme

Her Microsoft 365 kuruluşunda yöneticiler, liderler, yöneticiler veya hassas, özel veya yüksek öncelikli bilgilere erişimi olan diğer kullanıcılar gibi önemli kişiler vardır.

Kuruluşunuzun bu hesapları korumasına yardımcı olmak için artık belirli kullanıcıları öncelikli hesaplar olarak belirleyebilir ve ek koruma sağlayan uygulamaya özgü özelliklerden yararlanabilirsiniz. Gelecekte, daha fazla uygulama ve özellik öncelikli hesapları destekleyecek ve başlangıç olarak iki özellik duyurduk: **öncelik hesabı koruması** ve **premium posta akışı izleme**.

- **Öncelik hesabı koruması** - Office 365 için Microsoft Defender (eski adı Office 365 yla Gelişmiş Tehdit Koruması) uyarılarda, raporlarda ve araştırmalarda filtrelerde kullanılabilecek etiketler olarak öncelik hesaplarını destekler. Daha fazla bilgi için [bkz. Office 365 için Microsoft Defender'de kullanıcı etiketleri](../../security/office-365-security/user-tags.md).

  Doğal bir soru şudur: "Tüm kullanıcılar öncelikli değil mi? Neden tüm kullanıcılar öncelikli hesaplar olarak belirlenmiyor?" Evet, tüm kullanıcılar önceliklidir, ancak öncelik hesabı koruması aşağıdaki ek avantajları sunar:

  - **Ek buluşsal yöntemler**: Microsoft veri merkezlerindeki posta akışı analizimiz, şirket yöneticileri için posta akışı desenlerinin ortalama çalışandan farklı olduğunu gösterir. Öncelik hesabı koruması, şirket yöneticilerine özel olarak uyarlanmış ve normal bir çalışana fayda sağlayabilen ek buluşsal yöntemler sunar.
  - **Raporlamada ek görünürlük**: Uygulamada, tüm kullanıcılara (veya etkilenen tüm kullanıcılara) yönelik bilgiler uyarılarda, raporlarda ve araştırmalarda zaten kullanılabilir. Filtre olarak öncelik hesapları etiketi, araştırmalarınızı özellikle hedeflemenizi sağlar.

- **Premium Posta Akışı İzleme** - İyi durumdaki posta akışı işletmenin başarısı için kritik olabilir ve teslim gecikmeleri veya hataları işletmeyi olumsuz etkileyebilir. Başarısız veya gecikmeli e-postalar için bir eşik seçebilir, bu eşik aşıldığında uyarılar alabilir ve öncelik hesapları için e-posta sorunlarının raporunu görüntüleyebilirsiniz. Daha fazla bilgi için [modern EAC'de öncelik hesapları raporuyla ilgili Email sorunlarına](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report) göz atın

Öncelik hesapları için en iyi güvenlik yöntemleri için bkz. [Öncelik hesapları için güvenlik önerileri](../../security/office-365-security/security-recommendations-for-priority-accounts.md).

## <a name="before-you-begin"></a>Başlamadan önce

Bu konuda açıklanan **Öncelik hesabı koruma** özelliği yalnızca aşağıdaki gereksinimleri karşılayan kuruluşlar tarafından kullanılabilir:

- Office 365 E3, Office 365 E5, Microsoft 365 E5 veya Microsoft 365 E5 Güvenlik olanlar dahil olmak üzere plan 2'yi Office 365 için Microsoft Defender.

Bu konuda açıklanan **Premium Posta Akışı İzleme** özelliği yalnızca aşağıdaki gereksinimleri karşılayan kuruluşlar tarafından kullanılabilir:

- Kuruluşunuzun lisans sayısı en az 5.000 olmalıdır; bunlardan biri veya aşağıdaki ürünlerin bir birleşimi: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5. Örneğin, kuruluşunuzda 3.000 Office 365 E3 lisansı ve uygun ürünlerden toplam 5.500 lisans için 2.500 Microsoft 365 E5 olabilir.
- Kuruluşunuzun bir veya daha fazla temel iş yükü (Teams, OneDrive İş, SharePoint Online, Exchange Online ve Office uygulamaları) için en az 50 aylık etkin kullanıcısı olmalıdır.

> [!NOTE]
> En fazla 250 öncelik hesabını izleyebilirsiniz.

Bir posta kutusuna öncelik hesabı koruması uyguladığınızda, posta kutusuna erişimi olan kullanıcılara da öncelik hesabı koruması uygulamanız gerekir (örneğin, CEO ve CEO'nun takvimini yöneten yönetici yardımcısı).

### <a name="add-priority-accounts-from-the-setup-page"></a>Kurulum sayfasından öncelik hesapları ekleme

**Kurulum sayfasından** öncelik hesapları ekleyin.

1. konumundaki Microsoft 365 yönetim merkezi <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>gidin.

2. **Kuruluş bilgisi** **kurulumu'na** >  gidin ve **En önemli hesaplarınızı izleme'nin** altında **Görüntüle'yi** seçin.

3. **Başlarken** veya **Yönet'i** seçin.

4. **Öncelik hesapları ekle** sayfasında, arama alanına öncelik hesapları listesine eklemek istediğiniz kişinin adını veya e-posta adresini yazın. Ayrıca başarısız veya gecikmeli e-postalar için e-posta eşiğinizi ayarlayabilir ve öncelik hesaplarıyla ilgili sorunların haftalık raporunu alabilirsiniz.

5. Kullanıcıyı seçin ve **Kaydet'i** seçin.

Ayrıca, Etkin kullanıcılar sayfasından da öncelik hesapları ekleyebilirsiniz.

### <a name="add-priority-accounts-from-active-users-page"></a>Etkin kullanıcılar sayfasından öncelik hesapları ekleme

Etkin kullanıcılar sayfasından öncelik hesapları ekleyin.

1. Şuradan yönetim merkezine gidin: <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.

2. **Etkin Kullanıcılar'a** >  gidin ve sayfanın üst kısmındaki üç noktayı (daha fazla eylem) seçin. **Öncelik hesaplarını yönet'i** seçin.

3. **Hesap ekle'yi** seçin ve **Öncelik hesapları ekle** sayfasında, arama alanına öncelik hesapları listesine eklemek istediğiniz kişinin adını yazın.

4. Kullanıcıyı seçin ve **Kaydet'i** seçin.

## <a name="remove-a-user-from-the-priority-accounts-list"></a>Kullanıcıyı öncelik hesapları listesinden kaldırma

1. konumundaki Microsoft 365 yönetim merkezi <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>gidin.

2. **Kuruluş bilgisi** **kurulumu'na** >  gidin ve **En önemli hesaplarınızı izleme'nin** altında **Görüntüle'yi** seçin.

3. **En çok hesaplarınızı izleyin** sayfasında **, Bu özelliği yönet'in** altında **Öncelik hesapları'nı** seçin.

4. **Öncelik hesapları** sayfasında, listeden kaldırmak istediğiniz kullanıcıyı veya kullanıcıları seçin ve **Hesapları kaldır'ı** seçin.

## <a name="related-topics"></a>İlgili konular

[Microsoft 365'te Öncelik Hesaplarını Kullanma](https://techcommunity.microsoft.com/t5/microsoft-365-blog/using-priority-accounts-in-microsoft-365/ba-p/1873314)
