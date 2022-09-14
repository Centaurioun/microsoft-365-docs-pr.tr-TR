---
title: Microsoft Online Email Yönlendirme Adresi (MOERA) ve park edilmiş Etki Alanları için DMARC Raporlama'yı etkinleştirme
description: MOERA ve park edilmiş etki alanları için DMARC'yi yapılandırma adımları.
search.product: ''
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-guidance-templates
ms.topic: how-to
ms.technology: mdo
search.appverid: met150
ms.openlocfilehash: aed556a96adf3f8a135aeb42289bb2ee30af3f78
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67686305"
---
# <a name="how-to-enable-dmarc-reporting-for-microsoft-online-email-routing-address-moera-and-parked-domains"></a>Microsoft Online Email Yönlendirme Adresi (MOERA) ve park edilmiş Etki Alanları için DMARC Raporlama'yı etkinleştirme

Etki alanı e-posta güvenliği koruması için en iyi yöntem, Etki Alanı Tabanlı İleti Kimlik Doğrulaması, Raporlama ve Uyumluluk (DMARC) kullanarak kendinizi kimlik sahtekarlığına karşı korumaktır. Etki alanlarınız için DMARC'yi henüz etkinleştirmediyseniz, burada ayrıntılı olarak açıklanan ilk adım bu olmalıdır: [Etki Alanı Tabanlı İleti Kimlik Doğrulaması, Raporlama ve Uyumluluk (DMARC)](/microsoft-365/security/office-365-security/use-dmarc-to-validate-email)

Bu kılavuz, DMARC'yi ana DMARC makalesinin kapsamına alınmayan etki alanları için yapılandırmanıza yardımcı olmak üzere tasarlanmıştır. Bu etki alanları, e-posta için kullanmadığınız ancak korumasız kalmaları durumunda saldırganlar tarafından yararlanabileceğiniz etki alanlarını içerir:

- Microsoft Online Email Yönlendirme Adresi (MOERA) etki alanı olarak da bilinen etki alanınız`onmicrosoft.com`.
- Şu anda e-posta için kullanmadığınız park edilmiş özel etki alanları.

## <a name="what-youll-need"></a>İhtiyacınız olan şey

- Microsoft 365 yönetim merkezi ve etki alanlarınızı barındıran DNS sağlayıcınıza erişim.
- Microsoft 365 yönetim merkezi uygun değişiklikleri yapmak için Genel Yönetici olarak yeterli izinler.
- Bu makaledeki adımları tamamlamak için 10 dakika.

## <a name="activate-dmarc-for-moera-domain"></a>MOERA Etki Alanı için DMARC'i etkinleştirme

1. konumunda Microsoft 365 yönetim merkezi <https://admin.microsoft.com>açın.
1. Sol gezinti bölmesinde **Tümünü Göster'i** seçin.
1. **Ayarlar'ı** genişletin ve **Etki Alanları'nı** tıklatın.
1. Kiracı etki alanınızı seçin (örneğin, contoso.onmicrosoft.com).
1. Yüklenen sayfada **DNS kayıtları'nı** seçin.
1. **+ Kayıt ekle'yi** seçin.
1. Sağ tarafta bir açılır pencere görünür. Seçili Türün **TXT (Metin)** olduğundan emin olun.
1. **TXT adı** olarak ekleyin`_dmarc`.
1. Belirli DMARC değerinizi ekleyin.
1. **Kaydet'e** basın.

## <a name="active-dmarc-for-parked-domains"></a>Park edilmiş etki alanları için etkin DMARC

1. SPF'nin park edilmiş etki alanınız için zaten yapılandırılmış olup olmadığını denetleyin. Yönergeler için bkz. Kimlik [sahtekarlığına engel olmak için SPF'yi ayarlama - Office 365 | Microsoft Docs](/microsoft-365/security/office-365-security/set-up-spf-in-office-365-to-help-prevent-spoofing#how-to-handle-subdomains)
1. DNS Etki Alanı sağlayıcınıza başvurun.
1. Uygun e-posta adresleriniz ile bu DMARC txt kaydını eklemeyi isteyin: `v=DMARC1; p=reject; rua=mailto:d@rua.contoso.com;ruf=mailto:d@ruf.contoso.com`.

## <a name="next-steps"></a>Sonraki Adımlar

DNS değişikliklerinin yayılmasını bekleyin ve yapılandırılan etki alanlarını yanıltmaya çalışın. Denemenin DMARC kaydına göre engellenip engellenmediğini denetleyin ve bir DMARC raporu alırsınız.

## <a name="more-information"></a>Daha Fazla Bilgi

[Sahtekarlık önlemeye yardımcı olmak için SPF'yi ayarlama - Office 365 | Microsoft Docs](/microsoft-365/security/office-365-security/set-up-spf-in-office-365-to-help-prevent-spoofing)

[E-postayı doğrulamak için DMARC kullanma, kurulum adımları - Office 365 | Microsoft Docs](/microsoft-365/security/office-365-security/use-dmarc-to-validate-email)
