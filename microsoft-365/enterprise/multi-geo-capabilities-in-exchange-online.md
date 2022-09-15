---
title: Exchange Multi-Geo
ms.reviewer: adwood
ms.author: chrisda
author: chrisda
manager: serdars
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.localizationpriority: medium
description: Exchange Online'daki özellik sınırlamaları ve posta kutusu yerleşimi gibi çok coğrafi özellikler hakkında bilgi edinin.
ms.openlocfilehash: 549cd033856e01375b5549dc0b674617d02188ff
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67698363"
---
# <a name="multi-geo-capabilities-in-exchange-online"></a>Exchange Online'da Multi-Geo Capabilities

Çok coğrafi bir ortamda, kullanıcı başına Exchange Online posta kutusu içeriğinin (bekleyen veriler) konumunu seçebilirsiniz.

Posta kutularını uydu coğrafi konumlarına şu şekilde yerleştirebilirsiniz:

- Doğrudan uydu coğrafi konumunda yeni bir Exchange Online posta kutusu oluşturma.

- Kullanıcının tercih edilen veri konumunu değiştirerek mevcut bir Exchange Online posta kutusunu uydu coğrafi konumuna taşıma.

- Şirket içi Exchange kuruluşundan bir posta kutusunu doğrudan uydu coğrafi konumuna ekleme.

## <a name="mailbox-placement-and-moves"></a>Posta kutusu yerleşimi ve taşımaları

Microsoft önkoşul çok coğrafi yapılandırma adımlarını tamamladıktan sonra, Exchange Online Azure AD'daki kullanıcı nesnelerinde **PreferredDataLocation** özniteliğini kabul eder.

Exchange Online **PreferredDataLocation** özelliğini Azure AD Exchange Online dizin hizmetindeki **MailboxRegion** özelliğiyle eşitler. **MailboxRegion** değeri, kullanıcı posta kutularının ve ilişkili arşiv posta kutularının yerleştirileceği coğrafi konumu belirler. Kullanıcının birincil posta kutusunu ve arşiv posta kutularını farklı coğrafi konumlarda bulunacak şekilde yapılandırmak mümkün değildir. Kullanıcı nesnesi başına yalnızca bir coğrafi konum yapılandırılabilir.

- **PreferredDataLocation** mevcut posta kutusu olan bir kullanıcıda yapılandırıldığında, posta kutusu yeniden konumlandırma kuyruğuna alınır ve otomatik olarak belirtilen coğrafi konuma taşınır.

- **PreferredDataLocation** mevcut posta kutusu olmayan bir kullanıcıda yapılandırıldığında, posta kutusunu sağladığınızda belirtilen coğrafi konuma sağlanır.

- Bir kullanıcıda **PreferredDataLocation** belirtilmediğinde, posta kutusunu sağladığınızda merkezi coğrafi konumda sağlanır.

- **PreferredDataLocation** kodu yanlışsa (örneğin, NAM yerine NAN yazım hatası), posta kutusu merkezi coğrafi konumda sağlanır.

**Not**: Çoklu coğrafi özellikler ve Skype Kurumsal Çevrimiçi olarak barındırılan çevrimiçi toplantılar, hizmetleri bulmak için kullanıcı nesnelerinde **PreferredDataLocation** özelliğini kullanır. Bölgesel olarak barındırılan toplantılar için kullanıcı nesnelerinde **PreferredDataLocation** değerlerini yapılandırırsanız, Microsoft 365 kiracısında çoklu coğrafi konum etkinleştirildikten sonra bu kullanıcıların posta kutusu otomatik olarak belirtilen coğrafi konuma taşınır.

## <a name="feature-limitations-for-multi-geo-in-exchange-online"></a>Exchange Online'da çoklu coğrafi bölge için özellik sınırlamaları

- Exchange yönetim merkezinde (EAC) kullanılabilen güvenlik ve uyumluluk özellikleri (örneğin, denetim ve eBulma) çok coğrafili kuruluşlarda kullanılamaz. Bunun yerine, güvenlik ve uyumluluk özelliklerini yapılandırmak için [Microsoft 365 Güvenlik & Uyumluluk Merkezi'ni](https://support.office.com/article/7e696a40-b86b-4a20-afcc-559218b7b1b8) kullanmanız gerekir.

- Mac için Outlook kullanıcılar, posta kutularını yeni bir coğrafi konuma taşırken Çevrimiçi Arşiv klasörüne geçici erişim kaybıyla karşılaşabilir. Bu koşul, kullanıcının birincil posta kutuları ve arşiv posta kutuları farklı coğrafi konumlarda olduğunda ortaya çıkar çünkü coğrafi konumlar arası posta kutusu taşıma işlemleri farklı zamanlarda tamamlanabilir.

- Kullanıcılar posta *kutusu klasörlerini* Web üzerinde Outlook(eski adıyla Outlook Web App veya OWA) coğrafi konumlar arasında paylaşamaz. Örneğin, Avrupa Birliği'ndeki bir kullanıcı Birleşik Devletler bulunan bir posta kutusunda paylaşılan klasörü açmak için Web üzerinde Outlook kullanamaz. Ancak Web üzerinde Outlook kullanıcıları, başka bir kişinin *posta kutusunu* Outlook Web App ayrı bir tarayıcı penceresinde açma başlığı altında açıklandığı gibi [ayrı bir tarayıcı penceresi kullanarak farklı coğrafi konumlarda diğer posta kutularını](https://support.office.com/article/A909AD30-E413-40B5-A487-0EA70B763081#__toc372210362) açabilir.

  **Not**: Windows üzerinde Outlook'ta coğrafi konumlar arası posta kutusu klasör paylaşımı desteklenir.

- Ortak klasörler çok coğrafili kuruluşlarda desteklenir. Ancak ortak klasörlerin merkezi coğrafi konumda kalması gerekir. Ortak klasörleri uydu coğrafi konumlarına taşıyamazsınız.

- Çok coğrafi bir ortamda, coğrafi bölgeler arası posta kutusu denetimi desteklenmez. Örneğin, kullanıcıya farklı bir coğrafi konumdaki paylaşılan posta kutusuna erişim izinleri atanmışsa, bu kullanıcı tarafından gerçekleştirilen posta kutusu eylemleri paylaşılan posta kutusunun posta kutusu denetim günlüğüne kaydedilmez. Exchange yöneticisi denetim olayları da yalnızca varsayılan konum için kullanılabilir. Daha fazla bilgi için bkz. [Posta kutusu denetimini yönetme](../compliance/enable-mailbox-auditing.md).
