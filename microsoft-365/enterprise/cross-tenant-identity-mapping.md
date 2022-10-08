---
title: Kiracılar Arası Kimlik Eşlemesi (önizleme)
description: Kiracılar arası geçişlere hazırlanırken Microsoft 365 kuruluşları arasında kimlikleri eşleme.
author: briandaymsft
ms.author: brianday
manager: rolowe
ms.topic: overview
ms.date: 07/18/2022
ms.service: office-365
ms.custom: template-overview
ms.openlocfilehash: 21738fd4131bcaa7ea8c1022608003eea6f1562e
ms.sourcegitcommit: ecc04b5b8f84b34255a2d5e90b5ab596af0d16c7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/01/2022
ms.locfileid: "67878157"
---
# <a name="cross-tenant-identity-mapping-preview"></a>Kiracılar Arası Kimlik Eşlemesi (önizleme)

Kiracılar Arası Kimlik Eşlemesi, bir Microsoft 365 kuruluşundan diğerine geçişler sırasında kullanılabilen bir özelliktir (genellikle kiracılar arası geçiş olarak adlandırılır). Kuruluş sınırları arasında bire bir nesne ilişkileri kurmak için güvenli bir yöntem sağlar ve hedef nesneleri başarılı bir geçiş için otomatik olarak hazırlar.

