---
title: Kendi etki alanınızı veya DNS kayıtlarınızı ekledikten sonra sorunları bulma ve düzeltme
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- VSBFY23
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 40398b0b-bdd0-4afd-ab5e-b5ae6b7990bf
description: DNS kayıtlarının doğru ayarlandığından emin olarak özel bir etki alanı ayarlarken karşılaştığınız sorunları izlemeyi öğrenin.
ms.openlocfilehash: 2e4f69b19fd87f45017a304414018995e90703a7
ms.sourcegitcommit: 2f6a7410e9919f753a759c1ada441141e18f06fd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/30/2022
ms.locfileid: "67085169"
---
# <a name="find-and-fix-issues-after-adding-your-domain-or-dns-records"></a>Kendi etki alanınızı veya DNS kayıtlarınızı ekledikten sonra sorunları bulma ve düzeltme

 Aradığınızı bulamazsanız, **[Etki Alanları SSS sayfasını inceleyin](../setup/domains-faq.yml)**. 
  
Etki alanınızı Microsoft 365 ile çalışacak şekilde ayarlamak zor olabilir. DNS sistemiyle çalışmak oldukça zordur ve etki alanınız için DNS kurulumu, e-posta gibi önemli iş etkinliklerinizi etkileyebilir!

> [!NOTE]
> Etki alanınızın durumunu denetleyerek etki alanınızla ilgili sorunları de kontrol edebilirsiniz. **Kurulum** > **Etki Alanları'na** gidin ve **Durum** sütunundaki bildirimleri görüntüleyin. Bir sorun görürseniz üç noktayı (diğer eylemler) seçin ve ardından **Sistem durumunu denetle'yi** seçin. Açılan bölmede etki alanınızda oluşan sorunlar açıklanır.
  
## <a name="whats-going-on"></a>Ne var ne yok?

