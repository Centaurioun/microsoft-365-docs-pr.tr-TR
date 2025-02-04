---
title: İş için Microsoft Defender'de kullanıcı ekleme ve lisans atama
description: Kullanıcı ekleme ve cihazlarını korumak için İş için Defender lisansları atama
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: conceptual
ms.service: microsoft-365-security
ms.subservice: mdb
ms.localizationpriority: medium
ms.date: 08/24/2022
ms.collection:
- m365-security
- tier1
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.openlocfilehash: 96078d0ebbc8512d9fe63106bc8e441c55110dd4
ms.sourcegitcommit: 4dfb5de8c61847b8ddd10410ad20d34860eed8f6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/28/2022
ms.locfileid: "68110897"
---
# <a name="add-users-and-assign-licenses-in-microsoft-defender-for-business"></a>İş için Microsoft Defender'de kullanıcı ekleme ve lisans atama

İş için Defender'a kaydolmuş olur olmaz, ilk adımınız kullanıcıları eklemek ve lisans atamaktır. Bu makalede kullanıcı ekleme adımları açıklanır ve sonraki adımlar açıklanır.

## <a name="add-users-and-assign-licenses"></a>Kullanıcı ekleme ve lisans atama

> [!IMPORTANT]
> Bu görevi gerçekleştirmek için genel yönetici olmanız gerekir.  Şirketinizi Microsoft 365 veya İş için Defender'a kaydolan kişi varsayılan olarak genel yöneticidir.

1. konumundaki Microsoft 365 yönetim merkezi [https://admin.microsoft.com](https://admin.microsoft.com) gidin ve oturum açın.

2. **Etkin Kullanıcılar'a** >  gidin ve Kullanıcı **ekle'yi** seçin.

3. **Temel bilgileri ayarla** bölmesinde, temel kullanıcı bilgilerini doldurun ve **İleri'yi** seçin.

   - **Ad**: Ad ve soyadını, görünen adı ve kullanıcı adını girin.
   - **Etki alanı** Kullanıcı hesabının etki alanını seçin. Örneğin, kullanıcının kullanıcı adı `Pat`ise ve etki alanı ise `contoso.com`, kullanarak `pat@contoso.com`oturum açar.
   - **Parola ayarları**: Otomatik olarak oluşturulan parolayı mı kullanacağınızı yoksa kullanıcı için kendi güçlü parolanızı mı oluşturacağını seçin. Kullanıcı 90 gün sonra parolasını değiştirmelidir. Alternatif olarak **, bu kullanıcının ilk kez oturum açarken parolasını değiştirmesini gerektir seçeneğini de** belirleyebilirsiniz. Kullanıcı eklendiğinde kullanıcının parolasını e-postayla göndermek isteyip istemediğinizi de seçebilirsiniz.

4. **Ürün lisansları ata** sayfasında İş için Defender'ı (veya Microsoft 365 İş Ekstra) seçin. Ardından **İleri'yi** seçin. 

   Kullanılabilir lisansınız yoksa da kullanıcı ekleyebilir ve ek lisans satın alabilirsiniz. Kullanıcı ekleme hakkında daha fazla bilgi için bkz. [Aynı anda kullanıcı ekleme ve lisans atama](../../admin/add-users/add-users.md).

5. **İsteğe bağlı ayarlar** sayfasında **Profil bilgilerini** genişletebilir ve kullanıcının iş unvanı, departmanı, konumu gibi ayrıntıları doldurabilirsiniz. Ardından **İleri'yi** seçin.

6. **Gözden geçir ve bitir** sayfasında ayrıntıları gözden geçirin ve kullanıcıyı eklemek için **Eklemeyi bitir'i** seçin. Herhangi bir değişiklik yapmanız gerekiyorsa önceki sayfaya geri dönmek için **Geri'yi** seçin.

## <a name="next-steps"></a>Sonraki adımlar

- [Microsoft 365 Defender portalını ziyaret edin](mdb-get-started.md)
- [İş için Defender'da kurulum sihirbazını kullanın](mdb-use-wizard.md).