>[!NOTE]
>Kiracılar Arası Kimlik Eşlemesi, geliştirmenin özel bir önizleme aşamasındadır. Tamamlanmamış bir proje olarak herhangi bir bilgi veya kullanılabilirlik herhangi bir zamanda değiştirilebilir. Özel önizleme müşterileri için destek e-posta yoluyla ele alınacaktır. Kiracılar Arası Kimlik Eşlemesi, [Çevrimiçi Hizmetler için Microsoft Evrensel Lisans](https://www.microsoft.com/licensing/terms/product/ForOnlineServices/all) **Koşulları'nın önizleme koşulları** kapsamındadır.

## <a name="benefits-of-using-cross-tenant-identity-mapping"></a>Kiracılar Arası Kimlik Eşlemesi kullanmanın avantajları

Kiracılar Arası Kimlik Eşlemesi, hedef kuruluştaki Posta Etkin Kullanıcı nesnelerini yapılandırmak amacıyla büyük veri kümelerini kaynak kuruluştan dışarı aktarma gereksinimini ortadan kaldırır.

Kiracılar Arası Kimlik Eşleme ile veriler Microsoft güvenlik sınırı içinde kalır ve tek yönlü güven olarak hizmet veren özel olarak yapılandırılmış **Kuruluş İlişkileri** kullanılarak doğrudan kaynak kuruluştan hedef kuruluşa güvenli bir şekilde kopyalanır.

Kiracılar Arası Kimlik Eşlemesi'nin kullanılması _, ExchangeGuid_, _ArchiveGuid_ ve tüm gerekli _X500 proxy adresleri_ gibi değerleri otomatik olarak yapılandırarak geçiş için binlerce hedef nesne olabilecekleri yapılandırırken hata olasılığını azaltır.

Kiracılar Arası Kimlik Eşlemesi kullanmanın bazı ek avantajları:

- Bir hatanın başarısız geçişlerle sonuçlandığı el ile gerçekleştirilen işlemlerin sayısını azaltır
- Kaynak kuruluştan hedef kuruluşa geçiş için kapsam içindeki nesnelerin tanımlanmasını otomatikleştirir
- Kaynak kuruluştaki Posta Kutusu Kullanıcısı nesnesinin hedef kuruluştaki önceden var olan Posta Etkin Kullanıcı nesnesiyle 1:1 eşlemesini oluşturur
- Gerekli özniteliklerin kaynak kuruluş Posta Kutusu Kullanıcısı'ndan hedef kuruluşa Posta Etkin Kullanıcı popülasyonunu otomatikleştirir
- Kaynak kuruluş kullanıcılarının primarySMTPAddress değerine göre [kiracılar arası posta kutusu geçişi](cross-tenant-mailbox-migration.md) için hazırlanan ve hazır nesnelerin listesini sağlar

## <a name="faq-about-cross-tenant-identity-mapping"></a>Kiracılar Arası Kimlik Eşleme hakkında SSS

Özel önizlemeye katılmak isteyip istediğinizi değerlendirebilmeniz için sık sorulan bilgileri sağlamak istiyoruz.

- Bu özellik yalnızca [Kiracılar arası posta kutusu geçişi (önizleme)](cross-tenant-mailbox-migration.md) ile kullanılmak üzere tasarlanmıştır ve Microsoft dışı üçüncü taraf geçiş çözümleriyle kullanılmamalıdır.
- Veri işleme (depolama, işlem, aktarım vb.) şu anda Amerika'nın Birleşik Devletler içinde ve geçişe katılan kuruluşların Exchange Online ana bölgesindedir.
  - Multi-Geo özellikli kuruluşlarda, kuruluşun Exchange Online için ana coğrafi konumu kullanılır.
- Bu özellik şu anda yalnızca dünya çapındaki Microsoft 365 teklifinde etkinleştirilebilir. GCC, GCC High, DoD, Office 365 by 21 Vianet vb.
- Özellik PowerShell tabanlı olduğundan powershell hakkında bilgi sahibi olması gerekir
- Bu özellik, REST uç noktasına şifreli bir bağlantı üzerinden iletişim kurar.
- Özellik şu anda ilk kurulum için Genel Yönetici rolünü gerektirir. Bu davranış gelecekteki bir güncelleştirmede değişebilir.
- Kuruluş İlişkileri, her iki kuruluşun da bu işlem türünü gerçekleştirme yetkisine sahip olduğundan emin olmak için çift el sıkışmalı bir yaklaşım olarak kullanılır.
- Yalnızca bulut veya hibrit kuruluşlarla çalışır.
- Karma yapılandırmadaki hedef kuruluşlar, şirket içi dizinden eşitlenen Posta Etkin Kullanıcı nesnelerini değiştirmek için bir şirket içi Exchange sunucusu gerektirir. Exchange Server 2019 CU12'de yayınlanan yeni Exchange Yönetim Aracı özelliği desteğini test etmedik.

## <a name="what-does-participating-in-the-private-preview-entail"></a>Özel önizlemeye katılmak neleri gerektirir?

Hem Kiracılar Arası Kimlik Eşlemeyi denemek hem de deneyimlerine göre geri bildirim sağlamak isteyen müşterileri arıyoruz. Daha önce yaptığınız geçişlerle karşılaştırıldığında geçişi sizin için kolaylaştırdı mı? Eksik olduğunu hissettiğiniz özellikler var mı? Tüm yapıcı geri bildirimler memnuniyetle karşılanır.

## <a name="how-to-participate"></a>Nasıl katılır?

Katılmak istiyorsanız veya daha fazla sorunuz varsa, lütfen [CTIMPreview@service.microsoft.com](mailto:CTIMPreview@service.microsoft.com) e-posta gönderin ve Kiracılar Arası Kimlik Eşlemesi'ni kullanmak istediğiniz geçişle ilgili bazı temel bilgileri sağlayın.

## <a name="next-steps"></a>Sonraki adımlar

Bu hazırlık, Kiracılar Arası Kimlik Eşlemesi'nin otomatikleştireceği işlem olduğundan, hedef kullanıcı nesnelerini geçiş için hazırlamayla ilgili geçerli Kiracılar Arası Posta Kutusu Geçişi adımlarını gözden geçirmenizi öneririz.

- [Kiracılar Arası Posta Kutusu Geçişlerini Gözden Geçirme (önizleme)](cross-tenant-mailbox-migration.md#prepare-target-user-objects-for-migration)
