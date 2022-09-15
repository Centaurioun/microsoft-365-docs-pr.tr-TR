---
title: Adım 1. Kurumsal kiracılar için Microsoft 365 kiracınız
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- highpri
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
- tenant-management
- m365solution-scenario
ms.custom:
- Ent_Solutions
description: Çoklu coğrafi ve hareketli konum seçenekleriyle tek veya birden çok Microsoft 365 kiracısını dağıtın ve yönetin.
ms.openlocfilehash: a1fdf6cf86fd7e889712e020f5aaeb33284c96ae
ms.sourcegitcommit: 0af064e8b6778060f1bd365378d69b16fc9949b5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/15/2022
ms.locfileid: "67730583"
---
# <a name="step-1-your-microsoft-365-for-enterprise-tenants"></a>Adım 1. Kurumsal kiracılar için Microsoft 365 kiracınız

İlk kiracı kararlarınızdan biri kaç tane olmasıdır. Her Microsoft 365 kiracısı ayrı, benzersiz ve diğer tüm Microsoft 365 kiracılarından ayrıdır. Buna karşılık gelen Azure AD kiracısı da ayrı, benzersiz ve diğer tüm Microsoft 365 kiracılarından ayrıdır.

## <a name="single-tenant"></a>Tek kiracı
Tek bir kiracıya sahip olmak, kuruluşunuzun Microsoft 365'i kullanmasının birçok yönünü basitleştirir. Tek bir kiracı, tek bir hesap, grup ve ilke kümesine sahip tek bir Azure AD kiracı anlamına gelir. Kuruluşunuz genelindeki kaynakların izinleri ve paylaşımı bu merkezi kimlik sağlayıcısı aracılığıyla gerçekleştirilebilir.

Tek bir kiracı, kullanıcılarınız için en zengin ve basitleştirilmiş işbirliği ve üretkenlik deneyimini sağlar.

Microsoft 365 kiracısının varsayılan konumunu ve Azure AD kiracısını gösteren bir örnek aşağıda verilmiştir.

![Azure AD kiracısı olan tek bir Microsoft 365 kiracısı.](../media/tenant-management-overview/tenant-management-example-tenant.png)

## <a name="multiple-tenants"></a>Birden çok kiracı

Kuruluşunuzun birden çok kiracıya sahip olmasının birçok nedeni vardır:

- Yönetim yalıtımı
- Merkezi olmayan BT
- Geçmişe dönük kararlar
- Birleştirmeler, devralmalar veya dalgıçlar
- Holding kuruluşları için markalamanın net bir şekilde ayrılması
- Üretim öncesi, test veya korumalı alan kiracıları

Burada, aynı varsayılan veri merkezi coğrafi alanında iki kiracısı (A Kiracısı ve B Kiracısı) olan bir kuruluş örneği verilmiştir. Her kiracı ayrı bir Azure AD kiracısı olarak.

![Kendi Azure AD kiracıları olan birden çok Microsoft 365 kiracısı.](../media/tenant-management-overview/tenant-management-example-multi-tenant.png)

Birden çok kiracınız olduğunda, bunları yönetirken ve kullanıcılarınıza hizmet sağlarken kısıtlamalar ve ek dikkat edilmesi gerekenler vardır.

### <a name="inter-tenant-collaboration"></a>Kiracılar arası işbirliği

Kullanıcılarınızın farklı Microsoft 365 kiracılarında güvenli bir şekilde daha etkili bir şekilde işbirliği yapmalarını istiyorsanız, kiracılar arası işbirliği seçenekleri arasında dosyalar ve konuşmalar için merkezi bir konum kullanma, takvimleri paylaşma, anlık ileti kullanma, iletişim için sesli/görüntülü aramalar kullanma ve kaynaklara ve uygulamalara erişimin güvenliğini sağlama yer alır.

Daha fazla bilgi için bkz. [Microsoft 365 kiracılar arası işbirliği](../enterprise/microsoft-365-inter-tenant-collaboration.md).

### <a name="cross-tenant-mailbox-migration-preview"></a>Kiracılar arası posta kutusu geçişi (önizleme)

