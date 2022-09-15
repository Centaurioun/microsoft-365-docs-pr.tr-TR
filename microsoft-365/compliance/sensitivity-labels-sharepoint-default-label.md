---
title: SharePoint belge kitaplığı için varsayılan duyarlılık etiketini yapılandırma
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Yeni ve etiketsiz belgeler için SharePoint belge kitaplığı için varsayılan duyarlılık etiketini yapılandırın.
ms.openlocfilehash: 6f3146f8ce59f88eafc311cd9bf382f06103eb94
ms.sourcegitcommit: b1ed6470645455c2f1fcf467450debc622c40147
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/15/2022
ms.locfileid: "67710773"
---
# <a name="configure-a-default-sensitivity-label-for-a-sharepoint-document-library"></a>SharePoint belge kitaplığı için varsayılan duyarlılık etiketini yapılandırma

>*[Güvenlik & uyumluluğu için Microsoft 365 lisanslama kılavuzu](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

> [!NOTE]
> Bu özellik önizleme aşamasındadır ve değiştirilebilir. Ayrıca, özellik genel kullanıma sunulduğunda (GA) lisans ayrıntılarının sağlandığı premium bir özelliktir.
> 
> Önizleme duyurusunu okumak için [blog gönderisine](https://techcommunity.microsoft.com/t5/security-compliance-and-identity/public-preview-default-label-for-a-document-library-in/ba-p/3585136) bakın.

[SharePoint duyarlılık etiketleri için etkinleştirildiğinde](sensitivity-labels-sharepoint-onedrive-files.md), belge kitaplıkları için varsayılan bir etiket yapılandırabilirsiniz. Ardından, bu kitaplığa yüklenen tüm yeni dosyalar veya kitaplıkta düzenlenen mevcut dosyalar, duyarlılık etiketi yoksa veya duyarlılık etiketine sahipse ancak [daha düşük öncelikliyse](sensitivity-labels.md#label-priority-order-matters) bu etiket uygulanır.

Örneğin, **Gizli** etiketini belge kitaplığı için varsayılan duyarlılık etiketi olarak yapılandırabilirsiniz. İlke varsayılan etiketi **Genel** olan bir kullanıcı bu kitaplığa yeni bir dosya kaydeder. SharePoint, bu etiketin yüksek önceliği nedeniyle bu dosyayı **Gizli** olarak etiketleyecektir. Olası sonuçların hızlı bir özeti için bkz. Var [olan bir etiket bu sayfada geçersiz kılınacak mı](#will-an-existing-label-be-overridden) ?

Varsayılan etiket, temel bir koruma düzeyi ve içerik incelemesi olmadan otomatik etiketleme biçimi sunar. Bu özelliğin varsayılan etiketini etiket ilkelerinde varsayılan etiketle ayırt etmeye yardımcı olmak için:

- **Belge kitaplığı için varsayılan duyarlılık etiketi**: Konum tabanlı etiketleme, yalnızca SharePoint için geçerlidir. El ile uygulanmadığı sürece düşük öncelikli etiketi geçersiz kılar.
- **İlkeden gelen varsayılan duyarlılık etiketi**: Her zaman tüm konumlar için geçerlidir. Hiçbir zaman var olan bir etiketi geçersiz kılmaz.

Dosya oluşturmak veya düzenlemek için Web üzerinde Office kullandığınızda, belge kitaplığı için varsayılan duyarlılık etiketi gecikme olmadan uygulanabilir. Ancak, windows, macOS, iOS veya Android'de Microsoft 365 Uygulamaları kullanarak bir dosyayı karşıya yüklerseniz veya oluşturursanız ve ardından SharePoint'e kaydederseniz etiketleme hemen yapılmaz:

- Dosya yükleme: Etiketin uygulanması birkaç dakika sürebilir.
- Microsoft 365 Uygulamaları: Etiket uygulama kapatıldıktan sonra uygulanır.

## <a name="will-an-existing-label-be-overridden"></a>Mevcut bir etiket geçersiz kılınacak mı?

Sonuçların özeti:

|Mevcut etiket |Kitaplık varsayılan etiketiyle geçersiz kılma |
|:-----|:-----|:-----|
|El ile uygulanan, herhangi bir öncelik| Hayır |
|Otomatik olarak uygulandı, düşük öncelikli | Evet |
|Otomatik olarak uygulandı, daha yüksek öncelikli | Hayır |
|İlkeden varsayılan etiket, düşük öncelikli | Evet |
|İlkeden varsayılan etiket, daha yüksek öncelikli | Hayır |

## <a name="requirements"></a>Gereksinimler

- [SharePoint ve OneDrive'da Office dosyaları için duyarlılık etiketlerini etkinleştirdiniz](sensitivity-labels-sharepoint-onedrive-files.md).

- [Kitaplık için SharePoint Bilgi Hakları Yönetimi (IRM) etkinleştirilmedi](set-up-irm-in-sp-admin-center.md#irm-enable-sharepoint-document-libraries-and-lists). Bu eski teknoloji, SharePoint belge kitaplığı için varsayılan duyarlılık etiketinin kullanılmasıyla uyumlu değildir. IRM için bir kitaplık etkinleştirildiyse, varsayılan duyarlılık etiketini seçemezsiniz.

## <a name="limitations"></a>Sınırlamalar

- SharePoint'te bekleyen mevcut dosyalar için geçerli değildir.

- [Duyarlılık etiketleriyle şifrelenmiş dosyalar için birlikte yazmayı etkinleştirmediğiniz](sensitivity-labels-coauthoring.md) sürece, kullanıcılar **Dosya** \> **Farklı Kaydet** seçeneğini seçtiğinde belge kitaplığı için varsayılan duyarlılık etiketinin uygulanmasında gecikmeyle karşılaşırsınız.

- Web için Office duyarlılık etiketlerinde olduğu gibi, [şifreleme uygulayan bazı etiket yapılandırmaları](encryption-sensitivity-labels.md#configure-encryption-settings) SharePoint için uygun değildir ve bu nedenle SharePoint belge kitaplığı için varsayılan duyarlılık etiketini desteklemez:
    - Word, PowerPoint ve Excel'de kullanıcıların etiketi ve onay kutusunu **uyguladığında izin atamasına izin verin****, kullanıcılardan izinleri belirtmelerini iste** seçeneğini belirleyin. Bu ayar bazen "kullanıcı tanımlı izinler" olarak adlandırılır.
    - **İçeriğe kullanıcı erişiminin süresi doluyor** , **Hiçbir Zaman** dışında bir değere ayarlanır.
    - **Çift Anahtar Şifrelemesi** seçildi.

## <a name="how-to-configure-a-default-sensitivity-label-for-a-sharepoint-document-library"></a>SharePoint belge kitaplığı için varsayılan duyarlılık etiketini yapılandırma

Mevcut belge kitaplığı için:

1. SharePoint'te, belge kitaplığı \> **Ayarlar** \> **Kitaplığı ayarlarına** gidin.

2. **Kitaplık ayarları** açılır bölmesinde **Varsayılan duyarlılık etiketleri'ni** seçin ve ardından açılan kutudan bir etiket seçin. Örneğin:
    
    ![SharePoint kitaplığı için varsayılan duyarlılık etiketini yapılandırmayı gösteren ekran görüntüsü.](../media/default-sensitivity-label-spo2.png)
    
    Ayarın PDF dosyaları için destekten bahsettiğini görmenize rağmen, bu dosya türü şu anda bu senaryo için desteklenmemektedir.

Yeni bir belge kitaplığı oluşturuyorsanız, **Belge kitaplığı oluştur** açılır penceresinden aynı **Varsayılan duyarlılık etiketleri** ayarını yapılandırabilirsiniz.

SharePoint kitaplığı için varsayılan duyarlılık etiketini ayarlamak ve değiştirmek için gereken izinler devralınır. Kitaplık adını ve açıklamasını değiştirme özelliğinde olduğu gibi, herhangi bir SharePoint site üyesi bu izne sahiptir.

## <a name="monitoring-application-of-library-default-sensitivity-labels"></a>Kitaplık varsayılan duyarlılık etiketlerinin izleme uygulaması

Dosyalara uygulanan duyarlılık etiketlerinin adlarını görmek için SharePoint **Duyarlılık** sütununu kullanın. Etiket bu özellikler tarafından uygulandığında, etiket adının araç ipucu **Bu dosya otomatik olarak etiketlendi** ifadesini görüntüler. Ancak bu araç ipucu, belge kitaplığı için varsayılan duyarlılık etiketine özel değildir. Ayrıca, otomatik etiketleme ilkeleri kullanılarak veya kullanıcının duyarlılık etiketi ilkelerinden gelen varsayılan etiketinin sonucu olarak duyarlılık etiketleri uygulandığında da görüntülenir.

Kitaplığın varsayılan duyarlılık etiketi nedeniyle etiketin ne zaman uygulandığını özel olarak belirlemek için [uyumluluk portalındaki denetim günlüğünü](search-the-audit-log-in-security-and-compliance.md) ve **Duyarlılık etiketi etkinlik** grubundan **Uygulanan duyarlılık etiketi dosyası** denetim olayını kullanın. Sonra:
1. Açılır bölmede ayrıntıları görüntülemek için bir girdi seçin.

2. Ayrıntılar bölmesinden **SensitivityLabelEventData bölümüne** gidin ve **ActionScourceDetails** değerini belirleyin.

3. Belge kitaplığı için varsayılan duyarlılık etiketi nedeniyle etiket uygulandığında **için 6** değeri kullanılır.

Bu özelliğin yapılandırma ayarını denetlemek için **SharePoint** liste etkinlikleri **grubundan Güncelleştirilmiş liste** denetim olayını kullanın. Belge kitaplığının ayrıntılar açılır bölmesinde, **OldSensitivityLabeld** ve **SensitivityLabelId'nin** üç durum değişikliğini yansıtabileceği **SensitivityLabelEventData** bölümüne kaydırın:

- Duyarlılık etiketi uygulandı
- Duyarlılık etiketi bir etiketten diğerine değiştirildi
- Duyarlılık etiketi kaldırıldı

Duyarlılık etiketi GUID'lerini etiket adlarıyla eşlemek için [Get-Label](/powershell/module/exchange/get-label) cmdlet'ini kullanın:

1. İlk olarak [Office 365 Güvenlik & Uyumluluk Merkezi PowerShell'e bağlanın](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).

2. Ardından, GUID'yi belirttiğiniz aşağıdaki komutu çalıştırın:

    ```powershell
    Get-Label -Identity "<GUID>" | Name

## Next steps

Default labeling ensures a minimum level of protection but doesn't take into account the file contents that might require a higher level of protection. Consider supplementing this labeling method with [automatic labeling](apply-sensitivity-label-automatically.md) that uses content inspection, and encourage [manual labeling](https://support.microsoft.com/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9) for users to replace the default label when needed.