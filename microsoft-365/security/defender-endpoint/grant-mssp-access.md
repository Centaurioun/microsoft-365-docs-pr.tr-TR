---
title: Yönetilen güvenlik hizmeti sağlayıcısına (MSSP) erişim izni verme
description: MSSP tümleştirmesini Uç Nokta için Microsoft Defender yapılandırmak için gerekli adımları uygulayın
keywords: yönetilen güvenlik hizmeti sağlayıcısı, mssp, yapılandırma, tümleştirme
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier3
ms.topic: article
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 280bac711494cd06d5fe54784e0f7d27b32e5945
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2022
ms.locfileid: "68224546"
---
# <a name="grant-managed-security-service-provider-mssp-access-preview"></a>Yönetilen güvenlik hizmeti sağlayıcısına (MSSP) erişim izni verme (önizleme)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç nokta için Defender'i deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-mssp-support-abovefoldlink)

> [!IMPORTANT]
> Bazı bilgiler, ticari olarak piyasaya sürülmeden önce önemli ölçüde değiştirilebilen önceden yayımlanmış ürünle ilgilidir. Microsoft, burada sağlanan bilgilerle ilgili olarak açık veya zımni hiçbir garanti vermez.

Çok kiracılı bir temsilci erişim çözümü uygulamak için aşağıdaki adımları izleyin:

1. Uç Nokta için Defender'da [rol tabanlı erişim denetimini](rbac.md) etkinleştirin ve Active Directory (AD) gruplarına bağlanın.

2. Erişim isteği ve sağlama için [İdare Erişim Paketlerini](/azure/active-directory/governance/identity-governance-overview) yapılandırın.

