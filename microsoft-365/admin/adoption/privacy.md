---
title: Microsoft Benimseme Puanı - Gizlilik
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
monikerRange: o365-worldwide
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
description: Gizlilik, Benimseme Puanı ile nasıl korunur?
ms.openlocfilehash: d94b3bbf02be6c9a49926b2aadd6d4f35a4aa804
ms.sourcegitcommit: f1b3ecde15e5cbbeadaf51b2cadb6b1d677fc265
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2022
ms.locfileid: "67437940"
---
# <a name="privacy-controls-for-adoption-score"></a>Benimseme Puanı için gizlilik denetimleri

Benimseme Puanı, Microsoft 365 kullanımı ve onu destekleyen teknoloji deneyimleri aracılığıyla kuruluşunuzun dijital dönüşüm yolculuğuna ilişkin içgörüler sağlar.  Kuruluşunuzun puanı, kişi ve teknoloji deneyimi ölçümlerini yansıtır ve sizinkine benzer kuruluşların karşılaştırmalarıyla karşılaştırılabilir. Daha fazla ayrıntı için [Benimseme Puanına genel bakış](adoption-score.md) bölümünü görüntüleyin.

Gizliliğiniz Microsoft için önemlidir. Gizliliğinizi nasıl koruduğumuz hakkında bilgi edinmek için [Microsoft'un gizlilik bildirimine](https://privacy.microsoft.com/privacystatement) bakın. Benimseme Puanı, kuruluşunuzun BT yöneticisi olarak, görüntülediğiniz Benimseme Puanı bilgilerinin eyleme dönüştürülebilir olduğundan emin olmanıza yardımcı olmak için gizlilik ayarlarına erişmenizi sağlarken kuruluşunuzun Microsoft'a verdiği güveni tehlikeye atamaz.

Kişiler deneyimleri alanında ölçümler yalnızca kuruluş düzeyinde kullanılabilir. Bu alan, içerik işbirliği, hareketlilik, toplantılar, ekip çalışması ve iletişim kategorilerine bakarak kişilerin Microsoft 365'i nasıl kullandığına bakar. İç gizlilik ilkesi gereksinimlerinizi karşılamanıza yardımcı olmak için çeşitli denetim düzeyleriyle size olanak sağlarız.
Denetimler size şu bilgileri verir:

- Benimseme Puanı'nda bilgileri kimlerin görebileceğini denetlemek için esnek yönetici rolleri.
- kişi deneyimleri alanından çıkma özelliği.

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

Rapor Okuyucusu veya Kullanım Özeti Raporları Okuyucusu rolünü, değişiklik yönetimi ve benimsemeden sorumlu olan, ancak bt yöneticisi olması gerekmeyen herkese atayın. Bu rol, microsoft 365 yönetim merkezinde benimseme puanı deneyiminin tamamına erişim sağlar.

Kullanım Özeti Raporları Okuyucusu rolünün, 2020'nin sonraki Microsoft 365 yönetim merkezi atanabilene kadar PowerShell cmdlet'leri aracılığıyla atanmalıdır.

PowerShell ile Kullanım Özeti Raporları Okuyucusu rolünü atamak için:

- Aşağıdaki PowerShell'i çalıştırın:

```powershell
Connect-AzureAD
Enable-AzureADDirectoryRole -RoleTemplateId '75934031-6c7e-415a-99d7-48dbd49e875e'
$role=Get-AzureADDirectoryRole -Filter "roleTemplateId eq '75934031-6c7e-415a-99d7-48dbd49e875e'"
Get-AzureADDirectoryRoleMember -ObjectId $role.ObjectId
$u=Get-AzureADUser -ObjectId <user upn>
Add-AzureADDirectoryRoleMember -ObjectId $role.ObjectId -RefObjectId $u.ObjectId
```

## <a name="capability-to-opt-out-of-people-experiences"></a>Kişi deneyimlerini geri çevirme özelliği

Benimseme Puanı'nın kişi deneyimleri alanından da çıkabilirsiniz. Devre dışı bırakmanız durumunda kuruluşunuzdan hiç kimse bu ölçümleri görüntüleyemez ve kuruluşunuz iletişim, toplantılar, ekip çalışması, içerik işbirliği ve mobilite içeren hesaplamalardan kaldırılacaktır. Kuruluşunuzun kişi deneyim raporları dışında bırakılabilmesi için Genel yönetici olmanız gerekir.

Geri çevirmek için:

1. Yönetim merkezinde **Ayarlar**  >  **Kuruluş Ayarları** > **Benimseme Puanı'na** gidin.
2. **Microsoft 365 kullanım verilerinin kişiler tarafından içgörüler için kullanılmasına izin ver** yazan kutunun işaretini kaldırın. Intune yapılandırma yöneticisinde Endpoint Analytics için veri paylaşımı ayarlarının nasıl değiştirileceği hakkında bilgi edinmek için **Daha fazla bilgi'yi** seçin.
3. **Kaydet'i** seçin.

:::image type="content" source="../../media/orgsettingspageoptout.png" alt-text="Kişi deneyimlerini geri çevirebileceğiniz kuruluş ayarları sayfası.":::
