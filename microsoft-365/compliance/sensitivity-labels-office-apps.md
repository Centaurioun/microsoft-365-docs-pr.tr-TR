---
title: Office uygulamalarında duyarlılık etiketlerini yönetme
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- purview-compliance
- tier1
search.appverid:
- MOE150
- MET150
description: MASAÜSTÜ, mobil ve web için Office uygulamalarında duyarlılık etiketlerini yönetmek için BT yöneticilerine yönelik bilgiler.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4e6571b59d8ab6ec3624fda0a7827118e939d2fa
ms.sourcegitcommit: 21548843708d80bc861f03ffae41457252492bb6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2022
ms.locfileid: "68793713"
---
# <a name="manage-sensitivity-labels-in-office-apps"></a>Office uygulamalarında duyarlılık etiketlerini yönetme

>*[Güvenlik & uyumluluğu için Microsoft 365 lisanslama kılavuzu](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

Microsoft Purview uyumluluk portalı duyarlılık etiketlerini [yayımladığınızda](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy), kullanıcılar verileri oluşturuldukça veya düzenlendiklerinde sınıflandırmak ve korumak için Office uygulamalarında görünmeye başlarlar.

Office uygulamalarında duyarlılık etiketlerini başarıyla yönetmenize yardımcı olması için bu makaledeki bilgileri kullanın. Örneğin, yerleşik etiketlemeye özgü özellikler için ihtiyacınız olan en düşük uygulama sürümlerini, bu özellikler için ek yapılandırma bilgilerini belirleyin ve Azure Information Protection birleşik etiketleme istemcisi ve diğer uygulamalar ve hizmetlerle etkileşimleri anlayın.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="labeling-client-for-desktop-apps"></a>Masaüstü uygulamaları için istemci etiketleme

Windows ve Mac için Office masaüstü uygulamalarında yerleşik olarak bulunan duyarlılık etiketlerini kullanmak için Office'in abonelik sürümünü kullanmanız gerekir. Bu etiketleme istemcisi, Office'in bazen "Office Perpetual" olarak adlandırılan tek başına sürümlerini desteklemez.

[Azure Information Protection (AIP) birleşik etiketleme istemcisi](/azure/information-protection/rms-client/aip-clientv2) artık [bakım modundadır](https://techcommunity.microsoft.com/t5/security-compliance-and-identity/announcing-aip-unified-labeling-client-maintenance-mode-and/ba-p/3043613). Şu anda bu istemciyi Office uygulamalarında etiketleme için kullanıyorsanız, yerleşik etiketlemeye geçmenizi öneririz. Daha fazla bilgi için bkz. [Azure Information Protection (AIP) eklentisini Office uygulamaları için yerleşik etiketlemeye geçirme](sensitivity-labels-aip.md).

## <a name="support-for-sensitivity-label-capabilities-in-apps"></a>Uygulamalarda duyarlılık etiketi özellikleri desteği

Aşağıdaki tablolarda, Office uygulamalarında yerleşik olarak bulunan duyarlılık etiketleri için belirli özellikler sağlayan en düşük Office sürümü listelenir. Ya da etiket özelliği genel önizleme aşamasındaysa veya gelecek bir sürüm için gözden geçiriliyorsa:

- [Word, Excel ve PowerPoint için yetenekler tablosu](#sensitivity-label-capabilities-in-word-excel-and-powerpoint)
- [Outlook için Yetenekler tablosu](#sensitivity-label-capabilities-in-outlook)

Gelecek sürümler için planlanan yeni etiketleme özellikleri hakkında ayrıntılı bilgi için [Microsoft 365 yol haritasını](https://www.microsoft.com/microsoft-365/roadmap?filters=Microsoft%20Information%20Protection&searchterms=label) kullanın.

Office uygulamalarının yeni sürümleri farklı güncelleştirme kanalları için farklı zamanlarda kullanıma sunulur. Windows için yeni özellikleri daha önce Kurumsal Kanal yerine Geçerli Kanal veya Aylık Kurumsal Kanal'da Semi-Annual edineceksiniz. En düşük sürüm numaraları bir güncelleştirme kanalından diğerine de farklı olabilir. Daha fazla bilgi için bkz[. Microsoft 365 Uygulamaları güncelleştirme kanallarına genel bakış](/deployoffice/overview-update-channels) ve [Microsoft 365 Uygulamaları için Güncelleştirme geçmişi](/officeupdates/update-history-microsoft365-apps-by-date).

Özel önizlemedeki yeni özellikler tablolara dahil değildir, ancak kuruluşunuzu [Microsoft Bilgi Koruması özel önizleme programına](https://aka.ms/mip-preview) aday göstererek bu önizlemelere katılabilirsiniz.

iOS ve Android için Office için Office: Duyarlılık etiketleri [Office uygulamasında](https://www.microsoft.com/en-us/microsoft-365/blog/2020/02/19/new-office-app-android-ios-available/) yerleşik olarak bulunur.

> [!TIP]
> Tablolardaki en düşük sürümleri sahip olduğunuz sürümlerle karşılaştırdığınızda, baştaki sıfırları atlarken yayın sürümlerinin yaygın uygulamasını unutmayın.
> 
> Örneğin, 4.2128.0 sürümünüz var ve 4.7.1+ sürümünün en düşük sürüm olduğunu okuyorsunuz. Daha kolay karşılaştırma için 4.7.1 (başta sıfır yok) öğesini 4 olarak okuyun. **0007.1** (4 değil.**7000.1**). 4.2128.0 sürümünüz 4.0007.1'den yüksek olduğundan sürümünüz desteklenir.

### <a name="sensitivity-label-capabilities-in-word-excel-and-powerpoint"></a>Word, Excel ve PowerPoint'teki duyarlılık etiketi özellikleri

Listelenen sayılar, her özellik için gereken en düşük Office uygulaması sürümleridir. 

> [!NOTE]
> Windows ve Semi-Annual Enterprise Channel için desteklenen en düşük sürüm numaraları henüz yayımlanmamış olabilir. [Daha fazla bilgi edinin](/officeupdates/update-history-microsoft365-apps-by-date#supported-versions)
 
|Yeteneği |Windows |Mac |iOS |Android |Web |
|-----------|-------:|----|----|--------|----|
|[AIP eklentisi varsayılan olarak devre dışı bırakıldı](sensitivity-labels-aip.md#how-to-configure-newer-versions-of-office-to-enable-the-aip-add-in)| Önizleme: [Beta Kanalına](https://office.com/insider) Dağıtım | İlgili değil  | İlgili değil | İlgili değil| İlgili değil |
|[Etiketi el ile uygulama, değiştirme veya kaldırma](https://support.microsoft.com/en-us/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| Güncel Kanal: 1910+ <br /><br> Aylık Kurumsal Kanal: 1910+ <br /><br> Semi-Annual Enterprise Channel: 2002+ | 16.21+     | 2.21+ | 16.0.11231+ | [Evet - kabul et](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Çok dilli destek](create-sensitivity-labels.md#additional-label-settings-with-security--compliance-powershell)| Güncel Kanal: 1910+ <br /><br> Aylık Kurumsal Kanal: 1910+ <br /><br> Semi-Annual Enterprise Channel: 2002+ | 16.21+     | 2.21+ | 16.0.11231+ | İnceleme altında |
|Yeni belgelere [varsayılan etiket uygulama](sensitivity-labels.md#what-label-policies-can-do)                                         | Güncel Kanal: 1910+ <br /><br> Aylık Kurumsal Kanal: 1910+ <br /><br> Semi-Annual Enterprise Channel: 2002+ | 16.21+     | 2.21+ | 16.0.11231+ | [Evet - kabul et](sensitivity-labels-sharepoint-onedrive-files.md)                                                        |
|Mevcut belgelere [varsayılan etiket uygulama](sensitivity-labels.md#what-label-policies-can-do) | Güncel Kanal: 2208+ <br /><br> Aylık Kurumsal Kanal: 2207+  <br /><br> Semi-Annual Enterprise Channel: İnceleme altında | 16.63+ | İnceleme altında | İnceleme altında | [Evet - kabul et](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Etiketi değiştirmek için gerekçe gerektir](sensitivity-labels.md#what-label-policies-can-do)                     | Güncel Kanal: 1910+ <br /><br> Aylık Kurumsal Kanal: 1910+  <br /><br> Semi-Annual Enterprise Channel: 2002+ | 16.21+     | 2.21+ | 16.0.11231+ | [Evet - kabul et](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Özel yardım sayfasına yardım bağlantısı sağlama](sensitivity-labels.md#what-label-policies-can-do)                       | Güncel Kanal: 1910+ <br /><br> Aylık Kurumsal Kanal: 1910+ <br /><br> Semi-Annual Enterprise Channel: 2002+ | 16.21+     | 2.21+ | 16.0.11231+ | [Evet - kabul et](sensitivity-labels-sharepoint-onedrive-files.md) |
|[İçeriği işaretleme](sensitivity-labels.md#what-sensitivity-labels-can-do)                                              | Güncel Kanal: 1910+ <br /><br> Aylık Kurumsal Kanal: 1910+ <br /><br> Semi-Annual Enterprise Channel: 2002+ | 16.21+     | 2.21+ | 16.0.11231+ | [Evet - kabul et](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Değişkenlerle dinamik işaretler](#dynamic-markings-with-variables)                                              | Güncel Kanal: 2010+ <br /><br> Aylık Kurumsal Kanal: 2010+ <br /><br> Semi-Annual Enterprise Channel: 2102+ | 16.42+     | 2.42+ | 16.0.13328+ | [Evet - kabul et](sensitivity-labels-sharepoint-onedrive-files.md) |
|[İzinleri şimdi atayın](encryption-sensitivity-labels.md#assign-permissions-now)                                 | Güncel Kanal: 1910+ <br /><br> Aylık Kurumsal Kanal: 1910+ <br /><br> Semi-Annual Enterprise Channel: 2002+ | 16.21+     | 2.21+ | 16.0.11231+ | [Evet - kabul et](sensitivity-labels-sharepoint-onedrive-files.md) |
|[Kullanıcıların izin atamasına izin ver: <br /> - Kullanıcılardan özel izinler (kullanıcılar ve gruplar) isteme](encryption-sensitivity-labels.md#let-users-assign-permissions)                     |Güncel Kanal: 2004+ <br /><br> Aylık Kurumsal Kanal: 2004+ <br /><br> Semi-Annual Enterprise Channel: 2008+ | 16.35+   | İnceleme altında   | İnceleme altında         | İnceleme altında                                                        |
|[Kullanıcıların izin atamasına izin ver: <br /> - Kullanıcılardan özel izinler (kullanıcılar, gruplar ve kuruluşlar) isteme](encryption-sensitivity-labels.md#support-for-organization-wide-custom-permissions)                     |Önizleme: [Beta Kanalına](https://office.com/insider) Dağıtım  | İnceleme altında   | İnceleme altında   | İnceleme altında         | İnceleme altında                                                        |
|[Etiketle ilgili kullanıcı etkinliğini denetleme](#auditing-labeling-activities)                      | Güncel Kanal: 2011+ <br /><br> Aylık Kurumsal Kanal: 2011+ <br /><br> Semi-Annual Enterprise Channel: 2108+ | 16.43+ | 2.46+ | 16.0.13628+ | Evet |
|[Kullanıcıların e-postalarına ve belgelerine etiket uygulamasını gerektirme](#require-users-to-apply-a-label-to-their-email-and-documents)   | Güncel Kanal: 2101+ <br /><br> Aylık Kurumsal Kanal: 2101+ <br /><br> Semi-Annual Enterprise Channel: 2108+ | 16.45+         | 2.47+ | 16.0.13628+ | [Evet - kabul et](sensitivity-labels-sharepoint-onedrive-files.md)                                            
|[İçeriğe otomatik olarak bir hassasiyet etiketi uygulama](apply-sensitivity-label-automatically.md) <br /> - Hassas bilgi türlerini kullanma                    | Güncel Kanal: 2009+ <br /><br> Aylık Kurumsal Kanal: 2009+ <br /><br> Semi-Annual Enterprise Channel: 2102+ | 16.44+ | İnceleme altında | İnceleme altında | [Evet - kabul et](sensitivity-labels-sharepoint-onedrive-files.md) |
|[İçeriğe otomatik olarak bir hassasiyet etiketi uygulama](apply-sensitivity-label-automatically.md) <br /> - Eğitilebilir sınıflandırıcıları kullanma                    | Güncel Kanal: 2105+ <br /><br> Aylık Kurumsal Kanal: 2105+ <br /><br> Semi-Annual Enterprise Channel: 2108+ | 16.49+ | İnceleme altında | İnceleme altında | İnceleme altında |
|Etiketlenmiş ve şifrelenmiş belgeler için [birlikte yazma ve Otomatik Kaydetme](sensitivity-labels-coauthoring.md) desteği | Güncel Kanal: 2107+ <br /><br> Aylık Kurumsal Kanal: 2107+ <br /><br> Semi-Annual Enterprise Channel: 2202+ |  16.51+ | 2.58+ | 16.0.14931+  | [Evet - kabul et](sensitivity-labels-sharepoint-onedrive-files.md) |
|[PDF desteği](#pdf-support)| Güncel Kanal: 2208+ <br /><br> Aylık Kurumsal Kanal: 2209+ <br /><br> Semi-Annual Enterprise Channel: İnceleme altında|  İnceleme altında | İnceleme altında | İnceleme altında | İnceleme altında |
|[Duyarlılık çubuğu](#sensitivity-bar) ve [görüntü etiketi rengi](#label-colors) | Önizleme: [Beta Kanalına](https://office.com/insider) Dağıtım | İnceleme altında | İnceleme altında | İnceleme altında | İnceleme altında |

### <a name="sensitivity-label-capabilities-in-outlook"></a>Outlook'ta duyarlılık etiketi özellikleri

Listelenen sayılar, her özellik için gereken en düşük Office uygulaması sürümleridir. 

> [!NOTE]
> Windows ve Semi-Annual Enterprise Channel için desteklenen en düşük sürüm numaraları henüz yayımlanmamış olabilir. [Daha fazla bilgi edinin](/officeupdates/update-history-microsoft365-apps-by-date#supported-versions)

|Yeteneği |Windows için Outlook |Mac için Outlook |iOS üzerinde Outlook |Android üzerinde Outlook |Web üzerinde Outlook |
|-----------|-------------------:|----------------|---------------|-------------------|-------------------|
|[AIP eklentisi varsayılan olarak devre dışı bırakıldı](sensitivity-labels-aip.md#how-to-configure-newer-versions-of-office-to-enable-the-aip-add-in)| Önizleme: [Beta Kanalına](https://office.com/insider) Dağıtım | İlgili değil  | İlgili değil | İlgili değil| İlgili değil |
|[Etiketi el ile uygulama, değiştirme veya kaldırma](https://support.microsoft.com/en-us/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| Güncel Kanal: 1910+ <br /><br> Aylık Kurumsal Kanal: 1910+ <br /><br> Semi-Annual Enterprise Channel: 2002+ | 16.21+                 | 4.7.1+         | 4.0.39+           | Evet               |
|[Çok dilli destek](create-sensitivity-labels.md#additional-label-settings-with-security--compliance-powershell)| Güncel Kanal: 1910+ <br /><br> Aylık Kurumsal Kanal: 1910+ <br /><br> Semi-Annual Enterprise Channel: 2002+ | 16.21+ | 4.7.1+ | 4.0.39+ | Evet |
|[Varsayılan etiket uygulama](sensitivity-labels.md#what-label-policies-can-do)                                         | Güncel Kanal: 1910+ <br /><br> Aylık Kurumsal Kanal: 1910+ <br /><br> Semi-Annual Enterprise Channel: 2002+ | 16.21+                 | 4.7.1+         | 4.0.39+           | Evet               |
|[Etiketi değiştirmek için gerekçe gerektir](sensitivity-labels.md#what-label-policies-can-do)                     | Güncel Kanal: 1910+ <br /><br> Aylık Kurumsal Kanal: 1910+ <br /><br> Semi-Annual Enterprise Channel: 2002+ | 16.21+                 | 4.7.1+         | 4.0.39+           | Evet               |
|[Özel yardım sayfasına yardım bağlantısı sağlama](sensitivity-labels.md#what-label-policies-can-do)                       | Güncel Kanal: 1910+ <br /><br> Aylık Kurumsal Kanal: 1910+ <br /><br> Semi-Annual Enterprise Channel: 2002+ | 16.21+                 | 4.7.1+         | 4.0.39+           | Evet               |
|[İçeriği işaretleme](sensitivity-labels.md#what-sensitivity-labels-can-do)                                              | Güncel Kanal: 1910+ <br /><br> Aylık Kurumsal Kanal: 1910+ <br /><br> Semi-Annual Enterprise Channel: 2002+ | 16.21+                 | 4.7.1+         | 4.0.39+           | Evet               |
|[Değişkenlerle dinamik işaretler](#dynamic-markings-with-variables)                                              | Güncel Kanal: 1910+ <br /><br> Aylık Kurumsal Kanal: 1910+ <br /><br> Semi-Annual Enterprise Channel: 2002+ | 16.21+                 | 4.7.1+         | 4.0.39+           | Evet               |
|[İzinleri şimdi atayın](encryption-sensitivity-labels.md#assign-permissions-now)                                 | Güncel Kanal: 1910+ <br /><br> Aylık Kurumsal Kanal: 1910+ <br /><br> Semi-Annual Enterprise Channel: 2002+ | 16.21+                 | 4.7.1+         | 4.0.39+           | Evet               |
|[Kullanıcıların izin atamasına izin ver: <br /> - İletme](encryption-sensitivity-labels.md#let-users-assign-permissions)                     | Güncel Kanal: 1910+ <br /><br> Aylık Kurumsal Kanal: 1910+ <br /><br> Semi-Annual Enterprise Channel: 2002+ | 16.21+                 | 4.7.1+         | 4.0.39+           | Evet               |
|[Kullanıcıların izin atamasına izin ver: <br /> - Yalnızca Şifrele](encryption-sensitivity-labels.md#let-users-assign-permissions)  | Güncel Kanal: 2011+ <br /><br> Aylık Kurumsal Kanal: 2011+ <br /><br> Semi-Annual Enterprise Channel: 2108+ | 16.48+ <sup>\*</sup> | 4.2112.0+  | 4.2112.0+ | Evet |
|[Kullanıcıların e-postalarına ve belgelerine etiket uygulamasını gerektirme](#require-users-to-apply-a-label-to-their-email-and-documents)   | Güncel Kanal: 2101+ <br /><br> Aylık Kurumsal Kanal: 2101+ <br /><br> Semi-Annual Enterprise Channel: 2108+ | 16.43+ <sup>\*</sup>                    | 4.2111+            | 4.2111+                | Evet                |
|[Etiketle ilgili kullanıcı etkinliğini denetleme](#auditing-labeling-activities) | Güncel Kanal: 2011+ <br /><br> Aylık Kurumsal Kanal: 2011+ <br /><br> Semi-Annual Enterprise Channel: 2108+ | 16.51+ <sup>\*</sup> | 4.2126+ | 4.2126+ | Evet |
|[İçeriğe otomatik olarak bir hassasiyet etiketi uygulama](apply-sensitivity-label-automatically.md) <br /> - Hassas bilgi türlerini kullanma                    | Güncel Kanal: 2009+ <br /><br> Aylık Kurumsal Kanal: 2009+ <br /><br> Semi-Annual Enterprise Channel: 2102+ | 16.44+ <sup>\*</sup>                    | İnceleme altında           | İnceleme altında               | Evet |
|[İçeriğe otomatik olarak bir hassasiyet etiketi uygulama](apply-sensitivity-label-automatically.md) <br /> - Eğitilebilir sınıflandırıcıları kullanma                    | Güncel Kanal: 2105+ <br /><br> Aylık Kurumsal Kanal: 2105+ <br /><br> Semi-Annual Enterprise Channel: 2108+ | 16.49+ | İnceleme altında           | İnceleme altında               | Evet |
|[Varsayılan etiket ve zorunlu etiketleme için farklı ayarlar](#outlook-specific-options-for-default-label-and-mandatory-labeling)                    | Güncel Kanal: 2105+ <br /><br> Aylık Kurumsal Kanal: 2105+ <br /><br> Semi-Annual Enterprise Channel: 2108+ | 16.43+ <sup>\*</sup>                   | 4.2111+           | 4.2111+               | Evet |
|[PDF desteği](#pdf-support) | Önizleme: [Beta Kanalına](https://office.com/insider) Dağıtım|  İnceleme altında | İnceleme altında | İnceleme altında | İnceleme altında |
|[S/MIME koruması uygulama](#configure-a-label-to-apply-smime-protection-in-outlook) | Önizleme: [Beta Kanalı](https://office.com/insider) | 16.61+ <sup>\*</sup>                   | 4.2226+ | 4.2203+ | İnceleme altında |
|[Duyarlılık çubuğu](#sensitivity-bar) ve [görüntü etiketi rengi](#label-colors) | İnceleme altında |  İnceleme altında | İnceleme altında | İnceleme altında | İnceleme altında |

**Dipnot:**

<sup>\*</sup>[Yeni Mac için Outlook](https://support.microsoft.com/office/the-new-outlook-for-mac-6283be54-e74d-434e-babb-b70cefc77439) gerektirir

## <a name="office-built-in-labeling-client-and-the-azure-information-protection-client"></a>Office yerleşik etiketleme istemcisi ve Azure Information Protection istemcisi

Kullanıcıların Windows bilgisayarlarında [Azure Information Protection (AIP) istemcisi](/azure/information-protection/rms-client/aip-clientv2) yüklüyse, yerleşik etiketler [etiketlemeyi destekleyen](#labeling-client-for-desktop-apps) en son Windows Office uygulamaları için yeni varsayılan etiketlerdir. Yerleşik etiketler, AIP istemcisi tarafından kullanılan bir Office eklentisini kullanmadığından, daha fazla kararlılık ve daha iyi performans avantajına sahiptir. Ayrıca gelişmiş sınıflandırıcılar gibi en son özellikleri de destekler.

> [!NOTE]
> Windows bilgisayarlarda beklediğiniz etiketleme özelliklerini görmüyorsanız, Office güncelleştirme kanalınız için desteklenen en düşük sürümleri onaylamanıza rağmen, bunun nedeni Office'in eski sürümleri için [AIP eklentisini devre dışı bırakmanız](sensitivity-labels-aip.md#how-to-disable-the-aip-add-in-to-use-built-in-labeling-for-office-apps) gerekebilir.

AIP istemcisiyle etiketleme desteği hakkında daha fazla bilgi edinmek ve bu istemciyi yalnızca Office uygulamalarında devre dışı bırakma hakkında daha fazla bilgi edinmek için bkz. [Azure Information Protection (AIP) eklentisini Office uygulamaları için yerleşik etiketlemeye geçirme](sensitivity-labels-aip.md).

## <a name="if-you-need-to-turn-off-built-in-labeling-in-office-apps-on-windows"></a>Windows'da Office uygulamalarında yerleşik etiketlemeyi kapatmanız gerekiyorsa

Office'in yerleşik etiketleme istemcisi, duyarlılık etiketlerini ve duyarlılık etiketi ilke ayarlarını Microsoft Purview uyumluluk portalı indirir.

Office yerleşik etiketleme istemcisini kullanmak için, Microsoft Purview uyumluluk portalı kullanıcılara yayımlanmış bir veya daha fazla [etiket ilkeniz](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) ve [desteklenen bir Office sürümünüz](#support-for-sensitivity-label-capabilities-in-apps) olmalıdır.

Bu koşulların her ikisi de karşılanıyorsa ancak Windows Office uygulamalarında yerleşik etiketleri kapatmanız gerekiyorsa, aşağıdaki grup ilkesi ayarını kullanın:

1. **Kullanıcı Yapılandırması/Yönetim Şablonları/Microsoft Office 2016/Güvenlik Ayarları'na** gidin.

2. **Duyarlılık etiketlerini uygulamak ve 0 olarak görüntülemek için Office'te Duyarlılık özelliğini kullan'ı** ayarlayın.

Daha sonra bu yapılandırmayı geri almanız gerekiyorsa, değeri **1** olarak değiştirin. Şeritte **duyarlılık düğmesi beklendiği** gibi görüntülenmiyorsa bu değeri 1 olarak değiştirmeniz de gerekebilir. Örneğin, önceki bir yönetici bu etiketleme ayarını kapattı.
 
Grup ilkesi kullanarak veya [Microsoft 365 için Bulut İlkesi hizmetini](/DeployOffice/overview-office-cloud-policy-service) kullanarak bu ayarı dağıtın. Bu Office uygulamaları yeniden başlatıldığında bu ayar geçerlilik kazanır. 

Bu ayar Windows Office uygulamalarına özgü olduğundan, Windows'ta duyarlılık etiketlerini (Power BI gibi) veya diğer platformları (macOS, mobil cihazlar ve Web için Office) destekleyen diğer uygulamaları etkilemez. Kullanıcıların bir kısmının veya tümünün tüm uygulamalarda ve tüm platformlarda duyarlılık etiketlerini görmesini ve kullanmasını istemiyorsanız, bu kullanıcılara duyarlılık etiketi ilkesi atamayın.

## <a name="office-file-types-supported"></a>Desteklenen Office dosya türleri

Genel olarak, Word, Excel ve PowerPoint dosyaları için yerleşik etiketlemeye sahip Office uygulamaları Açık XML biçimini (.docx ve .xlsx gibi) destekler ancak Microsoft Office 97-2003 biçimini (.doc ve .xls gibi), Açık Belge Biçimi'ni (.odt ve .ods gibi) veya diğer biçimleri desteklemez. Yerleşik etiketleme için bir dosya türü desteklenmediğinde, **Duyarlılık** düğmesi Office uygulamasında kullanılamaz.

Bu hizmetler duyarlılık etiketleri için etkinleştirildiğinde SharePoint ve OneDrive için desteklenen belirli dosya türleri için bkz. [SharePoint ve OneDrive'da Office dosyaları için duyarlılık etiketlerini etkinleştirme](sensitivity-labels-sharepoint-onedrive-files.md#supported-file-types).

Azure Information Protection birleşik etiketleme istemcisi hem Open XML biçimini hem de Microsoft Office 97-2003 biçimini destekler. Daha fazla bilgi için, bu [istemcinin yönetici kılavuzundaki Azure Information Protection birleşik etiketleme istemcisi tarafından desteklenen dosya türleri](/azure/information-protection/rms-client/clientv2-admin-guide-file-types) bölümüne bakın.

Diğer etiketleme çözümleri için desteklenen dosya türlerine ilişkin belgelerine bakın.

## <a name="protection-templates-and-sensitivity-labels"></a>Koruma şablonları ve duyarlılık etiketleri

Microsoft Purview İleti Şifrelemesi için tanımladığınızlar gibi yönetici tanımlı [koruma şablonları](/azure/information-protection/configure-policy-templates), yerleşik etiketleme kullanırken Office uygulamalarında görünmez. Bu basitleştirilmiş deneyim, şifrelemenin etkinleştirildiği duyarlılık etiketlerine aynı ayarlar eklendiğinden bir koruma şablonu seçmenize gerek olmadığını yansıtır.

*EncryptionTemplateId* parametresiyle [New-Label](/powershell/module/exchange/new-label) cmdlet'ini kullandığınızda var olan bir şablonu duyarlılık etiketine dönüştürebilirsiniz.

## <a name="information-rights-management-irm-options-and-sensitivity-labels"></a>Bilgi Hakları Yönetimi (IRM) seçenekleri ve duyarlılık etiketleri

Şifreleme uygulamak için yapılandırdığınız duyarlılık etiketleri, kullanıcıların kendi şifreleme ayarlarını belirtme karmaşıklığını ortadan kaldırır. Birçok Office uygulamasında bu tek tek şifreleme ayarları, Bilgi Hakları Yönetimi (IRM) seçenekleri kullanılarak kullanıcılar tarafından el ile yapılandırılmaya devam edebilir. Örneğin, Windows uygulamaları için:

- Belge için: **Dosya** > **Bilgileri** > **Belgeyi** >  Koru **Erişimi Kısıtla**
- e-posta için: **Seçenekler** sekmesinden **Şifrele** > 
  
Kullanıcılar başlangıçta bir belgeyi veya e-postayı etiketlediğinde, etiket yapılandırma ayarlarınızı kendi şifreleme ayarlarıyla geçersiz kılabilir. Örneğin:

- Kullanıcı bir belgeye **Gizli \ Tüm Çalışanlar** etiketini uygular ve bu etiket kuruluştaki tüm kullanıcılar için şifreleme ayarlarını uygulamak üzere yapılandırılır. Daha sonra bu kullanıcı, kuruluşunuzun dışındaki bir kullanıcıya erişimi kısıtlamak için IRM ayarlarını el ile yapılandırıyor. Sonuç, **Gizli \ Tüm Çalışanlar** etiketli ve şifrelenmiş bir belgedir, ancak kuruluşunuzdaki kullanıcılar belgeyi beklendiği gibi açamaz.

- Kullanıcı bir e-postaya **Yalnızca Gizli \ Alıcılar** etiketini uygular ve bu e-posta **İletme** şifreleme ayarını uygulayacak şekilde yapılandırılır. Outlook uygulamasında bu kullanıcı daha sonra Yalnızca Şifrele için IRM ayarını el ile seçer. Sonuç olarak e-posta şifrelenmiş olarak kalır ancak **Gizli \ Yalnızca Alıcılar** etiketine sahip olmasına rağmen alıcılar tarafından iletilebilir.
    
    Özel durum olarak, Web üzerinde Outlook için **Şifreleme** menüsündeki seçenekler kullanıcının seçili durumdaki etiket şifreleme uyguladığında seçemez.

- Kullanıcı **belgeye Genel** etiketini uygular ve bu etiket şifreleme uygulamak için yapılandırılmamış. Daha sonra bu kullanıcı, belgeye erişimi kısıtlamak için IRM ayarlarını el ile yapılandırıyor. Sonuç, **Genel** etiketli ancak bazı kullanıcıların beklendiği gibi açamaması için şifreleme uygulayan bir belgedir.

Belge veya e-posta zaten etiketlenmişse, içerik henüz şifrelenmemişse veya [kullanım hakkı](/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions) Dışarı Aktar veya Tam Denetim'e sahipse, kullanıcı bu eylemlerden herhangi birini yapabilir. 

Anlamlı raporlama ile daha tutarlı bir etiket deneyimi için, kullanıcıların belgeleri ve e-postaları korumak için yalnızca etiketleri uygulaması için uygun etiketler ve yönergeler sağlayın. Örneğin:

- Kullanıcıların kendi izinlerini ataması gereken özel durumlar için, [kullanıcıların kendi izinlerini atamasına izin veren](encryption-sensitivity-labels.md#let-users-assign-permissions) etiketler sağlayın. 

- Kullanıcıların şifreleme uygulayan bir etiketi seçtikten sonra şifrelemeyi el ile kaldırması yerine, kullanıcılar aynı sınıflandırmaya sahip bir etikete ihtiyaç duyduğunda ancak şifreleme olmadığında alt etiket alternatifi sağlar. Gibi:
    - **Gizli \ Tüm Çalışanlar**
    - **Gizli \ Herkes (şifreleme yok)**

- Kullanıcıların bunları seçmesini önlemek için IRM ayarlarını devre dışı bırakmayı göz önünde bulundurun:
    - Windows için Outlook: 
        - *DisableDNF* ve *DisableEO* kayıt defteri anahtarları `DWORD:00000001``HKEY_CURRENT_USER\Software\Microsoft\Office\16.0\Common\DRM`
        - **Şifrele düğmesi için varsayılan şifreleme seçeneğini yapılandır grup ilkesi ayarının** yapılandırılmadığından emin olun
    - Mac için Outlook: 
        - Mac için Outlook [için tercihleri ayarlama](/DeployOffice/mac/preferences-outlook) bölümünde belgelenen *DisableEncryptOnly* ve *DisableDoNotForward* güvenlik ayarları
    - Web üzerinde Outlook: 
        - [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) için *BasitleştirilmişClientAccessDoNotForwardDisabled* ve *SimplifiedClientAccessEncryptOnlyDisabled* parametreleri belgelendi
    - iOS ve Android için Outlook: Bu uygulamalar, etiketleri olmayan şifreleme uygulayan kullanıcıları desteklemez, bu nedenle devre dışı bırakılamaz.

> [!NOTE]
> Kullanıcılar SharePoint veya OneDrive'da depolanan etiketli bir belgeden şifrelemeyi el ile kaldırırsa ve [SharePoint ve OneDrive'daki Office dosyaları için duyarlılık etiketlerini etkinleştirdiyseniz](sensitivity-labels-sharepoint-onedrive-files.md), belgeye bir sonraki erişildiğinde veya indirildiğinde etiket şifrelemesi otomatik olarak geri yüklenir. 

## <a name="encryption-based-label-matching-for-documents"></a>Belgeler için şifreleme tabanlı etiket eşleştirme

Bir belge yönetici tanımlı izinlerle şifrelendiğinde, şifreleme ilkesi belgeye eklenir. Bu, etiketlemeden bağımsız olarak gerçekleşir. Örneğin, bir Office eki bir e-posta iletisinden şifrelemeyi devraldığında veya bir kullanıcı Kendi Office uygulamasında Bilgi Hakları Yönetimi (IRM) kullanarak bir koruma şablonu uyguladığında. Kiracıdaki bir duyarlılık etiketi aynı şifreleme ilkesiyle eşleşiyorsa, Office uygulamaları bu eşleşen etiketi belgeye otomatik olarak atar.

Bu senaryoda, eşleşen duyarlılık etiketi etiketlenmemiş bir belgeyi etiketleyebilir ve şifreleme uygulamayan mevcut bir etiketi değiştirebilir. Örneğin, **Genel** etiketi **Gizli / Tüm Çalışanlar** ile değiştirilir. Belge daha önce etiketlenmemişse ve AIP Eklentisini kullanmıyorsanız, eşleşen etiketten içerik işaretleri otomatik olarak uygulanmaz.

Bu senaryo, eski şifreleme çözümlerini koruma şablonlarından şifreleme uygulayan duyarlılık etiketlerine taşımaya yardımcı olur.

Ancak, bu davranışı alıcı tarafından açıldığında e-posta ekleri için bir etiketleme senaryosuyla da görürsünüz. Örneğin:

1. Kullanıcı bir e-posta oluşturur ve şifrelenmemiş bir Office belgesi ekler ve ardından e-postaya bir etiket uygular.
    
    Etiket, İletme veya Encrypt-Only seçenekleri yerine yönetici tarafından ayarlanan izinlerle şifreleme uygular. Örneğin, etiket yapılandırması için yönetici **Şimdi izin ata'yı** seçer ve tüm çalışanların okuma erişimine sahip olduğunu belirtir.

2. E-posta gönderildiğinde, [ek otomatik olarak şifrelemeyi devralır, ancak etiketi devralmaz](encryption-sensitivity-labels.md#email-attachments-for-encrypted-email-messages).

3. Aynı kiracıdaki bir alıcı şifrelenmiş belgeyi açtığında, belge için yönetici tanımlı izinler için eşleşen bir etiket otomatik olarak görüntülenir ve belge kaydedilirse kalıcı olur.
    
    Etkinlik Gezgini'nde görüntülenen bir denetim olayı olarak, bu kullanıcı e-posta göndereni değil etiketi uyguladı.

Şifreleme tabanlı etiket eşleştirmesi yalnızca kiracı içinde, yönetici tanımlı izinler için çalışır ve eşleşen duyarlılık etiketi belgeyi açan kullanıcıya yayımlanmalıdır. Belge kaydedilirse eşleşen etiket kalır.

## <a name="sensitivity-label-compatibility"></a>Duyarlılık etiketi uyumluluğu

**RMS kullanan uygulamalarla**: Duyarlılık etiketlerini desteklemeyen [, RMS kullanan bir uygulamada](/azure/information-protection/requirements-applications#rms-enlightened-applications) etiketlenmiş ve şifrelenmiş bir belgeyi veya e-postayı açarsanız, uygulama şifreleme ve hak yönetimini zorunlu kılmaya devam eder.

**Azure Information Protection istemcisiyle**: Belgelere ve e-postalara uyguladığınız duyarlılık etiketlerini, Azure Information Protection istemcisini kullanarak office yerleşik etiketleme istemcisiyle görüntüleyebilir ve değiştirebilirsiniz.

**Office'in diğer sürümleriyle**: Yetkili kullanıcılar etiketli belgeleri ve e-postaları Office'in diğer sürümlerinde açabilir. Ancak, etiketi yalnızca desteklenen Office sürümlerinde veya Azure Information Protection istemcisini kullanarak görüntüleyebilir veya değiştirebilirsiniz. Desteklenen Office uygulaması sürümleri [önceki bölümde](#support-for-sensitivity-label-capabilities-in-apps) listelenmiştir.

## <a name="support-for-sharepoint-and-onedrive-files-protected-by-sensitivity-labels"></a>Duyarlılık etiketleriyle korunan SharePoint ve OneDrive dosyaları desteği

SharePoint veya OneDrive'daki belgeler için office yerleşik etiketleme istemcisini Web üzerinde Office kullanmak [için, SharePoint ve OneDrive'da Office dosyaları için duyarlılık etiketlerini etkinleştirdiğinizden](sensitivity-labels-sharepoint-onedrive-files.md) emin olun.

## <a name="support-for-external-users-and-labeled-content"></a>Dış kullanıcılar ve etiketli içerik desteği

Bir belgeyi veya e-postayı etiketlediğinizde, etiket kiracınızı ve etiket GUID'sini içeren meta veriler olarak depolanır. Etiketlenmiş bir belge veya e-posta duyarlılık etiketlerini destekleyen bir Office uygulaması tarafından açıldığında, bu meta veriler okunur ve yalnızca kullanıcı aynı kiracıya aitse etiket kendi uygulamasında görüntülenir. Örneğin, Word, PowerPoint ve Excel için yerleşik etiketleme için etiket adı durum çubuğunda görüntülenir. 

Başka bir deyişle, belgeleri farklı etiket adları kullanan başka bir kuruluşla paylaşırsanız, her kuruluş belgeye kendi etiketlerini uygulayabilir ve bunları görebilir. Ancak, uygulanan bir etiketten aşağıdaki öğeler kuruluşunuzun dışındaki kullanıcılar tarafından görülebilir:

- İçerik işaretleri. Bir etiket üst bilgi, alt bilgi veya filigran uyguladığında, bunlar doğrudan içeriğe eklenir ve birisi değiştirene veya silene kadar görünür durumda kalır.

- Şifreleme uygulayan bir etiketten temel alınan koruma şablonunun adı ve açıklaması. Bu bilgiler, belgeyi açma yetkisi olan kişiler ve bu belge için kullanım hakları hakkında bilgi sağlamak için belgenin en üstündeki ileti çubuğunda görüntülenir.

### <a name="sharing-encrypted-documents-with-external-users"></a>Şifrelenmiş belgeleri dış kullanıcılarla paylaşma

Kendi kuruluşunuzdaki kullanıcılara erişimi kısıtlayabilirsiniz ancak erişimi Azure Active Directory'de (Azure AD) hesabı olan diğer tüm kullanıcılara da genişletebilirsiniz. Varsayılan olarak, bu dış kullanıcıların kimlikleri ek yapılandırma olmadan doğrulanır. Ancak, [dış kimlikler Azure AD kiracılar arası erişim ayarları](/azure/active-directory/external-identities/cross-tenant-access-overview) ve [Koşullu Erişim](/azure/active-directory/conditional-access/overview) için ek yapılandırma gerekebilir. 

Dış kullanıcıların Azure AD içinde bir hesabı yoksa, kiracınızdaki konuk hesaplarını kullanarak kimlik doğrulaması yapabilir. Bu konuk hesapları, SharePoint ve OneDrive'da [Office dosyaları için duyarlılık etiketlerini etkinleştirdiğinizde SharePoint veya OneDrive'daki](sensitivity-labels-sharepoint-onedrive-files.md) paylaşılan belgelere erişmek için de kullanılabilir.

İsteğe bağlı Azure AD özellikleri ve kimlik doğrulama gereksinimleri için konuk hesaplarını kullanma hakkında daha fazla bilgi için bkz. [şifreleme içeriği için Azure AD yapılandırması](encryption-azure-ad-configuration.md).

Tüm Office uygulamaları ve [RMS kullanan diğer uygulamalar](/azure/information-protection/requirements-applications#rms-enlightened-applications) , kullanıcı başarıyla kimlik doğrulamasından geçtikten sonra şifrelenmiş belgeleri açabilir. 

## <a name="when-office-apps-apply-content-marking-and-encryption"></a>Office uygulamaları içerik işaretleme ve şifreleme uyguladığında

Office uygulamaları, kullandığınız uygulamaya bağlı olarak duyarlılık etiketiyle içerik işaretleme ve şifreleme işlemlerini farklı şekilde uygular.

| Uygulama | İçerik işaretleme | Şifreleme |
| --- | --- | --- |
| Tüm platformlarda Word, Excel, PowerPoint | Hemen | Hemen |
| PC ve Mac için Outlook | Exchange Online e-postayı gönderdikten sonra | Hemen |
| Web üzerinde Outlook, iOS ve Android | Exchange Online e-postayı gönderdikten sonra | Exchange Online e-postayı gönderdikten sonra |
|

Office uygulamalarının dışındaki dosyalara duyarlılık etiketleri uygulayan çözümler, dosyaya etiketleme meta verileri uygulayarak bunu yapar. Bu senaryoda, etiketin yapılandırmasından içerik işaretleme dosyaya eklenmez, ancak şifreleme uygulanır. 

Bu dosyalar bir Office masaüstü uygulamasında açıldığında, dosya ilk kaydedildiğinde içerik işaretleri Azure Information Protection birleşik etiketleme istemcisi tarafından otomatik olarak uygulanır. Masaüstü, mobil veya web uygulamaları için yerleşik etiketleme kullandığınızda içerik işaretleri otomatik olarak uygulanmaz.

Office uygulamalarının dışında duyarlılık etiketi uygulamayı içeren senaryolar şunlardır:

- Azure Information Protection birleşik etiketleme istemcisinden tarayıcı, Dosya Gezgini ve PowerShell 

- SharePoint ve OneDrive için otomatik etiketleme ilkeleri

- Power BI'dan etiketlenmiş ve şifrelenmiş veriler dışarı aktarıldı

- Bulut Uygulamaları için Microsoft Defender

Bu senaryolarda, yerleşik etiketlemesi olan bir kullanıcı, office uygulamalarını kullanarak geçerli etiketi geçici olarak kaldırarak veya değiştirerek ve özgün etiketi yeniden uygulayarak etiketin içerik işaretlerini uygulayabilir.

### <a name="dynamic-markings-with-variables"></a>Değişkenlerle dinamik işaretler

> [!IMPORTANT]
> Office uygulamalarınız bu özelliği desteklemiyorsa, işaretleri değişkenleri çözümlemek yerine etiket yapılandırmasında belirtilen özgün metin olarak uygular.
> 
> Azure Information Protection birleşik etiketleme istemcisi dinamik işaretlemeleri destekler. Office'te yerleşik olarak bulunan etiketleme için desteklenen en düşük [sürümler](#support-for-sensitivity-label-capabilities-in-apps) için bu sayfadaki özellikler bölümündeki tablolara bakın.

İçerik işaretleri için duyarlılık etiketi yapılandırırken, üst bilgi, alt bilgi veya filigranınız için metin dizesinde aşağıdaki değişkenleri kullanabilirsiniz:

| Değişken | Açıklama | Etiket uygulandığında örnek |
| -------- | ----------- | ------- |
| `${Item.Label}` | Uygulanan etiketin etiket görünen adı | **Genel**|
| `${Item.Name}` | Etiketlenen içeriğin dosya adı veya e-posta konusu | **Sales.docx** |
| `${Item.Location}` | Etiketlenen belgenin yolu ve dosya adı veya etiketlenen bir e-postanın e-posta konusu | **\\\Sales\2020\Q3\Report.docx**|
| `${User.Name}` | Etiketi uygulayan kullanıcının görünen adı | **Richard Simone** |
| `${User.PrincipalName}` | Etiketi uygulayan kullanıcının Azure AD kullanıcı asıl adı (UPN) | **rsimone\@contoso.com** |
| `${Event.DateTime}` | İçeriğin etiketlendiği tarih ve saat, microsoft 365 uygulamalarında etiketi uygulayan kullanıcının yerel saat diliminde veya Office Online ve otomatik etiketleme ilkeleri için UTC (Eşgüdümlü Evrensel Saat) | **10.08.2020 13:30** |

> [!NOTE]
> Bu değişkenlerin söz dizimi büyük/küçük harfe duyarlıdır.

#### <a name="setting-different-visual-markings-for-word-excel-powerpoint-and-outlook"></a>Word, Excel, PowerPoint ve Outlook için farklı görsel işaretler ayarlama

Ek değişken olarak, metin dizesinde "If.App" değişken deyimini kullanarak Office uygulama türü başına görsel işaretler yapılandırabilir ve **Word**, **Excel**, **PowerPoint** veya **Outlook** değerlerini kullanarak uygulama türünü tanımlayabilirsiniz. Ayrıca, aynı If.App deyiminde birden fazla değer belirtmek istiyorsanız bu değerleri kısaltabilirsiniz.

Aşağıdaki sözdizimini kullanın:

```
${If.App.<application type>}<your visual markings text> ${If.End}
```

Diğer dinamik görsel işaretlerinde olduğu gibi söz dizimi büyük/küçük harfe duyarlıdır ve her uygulama türünün (WEPO) kısaltmalarını içerir.

Örnekler:

- **Yalnızca Word belgeleri için üst bilgi metnini ayarlayın:**

    `${If.App.Word}This Word document is sensitive ${If.End}`

    Yalnızca Word belge üst bilgilerinde, etiket "Bu Word belgesi hassas" üst bilgi metnini uygular. Diğer Office uygulamalarına üst bilgi metni uygulanmaz.

- **Word, Excel ve Outlook için alt bilgi metni ve PowerPoint için farklı alt bilgi metni ayarlayın:**

    `${If.App.WXO}This content is confidential. ${If.End}${If.App.PowerPoint}This presentation is confidential. ${If.End}`

    Word, Excel ve Outlook'ta etiket, "Bu içerik gizlidir" alt bilgi metnini uygular. PowerPoint'te etiket, "Bu sunu gizlidir" alt bilgi metnini uygular.

- **Word ve PowerPoint için belirli bir filigran metni ayarlayın ve ardından Word, Excel ve PowerPoint için filigran metni ayarlayın:**

    `${If.App.WP}This content is ${If.End}Confidential`

    Word ve PowerPoint'te etiket, "Bu içerik Gizlidir" filigran metnini uygular. Excel'de, etiket "Gizli" filigran metnini uygular. Outlook'ta, görsel işaretler olarak filigranlar Outlook için desteklenmediğinden etiket filigran metni uygulamaz.

## <a name="require-users-to-apply-a-label-to-their-email-and-documents"></a>Kullanıcıların e-postalarına ve belgelerine etiket uygulamasını gerektirme

> [!IMPORTANT]
> 
> [Azure Information Protection birleşik etiketleme istemcisi](/azure/information-protection/rms-client/install-unifiedlabelingclient-app), zorunlu etiketleme olarak da bilinen bu yapılandırmayı destekler. Office uygulamalarında yerleşik olarak bulunan etiketleme için, en düşük [sürümler](#support-for-sensitivity-label-capabilities-in-apps) için bu sayfadaki özellikler bölümündeki tablolara bakın.
>
> Belgeler için zorunlu etiketlemeyi kullanmak ancak e-postaları kullanmak için, sonraki bölümde Outlook'a özgü seçeneklerin nasıl yapılandırıldığını açıklayan yönergelere bakın.
> 
> Power BI için zorunlu etiketleme kullanmak için bkz. [Power BI için zorunlu etiket ilkesi](/power-bi/admin/service-security-sensitivity-label-mandatory-label-policy).

**Kullanıcıların e-postalarına ve belgelerine etiket uygulamasını gerektir** ilke ayarı seçildiğinde, ilkeye atanan kullanıcıların aşağıdaki senaryolar altında bir duyarlılık etiketi seçip uygulaması gerekir:

- Azure Information Protection birleşik etiketleme istemcisi için:
    - Belgeler için (Word, Excel, PowerPoint): Etiketsiz bir belge kaydedildiğinde veya kullanıcılar belgeyi kapattığında.
    - E-postalar için (Outlook): Kullanıcılar etiketsiz bir ileti gönderdiği sırada.

- Office uygulamalarında yerleşik etiketleme için:
    - Belgeler için (Word, Excel, PowerPoint): Etiketsiz bir belge açıldığında veya kaydedildiğinde.
    - E-postalar için (Outlook): Kullanıcılar etiketsiz bir e-posta iletisi gönderirken.

Yerleşik etiketleme için ek bilgiler:

- Etiketsiz bir belgeyi açtıkları için kullanıcılardan duyarlılık etiketi eklemeleri istendiğinde, etiket ekleyebilir veya belgeyi salt okunur modda açmayı seçebilirler.

- Zorunlu etiketleme etkin olduğunda, kullanıcılar belgelerden duyarlılık etiketlerini kaldıramaz, ancak var olan bir etiketi değiştirebilir.

- Zorunlu etiketleme etkin olduğunda, belge etiketlendiğinde veya şifrelendiğinde PDF'ye yazdır seçeneği kullanılamaz. Daha fazla bilgi için bu sayfadaki [PDF desteği](#pdf-support) bölümüne bakın.

Bu ayarın ne zaman kullanılacağı hakkında yönergeler için [ilke ayarları](sensitivity-labels.md#what-label-policies-can-do) hakkındaki bilgilere bakın.

> [!NOTE]
> Zorunlu etiketlemeye ek olarak belgeler ve e-postalar için varsayılan etiket ilkesi ayarını kullanıyorsanız: 
>
> Varsayılan etiket her zaman zorunlu etiketlemeye göre önceliklidir. Ancak belgeler için, Azure Information Protection birleşik etiketleme istemcisi tüm etiketlenmemiş belgelere varsayılan etiketi uygularken, yerleşik etiketleme varsayılan etiketi etiketlenmemiş mevcut belgelere değil, yeni belgelere uygular. Davranıştaki bu fark, varsayılan etiket ayarıyla zorunlu etiketleme kullandığınızda, yerleşik etiketleme kullandıklarında kullanıcılardan büyük olasılıkla Azure Information Protection birleşik etiketleme istemcisini kullandıklarından daha sık duyarlılık etiketi uygulamalarının isteneceği anlamına gelir.
> 
> Şimdi kullanıma sunulacak: Yerleşik etiketleme kullanan ve mevcut belgeler için varsayılan etiketi destekleyen Office uygulamaları. Ayrıntılar için Word, Excel ve [PowerPoint'in yetenekler tablosuna](sensitivity-labels-office-apps.md#sensitivity-label-capabilities-in-word-excel-and-powerpoint) bakın.

## <a name="outlook-specific-options-for-default-label-and-mandatory-labeling"></a>Varsayılan etiket ve zorunlu etiketleme için Outlook'a özgü seçenekler

Yerleşik etiketleme için, bu sayfadaki [Outlook'un yetenekler tablosunu](#sensitivity-label-capabilities-in-outlook) ve **varsayılan etiket ve zorunlu etiketleme için Farklı ayarlar** satırını kullanarak Outlook'un bu özellikleri destekleyen en düşük sürümlerini belirleyin. Azure Information Protection birleşik etiketleme istemcisinin tüm sürümleri bu Outlook'a özgü seçenekleri destekler.

Outlook uygulaması belgeler için varsayılan etiket ayarından farklı bir varsayılan etiket ayarını desteklediğinde:

- Microsoft Purview uyumluluk portalı etiket ilkesi yapılandırmasında, **E-postalara varsayılan etiket uygula** sayfasında: Etiketlenmemiş tüm e-postalara uygulanacak veya varsayılan etiket olmayan duyarlılık etiketi seçiminizi belirtebilirsiniz. Bu ayar, yapılandırmanın önceki Belgeler **için İlke ayarları** sayfasındaki **Bu etiketi varsayılan olarak belgelere uygula** ayarından bağımsızdır.

Outlook uygulaması, belgeler için varsayılan etiket ayarından farklı bir varsayılan etiket ayarını desteklemediğinde: Outlook her zaman etiket ilkesi yapılandırmasının **Belgeler için ilke ayarları** sayfasındaki **Belgelere varsayılan olarak bu etiketi uygula** için belirttiğiniz değeri kullanır.

Outlook uygulaması zorunlu etiketlemeyi kapatmayı desteklediğinde:

- Microsoft Purview uyumluluk portalı etiket ilkesi yapılandırmasında, **İlke ayarları** sayfasında: **Kullanıcıların e-postalarına veya belgelerine etiket uygulamasını gerektir'i** seçin. Ardından **İleri İleri'yi** >  seçin ve **Kullanıcıların e-postalarına etiket uygulamasını gerektir** onay kutusunu temizleyin. Zorunlu etiketlemenin e-postalara ve belgelere uygulanmasını istiyorsanız onay kutusunu seçili tutun.

Outlook uygulaması zorunlu etiketlemeyi kapatmayı desteklemediğinde: **Kullanıcıların e-postalarına veya belgelerine ilke ayarı olarak etiket uygulamasını gerektir'i** seçerseniz, Outlook her zaman kullanıcılardan etiketlenmemiş e-postalar için etiket seçmelerini ister.

> [!NOTE]
> [Set-LabelPolicy](/powershell/module/exchange/set-labelpolicy) veya [New-LabelPolicy](/powershell/module/exchange/new-labelpolicy) cmdlet'lerini kullanarak **PowerShell gelişmiş ayarlarını OutlookDefaultLabel** ve **DisableMandatoryInOutlook** yapılandırdıysanız:
> 
> Bu PowerShell ayarları için seçtiğiniz değerler Microsoft Purview uyumluluk portalı etiket ilkesi yapılandırmasına yansıtılır ve bu ayarlar otomatik olarak bu ayarları destekleyen Outlook uygulamaları için çalışır. Diğer PowerShell gelişmiş ayarları yalnızca Azure Information Protection birleşik etiketleme istemcisi için desteklenmektedir.

## <a name="configure-a-label-to-apply-smime-protection-in-outlook"></a>Outlook'ta S/MIME koruması uygulamak için etiket yapılandırma

> [!NOTE]
> Bu özellik şu anda yerleşik etiketleme için ve platformlar genelinde yayının çeşitli aşamalarında kullanıma sunulmuştur. Bu sayfadaki Outlook [için capabilities tablosunu](#sensitivity-label-capabilities-in-outlook) ve **S/MIME koruması uygula** satırını kullanarak Outlook'un bu özelliği destekleyen en düşük sürümlerini belirleyin.
> 
> Bir etiketi S/MIME koruması uygulamak üzere yapılandırıyorsanız ancak Windows üzerinde Outlook henüz bunu desteklemiyorsa etiket görüntülenmeye devam eder ve uygulanabilir, ancak S/MIME ayarları yoksayılır. Exchange otomatik etiketleme ilkeleri için bu etiketi seçemezsiniz.

Bu yapılandırma Microsoft Purview uyumluluk portalı kullanılamaz. [Güvenlik & Uyumluluğu PowerShell'e bağlandıktan sonra PowerShell](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell) gelişmiş ayarlarını [Etiket Ayarla](/powershell/module/exchange/set-label) veya [Yeni Etiket](/powershell/module/exchange/new-label) cmd ile kullanmanız gerekir.

Bu ayarları yalnızca çalışan bir [S/MIME dağıtımınız](/microsoft-365/security/office-365-security/s-mime-for-message-signing-and-encryption) varsa ve etiketin [Azure Information Protection Rights Management şifrelemesini kullanan varsayılan koruma](encryption-sensitivity-labels.md) yerine e-postalar için bu koruma yöntemini otomatik olarak uygulamasını istiyorsanız kullanın. Sonuçta elde edilen koruma, kullanıcının Outlook'tan S/MIME seçeneklerini el ile seçmesi ile aynı olacaktır.

|Yapılandırma  |Gelişmiş ayar anahtarı/değeri |
|---------|---------|
|**S/MIME dijital imzası** | SMimeSign="True" |
|**S/MIME şifrelemesi** | SMimeEncrypt="True"|

Bu ayarlar için yapılandırdığınız etiketin uyumluluk portalında şifreleme için yapılandırılması gerekmez. Ancak varsa, S/MIME koruması yalnızca Outlook'ta Rights Management şifrelemesinin yerini alır. Diğer uygulamalar için etiket, Microsoft Purview uyumluluk portalı belirtilen şifreleme ayarlarını uygular.

Duyarlılık etiketi **GUID'sinin 8faca7b8-8d20-48a3-8ea2-0f96310a848e** olduğu örnek PowerShell komutları:

```PowerShell
Set-Label -Identity "8faca7b8-8d20-48a3-8ea2-0f96310a848e" -AdvancedSettings @{SMimeSign="True"}

Set-Label -Identity "8faca7b8-8d20-48a3-8ea2-0f96310a848e" -AdvancedSettings @{SMimeEncrypt="True"}
```

PowerShell gelişmiş ayarlarını belirtme konusunda daha fazla yardım için bkz. [Gelişmiş ayarları belirtmek için PowerShell ipuçları](create-sensitivity-labels.md#powershell-tips-for-specifying-the-advanced-settings).

## <a name="pdf-support"></a>PDF desteği

Yerleşik etiketleme için, desteklenen en düşük sürümleri belirlemek için bu sayfadaki [özellikler](#support-for-sensitivity-label-capabilities-in-apps) bölümündeki tabloları kullanın. Azure Information Protection birleşik etiketleme istemcisi Office uygulamalarında PDF'yi desteklemez.

Word, Excel ve PowerPoint, bir Office belgesini PDF belgesine dönüştürmek için aşağıdaki yöntemleri destekler:

- Dosya > PDF > Farklı Kaydet 
- Pdf > Dışarı Aktarma > Dosya
- Pdf > Kopya Gönderme > Paylaş

Bu eylem, [Dosya ve sayfa etkinlikleri](search-the-audit-log-in-security-and-compliance.md#file-and-page-activities) denetim grubundan **Yeniden Adlandırılmış dosya** denetim olayıyla günlüğe kaydedilir. Uyumluluk portalındaki denetim arama sonuçlarında, **etkinlik alanı için** **SensitivityLabeledFileRenamed** değerini görüntüleyen bu denetim olayının ayrıntılarını görürsünüz.

PDF oluşturulduğunda, herhangi bir içerik işareti ve şifreleme içeren etiketi devralır. Şifrelenmiş PDF'ler Windows veya Mac'te Microsoft Edge ile açılabilir. Daha fazla bilgi ve alternatif [okuyucular için bkz. Korumalı PDF'ler için hangi PDF okuyucular desteklenir?](/azure/information-protection/rms-client/protected-pdf-readers#viewing-protected-pdfs-in-microsoft-edge-on-windows-or-mac)

Outlook şu anda etiketli bir iletiden şifreleme devralan PDF eklerini desteklememektedir. Ancak, Outlook artık daha sonra açıklandığı gibi kullanıcıların PDF'ye yazdırmalarını uyarı veya engellemeyi destekliyor.

PDF senaryoları desteklenmez:

- PDF'ye yazdır
    
    Kullanıcılar bu seçeneği belirlerse, belgenin veya e-postanın etiketin ve şifrelemenin (uygulandıysa) korumasını kaybedeceği ve devam etmek için onaylamaları gerektiği konusunda uyarılırlar. Duyarlılık etiketi ilkeniz bir etiketi kaldırmak veya sınıflandırmasını düşürmek için gerekçe gerektiriyorsa, bu istemi görür.
    
    Bu seçenek duyarlılık etiketini kaldırdığından, zorunlu etiketleme kullanıyorsanız bu seçenek kullanıcılar tarafından kullanılamaz. Bu yapılandırma, kullanıcıların e-postalarına ve belgelerine etiket uygulamasını gerektiren duyarlılık etiketi ilkesi ayarını ifade eder.

- PDF/A biçimi ve şifrelemesi
    
     Etiket şifreleme uyguladığında uzun süreli arşivleme için tasarlanan bu PDF biçimi desteklenmez ve kullanıcıların Office belgelerini PDF'ye dönüştürmesini engeller. Yapılandırma bilgileri için[, ISO 19005-1 (PDF/A) ile PDF uyumluluğunu zorunlu kılma](https://admx.help/?Category=Office2016&Policy=office16.Office.Microsoft.Policies.Windows::L_EnforcePDFcompliancewithISO190051PDFA) için grup ilkesi belgelerine bakın.
    
- Parola koruması ve şifreleme
    
    **Belgenin** etiketi şifreleme uyguladığında Dosya  > **Bilgileri** > **Belgeyi** > **Parolayla Şifrele** seçeneğinin kullanılması desteklenmez. Bu senaryoda parolayla şifrele seçeneği kullanıcılar için kullanılamaz hale gelir.

Bu özellik hakkında daha fazla bilgi için Bkz. [Office uygulamalarıyla oluşturulan PDF'lere duyarlılık etiketleri uygulama](https://insider.office.com/blog/apply-sensitivity-labels-to-pdfs-created-with-office-apps) duyurusu.

Son kullanıcı belgeleri için bkz. [Office dosyalarından korumalı PDF'ler oluşturma](https://support.microsoft.com/topic/aba7e367-e482-49e7-b746-a385e48d01e4).

## <a name="sensitivity-bar"></a>Duyarlılık çubuğu

Word, Excel ve PowerPoint'te yerleşik etiketler için önizlemede yeni desteklenir, ancak henüz Outlook veya Web için Office için desteklenmez, en düşük sürümleri belirlemek için bu sayfadaki [özellikler](#support-for-sensitivity-label-capabilities-in-apps) bölümündeki tablolara bakın.

Desteklenen uygulamalar için duyarlılık etiketleri artık üst pencere çubuğundaki dosya adının yanında bir duyarlılık çubuğunda görüntülenir. Örneğin:

![Pencere başlık çubuğunda duyarlılık etiketleri.](../media/sensitivity-bar-example.png)

Etiketler ve etiket seçme veya değiştirme özelliği hakkındaki bilgiler, kaydetme ve yeniden adlandırma, dışarı aktarma, paylaşma, yazdırma ve [PDF'ye dönüştürme](#pdf-support) gibi kullanıcı iş akışlarıyla tümleştirilir. Daha fazla bilgi ve örnek ekran görüntüleri için bkz. [Windows için Office'te yeni duyarlılık çubuğu](https://insider.office.com/blog/sensitivity-bar-in-office-for-windows) blog gönderisi duyurusu.

Bu yüksek görünürlüğün bir parçası olarak, bu etiketler renkleri de destekler. Daha fazla bilgi için sonraki bölüme bakın.

### <a name="label-colors"></a>Etiket renkleri

> [!IMPORTANT]
> Etiketleme uygulamalarınız bu özelliği desteklemiyorsa, yapılandırılan etiket renklerini görüntülemez.
> 
> Azure Information Protection birleşik etiketleme istemcisi etiket renklerini destekler. Office'te yerleşik etiketleme için, etiket renkleri şu anda Windows üzerinde Word, Excel ve PowerPoint için önizleme aşamasında desteklenir, ancak henüz Outlook, macOS veya Web için Office için desteklenmez. Daha fazla bilgi için bu sayfadaki [özellikler](#support-for-sensitivity-label-capabilities-in-apps) bölümündeki tablolara bakın.

Yeni oluşturulan etiketlerin varsayılan olarak bir rengi yoktur. Etiketleriniz [Azure Information Protection'dan geçirildiyse](/azure/information-protection/configure-policy-migrate-labels) veya Azure Information Protection birleşik etiketleme istemcisi için etiket renkleri yapılandırdıysanız, bu etiket renkleri artık bunları destekleyen uygulamalarda görüntülenir.

Duyarlılık etiketleri için 10 standart renkten birini seçmek için Microsoft Purview uyumluluk portalı kullanın. **Etiket rengi** yapılandırması, etiket adı ve açıklamasından sonra etiket yapılandırmasının ilk sayfasındadır.

Alt etiketler için renkleri seçemezsiniz çünkü bunlar etiket rengini üst etiketlerinden otomatik olarak devralır.

Bir etiket varsayılan 10 renkten birinden farklı bir renk için yapılandırılmışsa **, Önceden atanmış özel renk kullan** onay kutusunun seçili olduğunu ve standart renk seçeneklerinin kullanılabilir olmadığını görürsünüz. Önce onay kutusunu temizleyerek özel rengi standart renklerden biriyle değiştirebilir ve ardından standart renklerden birini seçebilirsiniz. 

Uyumluluk portalını kullanarak farklı bir özel renk yapılandıramazsınız. Bunun yerine, sonraki bölümde açıklandığı gibi PowerShell kullanın.

#### <a name="configuring-custom-colors-by-using-powershell"></a>PowerShell kullanarak özel renkleri yapılandırma 

Duyarlılık etiketi için bir renk ayarlamak için [Güvenlik & Uyumluluğu PowerShell](/powershell/exchange/scc-powershell) gelişmiş ayar **rengini** kullanabilirsiniz. Bu yapılandırma, Microsoft Purview uyumluluk portalı yapılandıramazsınız renkleri destekler.

Renk seçiminizi belirtmek için rengin kırmızı, yeşil ve mavi (RGB) bileşenleri için onaltılık üçlü kod kullanın. Örneğin #40e0d0 turkuaz için RGB onaltılık değeridir.

Bu kodlar hakkında daha fazla bilgi için MSDN web belgelerindeki sayfaya bakın [\<color>](https://developer.mozilla.org/docs/Web/CSS/color_value) ve [RapidTable'ları](https://www.rapidtables.com/web/color/RGB_Color.html) da yararlı bulabilirsiniz. Bu kodları, resimleri düzenlemenize olanak sağlayan birçok uygulamada tanımlayabilirsiniz. Örneğin, Microsoft Paint bir paletten özel bir renk seçmenize olanak tanır ve RGB değerleri otomatik olarak görüntülenir ve bunu daha sonra kopyalayabilirsiniz.

Duyarlılık etiketi **GUID'sinin 8faca7b8-8d20-48a3-8ea2-0f96310a848e** olduğu örnek PowerShell komutu

```PowerShell
Set-Label -Identity 8faca7b8-8d20-48a3-8ea2-0f96310a848e -AdvancedSettings @{color="#40e0d0"}
```

Duyarlılık etiketleri için PowerShell gelişmiş ayarlarını belirtmenize yardımcı olacak daha fazla bilgi için bkz. [Gelişmiş ayarları belirtmek için PowerShell ipuçları](create-sensitivity-labels.md#powershell-tips-for-specifying-the-advanced-settings).

## <a name="auditing-labeling-activities"></a>Etiketleme etkinliklerini denetleme

Duyarlılık etiketi etkinlikleri tarafından oluşturulan denetim olayları hakkında bilgi için, [Microsoft Purview uyumluluk portalı denetim günlüğünde arama](search-the-audit-log-in-security-and-compliance.md) bölümündeki [Duyarlılık etiketi etkinlikleri](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities) bölümüne bakın.

Bu denetim bilgileri, duyarlılık etiketlerinizin nasıl kullanıldığını ve etiketlenmiş içeriğin nerede bulunduğunu anlamanıza yardımcı olmak için [içerik gezgininde](data-classification-content-explorer.md) ve [etkinlik gezgininde](data-classification-activity-explorer.md) görsel olarak temsil edilir. 

Ayrıca [, denetim günlüğü kayıtlarını dışarı aktarıp yapılandırırken](export-view-audit-log-records.md) tercih ettiğiniz güvenlik bilgileri ve olay yönetimi (SIEM) yazılımıyla özel raporlar da oluşturabilirsiniz. Daha büyük ölçekli raporlama çözümleri için [bkz. Office 365 Yönetim Etkinliği API başvurusu](/office/office-365-management-api/office-365-management-activity-api-reference).

> [!TIP]
> Özel raporlar oluşturmaya yardımcı olmak için aşağıdaki blog gönderilerine bakın:
> - [O365 Yönetim API'si aracılığıyla Microsoft Purview denetim günlüğü etkinlikleri - 1. Bölüm](https://techcommunity.microsoft.com/t5/security-compliance-and-identity/microsoft-365-compliance-audit-log-activities-via-o365/ba-p/2957171)
> - [O365 Yönetim API'si aracılığıyla Microsoft Purview denetim günlüğü etkinlikleri - 2. Bölüm](https://techcommunity.microsoft.com/t5/security-compliance-and-identity/microsoft-365-compliance-audit-log-activities-via-o365/ba-p/2957297) 

## <a name="end-user-documentation"></a>Son kullanıcı belgeleri

- [Office'te dosyalarınıza ve e-postalarınıza duyarlılık etiketleri uygulama](https://support.microsoft.com/en-us/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)
    - [Office'te duyarlılık etiketleriyle ilgili bilinen sorunlar](https://support.microsoft.com/en-us/office/known-issues-with-sensitivity-labels-in-office-b169d687-2bbd-4e21-a440-7da1b2743edc)

- [Office'te dosyalarınıza ve e-postalarınıza duyarlılık etiketlerini otomatik olarak uygulama veya önerme](https://support.office.com/article/automatically-apply-or-recommend-sensitivity-labels-to-your-files-and-emails-in-office-622e0d9c-f38c-470a-bcdb-9e90b24d71a1)
    - [Duyarlılık etiketlerini otomatik olarak uygulama veya önerme ile ilgili bilinen sorunlar](https://support.office.com/article/known-issues-with-automatically-applying-or-recommending-sensitivity-labels-451698ae-311b-4d28-83aa-a839a66f6efc)

- [Office dosyalarından korumalı PDF'ler oluşturma](https://support.microsoft.com/topic/aba7e367-e482-49e7-b746-a385e48d01e4)
