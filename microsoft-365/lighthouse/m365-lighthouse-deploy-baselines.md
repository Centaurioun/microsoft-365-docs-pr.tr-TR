---
title: Microsoft 365 Lighthouse temellerini dağıtma
f1.keywords: CSH
ms.author: sharik
author: SKjerland
manager: scotv
ms-reviewer: shcallaw, kywirpel
audience: Admin
ms.topic: article
ms.service: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: Microsoft 365 Lighthouse kullanan Yönetilen Hizmet Sağlayıcıları (MSP) için Microsoft 365 Lighthouse temellerini dağıtmayı öğrenin.
ms.openlocfilehash: 3094cc08cfdd68b316bb457d89bffde000476c13
ms.sourcegitcommit: 2b89bcff547e00be3d38dc8d1e6cbcf8f41eba42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2022
ms.locfileid: "67598857"
---
# <a name="deploy-microsoft-365-lighthouse-baselines"></a>Microsoft 365 Lighthouse temellerini dağıtma

Microsoft 365 Lighthouse, müşteri kiracıları içindeki kullanıcıların, cihazların ve verilerin güvenliğini sağlamak için standart yönetilen kiracı yapılandırmaları dağıtmanıza olanak tanır. Lighthouse ile standart olarak gelen yedi [varsayılan temel yapılandırma](m365-lighthouse-deploy-standard-tenant-configurations-overview.md) vardır. Lighthouse dağıtım planı özelliğini kullanarak tüm kiracılarınızda güvenlik yapılandırmalarını görüntüleyebilir, test edebilir ve dağıtabilirsiniz. Dağıtım planı yalnızca etkin kiracılar tarafından kullanılabilir. Kiracı eklendikten sonra, müşterilerinizin geçerli yapılandırmasını varsayılan temel yapılandırmayla karşılaştırabilir ve uygun eylemleri gerçekleştirebilirsiniz.

## <a name="before-you-begin"></a>Başlamadan önce

Sizin ve müşteri kiracılarınızın [Microsoft 365 Lighthouse](m365-lighthouse-requirements.md) gereksinimleri bölümünde listelenen gereksinimleri karşıladığından emin olun.

## <a name="view-a-deployment-plan"></a>Dağıtım planını görüntüleme

1. Lighthouse'un sol gezinti bölmesinde **Kiracılar'ı** seçin.

2. Kiracı listesinden, görüntülemek istediğiniz kiracıyı seçin.

3. **Dağıtım Planı** sekmesini seçin.

    Dağıtım Planı sekmesi, kiracının dağıtım planına dahil edilen ve her dağıtım adımı için aşağıdaki bilgileri içeren her dağıtım adımının aranabilir ve dışarı aktarılabilir bir listesini sağlar:

    | Sütun            | Açıklama |
    |-----------------|-------------------------------------------------------------------------------------|
    | Dağıtım adımı | Dağıtım adımının açıklaması.                                                     |
    | Durum          | Dağıtım adımının durumu.                                                  |
    | Temel        | Dağıtım adımının türetildiği temel.                             |
    | Kategori        | Dağıtım adımının Cihazları, Kimliği veya Verileri yönetmeyle ilişkili olup olmadığı. |
    | Son güncelleştirme    | Dağıtım adımının son güncelleştirildiği tarih.                             |

4. Dağıtım adımları listesinden gözden geçirmek istediğiniz dağıtım adımını seçin.

    Dağıtım adımı ayrıntıları sayfası aşağıdaki bilgileri sağlar:

    | Sütun            | Açıklama |
    |-------------------|-----------------------------------------------------------------------------------------------|
    | Özet        | Dağıtım adımının amacının özeti.                                         |
    | Temel       | Dağıtım adımının türetildiği temel.                             |
    | Kategori       | Dağıtım adımının Cihazları, Kimliği veya Verileri yönetmeyle ilişkili olup olmadığı. |
    | Gerekli SKU   | Dağıtım adımını tamamlamak için gereken SKU'lar.                                      |
    | Kullanıcı etkisi    | Adımı kiracının kullanıcılarına dağıtmanın etkisi.                             |
    | Kullanıcılarınız için | Kiracının kullanıcılarının yararlı bulabileceği kaynaklara bağlantılar.                             |
    | Sonraki adımlar     | Geçerli sonraki adımlarla ilgili bağlantılar ve yönergeler.                                |

    Dağıtım adımları, tamamlanması gereken bir veya daha fazla işlem içerir. Dağıtım adımı ayrıntıları sayfası, dağıtım adımına dahil edilen her işlemi listeleyen ve aşağıdaki bilgileri sağlayan bir tablo içerir:

    | Sütun            | Açıklama |
    |-------------------|-------------------------------------------------------------|
    | İşlem adı      | seçildiğinde ilgili işlem sekmesini açan işlemin adı.          |
    | Durum            | Dağıtım işlemine dahil edilen ayar yapılandırmalarının durumu algılandı.           |
    | Yönetim portalı | İşlemle ilişkili yapılandırma ayarlarının yönetildiği portal. |

