---
title: Uç Nokta için Microsoft Defender'de cihaz grupları oluşturma ve yönetme
description: Grup üzerinde geçerli olan kuralları onaylayarak cihaz grupları oluşturun ve bunlar üzerinde otomatik düzeltme düzeyleri ayarlayın
keywords: cihaz grupları, gruplar, düzeltme, düzey, kurallar, aad grubu, rol, atama, derecelendirme
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: ff038a72cccf5b79432ef15aa8bd8b396e5fb991
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67688627"
---
# <a name="create-and-manage-device-groups"></a>Cihaz grupları oluşturun ve yönetin

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- Azure Active Directory
- Office 365
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Kurumsal bir senaryoda, güvenlik işlemi ekiplerine genellikle bir cihaz kümesi atanır. Bu cihazlar, etki alanları, bilgisayar adları veya belirlenen etiketler gibi bir dizi öznitelik temelinde birlikte gruplandırılır.

Uç Nokta için Microsoft Defender'da cihaz grupları oluşturabilir ve bunları kullanarak şunları yapabilirsiniz:

- İlgili uyarılara ve verilere erişimi [atanmış RBAC rollerine](rbac.md) sahip belirli Azure AD kullanıcı gruplarıyla sınırlandırma
- Farklı cihaz kümeleri için farklı otomatik düzeltme ayarlarını yapılandırma
- Otomatik araştırmalarda uygulanacak belirli düzeltme düzeylerini atama
- Araştırmada, **Grup** filtresini kullanarak **Cihazlar listesini** belirli cihaz gruplarına göre filtreleyin.

Belirli eylemleri kimin gerçekleştirebileceğini denetlemek veya bir kullanıcı grubuna cihaz grupları atayarak bilgileri görmek için rol tabanlı erişim (RBAC) bağlamında cihaz grupları oluşturabilirsiniz. Daha fazla bilgi için bkz. [Rol tabanlı erişim denetimini kullanarak portal erişimini yönetme](rbac.md).

> [!TIP]
> RBAC uygulamasına kapsamlı bir bakış için şunu okuyun: [SOC'niz RBAC ile düz çalışıyor mu](https://techcommunity.microsoft.com/t5/Windows-Defender-ATP/Is-your-SOC-running-flat-with-limited-RBAC/ba-p/320015)?

Cihaz grubu oluşturma işleminin bir parçası olarak şunları yapacaksınız:

- Bu grup için otomatik düzeltme düzeyini ayarlayın. Düzeltme düzeyleri hakkında daha fazla bilgi için bkz. [Tehditleri araştırmak ve düzeltmek için Otomatik araştırmayı kullanma](automated-investigations.md).
- Cihaz adı, etki alanı, etiketler ve işletim sistemi platformuna göre gruba ait olan cihaz grubunu belirleyen eşleşen kuralı belirtin. Bir cihaz diğer gruplarla da eşleştirilirse, yalnızca en yüksek dereceli cihaz grubuna eklenir.
- Cihaz grubuna erişimi olması gereken Azure AD kullanıcı grubunu seçin.
- Cihaz grubunu oluşturulduktan sonra diğer gruplara göre sıralayın.

> [!NOTE]
> Cihaz grubuna herhangi bir Azure AD grubu atamazsanız tüm kullanıcılar tarafından erişilebilir.

## <a name="create-a-device-group"></a>Cihaz grubu oluşturma

1. Gezinti bölmesinde **Ayarlar** \> **Uç Noktaları İzinleri** \>  \> **Cihaz grupları'nı** seçin.

2. **Cihaz grubu ekle'ye** tıklayın.

3. Grup adını ve otomasyon ayarlarını girin ve hangi cihazların gruba ait olduğunu belirleyen eşleşen kuralı belirtin. Bkz. [Otomatik araştırma nasıl başlar](automated-investigations.md#how-the-automated-investigation-starts)?

    > [!TIP]
    > Cihazları gruplandırmak için etiketleme kullanmak istiyorsanız bkz. [Cihaz etiketlerini oluşturma ve yönetme](machine-tags.md).

4. Bu kuralla eşleştirilecek birkaç cihazın önizlemesini görüntüleme. Kuraldan memnunsanız **Kullanıcı erişimi** sekmesine tıklayın.

5. Oluşturduğunuz cihaz grubuna erişebilen kullanıcı gruplarını atayın.

    > [!NOTE]
    > Yalnızca RBAC rollerine atanmış Azure AD kullanıcı gruplarına erişim vekleyebilirsiniz.

6. **Kapat**'a tıklayın. Yapılandırma değişiklikleri uygulanır.

## <a name="manage-device-groups"></a>Cihaz gruplarını yönetme

Eşleştirme sırasında daha yüksek veya daha düşük öncelik verilmesi için cihaz grubunun derecesini yükseltebilir veya indirgeyebilirsiniz. Bir cihaz birden fazla grupla eşleştirildiğinde, yalnızca en yüksek dereceli gruba eklenir. Grupları düzenleyebilir ve silebilirsiniz.

> [!WARNING]
> Cihaz grubunun silinmesi e-posta bildirim kurallarını etkileyebilir. Bir cihaz grubu bir e-posta bildirim kuralı altında yapılandırılırsa, bu kuraldan kaldırılır. Cihaz grubu bir e-posta bildirimi için yapılandırılan tek grupsa, bu e-posta bildirim kuralı cihaz grubuyla birlikte silinir.

Varsayılan olarak, cihaz gruplarına portal erişimi olan tüm kullanıcılar erişebilir. Cihaz grubuna Azure AD kullanıcı grupları atayarak varsayılan davranışı değiştirebilirsiniz.

Hiçbir grupla eşleşmeyen cihazlar, Gruplanmamış cihazlar (varsayılan) grubuna eklenir. Bu grubun derecesini değiştiremez veya silemezsiniz. Ancak, bu grubun düzeltme düzeyini değiştirebilir ve bu gruba erişebilecek Azure AD kullanıcı gruplarını tanımlayabilirsiniz.

> [!NOTE]
> Cihaz grubu yapılandırmasında değişikliklerin uygulanması birkaç dakika kadar sürebilir.

### <a name="add-device-group-definitions"></a>Cihaz grubu tanımları ekleme

Cihaz grubu tanımları her koşul için birden çok değer de içerebilir. Tek bir cihaz grubunun tanımına birden çok etiket, cihaz adı ve etki alanı ayarlayabilirsiniz.

1. Yeni bir cihaz grubu oluşturun ve **ardından Cihazlar** sekmesini seçin.
2. Koşullardan biri için ilk değeri ekleyin.
3. Aynı özellik türünde daha fazla satır eklemek için seçin `+` .

> [!TIP]
> Özellik başına birden çok değere izin veren aynı koşul türündeki satırlar arasında 'OR' işlecini kullanın.
> Etiket, cihaz adı, etki alanı gibi her özellik türü için en fazla 10 satır (değer) ekleyebilirsiniz.

Cihaz grupları tanımlarına bağlanma hakkında daha fazla bilgi için bkz. [Cihaz grupları - Microsoft 365 güvenliği](https://sip.security.microsoft.com/homepage).

## <a name="related-topics"></a>İlgili konular

- [Rol tabanlı erişim denetimini kullanarak portal erişimini yönetme](rbac.md)
- [Cihaz etiketlerini oluşturun ve yönetin](machine-tags.md)
- [Graph API kullanarak kiracı cihaz gruplarının listesini alma](/graph/api/device-list-memberof)
