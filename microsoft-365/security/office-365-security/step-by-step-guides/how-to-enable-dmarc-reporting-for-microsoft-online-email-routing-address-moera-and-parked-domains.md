---
title: Microsoft Online Email Yönlendirme Adresi (MOERA) ve park edilmiş Etki Alanları için DMARC Raporlama'yı etkinleştirme
description: MOERA ve park edilmiş etki alanları için DMARC'yi yapılandırma adımları.
search.product: ''
search.appverid: ''
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
ms.openlocfilehash: dbe994ee0cba90f37acf7dcbd92c3b0d81d673a3
ms.sourcegitcommit: a209c9f86a7b4340a426c4cfed2d36a388c71124
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/15/2022
ms.locfileid: "66862420"
---
# <a name="how-to-enable-dmarc-reporting-for-microsoft-online-email-routing-address-moera-and-parked-domains"></a>Microsoft Online Email Yönlendirme Adresi (MOERA) ve park edilmiş Etki Alanları için DMARC Raporlama'yı etkinleştirme

Etki alanı e-posta güvenliği koruması için en iyi yöntem, Etki Alanı Tabanlı İleti Kimlik Doğrulaması, Raporlama ve Uyumluluk (DMARC) kullanarak kendinizi kimlik sahtekarlığına karşı korumaktır. Etki alanlarınız için DMARC'yi henüz etkinleştirmediyseniz, burada ayrıntılı olarak açıklanan ilk adım bu olmalıdır: [Etki Alanı Tabanlı İleti Kimlik Doğrulaması, Raporlama ve Uyumluluk (DMARC)](/microsoft-365/security/office-365-security/use-dmarc-to-validate-email)

Bu kılavuz, yukarıdaki kılavuzda yer almayan etki alanları için DMARC'yi yapılandırmanıza yardımcı olmak için tasarlanmıştır. Hem Microsoft Online Email Yönlendirme Adresiniz (MOERA) hem de henüz e-posta için kullanmamış olabileceğiniz ancak koruma altına alınana kadar saldırganlar tarafından kullanılabilecek park edilmiş etki alanları contosocorp.onmicrosoft.com.

## <a name="what-youll-need"></a>İhtiyacınız olan şey

- Microsoft 365 yönetim merkezi ve etki alanlarınızı barındıran DNS sağlayıcınıza erişim
- Microsoft 365 Yönetici Merkezi'nde uygun değişiklikleri yapmak için Genel Yönetici olarak yeterli izinler
- Aşağıdaki adımları tamamlamak için 10 dakika

## <a name="activate-dmarc-for-moera-domain"></a>MOERA Etki Alanı için DMARC'i etkinleştirme

1. [Microsoft 365 Yönetici Merkezi'ne](https://admin.microsoft.com) oturum açın.
1. Sol gezinti bölmesinde **Tümünü Göster'i** seçin.
1. Ayarlar'ı genişletin ve **Etki Alanları'nı** tıklatın.
1. Kiracı etki alanınızı (contoso.onmicrosoft.com) seçin.
1. Yüklenen sayfada **DNS kayıtları'nı** seçin.
1. **+ Kayıt ekle'yi** seçin.
1. Sağ tarafta bir açılır pencere görünür ve seçili Tür'in **TXT (Metin)** olduğundan emin olun.
1. txt adı olarak _dmarc ekleyin.
1. Belirli DMARC değerinizi ekleyin.
1. **Kaydet'e** basın.

## <a name="active-dmarc-for-parked-domains"></a>Park edilmiş etki alanları için etkin DMARC

1. Park edilmiş etki alanınız için SPF'nin zaten yapılandırılmış olup olmadığını denetleyin, şu kılavuzu izleyerek: Kimlik [sahtekarlıklarını önlemeye yardımcı olmak için SPF'yi ayarlama - Office 365 | Microsoft Docs](/microsoft-365/security/office-365-security/set-up-spf-in-office-365-to-help-prevent-spoofing#how-to-handle-subdomains)
1. DNS Etki Alanı sağlayıcınıza başvurun.
1. Uygun e-posta adresleriniz `v=DMARC1; p=reject; rua=mailto:d@rua.contoso.com;ruf=mailto:d@ruf.contoso.com`ile bu DMARC txt kaydını eklemeyi isteyin.

## <a name="next-steps"></a>Sonraki Adımlar

DNS değişikliklerinin yayılmasını bekleyin ve yapılandırılan etki alanlarını yanıltmaya çalışın. Denemenin DMARC kaydına göre engellenip engellenmediğini denetleyin ve bir DMARC raporu alırsınız.

## <a name="more-information"></a>Daha Fazla Bilgi

[Sahtekarlık önlemeye yardımcı olmak için SPF'yi ayarlama - Office 365 | ](/microsoft-365/security/office-365-security/set-up-spf-in-office-365-to-help-prevent-spoofing)
 Microsoft Docs [E-postayı doğrulamak için DMARC kullanma, kurulum adımları - Office 365 | Microsoft Docs](/microsoft-365/security/office-365-security/use-dmarc-to-validate-email)
