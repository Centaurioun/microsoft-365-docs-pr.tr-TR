---
title: Microsoft Bookings’i açma veya kapatma
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
ms.custom: admindeeplinkMAC
ms.localizationpriority: medium
ms.collection:
- Tier1
- scotvorg
ms.assetid: 5382dc07-aaa5-45c9-8767-502333b214ce
description: Microsoft 365'te Microsoft Bookings erişmeyi öğrenin.
ms.openlocfilehash: 52fe958d37dde7bd07602a03846566aa24c10488
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2022
ms.locfileid: "68728983"
---
# <a name="turn-microsoft-bookings-on-or-off"></a>Microsoft Bookings’i açma veya kapatma

Rezervasyonlar tüm kuruluşunuz veya belirli kullanıcılar için açılabilir veya kapatılabilir. Kullanıcılar için Bookings'i açtığınızda, bir Bookings sayfası oluşturabilir, takvim oluşturabilir ve diğer kişilerin onlarla zaman ayırmasına izin verebilirler. Bu makale, kuruluşları için Bookings'i yöneten sahiplere ve yöneticilere yöneliktir.

> [!NOTE]
> Bu bölümlerde açıklanan yönetici denetimleri, 21Vianet (Çin) müşterileri tarafından sağlanan Office 365 için kullanılamaz.

## <a name="turn-bookings-on-or-off-for-your-organization-using-the-microsoft-365-admin-center"></a>Microsoft 365 yönetim merkezi kullanarak kuruluşunuz için Bookings'i açma veya kapatma

1. Microsoft 365 yönetim merkezi genel yönetici olarak oturum açın.

2. Yönetim merkezinde **Ayarlar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">**Kuruluş ayarları'na**</a> gidin.

3. Kuruluşunuzda Bookings'i etkinleştirmek veya devre dışı bırakmak için **Kuruluşunuzun Bookings'i kullanmasına izin ver** onay kutusunu seçin.

   > [!NOTE]
   > Bookings'in kapatılması, Bookings sayfalarının oluşturulması ve yönetilmesi dahil olmak üzere hizmete tüm erişimi devre dışı bırakır.

4. **Değişiklikleri Kaydet**'i seçin.

### <a name="turn-bookings-on-or-off-for-your-organization-using-powershell"></a>PowerShell kullanarak kuruluşunuz için Bookings'i açma veya kapatma

[Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) PowerShell cmdlet'ini kullanarak kuruluşunuzda Bookings'i açmak veya kapatmak için [PowerShell'Exchange Online bağlanın](/powershell/exchange/connect-to-exchange-online-powershell) ve aşağıdaki komutu çalıştırın:

```PowerShell
   Set-OrganizationConfig -BookingsEnabled $false
```

### <a name="granular-controls"></a>Ayrıntılı denetimler

Bookings'i kimlerin kullanabileceğini denetlemek, Hangi Bookings bilgilerinin paylaşılacağına ve personelin Bir Rezervasyon takvimine eklenmeden önce onay gerekip gerekmediğine karar vermek için aşağıdaki ayarları kullanın.

:::image type="content" source="../media/control-access-sharing-bookings.png" alt-text="Ekran görüntüsü: Bookings'i kimlerin kullanabileceğini denetlemenize, hangi Bookings bilgilerinin paylaşıldığını ve personel onayına karar vermenizi sağlayan ayarlar":::

### <a name="block-bookings-from-outside-your-organization"></a>Kuruluşunuzun dışından gelen rezervasyonları engelleme

Bookings'i yalnızca kuruluşunuzdaki kişilerin randevu ayırtabilmesi için ayarlayabilirsiniz. Yalnızca kuruluşunuzda oturum açmış ve kimliği doğrulanmış kullanıcılar randevu rezervasyonu yapabilir.

### <a name="block-social-sharing-options"></a>Sosyal paylaşım seçeneklerini engelleme

Rezervasyon sayfalarının sosyal ağlarda nasıl paylaşıldığından denetleyebilirsiniz. Bu ayar Ayarlar **Kuruluş ayarları** -> **Bookings** **altındaki** ->  Microsoft 365 yönetim merkezi kullanılabilir.

### <a name="block-sharing-staff-details-with-customers"></a>Personel ayrıntılarını müşterilerle paylaşmayı engelleme

İletişim bilgileri gibi personel bilgileri hiçbir zaman müşterilere e-posta veya başka bir iletişim yoluyla gönderilmez.

### <a name="require-staff-approvals-before-sharing-freebusy-information"></a>Serbest/meşgul bilgilerini paylaşmadan önce personel onayları gerektir

Kuruluşunuzdaki çalışanların uygunluk bilgileri Bookings aracılığıyla paylaşılmadan ve rezervasyon sayfasından rezerve edilmeden önce kabul etmelerini zorunlu kılabilirsiniz.

Bu ayar etkinleştirildiğinde, rezervasyon takvimlerine personel olarak eklenen kişiler, isteği **Onayla/Reddet** bağlantısını içeren bir e-posta alır.

## <a name="restrict-collection-of-customer-data"></a>Müşteri verilerinin toplanmasını kısıtlama

Uyumluluk nedeniyle bazı müşteri bilgilerini toplamak istemeyebilirsiniz. Bu seçeneklerden herhangi biri için bir onay kutusu seçerseniz, bu alanlar müşterilerinize veya müşterilerinize gösterilen formlara dahil edilmeyecektir.

:::image type="content" source="../media/restrict-collection-customer-data.png" alt-text="Ekran görüntüsü: Müşterilerin hassas verileri sizinle paylaşmasını önlemeye yardımcı olmak için onay kutularını seçin":::

### <a name="turn-bookings-on-or-off-for-individual-users"></a>Bireysel kullanıcılar için Bookings'i açma veya kapatma

Bookings'i bireysel kullanıcılar için devre dışı bırakabilirsiniz.

1. Microsoft 365 yönetim merkezi gidin ve **Kullanıcılar** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">**Etkin kullanıcılar'ı**</a> seçin.

1. İstediğiniz kullanıcıyı ve ardından **Lisanslar ve Uygulamalar'ı** seçin.

1. **Uygulamalar'ı** genişletin ve Microsoft Bookings onay kutusunu temizleyin.

## <a name="allow-only-selected-users-to-create-bookings-calendars"></a>Yalnızca seçili kullanıcıların Bookings takvimleri oluşturmasına izin ver

İlke kısıtlamalarını kullanarak lisanslı kullanıcıların Bookings takvimleri oluşturabilmesini kısıtlayabilirsiniz. Kuruluşunuzdaki tüm kullanıcılar Bookings lisanslarına sahip olur, ancak yalnızca ilkeye dahil olanlar Bookings takvimleri oluşturabilir ve oluşturdukları takvimlere kimlerin erişebileceği üzerinde tam denetime sahip olabilir.

Bu ilkeye dahil olan kullanıcılar yeni Bookings takvimleri oluşturabilir ve mevcut Bookings takvimlerine herhangi bir kapasitede (yönetici rolü dahil) personel olarak eklenebilir. Bu ilkeye dahil olmayan kullanıcılar yeni Bookings takvimleri oluşturamaz ve bunu yapmaya çalışırlarsa bir hata iletisi alırlar.

PowerShell Exchange Online kullanarak aşağıdaki komutları çalıştırmanız gerekir. Exchange Online cmdlet'lerini çalıştırma hakkında daha fazla bilgi için bkz[. powershell Exchange Online bağlanma](/powershell/exchange/connect-to-exchange-online-powershell).

> [!IMPORTANT]
> Aşağıdaki adımlarda, kuruluşunuzda başka Outlook Web App (OWA) posta kutusu ilkesi oluşturulmamış olduğu varsayılır.

1. Kullanıcılar için Bookings takvimleri oluşturmasına izin verilmesi gereken yeni bir posta kutusu ilkesi oluşturun. (Bookings takvimi oluşturmaya yeni posta kutusu ilkeleri tarafından varsayılan olarak izin verilir.)

   ```PowerShell
   New-OwaMailboxPolicy -Name "BookingsCreators"
   ```

   Daha fazla bilgi için bkz. [New-OwaMailboxPolicy](/powershell/module/exchange/new-owamailboxpolicy).

2. Bookings takvimleri oluşturma izni vermek istediğiniz her kullanıcı için bu komutu çalıştırarak bu ilkeyi ilgili kullanıcılara atayın.

   ```PowerShell
   Set-CASMailbox -Identity <someCreator@emailaddress> -OwaMailboxPolicy "BookingsCreators"
   ```

   Daha fazla bilgi için bkz [. Set-CASMailbox](/powershell/module/exchange/set-casmailbox).

3. İsteğe bağlı: Kuruluşunuzdaki diğer tüm kullanıcılar için Bookings'i devre dışı bırakmak istiyorsanız bu komutu çalıştırın.

   ```PowerShell
   Set-OwaMailboxPolicy "OwaMailboxPolicy-Default" -BookingsMailboxCreationEnabled:$false
   ```

Daha fazla bilgi için bkz [. Set-OwaMailboxPolicy](/powershell/module/exchange/set-owamailboxpolicy).

OWA posta kutusu ilkeleri hakkında daha fazla bilgi için aşağıdaki konulara göz atın:

- [Exchange Online'da Web üzerinde Outlook posta kutusu ilkesi oluşturma](/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)

- [Exchange Online'da bir posta kutusuna Web üzerinde Outlook posta kutusu ilkesi uygulama veya kaldırma](/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)