- [Etki alanınızı doğrulayamaz mısınız?](#cant-verify-your-domain)
    
- [Outlook çalışmıyor mu?](#outlook-isnt-working)
    
- [Herkesin e-postası Microsoft 365'e geçti ve yalnızca E-postanızın geçişini mi istiyorsunuz?](#everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch)

- [Kar amacı gütmeyen kuruluş veya okul hesabı durumunu onaylayamaz mısınız?](#cant-confirm-non-profit-or-school-account-status)

- [Hizmetler etki alanınızla çalışmıyor mu?](#services-not-working-with-your-domain)
    
- [Web sitenize erişmiyor musunuz?](#accessing-your-website-isnt-working)

## <a name="cant-verify-your-domain"></a>Etki alanınızı doğrulayamıyor musunuz?

Etki alanı doğrulamasının gerektiği gibi çalışmamasının birkaç yaygın nedeni vardır:
  
1. **Doğrulama kaydı değeri doğru olmayabilir.** DNS barındırıcınızda, değeri TXT doğrulama kaydına aynı şekilde kopyalayıp yapıştırdığınızı tekrar gözden geçirin. Yaygın sorunlardan biri de kaydın "MS=" kısmının dahil edilmemesidir. Bu kısmı da belirtmeniz gerekir! 
    
2. **Kayıt kaydedilmemiş olabilir.** Bazı DNS barındırıcılarında, İnternet'te güncelleştirilebilmesi için bölge dosyasını kaydetmek (DNS kaydının bulunduğu konuma) üzere ek bir adım uygulamanız gerekir. Microsoft 365'in kaydı görebilmesi ve doğrulayabilmesi için değişikliklerinizi kaydettiğinizden emin olun. 
    
3. **Kayıt İnternet'te güncelleştirilmemiş olabilir.** Yeni kaydı görmemiz genellikle yalnızca birkaç dakika sürer, ancak bazı durumlarda bu işlem birkaç saate kadar sürebilir. 
    
## <a name="outlook-isnt-working"></a>Outlook çalışmıyor mu?

Etki alanınız için MX kaydınızı ve diğer DNS kayıtlarınızı doğru ayarladığınız halde posta çalışmıyorsa [Outlook sorunlarınızı düzeltmenize](/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues) yardımcı olmamız için bize ulaşın.
  
## <a name="everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch"></a>Herkesin e-postası Microsoft 365'e geçti ve yalnızca E-postanızın geçişini mi istiyorsunuz?
<a name="BKMK_EmailSwitched"> </a>

Etki alanınızı Microsoft 365'e eklediğinizde, genellikle etki alanınızın MX kaydı (siz veya Microsoft 365 tarafından) Microsoft 365'e işaret edecek şekilde güncelleştirilir ve bu etki alanına gönderilen TÜM e-postalar Microsoft 365'e gelmeye başlar. MX kaydını değiştirmeden önce, etki alanınızda e-postası olan herkes için Microsoft 365'te posta kutuları oluşturduğunuzdan emin olun.
  
Etki alanınızdaki herkes için e-postayı Microsoft 365'e taşımak istemiyorsanız ne olur? [Bunun yerine yalnızca birkaç e-posta adresiyle Microsoft 365'e pilot uygulama adımlarını](../setup/domains-faq.yml) uygulayabilirsiniz.
  
## <a name="cant-confirm-non-profit-or-school-account-status"></a>Kar amacı gütmeyen kuruluş veya okul hesabı durumunu onaylayamaz mısınız?
<a name="BKMK_validateAcct"> </a>

Yalnızca kuruluşunuzun etki alanını doğrulamanız ve herhangi bir hizmet ayarlamamanız gereken birkaç senaryo vardır. Örneğin, Microsoft 365'e kuruluşunuzun okul aboneliğine uygun olduğunu kanıtlamak için.
  
[Sahipliği, kar amacı gütmeyen kuruluş veya eğitim durumunu kanıtlamak veya tüm gerekli adımları tamamladığınızdan emin olmak için Yammer'ı etkinleştirmek için Microsoft 365 etki alanınızı](../setup/domains-faq.yml) doğrulama başlığı altında yer alan kılavuza göz atın. Her durum için biraz farklı. 
  
## <a name="services-not-working-with-your-domain"></a>Etki alanınızdaki hizmetler çalışmıyor mu?

Etki alanınızın DNS kurulumuyla ilgili sorunları düzeltmenize yardımcı olabiliriz. Microsoft 365'teki etki alanları sorun gidericisi, düzeltilmesi gereken tüm kayıtları ve kayıtların tam olarak ne olarak ayarlanması gerektiğini gösterir. 

> [!TIP]
> DNS'niz doğru ayarlandı, ancak posta masaüstünüzdeki Outlook'ta çalışmıyor mu? İşletmeniz için doğru şekilde ayarladığınızdan emin olmak için [Microsoft 365 ile sahip olabileceğiniz farklı posta akışı senaryolarına](/exchange/mail-flow-best-practices/mail-flow-best-practices) göz atın. Ya da buradan e-postayla ilgili daha fazla sorun giderme yardımı alabilirsiniz: [Outlook sorunlarını düzeltme](/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues). 
  
## <a name="accessing-your-website-isnt-working"></a>Web sitenize erişemiyor musunuz?

Tüm DNS sorunlarını çözdüyseniz ve hala sorun yaşıyorsanız, aşağıdakilerden birini deneyin.
  
- kişiler *contoso.com* web sitenize ulaşamıyor: [Web sitesi sorunlarını izleme](../setup/add-domain.md)
    
- A kaydınızı veya CNAME kaydınızı web sitenize işaret eden şekilde güncelleştiremezsiniz: [Microsoft 365'te özel DNS kayıtlarını güncelleştirme](../setup/add-domain.md)

## <a name="related-content"></a>İlgili içerik

[Sorun giderme: Doğrulanmış etki alanı değişikliğiyle ilgili verileri denetleme](/azure/active-directory/reports-monitoring/troubleshoot-audit-data-verified-domain) (makale)\
[Etki alanları hakkında SSS](../setup/domains-faq.yml) (makale)