3. [Microsoft Myaccess'te](/azure/active-directory/governance/entitlement-management-request-approve) erişim isteklerini ve denetimlerini yönetin.

## <a name="enable-role-based-access-controls-in-microsoft-defender-for-endpoint"></a>Uç Nokta için Microsoft Defender'de rol tabanlı erişim denetimlerini etkinleştirme

1. **Müşteri AAD'sinde MSSP kaynakları için erişim grupları oluşturma: Gruplar**

    Bu gruplar, Uç Nokta için Defender'da oluşturduğunuz Rollere bağlanır. Bunu yapmak için müşteri AD kiracısında üç grup oluşturun. Örnek yaklaşımımızda aşağıdaki grupları oluştururuz:

    - Katman 1 Analisti
    - Katman 2 Analisti
    - MSSP Analist Onaylayanları

2. Uç Nokta için Customer Defender'da uygun erişim düzeyleri için Uç Nokta için Defender rolleri oluşturun.

    Müşteri Microsoft 365 Defender portalında RBAC'yi etkinleştirmek için Genel Yönetici veya Güvenlik Yöneticisi haklarına sahip bir kullanıcı hesabından **Ayarlar > İzinler > Roller'e** ve "Rolleri aç"a erişin.

    :::image type="content" source="images/mssp-access.png" alt-text="MSSP erişimi" lightbox="images/mssp-access.png":::

    Ardından MSSP SOC Katmanı gereksinimlerini karşılamak için RBAC rolleri oluşturun. Bu rolleri "Atanan kullanıcı grupları" aracılığıyla oluşturulan kullanıcı gruplarına bağlayın.

    İki olası rol:

    - **Katman 1 Analistleri**

      Canlı yanıt dışındaki tüm eylemleri gerçekleştirin ve güvenlik ayarlarını yönetin.

    - **Katman 2 Analistleri**

      [Canlı yanıta](live-response.md) ek olarak Katman 1 özellikleri

    Daha fazla bilgi için bkz. [Rol tabanlı erişim denetimini kullanma](rbac.md).

## <a name="configure-governance-access-packages"></a>İdare Erişim Paketlerini Yapılandırma

1. **Müşteri AAD'sinde BAĞLı Kuruluş olarak MSSP Ekleme: Kimlik İdaresi**

    MSSP'nin bağlı bir kuruluş olarak eklenmesi, MSSP'nin istekte bulunmasını ve erişim sağlamasını sağlar.

    Bunu yapmak için, müşteri AD kiracısında Kimlik İdaresi: Bağlı kuruluş'a erişin. Yeni bir kuruluş ekleyin ve Kiracı Kimliği veya Etki Alanı aracılığıyla MSSP Analisti kiracınızı arayın. MSSP Analistleriniz için ayrı bir AD kiracısı oluşturmanızı öneririz.

2. **Müşteri AAD'sinde kaynak kataloğu oluşturma: Kimlik İdaresi**

    Kaynak katalogları, müşteri AD kiracısında oluşturulan mantıksal bir erişim paketleri koleksiyonutur.

    Bunu yapmak için, müşteri AD kiracısında Kimlik İdaresi: Kataloglar'a erişin ve **Yeni Katalog** ekleyin. Örneğimizde **buna MSSP Erişimleri** adını diyoruz.

    :::image type="content" source="images/goverance-catalog.png" alt-text="Yeni katalog sayfası" lightbox="images/goverance-catalog.png":::

    Daha fazla bilgi için bkz. [Kaynak kataloğu oluşturma](/azure/active-directory/governance/entitlement-management-catalog-create).

3. **MSSP kaynakları için erişim paketleri oluşturma Customer AAD: Identity Governance**

    Erişim paketleri, istekte bulunana onay üzerine verilecek hakların ve erişimlerin toplanmasıdır.

    Bunu yapmak için müşteri AD kiracısında Kimlik İdaresi: Erişim Paketleri'ne erişin ve **Yeni Erişim Paketi** ekleyin. MSSP onaylayanları ve her analist katmanı için bir erişim paketi oluşturun. Örneğin, aşağıdaki Katman 1 Analist yapılandırması şu şekilde bir erişim paketi oluşturur:

    - YENI istekleri yetkilendirmek için **AD grubu MSSP Analist Onaylayanlarının** bir üyesini gerektirir
    - SOC analistlerinin erişim uzantısı isteyebileceği yıllık erişim gözden geçirmeleri vardır
    - Yalnızca MSSP SOC Kiracısı'ndaki kullanıcılar tarafından istenebilir
    - Erişimin otomatik süresi 365 gün sonra doluyor

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/new-access-package.png" alt-text="Yeni erişim paketi sayfası" lightbox="images/new-access-package.png":::

    Daha fazla bilgi için bkz. [Yeni erişim paketi oluşturma](/azure/active-directory/governance/entitlement-management-access-package-create).

4. **Müşteri AAD'den MSSP kaynaklarına erişim isteği bağlantısı sağlama: Kimlik İdaresi**

    Erişimim portalı bağlantısı, MSSP SOC analistleri tarafından oluşturulan erişim paketleri aracılığıyla erişim istemek için kullanılır. Bağlantı dayanıklıdır, yani aynı bağlantı zaman içinde yeni analistler için kullanılabilir. Analist isteği **, MSSP Analist Onaylayanları** tarafından onay için bir kuyruğa girer.

    > [!div class="mx-imgBorder"]
    > :::image type="content" source="images/access-properties.png" alt-text="Özellikler sayfası" lightbox="images/access-properties.png":::

    Bağlantı, her erişim paketinin genel bakış sayfasında bulunur.

## <a name="manage-access"></a>Erişimi yönetin

1. Müşteri ve/veya MSSP myaccess'te erişim isteklerini gözden geçirin ve yetkilendirin.

    Erişim istekleri, MSSP Analist Onaylayanları grubunun üyeleri tarafından Erişimim müşterisinde yönetilir.

    Bunu yapmak için aşağıdakini kullanarak müşterinin myaccess'ine erişin: `https://myaccess.microsoft.com/@<Customer Domain>`.

    Örnek: `https://myaccess.microsoft.com/@M365x440XXX.onmicrosoft.com#/`

2. Kullanıcı arabiriminin **Onaylar** bölümünde istekleri onaylayın veya reddedin.

    Bu noktada analist erişimi sağlanmıştır ve her analistin müşterinin Microsoft 365 Defender portalına erişebilmesi gerekir:`https://security.microsoft.com/?tid=<CustomerTenantId>`

## <a name="related-topics"></a>İlgili konular

- [MSSP müşteri portalına erişin](access-mssp-portal.md)
- [Uyarı bildirimlerini yapılandırın](configure-mssp-notifications.md)
- [Müşteri kiracı uyarılarını getir](fetch-alerts-mssp.md)