Kiracılar arası posta kutusu geçişi öncesinde (önizlemede), kiracılar arasında Exchange Online posta kutularını taşırken, bir kullanıcı posta kutusunu geçerli kiracısından (kaynak kiracı) şirket içi ortamına tamamen çıkarmanız ve sonra bunları yeni bir kiracıya (hedef kiracı) eklemeniz gerekir. Yeni kiracılar arası posta kutusu geçiş özelliğiyle, hem kaynak hem de hedef kiracılardaki kiracı yöneticileri, şirket içi sistemlerinde en az altyapı bağımlılığı olan kiracılar arasında posta kutularını taşıyabilir. Bu, posta kutularının kullanıma dışı ve ekleme gereksinimini ortadan kaldırır.

Aşağıda, kiracılar arası posta kutusu geçişi öncesinde iki örnek kiracı ve bunların posta kutuları verilmiştir.

![Birden çok Microsoft 365 kiracısı ve posta kutuları.](../media/tenant-management-overview/tenant-management-cross-tenant-mailbox-before.png)

Bu çizimde, iki ayrı kiracının kendi etki alanları ve Exchange posta kutuları kümesi vardır.

Kiracılar arası posta kutusu geçişi sonrasında hedef kiracı (Kiracı A) aşağıdadır.

![Kiracılar arası posta kutusu geçişi sonrasında hedef kiracı.](../media/tenant-management-overview/tenant-management-cross-tenant-mailbox-after.png)

Bu çizimde, tek bir kiracının hem etki alanları hem de exchange posta kutusu kümeleri vardır.

Daha fazla bilgi için bkz. [Kiracılar arası posta kutusu geçişi](../enterprise/cross-tenant-mailbox-migration.md).

### <a name="tenant-to-tenant-migrations"></a>Kiracıdan kiracıya geçişler

Var olan bir Microsoft 365 kiracısını yeni bir kiracıya geçirmenize yol açabilecek birleştirmeler, devralmalar, dalgıçlar ve diğer senaryolar için çeşitli mimari yaklaşımlar vardır. 

Ayrıntılı yönergeler için bkz. [Microsoft 365 kiracıdan kiracıya geçişler](../enterprise/microsoft-365-tenant-to-tenant-migrations.md).

## <a name="multi-geo-for-a-tenant"></a>Kiracı için Multi-Geo

Microsoft 365 Multi-Geo ile veri yerleşimi gereksinimlerini karşılamak için seçtiğiniz diğer veri merkezi coğrafi konumlarında bekleyen verileri sağlayabilir ve depolayabilir ve aynı zamanda çalışanlarınıza modern üretkenlik deneyimlerinin küresel sunumunu sağlayabilirsiniz.

Multi-Geo ortamında Microsoft 365 kiracınız, Microsoft 365 aboneliğinizin ilk oluşturulduğu varsayılan veya merkezi bir konumdan ve bir veya daha fazla uydu konumundan oluşur. Çok coğrafi kiracılı bir kiracıda, coğrafi konumlar, gruplar ve kullanıcı bilgileri hakkındaki bilgiler genel Azure AD kiracısında ana şablon olarak yer alır. Kiracı bilgileriniz merkezi olarak yönetildiğinden ve her coğrafi konuma eşitlendiğinden, şirketinizden herhangi bir kişiyi içeren işbirliği deneyimleri konumlar arasında paylaşılır.

Burada, Avrupa'da varsayılan konumuna ve Kuzey Amerika uydu konumuna sahip bir kuruluş örneği verilmiştir. Her iki konum da tek Bir Microsoft 365 kiracısı için aynı genel Azure AD kiracısını paylaşır.

![Çok coğrafi microsoft 365 kiracısı örneği.](../media/tenant-management-overview/tenant-management-example-multi-geo.png)

Daha fazla bilgi için bkz. [Microsoft 365 Multi-Geo](../enterprise/microsoft-365-multi-geo.md).

## <a name="moving-core-data-to-a-new-datacenter-geo"></a>Çekirdek verileri yeni bir veri merkezi coğrafi konumuna taşıma

Microsoft, Microsoft 365 hizmetleri için yeni veri merkezi coğrafi bölgelerini açmaya devam ediyor. Bu yeni veri merkezi coğrafi alanları, devam eden müşteri talebimizi ve kullanım büyümemizi desteklemek için kapasite ve işlem kaynakları ekler. Ayrıca yeni veri merkezi coğrafi bölgeleri, temel müşteri verileri için coğrafi veri yerleşimi sunar.