## <a name="deploy-a-deployment-step"></a>Dağıtım adımı dağıtma

1. Sol gezinti sayfasında **Kiracılar'ı** seçin.

2. Kiracı listesinden, görüntülemek istediğiniz kiracıyı seçin.

3. **Dağıtım Planı** sekmesini seçin.

4. Dağıtım adımları listesinden, dağıtmak istediğiniz dağıtım adımını seçin.

5. **Gözden geçir ve dağıt'ı** seçin.

6. **Yapılandırmayı onayla** bölmesinde **Dağıt'ı** seçin.

## <a name="test-a-deployment-step"></a>Dağıtım adımlarını test edin

Koşullu Erişim ilkeleri aracılığıyla dağıtılan dağıtım adımları için, ayarları kiracıya dağıtmadan dağıtım adımındaki yapılandırma ayarlarını mevcut ilkelerdeki ayarlarla karşılaştırabilirsiniz.

1. Sol gezinti sayfasında **Kiracılar'ı** seçin.

2. Kiracı listesinden, görüntülemek istediğiniz kiracıyı seçin.

3. **Dağıtım Planı** sekmesini seçin.

4. Dağıtım adımları listesinden, dağıtmak istediğiniz dağıtım adımını seçin.

5. **Gözden geçir ve dağıt'ı** seçin.

6. **Yapılandırmayı onayla** bölmesinde **Bu ayarları dağıtım olmadan test et'i** seçin.

7. **Test'i** seçin.

**Yapılandırmayı onayla** bölmesi kapanır ve ilke karşılaştırmasını görüntüler. Mevcut kiracıdaki her ilke Algılanan ayarlar tablosunda listelenir.

Algılanan ayarlar tablosu, var olan her ilkeyi listeler ve ayarların sayısını ve parantez içinde aşağıdaki durumlardan birine sahip kullanıcı sayısını özetler:

| Durum         | Açıklama
|-------------|------------------------------------------------------------|
| Eşit ayarlar       | Kiracıda eşdeğer bir değerle dağıtım planındaki toplam yapılandırma ayarları sayısı.      |
| Eksik ayarlar     | Dağıtım planında kiracıda bir değer eksik olan yapılandırma ayarlarının toplam sayısı.      |
| Çakışan ayarlar | Dağıtım planındaki kiracıda çakışan bir değere sahip olan yapılandırma ayarlarının toplam sayısı. |

Algılanan ayarları, ayar ve kullanıcı düzeyinde her ilke için yapılandırma ayarı ayrıntılarını sağlayan modüler bir tabloda görüntüleyebilir ve tabloyu aşağıdaki ayar durumlarına göre sıralayabilirsiniz:

| Durum         | Açıklama
|-------------|------------------------------------------------------------|
| Toplam ayarlar       | Dağıtım işlemine dahil edilen yapılandırma ayarlarının toplam sayısı.                        |
| Eşit ayarlar       | Kiracıda eşdeğer bir değerle dağıtım planındaki toplam yapılandırma ayarları sayısı.      |
| Eksik ayarlar     | Dağıtım planında kiracıda bir değer eksik olan yapılandırma ayarlarının toplam sayısı.      |
| Çakışan ayarlar | Dağıtım planındaki kiracıda çakışan bir değere sahip olan yapılandırma ayarlarının toplam sayısı. |
| Ek ayarlar       | Kiracıda değeri olan ancak dağıtım planında değeri olmayan toplam yapılandırma ayarları sayısı.     |

Bu karşılaştırma yapıldığında Lighthouse Algılanan durum, Dağıtım durumu ve Dağıtım Adımı durumunu otomatik olarak güncelleştirir.

Karşılaştırılacak ilke yoksa **Gözden geçir ve dağıt'ı** seçerek **Yapılandırmayı onayla** bölmesini yeniden açın ve ardından **Dağıt'ı** seçin.

Karşılaştırabileceğiniz mevcut ilkeler varsa şunlardan birini yapabilirsiniz:

- Dağıtım planının yapılandırma ayarlarını düzenleyin ve mevcut ilkelerde yeniden test edin, **Gözden geçir ve dağıt'ı** seçerek **Yapılandırmayı onayla** bölmesini yeniden açın, istenen yapılandırma ayarlarını yapın, onay kutusunu yeniden seçin ve bölmenin alt kısmındaki **Test'i** seçin.

