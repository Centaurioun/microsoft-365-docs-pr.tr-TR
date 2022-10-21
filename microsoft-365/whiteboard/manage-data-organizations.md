---
title: Microsoft Whiteboard için verileri yönetme
ms.author: v-jdeweese
author: johnddeweese
manager: alexfaulkner
ms.reviewer: ''
audience: admin
ms.topic: article
ms.custom: ''
ms.service: microsoft-365-enterprise
search.appverid: MET150
ms.collection: ''
ms.localizationpriority: medium
description: Azure ve OneDrive İş'de Microsoft Whiteboard için veri saklama hakkında bilgi edinin.
ms.openlocfilehash: 136506afcec7fe067a270e0577678b5b6a9ec9ff
ms.sourcegitcommit: 87283bb02ca750286f7c069f811b788730ed5832
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2022
ms.locfileid: "68662851"
---
# <a name="manage-data-for-microsoft-whiteboard"></a>Microsoft Whiteboard için verileri yönetme

Whiteboard içeriği OneDrive İş ve Azure'da depolanır. OneDrive İş, tüm yeni beyaz tahtalar için varsayılan depolama alanıdır. Başlangıçta Azure'da oluşturulan beyaz tahtalar ve Surface Hub'da veya Microsoft Teams Odaları cihazda başlatılan beyaz tahtalar Azure'da depolanır.

Verileri yönetmek için önce Whiteboard'un kuruluşunuz için etkinleştirildiğinden emin olmanız gerekir. Daha fazla bilgi için bkz. [Whiteboard erişimini yönetme](manage-whiteboard-access-organizations.md).

## <a name="azure-storage-overview"></a>Azure depolamaya genel bakış

>[!NOTE]
> Aşağıdaki bilgiler Azure'da depolanan beyaz tahtalar için geçerlidir.

Whiteboard şu anda içeriği Azure'da güvenli bir şekilde depolar. Veriler ülkeye ve Whiteboard'un bu konumlarda yeni içerik depolamaya geçişine bağlı olarak farklı konumlarda depolanabilir. Yeni verilerin nerede oluşturulduğunu denetlemek için bkz. [Microsoft 365 müşteri verilerinizin depolandığı yer](/microsoft-365/enterprise/o365-data-locations).

Azure'daki içerik Veri Kaybı Önleme (DLP), eBulma, bekletme ilkeleri ve benzer özellikleri desteklemez. Bu içerik [Whiteboard PowerShell cmdlet'leri](/powershell/module/whiteboard/) kullanılarak yönetilebilir. Sonunda Azure'da depolanan beyaz tahtaların OneDrive İş geçirilmesi veya silinmesi gerekir.

### <a name="if-a-user-account-is-deleted-in-azure"></a>Azure'da bir kullanıcı hesabı silindiyse

Kullanıcının hesabı Azure'da silindiğinde beyaz tahtaların depolanma şeklini değiştiriyoruz. Değişiklik öncesinde, silinen bir kullanıcının hesabına ait olan tüm beyaz tahtalar da silinmişti. Ancak başkalarıyla paylaşılan beyaz tahtalar silinmez.

>[!NOTE]
> OneDrive İş'de depolanan beyaz tahtalar, OneDrive İş'daki diğer tüm içeriklerde olduğu gibi işlenir. Daha fazla bilgi için bkz. [Silinen kullanıcılar için OneDrive bekletmesini ayarlama](/onedrive/set-retention).

**1 Haziran 2022** itibarıyla Azure'da beyaz tahtaların davranışı değişti. Diğer kullanıcılarla paylaşılan tüm beyaz tahtalar silinir.

Silinen bir kullanıcının beyaz tahtalarını korumak istiyorsanız, hesabı silmeden *önce* sahipliği aktarabilirsiniz. Tek bir beyaz tahtayı veya tümünü başka bir kullanıcıya aktarabilirsiniz.