Yeni bir veri merkezi coğrafi alanının açılması sizi ve mevcut bir veri merkezi coğrafi alanında depolanan temel verilerinizi etkilemez ancak Microsoft, bekleyen kuruluşunuzun temel müşteri verilerinin yeni bir veri merkezi coğrafi alanına erken geçişini istemenizi sağlar.

Burada, bir Microsoft 365 kiracısının Avrupa Birliği (AB) veri merkezi coğrafi bölgesinden Birleşik Krallık'ta (Birleşik Krallık) bulunan coğrafi bölgeye taşındığı bir örnek verilmiştir.

![Microsoft 365 kiracısının veri merkezi coğrafi bölgeleri arasında taşınması örneği.](../media/tenant-management-overview/tenant-management-example-tenant-move.png)

Daha fazla bilgi için bkz [. Temel verileri yeni Microsoft 365 veri merkezi coğrafi bölgelerine taşıma](../enterprise/moving-data-to-new-datacenter-geos.md).

## <a name="products-and-licenses-for-a-tenant"></a>Kiracı için ürünler ve lisanslar

microsoft 365 kiracınız, Microsoft 365 E3 gibi ilk ürününüzü satın aldığınızda oluşturulur. Ürünle birlikte aylık veya yıllık ücret tahsil edilen lisanslar da vardır. Ardından bir yönetici, ürünlerinizden birinden kullanıcı hesabına doğrudan veya grup üyeliği aracılığıyla kullanılabilir bir lisans atar. Kuruluşunuzun iş gereksinimlerine bağlı olarak, her biri kendi lisans havuzuna sahip bir ürün kümeniz olabilir. 

Ürün kümesini ve her biri için lisans sayısını belirlemek için bazı planlamalar yapılması gerekir:

- Gelişmiş özelliklere ihtiyaç duyan kullanıcı hesapları için yeterli lisansa sahip olduğunuzdan emin olun.
- Kuruluşunuzdaki personel değişikliklerine bağlı olarak lisanslarınızın bitmesini veya çok fazla atanmamış lisansa sahip olmanıza engel olur.


## <a name="results-of-step-1"></a>1. Adımın Sonuçları

Kurumsal kiracılar için Microsoft 365 kiracılarınız için şunları belirlediniz:

- Kaç kiracınız olduğunu veya ihtiyacınız olduğunu.
- Her kiracı için, satın alınması gereken ürünler ve lisanslar.
- Veri yerleşimi gereksinimlerine uymak için kiracının Multi-Geo olması gerekip gerekmediği.
- Kiracılar arası işbirliğini ayarlamanız gerekip gerekmediği.
- Bir kiracıyı diğerine geçirmeniz gerekip gerekmediği.
- Çekirdek verileri bir veri merkezi coğrafi alanından yenisine taşımanız gerekip gerekmediği.

Burada yeni bir kiracı örneği verilmiştir.

![Yeni kiracı örneği.](../media/tenant-management-overview/tenant-management-tenant-build-step1.png)

Bu çizimde kiracının şunları vardır:

- Microsoft 365 veri merkezi coğrafi konumuna karşılık gelen varsayılan konum.
- Bir dizi ürün ve lisans.
- Bazıları ürünlere özgü bulut üretkenlik uygulamaları kümesi.
- Genel yönetici hesaplarını ve ilk DNS etki alanı adını içeren bir Azure AD kiracısı.

Bu çözümün ek adımlarını ilerlerken bu rakamı oluşturacağız.

## <a name="ongoing-maintenance-for-tenants"></a>Kiracılar için sürekli bakım

Sürekli olarak şunları yapmanız gerekebilir:

- Yeni bir kiracı ekleyin.
- Kiracıya ilk lisans sayısıyla yeni ürünler ekleyin.
- Değişen personel gereksinimlerini ayarlamak için kiracıdaki bir ürünün lisans kümesini değiştirin.
- Temel verilerinizi bir kiracıdan yeni bir veri merkezi coğrafi konumuna taşıyın.
- Veri yerleşimi gereksinimleri için Multi-Geo ekleyin.
- Kiracılar arası işbirliğini ayarlama.

## <a name="next-step"></a>Sonraki adım

[![2. Adım. Erişim için kiracınızı ağ için iyileştirin.](../media/tenant-management-overview/tenant-management-step-grid-networking.png)](tenant-management-networking.md)

Çalışanlarınızdan Microsoft 365 bulut hizmetlerine en uygun ağı sağlamak için [ağ](tenant-management-networking.md) iletişimi ile devam edin.
