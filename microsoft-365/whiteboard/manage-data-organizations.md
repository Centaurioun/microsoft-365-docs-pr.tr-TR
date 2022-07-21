---
title: Microsoft Whiteboard için verileri yönetme
ms.author: v-jdeweese
author: johnddeweese
manager: alexfaulkner
ms.reviewer: ''
audience: admin
ms.topic: article
ms.custom: ''
ms.prod: microsoft-365-enterprise
search.appverid: MET150
ms.collection: ''
ms.localizationpriority: medium
description: Azure ve OneDrive İş'de Microsoft Whiteboard için veri saklama hakkında bilgi edinin.
ms.openlocfilehash: 88ebe6de6983823e6f782f006ac2aa58cfe9af93
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66943056"
---
# <a name="manage-data-for-microsoft-whiteboard"></a>Microsoft Whiteboard için verileri yönetme

Whiteboard içeriği hem Azure'da hem de OneDrive İş depolanır. Yeni beyaz tahtalar OneDrive İş'da depolanır; tek istisna Surface Hub'dan başlatılan beyaz tahtaların Azure'da depolanmasıdır (gelecekte OneDrive İş taşınacaktır). Daha fazla bilgi için bkz. [Whiteboard'da paylaşımı yönetme](manage-sharing-organizations.md).

## <a name="azure-storage-overview"></a>Azure depolamaya genel bakış

Whiteboard şu anda içeriği Azure'da güvenli bir şekilde depolar. Veriler ülkeye ve Whiteboard'un bu konumlarda yeni içerik depolamaya geçişine bağlı olarak farklı konumlarda depolanabilir. Yeni verilerin nerede oluşturulduğunu denetlemek için bkz. [Microsoft 365 müşteri verilerinizin depolandığı yer](/microsoft-365/enterprise/o365-data-locations). 

Azure'daki içerik Veri Kaybı Önleme (DLP), eBulma, bekletme ilkeleri ve benzer özellikleri desteklemez. İçerik [Whiteboard PowerShell cmdlet'leri](/powershell/module/whiteboard/) kullanılarak yönetilebilir ve zaman içinde bu içeriğin OneDrive İş geçirilmesi veya silinmesi gerekir.

### <a name="if-a-user-account-is-deleted-in-azure"></a>Azure'da bir kullanıcı hesabı silindiyse

Kullanıcının hesabı Azure'da silindiğinde beyaz tahtaların depolanma şeklini değiştiriyoruz. Değişiklik öncesinde, bir kullanıcının hesabı silindiğinde, kullanıcının sahip olduğu beyaz tahtalar da silinir, ancak başkalarıyla paylaşılan beyaz tahtalar silinmez.

>[!NOTE]
> OneDrive İş'de depolanan beyaz tahtalar, OneDrive İş'daki diğer tüm içeriklerde olduğu gibi işlenir. Daha fazla bilgi için bkz. [Silinen kullanıcılar için OneDrive bekletmesini ayarlama](/onedrive/set-retention).

**1 Haziran 2022** itibarıyla Azure'da beyaz tahtaların davranışı değişti. Diğer kullanıcılarla paylaşılan tüm beyaz tahtalar silinir.

Silinen bir kullanıcının beyaz tahtalarını korumak istiyorsanız, hesabı silmeden *önce* sahipliği aktarabilirsiniz. Tek bir beyaz tahtayı veya tümünü başka bir kullanıcıya aktarabilirsiniz. 

- [Tüm beyaz tahtaları aktarmak](/powershell/module/whiteboard/invoke-transferallwhiteboards) için bu yönergeleri izleyin.

- Kullanıcı hesaplarını silme hakkında daha fazla bilgi için bkz. [Kuruluşunuzdan kullanıcı silme](/microsoft-365/admin/add-users/delete-a-user).

Tüm silme işlemlerinin veya betiğin bu değişikliği işlediğini doğrulayın. Beyaz tahtaların silinmesiyle ilgili bir sorun yoksa herhangi bir işlem yapmanız gerekmez. 

## <a name="onedrive-for-business-storage-overview"></a>OneDrive İş depolamaya genel bakış

Beyaz tahtalar beyaz tahtayı başlatan kişinin OneDrive İş klasöründe oluşturulur (SharePoint henüz desteklenmiyor). Bu işlem, tek başına Whiteboard uygulamalarında ve Microsoft Teams toplantılarında, sohbetlerinde ve kanallarında oluşturulan tüm beyaz tahtalar için geçerlidir. Tek istisna, Surface Hub'dan başlatılan beyaz tahtaların Azure'da depolanmasıdır (gelecekte OneDrive İş taşınacaktır).

Sağlanan OneDrive İş olmayan kullanıcılar, bu değişiklik uygulandığında artık yeni beyaz tahtalar oluşturamaz. Ancak, daha önce oluşturulmuş panolarını düzenlemeye devam edebilirler. Ayrıca, OneDrive İş sahip olan diğer kişiler tarafından kendileriyle paylaşılan beyaz tahtalar üzerinde de işbirliği yapabilir.

Ortalama beyaz tahta boyutu 50 KB ile 1 MB arasında olabilir ve OneDrive İş içeriğinizin bulunduğu her yerde bulunabilir. Kiracınızın verilerinin nerede depolandığını denetlemek için bkz. [Microsoft 365 müşteri verilerinizin depolandığı yer](/microsoft-365/enterprise/o365-data-locations). Ardından OneDrive İş konumuna bakın.

### <a name="controls-for-onedrive-for-business-storage"></a>OneDrive İş depolama denetimleri 

Mevcut OneDrive İş denetimlerini kullanarak Whiteboard verilerini yönetebilirsiniz. Daha fazla bilgi için bkz. [Kuruluşlar için OneDrive kılavuzu](/onedrive/plan-onedrive-enterprise).

Genel Veri Koruma Yönetmeliği (GDPR) için veri sahibi isteklerini (DSR) karşılamak için mevcut OneDrive İş araçlarını kullanabilirsiniz. Önceki tüm değişikliklerin dosyadan kaldırıldığından emin olmak istiyorsanız, dosyanın tamamını silmeniz gerekir.

Beyaz Tahta dosyaları, OneDrive İş'daki diğer içerikle aynı şekilde taşınabilir. Ancak, paylaşım bağlantıları ve izinleri taşınamayabilir.

Bugün desteklenen veri denetimleri:

- Bekletme ilkeleri
- Kota
- Yasal tutma
- DLP
- Temel eBulma – .whiteboard dosyaları, oluşturucunun OneDrive İş dosya olarak depolanır. Anahtar sözcük ve dosya türü araması için dizine eklenmiştir, ancak önizleme veya gözden geçirme için kullanılamaz. Dışarı aktarma işleminin ardından, bir yöneticinin içeriği görüntülemek için dosyayı OneDrive İş'a geri yüklemesi gerekir. Gelecekte ek destek planlanıyor.

Gelecek sürümler için planlanan veri denetimleri:

- Duyarlılık etiketleri
- Analytics
- Ek eBulma desteği

## <a name="see-also"></a>Ayrıca bkz.

[Whiteboard'a erişimi yönetme](manage-whiteboard-access-organizations.md)

[Whiteboard için paylaşımı yönetme](manage-sharing-organizations.md)

[Windows'da Whiteboard'ı dağıtma](deploy-on-windows-organizations.md)