- Farkları şunlardan biriyle mutabık hale getirmek için geçerli yönetim portalındaki mevcut ilkeleri düzenleyin:
  - Eksik ayarları uygulama
  - Çakışan ayarları düzenleme
  - Mevcut ilkeleri silme

Lighthouse aracılığıyla otomatikleştirilebilir her dağıtım işlemi için hem dağıtım durumu hem de algılanan durum vardır.

- Algılanan durum, bu işlemdeki ayarların şu anda ne ölçüde dağıtıldı olduğunu gösterir.
- Dağıtım durumu, kiracıya yapılan son dağıtımın durumudur.

Mevcut ilkelerden bağımsız olarak dağıtım adımlarını dağıtabilirsiniz, ancak çakışan ayarlar olmadan bunlar tamamlanmış olarak kabul edilmez. Çakışan bu ayarların çözümlenememesi kullanıcı deneyimini etkileyebilir. 

Mevcut bir ilkeden kiracıda eşit ayarlar bulunduğunda örneklerde dağıtım adımının dağıtımı, kiracı içindeki mevcut ayarların yinelenmesine neden olur, ancak kullanıcı deneyimini etkilemez. 

Farkındalığınız için ek ayarlar sağlanır ancak işlem yapmanız gerekmez.

İlke çakışması yönetimi hakkında daha fazla bilgi [için Koşullu Erişim belgelerine Azure AD bakın](/azure/active-directory/conditional-access/).

## <a name="update-deployment-step-status"></a>Dağıtım adımı durumunu güncelleştirme

1. Lighthouse'un sol gezinti sayfasında **Kiracılar'ı** seçin.

2. Kiracı listesinden, görüntülemek istediğiniz kiracıyı seçin.

3. **Dağıtım Planı** sekmesini seçin.

4. Dağıtım adımları listesinden güncelleştirmek istediğiniz dağıtım adımını seçin.

5. **Son adres** açılan listesinden bir eylem durumu seçin.

    | Eylem durumu | Açıklama |
    |--|--|
    | Son adres | Birden çok dağıtım adımı işlemi içermeyen tüm dağıtım adımlarının varsayılan durumu. |
    | Planlanan | Dağıtım adımı planlandı ancak henüz tamamlanmadı. |
    | Risk kabul edildi | Kullanıcı, dağıtım adımı uygulanarak aksi takdirde engellenen riski kabul etti. |
    | Risk Üçüncü Taraf Aracılığıyla Çözümlendi | Risk, üçüncü taraf bir uygulamanın veya yazılımın uygulanmasıyla çözülmüştür. |
    | Alternatif yollarla çözümlendi | Risk, bir iç aracın uygulanması gibi alternatif yollarla çözülmüştür. |
    | El ile yapılandırma uygulandı | Dağıtım planında belirtilen yapılandırma el ile uygulandı. |

## <a name="share-deployment-step"></a>Dağıtım paylaşma adımı

1. Sol gezinti sayfasında **Kiracılar'ı** seçin.

2. Kiracı listesinden, görüntülemek istediğiniz kiracıyı seçin.

3. **Dağıtım Planı** sekmesini seçin.

4. Dağıtım adımları listesinden, paylaşmak istediğiniz dağıtım adımını seçin.

5. **Paylaş** açılan listesinden aşağıdaki seçeneklerden birini seçin.

    | Seçeneği  | Açıklama |
    |-----------|-------------------------------------------------------------------------|
    | Kopya  | Dağıtım adımının bağlantısını panonuza kopyalar.                                     |
    | E-posta | Yerel makinenizde yeni e-posta iletinizi açar ve dağıtım adımının bağlantısını ekler. |

    Bağlantı, kuruluşunuzda izinleri olan herkesin kiracının dağıtım planını görüntülemesine olanak tanır.


## <a name="related-content"></a>İlgili içerik

[Standart kiracı yapılandırmalarını dağıtmak için Microsoft 365 Lighthouse temellerini kullanmaya genel bakış](m365-lighthouse-deploy-standard-tenant-configurations-overview.md) (makale)\
[Microsoft 365 Lighthouse Windows 365 (Bulut Bilgisayarları) sayfasına genel bakış](m365-lighthouse-tenants-page-overview.md) (makale)\
[Microsoft 365 Lighthouse SSS](m365-lighthouse-faq.yml) (makale)\
[Microsoft 365 Lighthouse portal güvenliğini yapılandırma](m365-lighthouse-configure-portal-security.md) (makale) 