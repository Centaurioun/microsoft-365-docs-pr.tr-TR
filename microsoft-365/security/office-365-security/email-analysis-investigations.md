---
title: Office 365 için Microsoft Defender araştırmalarında Email analizi
f1.keywords:
- NOCSH
author: dansimp
ms.author: dansimp
manager: dansimp
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.collection:
- m365-security
- m365initiative-defender-office365
keywords: otomatik olay yanıtı, araştırma, düzeltme, tehdit koruması
description: araştırmalarda e-posta analizinin Office 365 için Microsoft Defender nasıl çalıştığını görün.
ms.custom:
- air
- seo-marvel-mar2020
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 1d7c4f0f01f1aff00e36e5930fa9566e1f6a7993
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/27/2022
ms.locfileid: "68048648"
---
# <a name="email-analysis-in-investigations-for-microsoft-defender-for-office-365"></a>Office 365 için Microsoft Defender araştırmalarında Email analizi

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Uygulandığı öğe**
- [Office 365 için Microsoft Defender plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Uyarıların otomatik araştırması sırasında, Office 365 için Microsoft Defender özgün e-postayı tehditler için analiz eder ve özgün e-postayla ilgili ve bir saldırının olası bir parçası olan diğer e-postaları tanımlar. Bu analiz önemlidir çünkü e-posta saldırıları nadiren tek bir e-postadan oluşur.

Otomatik araştırmanın e-posta analizi, kuruluşunuz tarafından gönderilen ve alınan e-postaları sorgulamak için özgün e-postadaki öznitelikleri kullanarak e-posta kümelerini tanımlar. Bu, bir güvenlik operasyonları analistinin Gezgin veya Gelişmiş Avcılık'ta ilgili e-postaları avlamasına benzer. Saldırganlar genellikle güvenlik algılamasını önlemek için e-posta parametrelerini biçimlendirdiğinden eşleşen e-postaları tanımlamak için çeşitli sorgular kullanılır. Kümeleme analizi, araştırmada yer alan e-postaların nasıl işleneceğini belirlemek için şu denetimleri gerçekleştirir:

- E-posta analizi, ilişkili e-postaları bulmak için özgün e-postadaki öznitelikleri (gönderen değerleri (IP adresi, gönderen etki alanı) ve içerikleri (konu, küme kimliği) kullanarak e-postaların sorgularını (kümeleri) oluşturur.
- Özgün e-postanın URL'lerinin ve dosyalarının analizi, bazılarının kötü amaçlı olduğunu (kötü amaçlı yazılım veya kimlik avı) tanımlarsa, kötü amaçlı URL veya dosyayı içeren sorgular veya e-posta kümeleri de oluşturur.
- Email kümeleme analizi, kümedeki eşleşen e-postalarla ilişkili tehditleri sayarak e-postaların kötü amaçlı, şüpheli veya net tehditlere sahip olup olmadığını belirler. Sorguyla eşleşen e-posta kümesinde yeterli miktarda istenmeyen posta, normal kimlik avı, yüksek güvenilirlikli kimlik avı veya kötü amaçlı yazılım tehditleri varsa, e-posta kümesi bu tehdit türüne uygulanır.
- E-posta kümeleme analizi, e-postaların hala kaldırılması gerekip gerekmediğini veya düzeltilmiş veya engellenmiş olup olmadığını belirlemeye yardımcı olmak için özgün e-postanın ve e-posta kümelerindeki e-postaların en son teslim konumunu da denetler. Saldırganlar kötü amaçlı içeriğe ek olarak güvenlik ilkeleri ve koruma posta kutuları arasında değişiklik gösterebileceğinden bu çözümleme önemlidir. Bu özellik, sıfır saatlik otomatik temizleme (ZAP) ile bir veya daha fazla kötü amaçlı e-posta algılanıp kaldırılmış olsa bile kötü amaçlı içeriğin posta kutularında hala bulunabileceği durumlara yol açar.
- Kötü amaçlı yazılım, yüksek güvenilirlikli kimlik avı, kötü amaçlı dosyalar veya kötü amaçlı URL tehditleri nedeniyle kötü amaçlı olarak kabul edilen Email kümeleri, bulut posta kutusunda (gelen kutusu veya gereksiz klasör) bulunan e-postaları geçici olarak silmek için bekleyen bir eylem alır. Kötü amaçlı e-postalar veya e-posta kümeleri yalnızca "Posta Kutusunda Değil" (engellendi, karantinaya alındı, başarısız, geçici olarak silindi vb.) veya bulut posta kutusunda hiçbiri olmayan "Şirket İçi/Dış" ise, bunları kaldırmak için bekleyen hiçbir eylem ayarlanmaz.
- E-posta kümelerinden herhangi birinin kötü amaçlı olduğu belirlenirse, küme tarafından tanımlanan tehdit araştırmada yer alan özgün e-postaya geri uygulanır. Bu davranış, eşleşen e-postalara göre özgün bir e-postanın kararını belirlemek için e-posta avcılığı sonuçlarını kullanan bir güvenlik operasyonları analistine benzer. Bu sonuç, özgün bir e-postanın URL'lerinin, dosyalarının veya kaynak e-posta göstergelerinin algılanıp algılanmadığına bakılmaksızın, sistemin kişiselleştirme, dönüşüm, kaçınma veya diğer saldırgan teknikleri aracılığıyla algılamayı atlatabilecek kötü amaçlı e-postaları tanımlamasını sağlar.
- Kullanıcı güvenliğinin aşılmasına yönelik araştırmada, posta kutusu tarafından oluşturulan olası e-posta sorunlarını belirlemek için ek e-posta kümeleri oluşturulur. Bu işlem temiz bir e-posta kümesi (kullanıcıdan iyi e-postalar, olası veri sızdırma ve olası komut/denetim e-postaları), şüpheli e-posta kümeleri (istenmeyen posta veya normal kimlik avı içeren e-postalar) ve kötü amaçlı e-posta kümelerini (kötü amaçlı yazılım veya yüksek güvenilirlikli kimlik avı içeren e-postalar) içerir. Bu e-posta kümeleri, güvenlik operasyonları analistlerine güvenlik işlemleri analistleri verilerini, bir riskten kaynaklanan diğer sorunların giderilmesi gerekebileceğini ve özgün uyarıları tetiklemiş olabilecek e-postaların görünürlüğünü (örneğin, kullanıcı gönderme kısıtlamalarını tetikleyen kimlik avı/istenmeyen posta) sağlar

Benzerlik ve kötü amaçlı varlık sorguları aracılığıyla kümeleme analizi Email, bir saldırıdan yalnızca bir e-posta tanımlansa bile e-posta sorunlarının tam olarak tanımlanmasını ve temizlenmesini sağlar. E-posta kümesi ayrıntıları yan panel görünümlerindeki bağlantıları kullanarak sorguları Gezgin'de veya Gelişmiş Tehdit Avcılığı'nda açarak daha ayrıntılı analiz yapabilir ve gerekirse sorguları değiştirebilirsiniz. Bu özellik, e-posta kümesinin sorgularını çok dar veya çok geniş (ilişkisiz e-postalar dahil) bulursanız el ile iyileştirme ve düzeltme sağlar.

Araştırmalarda e-posta analizine yönelik ek geliştirmeler aşağıdadır.

## <a name="air-investigation-ignores-advanced-delivery-items-secops-mailbox-and-phishedu-messages"></a>AIR araştırması gelişmiş teslim öğelerini yoksayar (SecOps posta kutusu ve PhishEDU iletileri)

E-posta kümeleme analizi sırasında, tüm kümeleme sorguları Gelişmiş Teslim ilkesinde Güvenlik İşlemleri posta kutuları olarak ayarlanan güvenlik posta kutularını yoksayar. Benzer şekilde, e-posta kümeleme sorguları Gelişmiş Teslim ilkesinde yapılandırılan kimlik avı benzetimi (eğitim) iletilerini yoksayar. Kümeleme özniteliklerinin daha basit ve daha kolay okunmasını sağlamak için sorguda SecOps veya PhishEdu dışlama değerleri gösterilmez. Bu dışlama, tehdit analizi sırasında tehdit bilgileri ve işletim posta kutularının (SecOps posta kutuları) ve kimlik avı simülasyonlarının (PhishEdu) yoksayılmasını ve herhangi bir düzeltme sırasında kaldırılmamasını sağlar.

>[!Note]
>E-posta kümesi ayrıntılarından Explorer'da görüntülemek üzere bir e-posta kümesini açarken, Explorer'da PhishEdu ve SecOps posta kutusu filtreleri uygulanır ancak gösterilmez. Gezgin filtrelerini, tarihlerini değiştirir veya sayfadaki sorguyu yenilerseniz, PhishEdu/SecOps filtre dışlamaları kaldırılır ve bunlarla eşleşen e-postalar bir kez daha gösterilir. Tarayıcı yenileme işlevini kullanarak Gezgin sayfasını yenilerseniz, PhishEdu/SecOps filtreleri de dahil olmak üzere özgün sorgu filtreleri yeniden yüklenir ancak daha sonra yaptığınız tüm değişiklikler kaldırılır.
>

## <a name="air-updates-pending-email-action-status"></a>AIR güncelleştirmeleri bekleyen e-posta eylemi durumu

Araştırma e-posta analizi, araştırma kanıtını ve eylemlerini oluşturmak için araştırma sırasındaki e-posta tehditlerini ve konumlarını hesaplar. Araştırma dışındaki eylemler araştırmada yer alan e-postaları etkilediğinde bu veriler eski ve eski olabilir. Örneğin, güvenlik operasyonları el ile avcılık ve düzeltme, bir araştırmada yer alan e-postaları temizleyebilecektir. Benzer şekilde, paralel araştırmalarda onaylanan silme eylemleri veya Sıfır saatlik otomatik temizleme (ZAP) otomatik karantina eylemleri e-postaları kaldırmış olabilir. Ayrıca, e-posta teslimi sonrasında tehditlerin gecikmeli algılanması, araştırmanın e-posta sorgularına/kümelerine dahil edilen tehditlerin sayısını değiştirebilir.

Araştırma eylemlerinin güncel olduğundan emin olmak için bekleyen eylemlerin bulunduğu tüm araştırmalarda, e-posta konumlarını ve tehditlerini güncelleştirmek için e-posta analizi sorguları düzenli aralıklarla yeniden çalıştırılır.

- E-posta kümesi verileri değiştiğinde tehdit ve en son teslim konumu sayısı güncelleştirilir.
- Bekleyen eylemleri olan e-postalar veya e-posta kümesi artık posta kutusunda değilse, bekleyen eylem iptal edilir ve kötü amaçlı e-posta/küme düzeltildi olarak kabul edilir.
- Araştırmanın tüm tehditleri yukarıda belirtildiği gibi düzeltildikten veya iptal edildikten sonra, araştırma düzeltilmiş duruma geçirilir ve özgün uyarı çözümlenir.

## <a name="the-display-of-incident-evidence-for-email-and-email-clusters"></a>E-posta ve e-posta kümeleri için olay kanıtının görüntülenmesi

Bir olayın **Kanıt ve Yanıt** sekmesindeki Email tabanlı kanıt artık aşağıdaki bilgileri görüntüler.

:::image type="content" source="../../media/email-analysis-investigations/email-analysis-evidence-example.png" alt-text="Kanıt ve Yanıt'taki e-posta analizi bilgileri" lightbox="../../media/email-analysis-investigations/email-analysis-evidence-example.png":::

Şekildeki numaralandırılmış açıklama balonlarından:

1. **İşlem Merkezi'ne** ek olarak düzeltme eylemleri de gerçekleştirebilirsiniz.
2. **Kötü amaçlı** bir karara sahip (ancak **Şüpheli** olmayan) e-posta kümeleri için düzeltme eylemi gerçekleştirebilirsiniz.
3. E-posta istenmeyen postası kararı için kimlik avı yüksek güvenilirlik ve normal kimlik avı olarak bölünür.

   Kötü amaçlı bir karar için tehdit kategorileri kötü amaçlı yazılım, yüksek güvenilirlikli kimlik avı, kötü amaçlı URL ve kötü amaçlı dosyadır.

   Şüpheli bir karar için tehdit kategorileri istenmeyen posta ve normal kimlik avıdır.

4. e-posta sayısı, en son teslim konumunu temel alır ve posta kutularındaki ve şirket içi posta kutularındaki değil, posta kutularındaki e-posta sayaçlarını içerir.
5. En son veriler için güncelleştirilebilecek sorgunun tarih ve saatini içerir.

Bir olayın **Varlıklar** sekmesindeki e-posta veya e-posta kümeleri için **Engellendi** , bu öğe (posta veya küme) için posta kutusunda kötü amaçlı e-posta olmadığı anlamına gelir. Burada bir örnek verilmiştir.

:::image type="content" source="../../media/email-analysis-investigations/email-analysis-evidence-example-prevented.png" alt-text="Engellenen bir e-posta." lightbox="../../media/email-analysis-investigations/email-analysis-evidence-example-prevented.png":::

Bu örnekte, e-posta kötü amaçlıdır ancak posta kutusunda değildir.

## <a name="next-steps"></a>Sonraki adımlar

- [Bekleyen veya tamamlanan düzeltme eylemlerini görüntüleme](air-review-approve-pending-completed-actions.md)
