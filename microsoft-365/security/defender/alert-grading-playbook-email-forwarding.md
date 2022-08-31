---
title: Şüpheli e-posta iletme etkinliği için uyarı notları
description: Uyarıları gözden geçirmek ve saldırıyı düzeltmek ve ağınızı korumak için önerilen eylemleri uygulamak için şüpheli e-posta iletme etkinliği için uyarı notlama.
keywords: olaylar, uyarılar, araştırma, analiz etme, yanıt, bağıntı, saldırı, makineler, cihazlar, kullanıcılar, kimlikler, kimlik, posta kutusu, e-posta, 365, Microsoft, m365
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
search.appverid:
- MOE150
ms.openlocfilehash: 088cb74f16fae1155b86b1bfa6b5c72aae287720
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/31/2022
ms.locfileid: "67482108"
---
# <a name="alert-grading-for-suspicious-email-forwarding-activity"></a>Şüpheli e-posta iletme etkinliği için uyarı notları

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**
- Microsoft 365 Defender

Tehdit aktörleri, güvenliği aşılmış kullanıcı hesaplarını kullanıcının gelen kutusundaki e-postaları okuma, e-postaları dış alıcılara iletme ve kimlik avı postaları gönderme gibi çeşitli kötü amaçlı amaçlar için kullanabilir. Hedeflenen kullanıcı, e-postalarının iletildiğini bilmiyor olabilir. Bu, saldırganların kullanıcı hesapları tehlikeye atıldığında kullandığı çok yaygın bir taktiktir.

E-postalar el ile veya iletme kuralları kullanılarak otomatik olarak iletilebilir. Otomatik iletme, Gelen Kutusu Kuralları, Exchange Aktarım Kuralı (ETR) ve SMTP İletme gibi birden çok yolla uygulanabilir. El ile iletme kullanıcıların doğrudan eylem gerçekleştirmesini gerektirse de, otomatik olarak iletilen tüm e-postaların farkında olmayabilirler. Microsoft 365'te, kullanıcı bir e-postayı kötü amaçlı olabilecek bir e-posta adresine otomatik olarak ilettiğinde bir uyarı oluşturulur.

Bu playbook, Şüpheli Email İletme Etkinliği uyarılarını araştırmanıza ve bunları Doğru Pozitif (TP) veya Hatalı Pozitif (FP) olarak hızla notlamanıza yardımcı olur. Ardından, saldırıyı düzeltmek için TP uyarıları için önerilen eylemleri gerçekleştirebilirsiniz.

Office 365 için Microsoft Defender ve Microsoft Defender for Cloud Apps için uyarı not verme konusuna genel bakış için [giriş makalesine](alert-grading-playbooks.md) bakın.

Bu playbook'u kullanmanın sonuçları şunlardır:

- Otomatik iletilen e-postalarla ilişkili uyarıları kötü amaçlı (TP) veya iyi huylu (FP) etkinlikler olarak belirlediniz.

  Kötü amaçlıysa, etkilenen posta kutuları için [e-posta otomatik iletmeyi durdurdunuz](../office-365-security/external-email-forwarding.md) .

- E-postalar kötü amaçlı bir e-posta adresine iletildiyse gerekli eylemi yapmışsınızdır.

## <a name="email-forwarding-rules"></a>Email iletme kuralları

Email iletme kuralları, kullanıcıların kullanıcının posta kutusuna gönderilen e-posta iletilerini kuruluşun içindeki veya dışındaki başka bir kullanıcının posta kutusuna iletmek için bir kural oluşturmasına olanak tanır. Özellikle birden çok posta kutusu olan bazı e-posta kullanıcıları, işveren e-postalarını özel e-posta hesaplarına taşımak için iletme kurallarını yapılandırmaktadır. Email iletme kullanışlı bir özelliktir, ancak bilgilerin olası açığa çıkması nedeniyle güvenlik riski de oluşturabilir. Saldırganlar bu bilgileri kuruluşunuza veya iş ortaklarına saldırmak için kullanabilir.

