---
title: Azure Information Protection mevcut kiracılara sunulan koruma özellikleri
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
audience: ITPro
ms.topic: conceptual
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: 7ad6f58e-65d7-4c82-8e65-0b773666634d
ms.collection:
- m365-security
ms.custom:
- seo-marvel-apr2020
description: Bu makalede, Azure Information Protection koruma özelliklerinde kullanıma sunulan değişiklikler açıklanmaktadır
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: d26b4b3567c76e8a6384a6ec420562839d9cc2b1
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68622188"
---
# <a name="protection-features-in-azure-information-protection-rolling-out-to-existing-tenants"></a>Azure Information Protection mevcut kiracılara sunulan koruma özellikleri

**Uygulandığı öğe**
- [Office 365 için Microsoft Defender plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Bilgilerinizi korumanın ilk adımına yardımcı olmak için, Temmuz 2018'den itibaren tüm Azure Information Protection uygun kiracılar azure Information Protection koruma özellikleri varsayılan olarak açıktır. Azure Information Protection koruma özellikleri daha önce Office 365 Rights Management veya Azure RMS olarak biliniyordu. Kuruluşunuzun bir Office E3 hizmet planı veya daha yüksek bir hizmet planı varsa artık bu özellikleri kullanıma sunduğumuzda Azure Information Protection aracılığıyla bilgileri korumaya başlayabilirsiniz.

## <a name="changes-beginning-july-1-2018"></a>1 Temmuz 2018'de başlayan değişiklikler

Microsoft, 1 Temmuz 2018'den itibaren aşağıdaki abonelik planlarından birine sahip tüm kuruluşlar için Azure Information Protection'da koruma özelliğini etkinleştirecektir:

- Office 365 İleti Şifrelemesi, Office 365 E3 ve E5, Microsoft E3 ve E5, Office 365 A1, A3 ve A5 ile Office 365 G3 ve G5'in bir parçası olarak sunulur. Azure Information Protection tarafından desteklenen yeni koruma özelliklerini almak için ek lisanslara ihtiyacınız yoktur.

- Yeni Office 365 İleti Şifrelemesi özelliklerini almak için Azure Information Protection Plan 1'i aşağıdaki planlara da ekleyebilirsiniz: Exchange Online Plan 1, Exchange Online Plan 2, Office 365 F1, E1'i Microsoft 365 İş Temel, Microsoft 365 İş Standart veya Office 365 Kurumsal.

- Office 365 İleti Şifrelemesinden yararlanan her kullanıcının özelliğin kapsamına alınması için lisanslanması gerekir.

- Tam liste için, Office 365 İleti Şifrelemesi için Exchange Online [hizmet açıklamalarına](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description) bakın.

Kiracı yöneticileri, Office 365 yönetici portalında koruma durumunu denetleyebilir.

:::image type="content" source="../../media/303453c8-e4a5-4875-b49f-e80c3eb7b91e.png" alt-text="Etkinleştirilen Office 365'de hak yönetimi" lightbox="../../media/303453c8-e4a5-4875-b49f-e80c3eb7b91e.png":::

## <a name="why-are-we-making-this-change"></a>Neden bu değişikliği yapıyoruz?

Office 365 İleti Şifrelemesi, Azure Information Protection'daki koruma özelliklerinden yararlanıyor. Office 365 İleti Şifrelemesi'nde yapılan son geliştirmelerin ve Microsoft 365'te bilgi korumasına yapılan daha geniş yatırımlarımızın merkezinde kuruluşların koruma özelliklerimizi açmasını ve kullanmasını kolaylaştırıyoruz. Geçmişte şifreleme teknolojilerinin ayarlanması zor olmuştur. Azure Information Protection'daki koruma özelliklerini varsayılan olarak açarak hassas verilerinizi korumaya hızlıca başlayabilirsiniz.

## <a name="does-this-impact-me"></a>Bu beni etkiliyor mu?

Kuruluşunuz uygun bir Office 365 lisansı satın aldıysa, kiracınız bu değişiklikden etkilenir.

> [!IMPORTANT]
> Şirket içi ortamınızda Active Directory Rights Management Services (AD RMS) kullanıyorsanız, bu değişikliği önümüzdeki 30 gün içinde kullanıma sunmadan önce bu değişikliği hemen geri çevirmeniz veya Azure Information Protection'a geçmeniz gerekir. Geri çevirme hakkında bilgi için bkz. "AD RMS kullanıyorum, nasıl geri çevirebilirim?" bölümüne bakın. Geçişi tercih ediyorsanız bkz[. AD RMS'den Azure'a geçiş Information Protection.](/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms).

## <a name="can-i-use-azure-information-protection-with-active-directory-rights-management-services-ad-rms"></a>Azure Information Protection Active Directory Rights Management Services (AD RMS) ile kullanabilir miyim?

Hayır. Bu desteklenen bir dağıtım senaryosu değildir. Ek geri çevirme adımlarını uygulamadan, bazı bilgisayarlar otomatik olarak Azure Rights Management hizmetini kullanmaya başlayabilir ve ayrıca AD RMS kümenize bağlanabilir. Bu senaryo desteklenmiyor ve güvenilir olmayan sonuçlara sahip olduğundan, bu yeni özellikleri kullanıma sunmadan önceki 30 gün içinde bu değişikliği geri çevirmeniz önemlidir. Geri çevirme hakkında bilgi için bkz. "AD RMS kullanıyorum, nasıl geri çevirebilirim?" bölümüne bakın. Geçişi tercih ediyorsanız bkz[. AD RMS'den Azure'a geçiş Information Protection.](/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)

## <a name="how-do-i-know-if-im-using-ad-rms"></a>AD RMS kullanıp kullanmadığım Nasıl yaparım??

[AD RMS dağıtıp dağıtmadığınızdan denetlemek için Active Directory Rights Management Services 'a (AD RMS) sahip olduğunuzda Ortamı Azure Rights Management için hazırlama](/azure/information-protection/deploy-use/prepare-environment-adrms) başlığı altındaki bu yönergeleri kullanın:

1. İsteğe bağlı olsa da, çoğu AD RMS dağıtımı, etki alanı bilgisayarlarının AD RMS kümesini bulabilmesi için hizmet bağlantı noktasını (SCP) Active Directory'de yayımlar.

   Active Directory'de yayımlanmış bir SCP'niz olup olmadığını görmek için ADSI Düzenleme'yi kullanın: CN=Configuration [sunucu adı], CN=Hizmetler, CN=RightsManagementServices, CN=SCP

2. SCP kullanmıyorsanız, BIR AD RMS kümesine bağlanan Windows bilgisayarları, Windows kayıt defteri kullanılarak istemci tarafı hizmet bulma veya lisans yeniden yönlendirme için yapılandırılmalıdır: `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\ServiceLocation or HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\MSIPC\ServiceLocation`.

Bu kayıt defteri yapılandırmaları hakkında daha fazla bilgi için bkz [. Windows kayıt defterini kullanarak istemci tarafı hizmet bulmayı etkinleştirme](/azure/information-protection/rms-client/client-deployment-notes#enabling-client-side-service-discovery-by-using-the-windows-registry) ve [Lisans sunucusu trafiğini yeniden yönlendirme](/azure/information-protection/rms-client/client-deployment-notes#redirecting-licensing-server-traffic).

## <a name="i-use-ad-rms-how-do-i-opt-out"></a>AD RMS kullanıyorum, nasıl geri çevirebilirim?

Yaklaşan değişikliği geri çevirmek için şu adımları tamamlayın:

1. Kuruluşunuzda genel yönetici izinlerine sahip bir iş veya okul hesabı kullanarak bir Windows PowerShell oturumu başlatın ve Exchange Online bağlanın. Yönergeler için bkz. [Exchange Online PowerShell'e bağlanma](/powershell/exchange/connect-to-exchange-online-powershell).

2. Aşağıdaki söz dizimini kullanarak Set-IRMConfiguration cmdlet'ini çalıştırın:

  ```powershell
  Set-IRMConfiguration -AutomaticServiceUpdateEnabled $false
  ```

## <a name="what-can-i-expect-after-this-change-has-been-made"></a>Bu değişiklik yapıldıktan sonra ne bekleyebilirim?

Bu etkinleştirildikten sonra, geri çevirmediyseniz Microsoft [Ignite 2017'de](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Email-Encryption-and-Rights-Protection/ba-p/110801) duyurulan ve Azure Information Protection şifreleme ve koruma özelliklerinden yararlanan yeni Office 365 İleti Şifrelemesi sürümünü kullanmaya başlayabilirsiniz.

:::image type="content" source="../../media/599ca9e7-c05a-429e-ae8d-359f1291a3d8.png" alt-text="Web üzerinde Outlook'da OME korumalı ileti" lightbox="../../media/599ca9e7-c05a-429e-ae8d-359f1291a3d8.png":::

Yeni geliştirmeler hakkında daha fazla bilgi için bkz. [İleti Şifrelemesi Office 365](../../compliance/ome.md).
