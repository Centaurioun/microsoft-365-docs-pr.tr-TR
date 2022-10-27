---
title: Microsoft Benimseme Puanı - Gizlilik
f1.keywords:
- NOCSH
ms.author: camillepack
author: camillepack
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
monikerRange: o365-worldwide
ms.collection:
- Tier2
- scotvorg
- M365-subscription-management
- Adm_O365
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
description: Gizlilik, Benimseme Puanı ile nasıl korunur?
ms.openlocfilehash: 74ca30762ecaccc03ff76c7c928f3f96f566a05c
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2022
ms.locfileid: "68726871"
---
# <a name="privacy-controls-for-adoption-score"></a>Benimseme Puanı için gizlilik denetimleri

Benimseme Puanı, Microsoft 365 kullanımı ve onu destekleyen teknoloji deneyimleri aracılığıyla kuruluşunuzun dijital dönüşüm yolculuğuna ilişkin içgörüler sağlar.  Kuruluşunuzun puanı, kişi ve teknoloji deneyimi ölçümlerini yansıtır ve sizinkine benzer kuruluşların karşılaştırmalarıyla karşılaştırılabilir. Daha fazla ayrıntı için [Benimseme Puanına genel bakış](adoption-score.md) bölümünü görüntüleyin.

Gizliliğiniz Microsoft için önemlidir. Gizliliğinizi nasıl koruduğumuz hakkında bilgi edinmek için [Microsoft'un gizlilik bildirimine](https://privacy.microsoft.com/privacystatement) bakın. Benimseme Puanı, kuruluşunuzun BT yöneticisi olarak, görüntülediğiniz Benimseme Puanı bilgilerinin eyleme dönüştürülebilir olduğundan emin olmanıza yardımcı olmak için gizlilik ayarlarına erişmenizi sağlarken kuruluşunuzun Microsoft'a verdiği güveni tehlikeye atamaz.

Kişiler deneyimleri alanında ölçümler yalnızca kuruluş düzeyinde kullanılabilir. Bu alan, içerik işbirliği, hareketlilik, toplantılar, ekip çalışması ve iletişim kategorilerine bakarak kişilerin Microsoft 365'i nasıl kullandığına bakar. İç gizlilik ilkesi gereksinimlerinizi karşılamanıza yardımcı olmak için çeşitli denetim düzeyleriyle size olanak sağlarız.
Denetimler size şu bilgileri verir:

- Benimseme Puanı'nda bilgileri kimlerin görebileceğini denetlemek için esnek yönetici rolleri
- Kullanıcı ve grupları kişilerden kaldırma özelliği hesaplamalar yaşar
- Kişi deneyimleri alanından vazgeçme özelliği

## <a name="flexible-admin-roles-to-control-who-can-see-the-information-in-adoption-score"></a>Benimseme Puanı'nda bilgileri kimlerin görebileceğini denetlemek için esnek yönetici rolleri

Benimseme Puanı'nın tamamını görüntülemek için aşağıdaki yönetici rollerinden biri olmanız gerekir:

- Genel yönetici
- Exchange yöneticileri
- SharePoint yöneticisi
- Skype Kurumsal yöneticisi
- Ekipler yöneticisi
- Genel Okuyucu
- Rapor Okuyucusu
- Kullanım Özeti Raporları Okuyucusu
- Kullanıcı Deneyimi Başarı Yöneticisi

Genel yönetici, değişiklik yönetimi ve benimsemeden sorumlu olan herkese Rapor Okuyucusu rolünü, Kullanım Özeti Raporları Okuyucusu rolünü veya Kullanıcı Deneyimi Başarı Yöneticisi rolünü atayabilir, ancak bt yöneticisi olması gerekmez.

Rapor Okuyucusu rolüne sahip kullanıcılar kullanım raporlama verilerini ve rapor panosunu Microsoft 365 yönetim merkezi ve Power BI'daki benimseme bağlam paketini görüntüleyebilir. Kullanım Özeti Raporları Okuyucusu rolüne sahip kullanıcılar, Microsoft 365 Kullanım Analizi ve Benimseme Puanı'nda yalnızca kiracı düzeyi toplamlarını ve grup düzeyi toplamlarını görebilir. Kullanıcı Deneyimi Başarı Yöneticisi rolü, Kullanım Özeti Raporları Okuyucusu rolünün izinlerini içerir ve İleti Merkezi, Ürün Geri Bildirimi ve Hizmet Durumu gibi Benimseme ile ilgili daha fazla bilgiye erişebilir. Farklı roller hakkında daha fazla bilgi edinmek için bkz. [Azure AD yerleşik](/azure/active-directory/roles/permissions-reference) roller.

## <a name="capability-to-choose-specific-users-or-certain-groups"></a>Belirli kullanıcıları veya belirli grupları seçme özelliği

Kuruluşunuzdaki kişilerin içgörüleri deneyimlediğini belirlemek için verileri kullanılacak kullanıcıları ve grupları seçebilirsiniz. Bazı grupların atlanması içgörü hesaplamalarını etkiler. Kuruluşunuzun kişi deneyim raporları dışında bırakılabilmesi için Genel yönetici olmanız gerekir. Değişikliğin uygulanması 24 saat kadar sürebilir.

Belirli grupları atlar:

1. Yönetim merkezinde **Ayarlar** > **Kuruluş Ayarları** > **Benimseme Puanı'na** gidin.
2. **Belirli kullanıcıları grup aracılığıyla dışla'yı** seçin.  
3. Atacak bir veya birden çok Yönetici Center AAD grubu seçin.
4. **Değişiklikleri kaydet'i** seçin.

:::image type="content" source="../../media/adoption-score-exclude-users.png" alt-text="Ekran görüntüsü: İçgörüleri hesaplarken grup aracılığıyla belirli kullanıcıları dışlama seçeneği.":::

## <a name="capability-to-opt-out-of-people-experiences"></a>Kişi deneyimlerini geri çevirme özelliği

Benimseme Puanı'nın kişi deneyimleri alanından da çıkabilirsiniz. Devre dışı bırakmanız durumunda kuruluşunuzdan hiç kimse bu ölçümleri görüntüleyemez ve kuruluşunuz iletişim, toplantılar, ekip çalışması, içerik işbirliği ve mobilite içeren hesaplamalardan kaldırılacaktır. Kuruluşunuzun kişi deneyim raporları dışında bırakılabilmesi için Genel yönetici olmanız gerekir. Değişikliğin uygulanması 24 saat kadar sürebilir. Geçmiş verileri saklamak için değişikliğinizi utc saatinde günün sonundan önce geri döndürebilirsiniz.

Geri çevirmek için:

1. Yönetim merkezinde **Ayarlar**  >  **Kuruluş Ayarları** > **Benimseme Puanı'na** gidin.
2. **Kullanıcılar için hesaplama'yı** seçin. 
3. **Kişi deneyimlerinden veri kaldırmak istiyor musunuz?** onay ekranında **Verileri Kaldır'ı** seçin.
4. **Kaydet'i** seçin.

:::image type="content" source="../../media/adoption-score-calculate-insights.png" alt-text="Ekran görüntüsü: Kişi deneyimlerinden vazgeçmek için kuruluş ayarları seçeneği içgörüler":::
