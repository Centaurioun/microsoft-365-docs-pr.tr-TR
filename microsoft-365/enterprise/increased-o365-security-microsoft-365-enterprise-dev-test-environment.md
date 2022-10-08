---
title: Kurumsal test ortamınız için Microsoft 365 güvenliğini artırma
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 12/09/2019
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- scotvorg
- M365-security-compliance
ms.custom:
- Ent_TLGs
- admindeeplinkMAC
- admindeeplinkDEFENDER
- admindeeplinkSPO
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Kurumsal test ortamı için Microsoft 365'inizde ek Microsoft 365 güvenlik ayarlarını etkinleştirmek için bu Test Laboratuvarı Kılavuzu'nu kullanın.
ms.openlocfilehash: 83bef240651f86c1a5e357fa2883a730e7da0969
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2022
ms.locfileid: "68208886"
---
# <a name="increased-microsoft-365-security-for-your-microsoft-365-for-enterprise-test-environment"></a>Kurumsal test ortamınız için Microsoft 365 güvenliğini artırma

*Bu Test Laboratuvarı Kılavuzu yalnızca kurumsal test ortamları için Microsoft 365 için kullanılabilir.*

Bu makaledeki yönergelerle, kurumsal test ortamınız için Microsoft 365'te güvenliği artırmak için ek Microsoft 365 ayarlarını yapılandıracaksınız.