### <a name="suspicious-email-forwarding-activity"></a>Şüpheli e-posta iletme etkinliği

Saldırganlar, kullanıcıdan gelen kötü amaçlı etkinliklerini gizlemek için güvenliği aşılmış kullanıcı posta kutusundaki gelen e-postaları gizlemek için e-posta kuralları ayarlayabilir. Ayrıca, e-postaları silmek, e-postaları RSS klasörü gibi daha az fark edilebilir başka bir klasöre taşımak veya e-postaları dış hesaba iletmek için güvenliği aşılmış kullanıcı posta kutusunda kurallar da ayarlayabilir.

Bazı kurallar tüm e-postaları başka bir klasöre taşıyabilir ve bunları "okundu" olarak işaretleyebilirken, bazı kurallar yalnızca e-posta iletisinde veya konuda belirli anahtar sözcükler içeren postaları taşıyabilir. Örneğin, gelen kutusu kuralı diğerleri arasında "fatura", "kimlik avı", "yanıtlama", "şüpheli e-posta" veya "istenmeyen posta" gibi anahtar sözcükleri aramak ve bunları bir dış e-posta hesabına taşımak için ayarlanabilir. Saldırganlar istenmeyen postaları, kimlik avı e-postalarını veya kötü amaçlı yazılımları dağıtmak için güvenliği aşılmış kullanıcı posta kutusunu da kullanabilir.

Office 365 için Microsoft Defender şüpheli e-posta iletme kurallarını algılayabilir ve uyarır ve böylece gizli kuralları kaynakta bulup silebilirsiniz.

Daha fazla bilgi için şu blog gönderilerine bakın:

