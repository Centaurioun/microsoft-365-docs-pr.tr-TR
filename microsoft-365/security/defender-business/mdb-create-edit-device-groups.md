---
title: İş için Microsoft Defender'da cihaz grupları
description: Güvenlik ilkeleri, İş için Defender'daki cihaz grupları aracılığıyla cihazlara uygulanır.
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: microsoft-365-security
ms.subservice: mdb
ms.localizationpriority: medium
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: 600386ff5c5fccaa32ce8efde2ad7bd0d30c49b2
ms.sourcegitcommit: 511d15831b97d02e5a0f5e11834ad52617abd0f6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2022
ms.locfileid: "67600323"
---
# <a name="device-groups-in-microsoft-defender-for-business"></a>İş için Microsoft Defender'da cihaz grupları

İş için Defender'da ilkeler, cihaz grupları olarak adlandırılan belirli koleksiyonlar aracılığıyla cihazlara uygulanır. 

**Bu makalede şunlar açıklanmaktadır**:  

- [Cihaz grupları nelerdir?](#what-is-a-device-group)   
- [İş için Defender'da cihaz grupları oluşturma](#create-a-new-device-group)
- [Mevcut bir cihaz grubunu görüntüleme](#view-an-existing-device-group)
- [Tüm Cihazları Ekle seçeneğinin yaptığı işlem](#what-does-the-add-all-devices-option-do)


## <a name="what-is-a-device-group"></a>Cihaz grubu nedir?

Cihaz grubu, işletim sistemi sürümü gibi belirli ölçütler nedeniyle birlikte gruplandırılmış bir cihaz koleksiyonudur. Ölçütleri karşılayan cihazlar, siz hariç tutmadığınız sürece bu cihaz grubuna dahil edilir. İş için Defender'da ilkeler cihazlara cihaz grupları kullanılarak uygulanır.

İş için Defender, kullanabileceğiniz varsayılan cihaz gruplarını içerir. Varsayılan cihaz grupları, İş için Defender'a eklenen tüm cihazları içerir. Örneğin, Windows cihazları için varsayılan bir cihaz grubu vardır. Windows cihazlarını her eklediğinizde, bunlar otomatik olarak varsayılan cihaz grubuna eklenir.

Belirli cihazlara belirli ayarlarla ilke atamak için yeni cihaz grupları da oluşturabilirsiniz. Örneğin, bir Windows cihaz kümesine atanmış bir güvenlik duvarı ilkeniz ve başka bir Windows cihaz kümesine atanmış farklı bir güvenlik duvarı ilkeniz olabilir. İlkelerinizle kullanılacak belirli cihaz gruplarını tanımlayabilirsiniz.

> [!NOTE]
> İş için Defender'da ilkeler oluştururken bir öncelik sırası atanır. Belirli bir cihaz kümesine birden çok ilke uygularsanız, bu cihazlar yalnızca ilk uygulanan ilkeyi alır. Daha fazla bilgi için bkz. [İş için Defender'da ilke sırasını anlama](mdb-policy-order.md).

Varsayılan cihaz gruplarınız ve tanımladığınız tüm özel cihaz grupları dahil olmak üzere tüm cihaz grupları [Azure Active Directory'de](/azure/active-directory/fundamentals/active-directory-whatis) (Azure AD) depolanır.

## <a name="create-a-new-device-group"></a>Yeni cihaz grubu oluşturma

Şu anda, İş için Defender'da, aşağıdaki yordamda açıklandığı gibi bir ilke oluşturma veya düzenleme sürecindeyken yeni bir cihaz grubu oluşturabilirsiniz: 

1. Microsoft 365 Defender portalına ([https://security.microsoft.com](https://security.microsoft.com)) gidin ve oturum açın.

2. Gezinti bölmesinde **Cihaz yapılandırması'nı** seçin. 

3. Aşağıdaki eylemlerden birini gerçekleştirin:

    1. Var olan bir ilkeyi seçin ve ardından **Düzenle'yi** seçin.
    2. Yeni bir ilke oluşturmak için **+ Ekle'yi** seçin.

    > [!TIP]
    > İlke oluşturma veya düzenleme konusunda yardım almak için bkz. [İş için Defender'da ilkeleri görüntüleme veya düzenleme](mdb-view-edit-policies.md).

4. **Genel bilgiler** adımında bilgileri gözden geçirin, gerekirse düzenleyin ve ardından **İleri'yi** seçin.

5. **+ Yeni grup oluştur'u** seçin. 

6. Cihaz grubu için bir ad ve açıklama belirtin ve ardından **İleri'yi** seçin.

7. Gruba eklenecek cihazları seçin ve ardından **Grup oluştur'u** seçin.

8. **Cihaz grupları** adımında, ilke için cihaz gruplarının listesini gözden geçirin. Gerekirse, listeden bir grubu kaldırın. Ardından **İleri'yi** seçin.

9. **Yapılandırma ayarları** sayfasında, ayarları gerektiği gibi gözden geçirin ve düzenleyin ve **ardından İleri'yi** seçin. Bu ayarlar hakkında daha fazla bilgi için bkz [. Yapılandırma ayarları](mdb-next-gen-configuration-settings.md).

10. **İlkenizi gözden geçirin** adımında tüm ayarları gözden geçirin, gerekli düzenlemeleri yapın ve ardından **İlke oluştur veya İlkeyi** **güncelleştir'i** seçin.

## <a name="view-an-existing-device-group"></a>Mevcut bir cihaz grubunu görüntüleme

Şu anda, İş için Defender'da, aşağıdaki yordamda açıklandığı gibi bir ilke oluşturma veya düzenleme sürecindeyken mevcut cihaz gruplarınızı görüntüleyebilirsiniz: 

1. Microsoft 365 Defender portalına ([https://security.microsoft.com](https://security.microsoft.com)) gidin ve oturum açın.

2. Gezinti bölmesinde **Cihaz yapılandırması'nı** seçin. 

3. Aşağıdaki eylemlerden birini gerçekleştirin:

    1. Var olan bir ilkeyi seçin ve ardından **Düzenle'yi** seçin.
    2. Yeni bir ilke oluşturmak için **+ Ekle'yi** seçin.

    > [!TIP]
    > İlke oluşturma veya düzenleme konusunda yardım almak için bkz. [İş için Defender'da ilkeleri görüntüleme veya düzenleme](mdb-view-edit-policies.md).

4. **Genel bilgiler** adımında bilgileri gözden geçirin, gerekirse düzenleyin ve ardından **İleri'yi** seçin.

5. **Var olan grubu kullan'ı** seçin. Açılır öğe açılır ve cihaz gruplarını görüntüler. Henüz herhangi bir cihaz grubunuz yoksa yeni bir cihaz grubu oluşturmanız istenir.

## <a name="what-does-the-add-all-devices-option-do"></a>Tüm Cihazları Ekle seçeneği ne yapar?

İlke oluştururken veya düzenlerken **Tüm cihazları ekle** seçeneğini görebilirsiniz.

:::image type="content" source="media/add-all-devices-option.png" alt-text="Tüm Cihazları Ekle seçeneğinin ekran görüntüsü.":::

Bu seçeneği belirlerseniz, Microsoft Intune'a kayıtlı tüm cihazlar varsayılan olarak oluşturduğunuz veya düzenlediğiniz ilkeyi alır. 

## <a name="next-steps"></a>Sonraki adımlar

Aşağıdaki görevlerden birini veya daha fazlasını seçin:

- [İlkeleri görüntüleme veya düzenleme](mdb-view-edit-policies.md)
- [Yeni ilke oluşturma](mdb-create-new-policy.md)
- [İş için Defender'da olayları görüntüleme ve yönetme](mdb-view-manage-incidents.md)
- [İş için Defender'da tehditlere yanıt verme ve tehditleri azaltma](mdb-respond-mitigate-threats.md)
- [İşlem merkezindeki düzeltme eylemlerini gözden geçirme](mdb-review-remediation-actions.md)