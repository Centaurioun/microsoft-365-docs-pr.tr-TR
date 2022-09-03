---
title: İş için Microsoft Defender'de güvenlik duvarı ilkeleri için özel kuralları yönetme
description: Özel kurallar güvenlik duvarı ilkeleri için özel durumlar sağlar. İş için Defender'da belirli bağlantıları engellemek veya izin vermek için özel kurallar kullanabilirsiniz.
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.service: microsoft-365-security
ms.subservice: mdb
ms.localizationpriority: medium
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: 38b4b70e3ad2c1de098f1b608d0470faa51e1604
ms.sourcegitcommit: 511d15831b97d02e5a0f5e11834ad52617abd0f6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2022
ms.locfileid: "67600257"
---
# <a name="manage-your-custom-rules-for-firewall-policies-in-microsoft-defender-for-business"></a>İş için Microsoft Defender'de güvenlik duvarı ilkeleri için özel kurallarınızı yönetme

İş için Defender, cihazlarınızı istenmeyen ağ trafiğinden korumaya yardımcı olan güvenlik duvarı ilkeleri içerir. Güvenlik duvarı ilkelerinizin özel durumlarını tanımlamak için özel kurallar kullanabilirsiniz. Yani, belirli bağlantıları engellemek veya izin vermek için özel kurallar kullanabilirsiniz.

Güvenlik duvarı ilkeleri ve ayarları hakkında daha fazla bilgi [edinmek için bkz. İş için Defender'da Güvenlik Duvarı](mdb-firewall.md).

**Bu makalede şunların nasıl yapılacağını açıklar**:

- [Güvenlik duvarı ilkesi için özel kural oluşturma](#create-a-custom-rule-for-a-firewall-policy)
- [Güvenlik duvarı ilkesi için özel kural düzenleme](#edit-a-custom-rule-for-a-firewall-policy)
- [Özel kuralı silme](#delete-a-custom-rule)


## <a name="create-a-custom-rule-for-a-firewall-policy"></a>Güvenlik duvarı ilkesi için özel kural oluşturma

1. Microsoft 365 Defender portalına ([https://security.microsoft.com](https://security.microsoft.com)) gidin ve oturum açın.

2. **Uç Noktalar** > **Cihaz yapılandırması'na** gidin ve ilke listesini gözden geçirin.

3. **Güvenlik duvarı** bölümünde var olan bir ilkeyi seçin veya yeni bir ilke ekleyin.

4. **Yapılandırma ayarları** adımında ayarları gözden geçirin. **Etki alanı ağında**, **Genel ağda** ve **Özel ağda** gerekli değişiklikleri yapın.

5. Özel kural oluşturmak için şu adımları izleyin: 

   1. **Özel kurallar'ın** altında **+ Kural ekle'yi** seçin. (En fazla 150 özel kuralınız olabilir.)
   2. **Yeni kural oluştur** açılır penceresinde kural için bir ad ve açıklama belirtin.
   3. Bir profil seçin. (Seçenekleriniz **Etki alanı ağı**, **Genel ağ** veya **Özel ağdır**.)
   4. **Uzak adres türü** listesinde **IP** veya **Uygulama dosya yolunu** seçin.
   5. **Değer** kutusunda uygun bir değer belirtin. 6d adımında ne seçtiğinize bağlı olarak, bir IP adresi, IP adresi aralığı veya uygulama dosyası yolu belirtebilirsiniz. (Bkz [. Güvenlik duvarı ayarları](mdb-firewall.md).)
   6. **Yeni kural oluştur** açılır penceresinde **Kural oluştur'u** seçin. 

6. **Yapılandırma ayarları** ekranında **İleri'yi** seçin.

7. **İlkenizi gözden geçirin** ekranında güvenlik duvarı ilke ayarlarında yapılan değişiklikleri gözden geçirin. Gerekli değişiklikleri yapın ve ardından **İlke oluştur'u** seçin.

## <a name="edit-a-custom-rule-for-a-firewall-policy"></a>Güvenlik duvarı ilkesi için özel kural düzenleme

1. Microsoft 365 Defender portalına ([https://security.microsoft.com](https://security.microsoft.com)) gidin ve oturum açın.

2. **Uç Noktalar** > **Cihaz yapılandırması'na** gidin ve ilke listesini gözden geçirin.

3. **Güvenlik duvarı** bölümünde var olan bir ilkeyi seçin veya yeni bir ilke ekleyin.

4. **Özel kurallar'ın** altında kural listesini gözden geçirin.

5. Bir kural seçin ve ardından **Düzenle'yi** seçin. Açılır penceresi açılır.

6. Özel kuralınızı düzenlemek için şu adımları izleyin:

   1. **Kuralı düzenle açılır penceresinde kuralın** adını ve açıklamasını gözden geçirin ve düzenleyin.
   2. Kuralın profilini gözden geçirin ve gerekirse düzenleyin. (Seçenekleriniz **Etki alanı ağı**, **Genel ağ** veya **Özel ağdır**.)
   3. **Uzak adres türü** listesinde **IP** veya **Uygulama dosya yolunu** seçin.
   4. **Değer** kutusunda uygun bir değer belirtin. 6. adımda ne seçtiğinize bağlı olarak, bir IP adresi, ip adresi aralığı veya uygulama dosyası yolu belirtebilirsiniz. (Bkz [. Güvenlik duvarı ayarları](mdb-firewall.md).)
   5. Kuralı etkin hale getirmek için **Kuralı etkinleştir** seçeneğini **Açık** olarak ayarlayın. Veya kuralı devre dışı bırakmak için anahtarı **Kapalı** olarak ayarlayın.
   6. **Kuralı düzenle** açılır penceresinde **Kuralı güncelleştir'i** seçin. 

7. **Yapılandırma ayarları** ekranında **İleri'yi** seçin.

8. **İlkenizi gözden geçirin** ekranında güvenlik duvarı ilke ayarlarında yapılan değişiklikleri gözden geçirin. Gerekli değişiklikleri yapın ve ardından **İlke oluştur'u** seçin.

## <a name="delete-a-custom-rule"></a>Özel kuralı silme

1. Microsoft 365 Defender portalına ([https://security.microsoft.com](https://security.microsoft.com)) gidin ve oturum açın.

2. **Uç Noktalar** > **Cihaz yapılandırması'na** gidin ve ilke listesini gözden geçirin.

3. **Güvenlik duvarı** bölümünde var olan bir ilkeyi seçin veya yeni bir ilke ekleyin.

4. **Özel kurallar'ın** altında kural listesini gözden geçirin.

5. Bir kural seçin ve ardından **Sil'i** seçin. Açılır penceresi açılır.

6. Onay ekranında **Sil'i** seçin. 

## <a name="next-steps"></a>Sonraki adımlar

- [İş için Defender'da olayları görüntüleme ve yönetme](mdb-view-manage-incidents.md)
- [İş için Defender'da tehditlere yanıt verme ve tehditleri azaltma](mdb-respond-mitigate-threats.md)
- [İşlem merkezindeki düzeltme eylemlerini gözden geçirme](mdb-review-remediation-actions.md)