- [İş Email Güvenliğinin Aşılmasına Neden Olan](https://techcommunity.microsoft.com/t5/microsoft-defender-for-office/business-email-uncompromised-part-one/ba-p/2159900)
- [İş e-posta güvenliğinin aşılması sahne arkası: Büyük bir BEC kampanyasını kesintiye uğratmak için etki alanları arası tehdit verilerini kullanma](https://www.microsoft.com/security/blog/2021/06/14/behind-the-scenes-of-business-email-compromise-using-cross-domain-threat-data-to-disrupt-a-large-bec-infrastructure/)

## <a name="alert-details"></a>Uyarı ayrıntıları

Şüpheli Email İletme Etkinliği uyarısını gözden geçirmek için, **Etkinlik listesi** bölümünü görmek için **Uyarılar** sayfasını açın. İşte bir örnek.

:::image type="content" source="../../media/alert-grading-playbook-email-forwarding/alert-grading-playbook-email-forwarding-activity-list.png" alt-text="Uyarıyla ilgili etkinliklerin listesi" lightbox="../../media/alert-grading-playbook-email-forwarding/alert-grading-playbook-email-forwarding-activity-list.png":::

Kenar çubuğunda bu etkinliğin ayrıntılarını görüntülemek için **Etkinlik'i**  seçin. İşte bir örnek.

:::image type="content" source="../../media/alert-grading-playbook-email-forwarding/alert-grading-playbook-email-forwarding-activity-details.png" alt-text="Etkinliğin ayrıntıları" lightbox="../../media/alert-grading-playbook-email-forwarding/alert-grading-playbook-email-forwarding-activity-details.png":::

**Neden** alanı, bu uyarıyla ilgili aşağıdaki bilgileri içerir.

- İletme Türü (FT) aşağıdakilerden biridir:
  - Exchange Aktarım Kuralı (ETR): ve Exchange Aktarım Kuralı kullanılarak iletildi
  - SMTP: Posta Kutusu İletme kullanılarak iletildi
  - Gelen KutusuRule: Gelen Kutusu Kuralı kullanılarak iletildi

- İleti İzleme Kimliği (MTI): Bu uyarıyı tetikleyen iletilen e-postanın tanımlayıcısı (NetworkMessageId). NetworkMessageId, kuruluşunuzdaki bir e-postanın benzersiz tanımlayıcısıdır.
- İletici (F): Bu e-postayı ileden kullanıcı.
- Şüpheli Alıcı Listesi (SRL): Bu e-postada şüpheli olarak kabul edilen alıcıların listesi.
- Alıcı Listesi (RL): Bu e-postadaki tüm alıcıların listesi.

## <a name="investigation-workflow"></a>Araştırma iş akışı

Bu uyarıyı araştırırken şunları belirlemeniz gerekir:

- Kullanıcı hesabı ve posta kutusu tehlikeye girdi mi?
- Etkinlikler kötü amaçlı mı?

### <a name="is-the-user-account-and-its-mailbox-compromised"></a>Kullanıcı hesabı ve posta kutusu tehlikeye girdi mi?

Gönderenin geçmiş davranışlarına ve son etkinliklerine bakarak, kullanıcının hesabının gizliliğinin ihlal edilmiş olarak kabul edilip edilmeyeceğini saptayabilmelisiniz. Microsoft 365 Defender portalında kullanıcının sayfasından alınan uyarıların ayrıntılarını görebilirsiniz.

Etkilenen posta kutusu için bu ek etkinlikleri de analiz edebilirsiniz:

- E-postayla ilgili tehditleri anlamak için Tehdit Gezgini'ni kullanma
  - Gönderen tarafından gönderilen en son e-postalardan kaçının kimlik avı, istenmeyen posta veya kötü amaçlı yazılım olarak algılandığından gözlemleyin.
  - Gönderilen e-postaların kaç tanesinde hassas bilgiler olduğunu gözlemleyin.

- Microsoft Azure portal riskli oturum açma davranışını değerlendirin.
- Kullanıcının cihazındaki kötü amaçlı etkinlikleri denetleyin.

### <a name="are-the-activities-malicious"></a>Etkinlikler kötü amaçlı mı?

E-posta iletme etkinliğini araştırma. Örneğin, e-postanın türünü, bu e-postanın alıcısını veya e-postanın nasıl iletildiğine bakın.

Daha fazla bilgi için aşağıdaki makalelere bakın:

- [Otomatik iletilen iletiler içgörüsü](/microsoft-365/security/office-365-security/mfi-auto-forwarded-messages-report)
- [E-posta içgörüsü ileten yeni kullanıcılar](/microsoft-365/security/office-365-security/mfi-new-users-forwarding-email)
- [Güvenliği Aşılmış Email Hesabına Yanıt Verme](/microsoft-365/security/office-365-security/responding-to-a-compromised-email-account)
- [Outlook'ta yanlış pozitifleri ve yanlış negatifleri bildirme](/microsoft-365/security/office-365-security/report-false-positives-and-false-negatives)

Şüpheli e-posta iletme etkinliklerini tanımlamaya yönelik iş akışı aşağıdadır.

:::image type="content" source="../../media/alert-grading-playbook-email-forwarding/alert-grading-playbook-email-forwarding-workflow.png" alt-text="E-posta iletme için uyarı araştırma iş akışı" lightbox="../../media/alert-grading-playbook-email-forwarding/alert-grading-playbook-email-forwarding-workflow.png":::

Tehdit Gezgini'ni kullanarak veya Microsoft 365 Defender portalındaki özelliklerin kullanılabilirliğine bağlı olarak gelişmiş tehdit avcılığı sorgularıyla bir e-posta iletme uyarısını araştırabilirsiniz. İşlemin tamamını veya sürecin bir bölümünü gerektiği gibi takip etmeyi seçebilirsiniz.

## <a name="using-threat-explorer"></a>Tehdit Gezgini'nin kullanımı

Tehdit Gezgini, bu etkinliğin şüpheli olup olmadığını belirlemek için e-postayla ilgili tehditler için etkileşimli bir araştırma deneyimi sağlar. Uyarı bilgilerinden aşağıdaki göstergeleri kullanabilirsiniz:

- SRL/RL: Şu ayrıntıları bulmak için (Şüpheli) Alıcılar Listesi'ni (SRL) kullanın:

    :::image type="content" source="../../media/alert-grading-playbook-email-forwarding/alert-grading-playbook-email-forwarding-recipients-list.png" alt-text="Alıcı listesi örneği" lightbox="../../media/alert-grading-playbook-email-forwarding/alert-grading-playbook-email-forwarding-recipients-list.png":::

  - Başka kim bu alıcılara e-posta iletmiştir?
  - Bu alıcılara kaç e-posta iletildi?
  - E-postalar bu alıcılara ne sıklıkta iletilir?

- MTI: Şu ayrıntıları bulmak için İleti İzleme Kimliği/Ağ İleti Kimliği'ni kullanın:

    :::image type="content" source="../../media/alert-grading-playbook-email-forwarding/alert-grading-playbook-email-forwarding-network-message-id.png" alt-text="Ağ İletisi Kimliği örneği" lightbox="../../media/alert-grading-playbook-email-forwarding/alert-grading-playbook-email-forwarding-network-message-id.png":::

  - Bu e-posta için hangi ek ayrıntılar sağlanır? Örneğin: konu, dönüş yolu ve zaman damgası.
  - Bu e-postanın kaynağı nedir? Benzer e-postalar var mı?
  - Bu e-posta herhangi bir URL içeriyor mu? URL herhangi bir hassas veriye işaret eder mi?
  - E-postada ek var mı? Ekler hassas bilgiler içeriyor mu?
  - E-postada gerçekleştirilen eylem neydi? Silindi mi, okundu olarak işaretlendi mi veya başka bir klasöre taşındı mı?
  - Bu e-postayla ilişkili tehditler var mı? Bu e-posta herhangi bir kampanyanın parçası mı?

Bu soruların yanıtlarına bağlı olarak, bir e-postanın kötü amaçlı mı yoksa zararsız mı olduğunu saptayabilmeniz gerekir.

## <a name="advanced-hunting-queries"></a>Gelişmiş tehdit avcılığı sorguları

Bir uyarıyla ilgili bilgileri toplamak ve etkinliğin şüpheli olup olmadığını belirlemek için [gelişmiş Tehdit Avcılığı](advanced-hunting-overview.md) sorgularını kullanmak için aşağıdaki tablolara erişiminiz olduğundan emin olun:

- EmailEvents - E-posta akışıyla ilgili bilgileri içerir.

- EmailUrlInfo - E-postalardaki URL'ler ile ilgili bilgileri içerir.

- CloudAppEvents -Kullanıcı etkinliklerinin denetim günlüğünü içerir.

- IdentityLogonEvents - Tüm kullanıcılar için oturum açma bilgilerini içerir.

> [!NOTE]
> Bazı parametreler kuruluşunuza veya ağınıza özgüdür. Her sorguda açıklandığı gibi bu belirli parametreleri doldurun.

Başka kimlerin bu alıcılara e-posta ilettiğini (SRL/RL) bulmak için bu sorguyu çalıştırın.

```kusto
let srl=pack_array("{SRL}"); //Put values from SRL here.
EmailEvents
| where RecipientEmailAddress in (srl)
| distinct SenderDisplayName, SenderFromAddress, SenderObjectId
```

Bu alıcılara kaç e-posta iletildiğini öğrenmek için bu sorguyu çalıştırın.

```kusto
let srl=pack_array("{SRL}"); //Put values from SRL here.
EmailEvents
| where RecipientEmailAddress in (srl)
| summarize Count=dcount(NetworkMessageId) by RecipientEmailAddress
```

E-postaların bu alıcılara ne sıklıkta ilettiğini öğrenmek için bu sorguyu çalıştırın.

```kusto
let srl=pack_array("{SRL}"); //Put values from SRL here.
EmailEvents
| where RecipientEmailAddress in (srl)
| summarize Count=dcount(NetworkMessageId) by RecipientEmailAddress, bin(Timestamp, 1d)
```

E-postanın URL'leri olup olmadığını öğrenmek için bu sorguyu çalıştırın.

```kusto
let mti='{MTI}'; //Replace {MTI} with MTI from alert
EmailUrlInfo
| where NetworkMessageId == mti
```

E-postada ek olup olmadığını öğrenmek için bu sorguyu çalıştırın.

   ```kusto
   let mti='{MTI}'; //Replace {MTI} with MTI from alert
   EmailAttachmentInfo
   | where NetworkMessageId == mti
   ```

İleticinin (gönderen) yeni kurallar oluşturup oluşturmadığını öğrenmek için bu sorguyu çalıştırın.

```kusto
let sender = "{SENDER}"; //Replace {SENDER} with display name of Forwarder
let action_types = pack_array(
    "New-InboxRule",
    "UpdateInboxRules",
    "Set-InboxRule",
    "Set-Mailbox",
    "New-TransportRule",
    "Set-TransportRule");
CloudAppEvents
| where AccountDisplayName == sender
| where ActionType in (action_types)
```

Bu kullanıcıdan gelen anormal oturum açma olayları olup olmadığını öğrenmek için bu sorguyu çalıştırın. Örneğin: bilinmeyen IP'ler, yeni uygulamalar, yaygın olmayan ülkeler, birden çok LogonFailed olayı.

```kusto
let sender = "{SENDER}"; //Replace {SENDER} with email of the Forwarder
IdentityLogonEvents
| where AccountUpn == sender
```

### <a name="investigating-forwarding-rules"></a>İletme kurallarını araştırma

Ayrıca, kural türüne (uyarıdaki FT değeri) göre Exchange yönetim merkezini kullanarak şüpheli iletme kurallarını da bulabilirsiniz.

- Etr

  Exchange aktarım kuralları **Kurallar** bölümünde listelenir. Tüm kuralların beklendiği gibi olduğunu doğrulayın.

- SMTP

  Gönderenin posta kutusunu **Yönet posta akışı ayarlarını \> seçerek posta kutusu\> iletme kurallarını görebilirsiniz Email İlet \> Düzenle'yi iletebilirsiniz**.

- Gelen KutusuRule

  Gelen kutusu kuralları e-posta istemcisiyle yapılandırılır. Kullanıcılar tarafından oluşturulan gelen kutusu kurallarını listelemek için [Get-InboxRule](/powershell/module/exchange/get-inboxrule) PowerShell cmdlet'ini kullanabilirsiniz.

### <a name="additional-investigation"></a>Ek araştırma

Şimdiye kadar bulunan kanıtlarla birlikte yeni iletme kuralları oluşturulup oluşturulmadığını belirleyebilirsiniz. Kuralla ilişkili IP adresini araştırın. Bunun anormal bir IP adresi olmadığından ve kullanıcı tarafından gerçekleştirilen olağan etkinliklerle tutarlı olduğundan emin olun.

## <a name="recommended-actions"></a>Önerilen eylemler

İlişkili etkinliklerin bu uyarıyı Gerçek Pozitif hale getireceğini belirledikten sonra uyarıyı sınıflandırın ve düzeltme için şu eylemleri gerçekleştirin:

1. Gelen kutusu iletme kuralını devre dışı bırakın ve silin.
2. Gelen KutusuRule iletme türü için kullanıcının hesap kimlik bilgilerini sıfırlayın.
3. SMTP veya ETR iletme türü için uyarıyı oluşturan kullanıcı hesabının etkinliklerini araştırın.

    - Diğer şüpheli yönetici etkinliklerini araştırın.

    - Kullanıcı hesabının kimlik bilgilerini sıfırlayın.

4. Etkilenen hesaplardan, IP adreslerinden ve şüpheli gönderenlerden kaynaklanan ek etkinlikleri denetleyin.

## <a name="see-also"></a>Ayrıca bkz.

- [Uyarı notlama genel bakış](alert-grading-playbooks.md)
- [Şüpheli gelen kutusu iletme kuralları](alert-grading-playbook-inbox-forwarding-rules.md)
- [Şüpheli gelen kutusu işleme kuralları](alert-grading-playbook-inbox-manipulation-rules.md)
- [Uyarıları araştırın](investigate-alerts.md)
