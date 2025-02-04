---
title: Faturalama profillerini anlama
author: cmcatee-MSFT
ms.author: cmcatee
manager: scotv
ms.reviewer: amberb, vikdesai
audience: Admin
ms.topic: article
f1.keywords:
- MACBillingBillsPaymentsBillingProfiles
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- Tier1
- scotvorg
- M365-subscription-management
- Adm_O365
ms.custom:
- commerce_billing
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid: MET150
description: Faturalama profillerinin faturaları nasıl desteklediğini öğrenin.
ms.date: 04/02/2021
ms.openlocfilehash: cff74260395f31738753c2217fe15fe51e05d35d
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2022
ms.locfileid: "68720338"
---
# <a name="understand-billing-profiles"></a>Faturalama profillerini anlama

Faturalama profili bir ödeme yöntemi, Fatura adresi bilgileri ve satın alma siparişi numarası ve e-posta fatura tercihi gibi diğer fatura ayarlarını içerir. Microsoft'tan satın alınan ürünlerin ödemesini yapmak için bir faturalama profili kullanırsınız. Faturalama profilleri otomatik olarak oluşturulur ve her biri ayrı olarak fatura edilir. 

> [!NOTE]
>
> Tüm hesapların faturalama profili yoktur. Bir profiliniz olup olmadığından emin değilseniz [faturalama profillerinizin listesini görüntüleyebilirsiniz](manage-billing-profiles.md#view-my-billing-profiles).

## <a name="what-are-billing-profile-roles"></a>Faturalama profili rolleri nelerdir?

Faturalama profillerindeki rollerin satın almaları denetleme ve faturaları görüntüleme ve yönetme izinleri vardır. Faturaları izleyen, düzenleyen ve ödeyen kullanıcılara bu rolleri atayın. Örneğin, kuruluşunuzdaki tedarik ekibinin üyeleri.

| Rol                         | Açıklama                                                                      |
|----------------------------- |--------------------------------------------------------------------------------- |
| Faturalama profili sahibi        | Faturalama profili için her şeyi yönetme                                          |
| Faturalama profili katkıda bulunanı  | Faturalama profilindeki izinler dışında her şeyi yönetme                        |
| Faturalama profili okuyucusu       | Faturalama profilindeki her şeyin salt okunur görünümü                                |
| Fatura yöneticisi              | Faturaları görüntüleme ve ödeme ve faturalama profilindeki her şeyin salt okunur görünümüne sahiptir  |

## <a name="view-my-billing-profiles"></a>Faturalama profillerimi görüntüle

> [!NOTE]
>
> Bu adımları izlerseniz ve faturalama profilleri listesi boşsa, bir faturalama profiliniz olmadığı ve bu özelliği kullanamamanız anlamına gelir.

1. Yönetim merkezinde, **Faturalar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Fatura ve ödemeler</a> sayfasına gidin.
2. **Faturalama profili** sekmesini ve ardından listeden bir faturalama profili seçin.

Her faturalama profili aşağıdaki bilgileri içerir:

- **Faturalama profili adı ve durumu** &ndash; Faturalama profilinin benzersiz adı ve faturalama profilinin satın alma için etkin mi yoksa devre dışı mı olduğu.
- **Fatura ayarları** &ndash; Ödeme hesabının ülkesine göre para birimi, fatura sıklığı ve tarihi, faturaları e-posta eki olarak alma seçeneği ve isteğe bağlı bir PO numarası alanı
- **Ödeme yöntemleri** &ndash; Varsa profil için birincil ve yedek ödeme yöntemini gösterir
- **Ödeme hesabı** &ndash; Profilin ilişkili olduğu ödeme hesabının adı. Ödeme hesapları hakkında daha fazla bilgi için bkz. [Ödeme hesaplarını anlama](../manage-billing-accounts.md).
- **İletişim bilgileri** &ndash; Fatura adresi, kişi adı ve e-posta adresi
- **Faturalama profili rolleri** &ndash; Bu profil için bir şeyler yapmak üzere faturalama profili rollerinden birine atanan kişilerin listesi. Örneğin, faturaları ödeyin, bir PO numarası ekleyin veya satın alma işlemleri yapmak için kullanılan ödeme yöntemini değiştirin.

> [!NOTE]
>
> Faturalama profili rollerini yalnızca kuruluşunuzdaki kullanıcılara atayabilirsiniz.

## <a name="need-help-contact-support"></a>Yardıma mı ihtiyacınız var? Destek ekibine başvurun

Azure ücretlerinizle ilgili sorularınız veya yardıma ihtiyacınız varsa <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">Azure desteği ile bir destek isteği oluşturun</a>.

Microsoft 365 yönetim merkezi faturalama profilinizle ilgili sorularınız varsa veya yardıma ihtiyacınız varsa [desteğe başvurun](../../admin/get-help-support.md).

## <a name="related-content"></a>İlgili içerik

[Aboneliğiniz için faturalama profiliyle ödeme](pay-for-subscription-billing-profile.md) (makale)\
[Ödeme hesaplarını anlama](../manage-billing-accounts.md) (makale)\
[Ödeme yöntemlerini yönetme](manage-payment-methods.md) (makale)
