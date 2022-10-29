---
title: UKG Boyutlarına Vardiyalar bağlantınızı yönetmek için Microsoft 365 yönetim merkezi kullanın
author: LanaChin
ms.author: v-lanachin
ms.reviewer: ''
manager: samanro
ms.topic: article
audience: admin
ms.service: microsoft-365-frontline
search.appverid: MET150
description: Microsoft 365 yönetim merkezi UkG Boyutlarına Vardiyalar bağlantınızı yönetmeyi öğrenin.
ms.localizationpriority: high
ms.collection:
- M365-collaboration
- m365-frontline
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
ms.openlocfilehash: a7b7845c2016e26fc540538cfecdb25771c3550f
ms.sourcegitcommit: 3d7dd25abcbf923b45eae84ff4d9d2bb95ef4ca4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/28/2022
ms.locfileid: "68777664"
---
# <a name="use-the-microsoft-365-admin-center-to-manage-your-shifts-connection-to-ukg-dimensions"></a>UKG Boyutlarına Vardiyalar bağlantınızı yönetmek için Microsoft 365 yönetim merkezi kullanın

[!INCLUDE [preview-feature](includes/preview-feature.md)]

## <a name="overview"></a>Genel bakış

[UKG Boyutları için Microsoft Teams Vardiyaları bağlayıcısı, Microsoft](shifts-connectors.md#microsoft-teams-shifts-connector-for-ukg-dimensions) Teams'deki Vardiyalar uygulamasını UKG Boyutları ile tümleştirmenize olanak tanır. Bir bağlantı kurduktan sonra ön cephe çalışanlarınız Vardiyalar'ın içinden UKG Dimensions'ta zamanlamalarını sorunsuz bir şekilde görüntüleyebilir ve yönetebilir.

Bağlantı oluşturmak için Microsoft 365 yönetim merkezi veya [PowerShell'de](shifts-connector-ukg-powershell-setup.md) [Shifts bağlayıcı sihirbazını](shifts-connector-wizard-ukg.md) kullanabilirsiniz. Bağlantı kurulduktan sonra Microsoft 365 yönetim merkezi yönetebilirsiniz. Bağlayıcı Yönetimi sayfasında, ayarladığınız her bağlantının yanı sıra sistem durumu ve eşitleme aralığı ayrıntıları gibi bilgiler listelenir. Ayrıca sihirbaza erişerek yeni bir bağlantı oluşturabilir veya mevcut bağlantılarınızdan herhangi birinde değişiklik yapabilirsiniz. Örneğin, eşitleme ayarlarını ve ekip eşlemelerini güncelleştirebilirsiniz.

> [!NOTE]
> Bağlantıyı yönetmek için PowerShell'i de kullanabilirsiniz. Örneğin, bir hata raporunu görüntüleyebilir, bağlantı ayarlarını değiştirebilir ve eşitlemeyi devre dışı bırakabilirsiniz. Daha fazla bilgi edinmek için bkz. [PowerShell kullanarak UKG Boyutlarına Vardiyalar bağlantınızı yönetme](shifts-connector-ukg-powershell-manage.md).

## <a name="manage-your-connection"></a>Bağlantınızı yönetme

1. [Microsoft 365 yönetim merkezi](https://admin.microsoft.com/) sol gezinti bölmesinde **Kurulum'u** seçin ve öne **çıkan koleksiyonlar'ın** altında **Ön cephe çalışanları'nı** seçin.
2. **Vardiya bağlayıcılarını yönet'i** ve ardından **Yönet'i** seçin. Bu seçeneğin yalnızca sihirbazı veya PowerShell'i kullanarak en az bir bağlantı ayarladıysanız kullanılabildiğini unutmayın.

    Burada, sihirbaz veya PowerShell aracılığıyla ayarladığınız tüm bağlantıların listesini ve her biri hakkındaki bilgileri görürsünüz.

    :::image type="content" source="media/shifts-connector-ukg-manage.png" alt-text="bağlantı listesini gösteren Microsoft 365 yönetim merkezi Bağlayıcı Yönetimi sayfasının ekran görüntüsü." lightbox="media/shifts-connector-ukg-manage.png":::

    - Yeni bağlantı oluşturmak için, sihirbazı başlatmak için sayfanın üst kısmındaki **Bağlayıcı ekle'yi** seçin.

    - Bağlantı hakkında daha fazla ayrıntı görüntülemek için bağlantı adına tıklayın. Ayrıntılar sayfasında, eşleme ve hesap yetkilendirme hataları (varsa), eşleme listesi (varsa) ve daha fazlası dahil olmak üzere sistem durumu bilgilerini görürsünüz. Sihirbazda bağlantı ayarlarını güncelleştirmek için **Düzenle'yi** de seçebilirsiniz.

      :::image type="content" source="media/shifts-connector-ukg-manage-details.png" alt-text="Bağlayıcı sistem durumu ve eşleme bilgilerini gösteren bağlantının ayrıntılar sayfasının ekran görüntüsü." lightbox="media/shifts-connector-ukg-manage-details.png":::

         Hata iletilerinin tam listesi ve bunların nasıl çözüleceğini öğrenmek için bu makalenin devamında yer alan [Hata iletilerinin listesi](#list-of-error-messages) bölümüne bakın.

    - Bağlantıda değişiklik yapmak için bağlantının yanındaki **Düzenle'yi** seçin. İstediğiniz ayarları güncelleştirebileceğiniz sihirbaza yönlendirilirsiniz.
  
> [!NOTE]
> Bağlantı kurulumu sırasında sihirbazın son sayfasında Bağlayıcı Yönetimi düğmesini seçtiğinizde doğrudan **Bağlayıcı Yönetimi** sayfasına da gidebilirsiniz.

## <a name="list-of-error-messages"></a>Hata iletilerinin listesi

Karşılaşabileceğiniz hata iletilerinin listesi ve bunları çözmenize yardımcı olacak bilgiler aşağıdadır.

|Hata türü |Hata ayrıntıları |Çözüm |
|---------|---------|---------|
|İş gücü yönetim sistemi kimlik doğrulaması yapılamıyor.|Sağladığınız iş gücü yönetim sistemi hesabı kimlik bilgileri geçersiz veya bu hesabın gerekli izinleri yok.|Bağlantı ayarlarında WFM hizmet hesabı kimlik bilgilerinizi güncelleştirin. Bunu yapmak için aşağıdaki yöntemlerden birini kullanın.<ul><li>Microsoft 365 yönetim merkezi Bağlayıcı Yönetimi sayfasında veya bağlantı ayrıntıları sayfasında **Düzenle'yi** seçerek Shifts bağlayıcı sihirbazına gidin.</li><li>[Set-CsTeamsShiftsConnectionInstance](/powershell/module/teams/set-csteamsshiftsconnectioninstance) veya [Update-CsTeamsShiftsConnectionInstance cmdlet'ini](/powershell/module/teams/update-csteamsshiftsconnectioninstance) kullanın.</li><li>[Bu PowerShell betiğini](shifts-connector-ukg-powershell-manage.md#change-connection-settings) kullanın.</li></ul>|
|Graph kimliği doğrulanamıyor. |Kimlik doğrulaması başarısız oldu. Belirlenen aktör için geçerli kimlik bilgileri girdiğinizden ve gerekli izinlere sahip olduğunuzdan emin olun.|Microsoft 365 sistem hesabınızın (belirlenen aktör olarak da bilinir) ekip sahibi olarak eklendiğinden emin olun.<br> Alternatif olarak, bağlantı ayarlarında Microsoft 365 sistem hesabı kimlik bilgilerinizi güncelleştirebilirsiniz.|
|Bazı kullanıcılar doğru eşleme yapamadı|Bazı kullanıcılar için eşleme başarısız oldu: \<X\> başarılı, \<X\> başarısız AAD kullanıcıları ve \<X\> başarısız iş gücü yönetim sistemi kullanıcıları.|Eşlemenin başarısız olduğu kullanıcıları tanımlamak için [Get-CsTeamsShiftsConnectionSyncResult](/powershell/module/teams/get-csteamsshiftsconnectionsyncresult) cmdlet'ini veya [bu PowerShell betiğini](shifts-connector-ukg-powershell-manage.md#user-mapping-errors) kullanın. Eşlenen takımdaki kullanıcıların WFM örneğindeki kullanıcılarla eşleştiğinden emin olun.|
|Bu toplu işte bir ekip veya ekip eşlenemiyor. |Bu belirlenen aktör profilinin ekip sahipliği ayrıcalıkları yok. |Microsoft 365 sistem hesabınızın (belirlenen aktör olarak da bilinir) ekip sahibi olarak eklendiğinden emin olun.<br>Microsoft 365 sistem hesabınızı değiştirdiyseniz, bu hesabı ekip sahibi olarak ekleyin ve bağlantı ayarlarını bu hesabı kullanacak şekilde güncelleştirin.|
|    |Bu ekip zaten mevcut bir bağlayıcı örneğine eşlenmiş durumda. |[Remove-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/remove-csteamsshiftsconnectionteammap) cmdlet'ini kullanarak ekibin mevcut bağlantıdan eşlemesini kaldırın. Ya da ekibi yeniden eşlemek için yeni bir bağlantı oluşturun.|
|    |Bu saat dilimi geçersiz. geçirilen saat dilimi tz veritabanı biçimini kullanmıyor.|Saat diliminin doğru olduğundan emin olun ve ardından ekibi yeniden eşleyin.|
|    |Bu bağlayıcı örneğini bulamıyoruz.|Ekibi mevcut bir bağlantıyla eşleyin.|
|    |Bu AAD ekibi bulunamadı.|Ekibin var olduğundan emin olun veya yeni bir ekip oluşturun.|

## <a name="related-articles"></a>İlgili makaleler

- [Vardiya bağlayıcıları](shifts-connectors.md)
- [Shifts bağlayıcı sihirbazını kullanarak Shifts'i UKG Boyutlarına bağlama](shifts-connector-wizard-ukg.md)
- [Vardiyaları UKG Boyutlarına bağlamak için PowerShell kullanma](shifts-connector-ukg-powershell-setup.md)
- [PowerShell kullanarak UkG Boyutlarına Vardiyalar bağlantınızı yönetme](shifts-connector-ukg-powershell-manage.md)
- [Vardiyalar uygulamasını yönetme](/microsoftteams/expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams?bc=/microsoft-365/frontline/breadcrumb/toc.json&toc=/microsoft-365/frontline/toc.json)
