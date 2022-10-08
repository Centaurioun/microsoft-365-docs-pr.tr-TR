---
title: İş için Microsoft Defender'de ilkeleri görüntüleme veya düzenleme
description: İş için Defender'da siber güvenlik ilkelerini görüntülemeyi, düzenlemeyi, oluşturmayı ve silmeyi öğrenin. Cihazlarınızı güvenlik ilkeleriyle koruyun.
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.service: microsoft-365-security
ms.subservice: mdb
ms.localizationpriority: medium
ms.date: 08/11/2022
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- m365-security
- m365-initiative-defender-business
- tier1
ms.openlocfilehash: 626287dcd8c1bed6dac91d55f020d9f5a5780cff
ms.sourcegitcommit: 0283c436f3ba61a708b52b57a1955f5ea74376a3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/28/2022
ms.locfileid: "68097763"
---
# <a name="view-or-edit-policies-in-microsoft-defender-for-business"></a>İş için Microsoft Defender'de ilkeleri görüntüleme veya düzenleme

İş için Defender'da güvenlik ayarları cihazlara uygulanan ilkeler aracılığıyla yapılandırılır. İş için Defender, kurulum ve yapılandırma deneyiminizi basitleştirmeye yardımcı olmak için şirketinizin cihazlarının eklendikleri anda korunmasına yardımcı olmak için önceden yapılandırılmış ilkeler içerir. Varsayılan ilkeleri kullanabilir, ilkeleri düzenleyebilir veya kendi ilkelerinizi oluşturabilirsiniz.

**Bu makalede şunların nasıl yapılacağını açıklar**:

- [Varsayılan ilkelerinize genel bakış elde edin](#default-policies-in-defender-for-business)
- [Mevcut ilkelerinizi görüntüleme](#view-your-existing-policies)
- [Var olan bir ilkeyi düzenleme](#edit-an-existing-policy)
- [Yeni ilke oluşturma](#create-a-new-policy)

> [!NOTE]
> Bu makaledeki yordamlarda, Microsoft 365 Defender portalında ([https://security.microsoft.com](https://security.microsoft.com) ) güvenlik ilkelerini görüntüleme, düzenleme ve oluşturma işlemleri açıklanmaktadır. Microsoft Intune kullanıyorsanız bkz. [Microsoft Intune'de uç nokta güvenliğini yönetme](/mem/intune/protect/endpoint-security).

## <a name="default-policies-in-defender-for-business"></a>İş için Defender'da varsayılan ilkeler

İş için Defender'da, şirketinizin cihazlarını korumaya yönelik iki ana ilke türü vardır:

- Microsoft Defender Virüsten Koruma ve diğer tehdit koruması özelliklerinin nasıl yapılandırıldığını belirleyen **yeni nesil koruma ilkeleri**
- Şirketinizin cihazlarına hangi ağ trafiğinin akışına izin verileceğini belirleyen **güvenlik duvarı ilkeleri**

## <a name="view-your-existing-policies"></a>Mevcut ilkelerinizi görüntüleme

1. Microsoft 365 Defender portalına ()[https://security.microsoft.com](https://security.microsoft.com) gidin ve oturum açın. 

2. Gezinti bölmesinde **Cihaz yapılandırması'nı** seçin. İlkeler işletim sistemine ( **Windows istemcisi** gibi) ve ilke türüne ( **yeni nesil koruma** ve **Güvenlik Duvarı** gibi) göre düzenlenir. 

3. bir işletim sistemi sekmesi (örneğin, **Windows istemcileri**) seçin ve ardından **Yeni nesil koruma** ve **Güvenlik Duvarı** kategorileri altındaki ilke listesini gözden geçirin. 

4. İlke hakkında daha fazla ayrıntı görüntülemek için adını seçin. İlkeyle korunan cihazlar gibi bu ilke hakkında daha fazla bilgi sağlayan bir yan bölme açılır.

## <a name="edit-an-existing-policy"></a>Var olan bir ilkeyi düzenleme

1. Microsoft 365 Defender portalına ()[https://security.microsoft.com](https://security.microsoft.com) gidin ve oturum açın. 

2. Gezinti bölmesinde **Cihaz yapılandırması'nı** seçin. İlkeler işletim sistemine ( **Windows istemcisi** gibi) ve ilke türüne ( **yeni nesil koruma** ve **Güvenlik Duvarı** gibi) göre düzenlenir. 

3. bir işletim sistemi sekmesi (örneğin, **Windows istemcileri**) seçin ve ardından **Yeni nesil koruma** ve **Güvenlik Duvarı** kategorileri altındaki ilke listesini gözden geçirin. 

4. İlkeyi düzenlemek için, ilkenin adını ve ardından **Düzenle'yi** seçin.

5. **Genel bilgiler** sekmesinde bilgileri gözden geçirin. Gerekirse açıklamayı düzenleyebilirsiniz. Ardından **İleri'yi** seçin.

6. **Cihaz grupları** sekmesinde, hangi cihaz gruplarının bu ilkeyi alması gerektiğini belirleyin.  

   - Seçili cihaz grubunu olduğu gibi tutmak için **İleri'yi** seçin.
   - İlkeden bir cihaz grubunu kaldırmak için **Kaldır'ı** seçin.
   - Yeni bir cihaz grubu ayarlamak için **Yeni grup oluştur'u** seçin ve ardından cihaz grubunuzu ayarlayın. (Bu görevle ilgili yardım almak için bkz. [İş için Defender'da cihaz grupları](mdb-create-edit-device-groups.md).)
   - İlkeyi başka bir cihaz grubuna uygulamak için **Var olan grubu kullan'ı** seçin.

   İlkeyi hangi cihaz gruplarının alacağını belirttikten sonra **İleri'yi** seçin.

7. **Yapılandırma ayarları** sekmesinde ayarları gözden geçirin. Gerekirse, ilkenizin ayarlarını düzenleyebilirsiniz. Bu görevle ilgili yardım almak için aşağıdaki makalelere bakın: 

   - [Yeni nesil yapılandırma ayarlarını anlama](mdb-next-gen-configuration-settings.md)   
   - [Güvenlik duvarı ayarları](mdb-firewall.md)

   Yeni nesil koruma ayarlarınızı belirttikten sonra **İleri'yi** seçin.

8. **İlkenizi gözden geçirin** sekmesinde genel bilgileri, hedeflenen cihazları ve yapılandırma ayarlarını gözden geçirin. 

   - **Düzenle'yi** seçerek gerekli değişiklikleri yapın.
   - Devam etmeye hazır olduğunuzda **İlkeyi güncelleştir'i** seçin.

## <a name="create-a-new-policy"></a>Yeni ilke oluşturma

1. Microsoft 365 Defender portalına ()[https://security.microsoft.com](https://security.microsoft.com) gidin ve oturum açın. 

2. Gezinti bölmesinde **Cihaz yapılandırması'nı** seçin. İlkeler işletim sistemine ( **Windows istemcisi** gibi) ve ilke türüne ( **yeni nesil koruma** ve **Güvenlik Duvarı** gibi) göre düzenlenir. 

3. bir işletim sistemi sekmesi (örneğin, **Windows istemcileri**) seçin ve **ardından Yeni nesil koruma** ilkeleri listesini gözden geçirin. 

4. **Yeni nesil koruma** veya **Güvenlik Duvarı** altında **+ Ekle'yi** seçin.

5. **Genel bilgiler** sekmesinde aşağıdaki adımları izleyin:

   1. Bir ad ve açıklama belirtin. Bu bilgiler, sizin ve ekibinizin ilkeyi daha sonra tanımlamanıza yardımcı olur.
   2. İlke sırasını gözden geçirin ve gerekirse düzenleyin. (Daha fazla bilgi için bkz. [İlke sırası](mdb-policy-order.md).)
   3. **İleri**'yi seçin. 

7. **Cihaz grupları** sekmesinde yeni bir cihaz grubu oluşturun veya mevcut bir grubu kullanın. İlkeler cihazlara cihaz grupları aracılığıyla atanır. Aklınızda bulundurmak istediğiniz bazı şeyler şunlardır:

   - Başlangıçta, yalnızca şirketinizdeki kişilerin şirket verilerine ve e-postasına erişmek için kullandığı cihazları içeren varsayılan cihaz grubunuz olabilir. Varsayılan cihaz grubunuzu tutabilir ve kullanabilirsiniz.
   - Varsayılan ilkeden farklı olan belirli ayarlara sahip bir ilke uygulamak için yeni bir cihaz grubu oluşturun. 
   - Cihaz grubunuzu ayarlarken işletim sistemi sürümü gibi belirli ölçütleri belirtirsiniz. Ölçütleri karşılayan cihazlar, siz hariç tutmadığınız sürece bu cihaz grubuna dahil edilir. 
   - Tanımladığınız varsayılan ve özel cihaz grupları dahil olmak üzere tüm cihaz grupları Azure Active Directory'de (Azure AD) depolanır.

   Cihaz grupları hakkında daha fazla bilgi edinmek için bkz. [İş için Defender'da cihaz grupları](mdb-create-edit-device-groups.md).

8. **Yapılandırma ayarları** sekmesinde ilkenizin ayarlarını belirtin ve ardından **İleri'yi** seçin. Tek tek ayarlar hakkında daha fazla bilgi için bkz [. İş için Defender yapılandırma ayarları](mdb-next-gen-configuration-settings.md).

9. **İlkenizi gözden geçirin** sekmesinde genel bilgileri, hedeflenen cihazları ve yapılandırma ayarlarını gözden geçirin. 

   - **Düzenle'yi** seçerek gerekli değişiklikleri yapın.
   - Devam etmeye hazır olduğunuzda **İlke oluştur'u** seçin.


## <a name="next-steps"></a>Sonraki adımlar

Aşağıdaki görevlerden birini veya daha fazlasını seçin:

- [Cihazları yönetme](mdb-manage-devices.md)
- [İş için Defender'da yeni ilke oluşturma](mdb-create-new-policy.md)
- [İş için Defender'da olayları görüntüleme ve yönetme](mdb-view-manage-incidents.md)
- [İş için Defender'da tehditlere yanıt verme ve tehditleri azaltma](mdb-respond-mitigate-threats.md)
- [İşlem merkezindeki düzeltme eylemlerini gözden geçirme](mdb-review-remediation-actions.md)