![Microsoft bulutu için Test Laboratuvarı Kılavuzları.](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Kuruluş için Microsoft 365 Test Laboratuvarı Kılavuzu yığınındaki tüm makalelerin görsel haritası için [buraya](../downloads/Microsoft365EnterpriseTLGStack.pdf) tıklayın.
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>1. Aşama: Kurumsal test ortamı için Microsoft 365'inizi oluşturma

Yalnızca daha yüksek Microsoft 365 güvenliğini minimum gereksinimlerle basit bir şekilde yapılandırmak istiyorsanız [Basit temel yapılandırma](lightweight-base-configuration-microsoft-365-enterprise.md) yönergelerini izleyin.
  
Sanal bir kuruluşta artırılmış Microsoft 365 güvenliği yapılandırmak istiyorsanız Doğrudan [kimlik doğrulamasındaki](pass-through-auth-m365-ent-test-environment.md) yönergeleri izleyin.
  
> [!NOTE]
> Artan Microsoft 365 güvenliğini test etmek için İnternet'e bağlı bir sanal intranet ve bir Active Directory Domain Services (AD DS) ormanı için dizin eşitlemesi içeren sanal kurumsal test ortamı gerekmez. Burada, otomatik lisanslama ve grup üyeliğini test edebilmeniz ve tipik bir kuruluşu temsil eden bir ortamda denemeler yapabileceğiniz bir seçenek olarak sağlanır. 

## <a name="phase-2-configure-increased-microsoft-365-security"></a>2. Aşama: Artırılmış Microsoft 365 güvenliğini yapılandırma

Bu aşamada, kurumsal test ortamınız için Microsoft 365'te daha fazla Microsoft 365 güvenliği sağlarsınız. Ek ayrıntılar ve ayarlar için bkz [. Artan güvenlik için kiracınızı yapılandırma](/office365/securitycompliance/tenant-wide-setup-for-increased-security).

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a>SharePoint Online'ı modern kimlik doğrulamasını desteklemeyen uygulamaları engelleyecek şekilde yapılandırma

Modern kimlik doğrulamasını desteklemeyen uygulamalar, Microsoft 365 aboneliğinizin ve dijital varlıklarının güvenliğini sağlamanın önemli bir öğesi olan [kimlik ve cihaz erişim yapılandırmalarına](../security/office-365-security/microsoft-365-policies-configurations.md) sahip olamaz. 

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 yönetim merkezi</a> gidin ve genel yönetici hesabınızla Microsoft 365 test laboratuvarı aboneliğinizde oturum açın.
    
  - Basit Microsoft 365 test ortamını kullanıyorsanız yerel bilgisayarınızdan oturum açın.
    
  - Sanal kurumsal Microsoft 365 test ortamını kullanıyorsanız, İstemci1 sanal makinesine bağlanmak için [Azure portal](https://portal.azure.com) kullanın ve ardından client1'den oturum açın.
 
2. Yeni **Microsoft 365 yönetim merkezi** sekmesinde, sol gezinti bölmesindeki **Yönetici merkezleri** altında **SharePoint'e** tıklayın.
3. Yeni **SharePoint yönetim merkezi** sekmesinde **İlkeler**<a href="https://go.microsoft.com/fwlink/?linkid=2185071" target="_blank">**Erişim denetimi'ni**</a> >  seçin.
4. **Modern kimlik doğrulamayı desteklemeyen uygulamalar'ı** seçin, **Erişimi engelle'yi** ve ardından **Kaydet'i** seçin.


### <a name="enable-defender-for-office-365-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a>SharePoint, OneDrive İş ve Microsoft Teams için Office 365 için Defender etkinleştirme

SharePoint, OneDrive ve Microsoft Teams için Office 365 için Defender, kuruluşunuzu yanlışlıkla kötü amaçlı dosyaları paylaşmaya karşı korur.

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Güvenlik & Uyumluluk Merkezi'ne</a> gidin ve genel yönetici hesabınızla oturum açın.

2. Sol gezinti bölmesinde, **Tehdit yönetimi'nin** altında **İlke'ye** ve ardından **Güvenli Ekler'e** tıklayın. 

3. **SharePoint, OneDrive ve Microsoft Teams'de dosyaları koruma** altında. **SharePoint, OneDrive ve Microsoft Teams için ATP'yi aç'ı** seçin.

4. **Kaydet**'e tıklayın.


### <a name="enable-anti-malware"></a>Kötü amaçlı yazılımdan korumayı etkinleştirme

Kötü amaçlı yazılım virüslerden ve casus yazılımlardan oluşur. Virüsler diğer programlara ve verilere bulaşır ve bilgisayarınıza yayılarak bulaşacak programları arar. Casus yazılım, oturum açma bilgileri ve kişisel veriler gibi kişisel bilgilerinizi toplayan ve kötü amaçlı yazılım yazarına geri gönderen kötü amaçlı yazılımları ifade eder. 

Microsoft 365, gelen ve giden iletileri kötü amaçlı yazılımlardan korumaya ve istenmeyen postalardan korunmanıza yardımcı olan yerleşik kötü amaçlı yazılım ve istenmeyen posta filtreleme özelliklerine sahiptir. Daha fazla bilgi için bkz [. İstenmeyen posta önleme & kötü amaçlı yazılımdan koruma](../security/office-365-security/anti-spam-and-anti-malware-protection.md).

Yaygın ek dosya türlerine sahip dosyalarda kötü amaçlı yazılımdan koruma işleminin gerçekleştirildiğinden emin olmak için:

1. **İlke** sayfasına dönmek için tarayıcınızda geri düğmesine tıklayın.
2. **Kötü amaçlı yazılımdan koruma'ya** tıklayın.
3. **Varsayılan** adlı ilkeye çift tıklayın.
4. **Kötü amaçlı yazılımdan koruma ilkesi** penceresinde **Ayarlar'a** tıklayın.
4. **Ortak Ek Türleri filtresi** altında **Açık'ı** seçin ve **kaydet'e** tıklayın.


## <a name="phase-3-examine-the-security-dashboard"></a>3. Aşama: Güvenlik panosunu inceleme

Microsoft 365'teki tehdit yönetimi, kuruluşunuzun verilerine mobil cihaz erişimini denetlemenize ve yönetmenize, kuruluşunuzun veri kaybına karşı korunmasına yardımcı olabilir ve gelen ve giden iletileri kötü amaçlı yazılımlardan ve istenmeyen postalardan korumaya yardımcı olabilir. Ayrıca etki alanınızın itibarını korumak ve gönderenlerin etki alanınızdan kötü amaçlı olarak hesap sahtekarlığı yapıp yapmadığını belirlemek için de tehdit yönetimini kullanırsınız. 

Güvenlik panosunu görmek için:

1. Gerekirse <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Güvenlik & Uyumluluk Merkezi'ne</a> gidin ve genel yönetici hesabınızla oturum açın.

2. Sol gezinti bölmesindeki **Tehdit yönetimi'nin** altında **Pano'ya** tıklayın.

Sağlanan bilgileri öğrenmek için panodaki tüm kartları yakından inceleyin.

Daha fazla bilgi için bkz [. Güvenlik Panosu](../security/office-365-security/security-dashboard.md).


## <a name="phase-4-examine-microsoft-secure-score"></a>4. Aşama: Microsoft Güvenli Puanını İnceleme

Microsoft Güvenli Puanı, güvenlik duruşunuzu bir sayı olarak gösterir ve bu da aboneliğinizde kullanılabilen özelliklere göre geçerli düzeyinizi gösterir. Ayrıca puanınızı geliştirmek için gerçekleştirebileceğiniz iyileştirme eylemlerinin bir listesini de sunar.

1. Tarayıcınızda yeni bir sekme oluşturun, <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portalına</a> gidin ve **ardından Güvenli puan'a** tıklayın.
2. **Genel Bakış** sekmesinde, geçerli Güvenli Puanınızı ve genel ortalamayla ve benzer sayıda lisansa sahip aboneliklerle karşılaştırmasını not edin.
3. **İyileştirme eylemleri** sekmesinde, puanınızı artırmak için gerçekleştirebileceğiniz eylemlerin listesini okuyun.

Daha fazla bilgi için bkz. [Microsoft Güvenli Puanı](../security/defender/microsoft-secure-score.md).

## <a name="next-steps"></a>Sonraki adımlar

Test ortamınızdaki ek [bilgi koruma](m365-enterprise-test-lab-guides.md#information-protection) özelliklerini ve özelliklerini keşfedin.

## <a name="see-also"></a>Ayrıca bkz.

[Kurumsal test laboratuvarı kılavuzları için Microsoft 365](m365-enterprise-test-lab-guides.md)

[Microsoft 365 Kurumsal’a genel bakış](microsoft-365-overview.md)

[Kurumsal belgeler için Microsoft 365](/microsoft-365-enterprise/)