- [Tüm beyaz tahtaları aktarmak](/powershell/module/whiteboard/invoke-transferallwhiteboards) için bu yönergeleri izleyin.

- Kullanıcı hesaplarını silme hakkında daha fazla bilgi için bkz. [Kuruluşunuzdan kullanıcı silme](/microsoft-365/admin/add-users/delete-a-user).

Tüm silme işlemlerinin veya betiğin bu değişikliği işlediğini doğrulayın. Beyaz tahtaların silinmesiyle ilgili bir sorun yoksa herhangi bir işlem yapmanız gerekmez.

## <a name="onedrive-for-business-storage-overview"></a>OneDrive İş depolamaya genel bakış

Beyaz tahtalar beyaz tahtayı başlatan kişinin OneDrive İş klasöründe oluşturulur. SharePoint henüz desteklenmiyor. Bu işlem, tek başına Whiteboard uygulamalarında ve Microsoft Teams toplantılarında, sohbetlerinde ve kanallarında oluşturulan tüm beyaz tahtalar için geçerlidir. Tek istisna, Surface Hub'dan başlatılan beyaz tahtaların Azure'da depolanmasıdır ancak gelecekte OneDrive İş taşınacaktır.

OneDrive İş sağlanmamış kullanıcılar, bu değişiklik uygulandığında artık yeni beyaz tahtalar oluşturamaz. Ancak, daha önce oluşturulmuş panolarını düzenlemeye devam edebilirler. Ayrıca, OneDrive İş sahip olan diğer kişiler tarafından kendileriyle paylaşılan beyaz tahtalar üzerinde de işbirliği yapabilir.

Ortalama beyaz tahta boyutu 50 KB ile 1 MB arasında olabilir ve OneDrive İş içeriğinizin bulunduğu her yerde bulunabilir. Kiracınızın verilerinin nerede depolandığını denetlemek için bkz. [Microsoft 365 müşteri verilerinizin depolandığı yer](/microsoft-365/enterprise/o365-data-locations). Ardından OneDrive İş konumuna bakın.

### <a name="controls-for-onedrive-for-business-storage"></a>OneDrive İş depolama denetimleri

Mevcut OneDrive İş denetimlerini kullanarak Whiteboard verilerini yönetebilirsiniz. Daha fazla bilgi için bkz. [Kuruluşlar için OneDrive kılavuzu](/onedrive/plan-onedrive-enterprise).

Genel Veri Koruma Yönetmeliği (GDPR) için veri sahibi isteklerini (DSR) karşılamak için mevcut OneDrive İş araçlarını kullanabilirsiniz. Önceki tüm değişikliklerin dosyadan kaldırıldığından emin olmak istiyorsanız, dosyanın tamamını silmeniz gerekir.

Beyaz Tahta dosyaları, OneDrive İş'daki diğer içerikle aynı şekilde taşınabilir. Ancak, paylaşım bağlantıları ve izinleri taşınamayabilir.

Bugün desteklenen veri denetimleri:

- Bekletme ilkeleri
- Kota
- Yasal tutma
- Dlp
- Temel eBulma – .whiteboard dosyaları, oluşturucunun OneDrive İş dosya olarak depolanır. Anahtar sözcük ve dosya türü araması için dizine eklenmiştir, ancak önizleme veya gözden geçirme için kullanılamaz. Dışarı aktarma işleminin ardından, bir yöneticinin içeriği görüntülemek için dosyayı OneDrive İş'a geri yüklemesi gerekir. Gelecek için daha fazla destek planlanıyor.

Gelecek sürümler için planlanan veri denetimleri:

- Duyarlılık etiketleri
- Analytics
- Daha fazla eBulma desteği

## <a name="see-also"></a>Ayrıca bkz.

[Whiteboard'a erişimi yönetme](manage-whiteboard-access-organizations.md)

[Whiteboard için paylaşımı yönetme](manage-sharing-organizations.md)

[Windows'da Whiteboard'ı dağıtma](deploy-on-windows-organizations.md)
