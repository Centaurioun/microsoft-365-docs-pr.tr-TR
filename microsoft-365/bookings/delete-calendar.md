---
title: Rezervasyon takvimi silme
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
ms.localizationpriority: medium
ms.assetid: 8c3a913c-2247-4519-894d-b6263eeb9920
description: Bookings takvimlerini silmek için Microsoft 365 yönetim merkezi veya Windows PowerShell kullanın.
ms.openlocfilehash: b5cb74940bc68116673322c6d38e3fecd4002326
ms.sourcegitcommit: 95ac076310ab9006ed92c69938f7ae771cd10826
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/20/2022
ms.locfileid: "67851202"
---
# <a name="delete-a-booking-calendar-in-bookings"></a>Bookings'te bir rezervasyon takvimini silme

Bu makalede, istenmeyen bir rezervasyon takvimini nasıl silebileceğiniz açıklanmaktadır. rezervasyon takvimini Microsoft 365 yönetim merkezi silebilir veya PowerShell'i kullanabilirsiniz. Bookings takvimi Exchange Online bir posta kutusu olduğundan, rezervasyon takvimini silmek için ilgili kullanıcı hesabını silersiniz.

> [!IMPORTANT]
> 2017 veya daha önce oluşturduğunuz tüm rezervasyon takvimlerinin bu konudaki PowerShell yönergeleri kullanılarak silinmesi gerekir. 2018 veya sonrasında oluşturulan tüm rezervasyon takvimleri Microsoft 365 yönetim merkezi silinebilir.

Rezervasyon takvimi, aşağıdakiler dahil olmak üzere bu rezervasyon takvimi ve verileriyle ilgili tüm bilgilerin depolandığı yerdir:

- Rezervasyon takvimi oluşturulduğunda eklenen iş bilgileri, logo ve çalışma saatleri
- Rezervasyon takvimi oluşturulduğunda eklenen ilgili personel ve hizmetler
- Tüm rezervasyonlar ve izin randevuları oluşturulduktan sonra rezervasyon takvimine eklenir.

> [!WARNING]
> Rezervasyon takvimi silindikten sonra bu ek bilgiler de kalıcı olarak silinir ve kurtarılamaz.

## <a name="delete-a-booking-calendar-in-the-microsoft-365-admin-center"></a>Microsoft 365 yönetim merkezi bir rezervasyon takvimini silme

1. Microsoft 365 yönetim merkezi gidin.

1. Yönetim merkezinde **Kullanıcılar** 'ı seçin.

   ![Microsoft 365 yönetim merkezi'deki Kullanıcılar kullanıcı arabiriminin görüntüsü.](../media/bookings-admin-center-users.png)

1. **Etkin Kullanıcılar** sayfasında, silmek istediğiniz rezervasyon takviminin adını seçin ve ardından **Kullanıcıyı sil'i** seçin.

   ![Microsoft 365 yönetim merkezi'de Kullanıcı Kullanıcı Arabirimini Sil'in görüntüsü.](../media/bookings-delete-user.png)

## <a name="delete-a-booking-calendar-using-exchange-online-powershell"></a>Exchange Online PowerShell kullanarak rezervasyon takvimini silme

1. [Exchange Online PowerShell’e bağlanma](/powershell/exchange/connect-to-exchange-online-powershell).

2. Kiracınızdaki rezervasyon posta kutularının listesini almak için aşağıdaki komutu çalıştırın:

   ```powershell
   Get-EXOMailbox -RecipientTypeDetails SchedulingMailbox
   ```

3. değerini kalıcı olarak silmek istediğiniz rezervasyon posta kutusu diğer adının tam adıyla değiştirin \<BookingCalendarToDelete\> ve aşağıdaki komutu çalıştırın:

   ```powershell
   Remove-Mailbox -Identity <BookingCalendarToDelete>
   ```

   > [!IMPORTANT]
   > Kalıcı olarak silmek istediğiniz rezervasyon posta kutusu diğer adının tam adını yazarken dikkatli olun.

4. Takvimin silindiğini doğrulamak için aşağıdaki komutu çalıştırın:

   ```powershell
    Get-EXOMailbox -RecipientTypeDetails SchedulingMailbox
   ```

   Silinen takvim çıktıda görünmez.
