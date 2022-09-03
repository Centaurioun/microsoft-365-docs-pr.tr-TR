---
title: Saldırı yüzeyini azaltmayı (ASR) anlama ve kullanma
ms.reviewer: ''
description: Uç Nokta için Microsoft Defender saldırı yüzeyi azaltma özellikleri hakkında bilgi edinin.
keywords: asr, saldırı yüzeyi azaltma, saldırı yüzeyi azaltma kuralları, Uç Nokta için Microsoft Defender, microsoft defender, virüsten koruma, av, windows defender
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: jweston-1
ms.author: v-jweston
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.custom: asr
ms.topic: conceptual
ms.subservice: mde
ms.collection:
- m365initiative-m365-defender
- M365-security-compliance
ms.date: 05/16/2022
ms.openlocfilehash: 08143912df1a8607b616cadfb4df0942a0054343
ms.sourcegitcommit: d3ef9391f621e8f4ca70661184b3bb82c6cbda94
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/02/2022
ms.locfileid: "67582438"
---
# <a name="understand-and-use-attack-surface-reduction-capabilities"></a>Saldırı yüzeyi azaltma özelliklerini anlama ve kullanma

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [Uç Nokta için Microsoft Defender Planı 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Uç Nokta için Microsoft Defender Planı 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender Virüsten Koruma

**Platform**
- Windows

> [!TIP]
> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Saldırı yüzeyleri, kuruluşunuzun siber tehditlere ve saldırılara karşı savunmasız olduğu tüm yerlerdir. Uç Nokta için Defender, saldırı yüzeylerinizi azaltmaya yardımcı olacak çeşitli özellikler içerir. Saldırı yüzeyini azaltma hakkında daha fazla bilgi edinmek için aşağıdaki videoyu izleyin.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4woug]

## <a name="configure-attack-surface-reduction-capabilities"></a>Saldırı yüzeyi azaltma özelliklerini yapılandırma

Ortamınızda saldırı yüzeyi azaltmayı yapılandırmak için şu adımları izleyin:

1. [Microsoft Edge için donanım tabanlı yalıtımı etkinleştirin](/windows/security/threat-protection/microsoft-defender-application-guard/install-md-app-guard).

2. [Saldırı yüzeyi azaltma kurallarını etkinleştirme](attack-surface-reduction-rules-deployment.md)

3. Uygulama denetimini etkinleştirin.

   1. Windows'ta temel ilkeleri gözden geçirin. Bkz [. Örnek Temel İlkeler](/windows/security/threat-protection/windows-defender-application-control/example-wdac-base-policies).
   2. [Uygulama Denetimi tasarım kılavuzuna Windows Defender](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-design-guide) bakın.
   3. Bkz[. Windows Defender Uygulama Denetimi (WDAC) ilkelerini dağıtma](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-deployment-guide).

4. [Denetimli klasör erişimini etkinleştirin](enable-controlled-folders.md).

5. [Çıkarılabilir depolama birimi korumasını](device-control-removable-storage-protection.md) etkinleştirme

6. [Ağ korumasını açın](enable-network-protection.md).

7. [Web korumasını](web-protection-overview.md) etkinleştirme

8. [Yararlanma korumasını etkinleştirin](enable-exploit-protection.md).

9. Ağ güvenlik duvarınızı ayarlayın.

   1. [Gelişmiş güvenlik özelliklerine sahip Windows Defender Güvenlik Duvarı'na](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security) genel bir bakış edinin.
   2. Güvenlik duvarı ilkelerinizi nasıl tasarlamak istediğinize karar vermek için Windows Defender Güvenlik Duvarı [tasarım kılavuzunu](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-design-guide) kullanın.
   3. Kuruluşunuzun [güvenlik duvarını](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-deployment-guide) gelişmiş güvenlikle ayarlamak için Windows Defender Güvenlik Duvarı dağıtım kılavuzunu kullanın.

> [!TIP]
> Çoğu durumda, saldırı yüzeyi azaltma özelliklerini yapılandırırken çeşitli yöntemler arasından seçim yapabilirsiniz:
>
> - Microsoft Endpoint Manager (artık Microsoft Intune ve Microsoft Endpoint Configuration Manager içerir)
> - Grup İlkesi
> - PowerShell cmdlet'leri

## <a name="test-attack-surface-reduction-in-microsoft-defender-for-endpoint"></a>Uç Nokta için Microsoft Defender'de saldırı yüzeyini azaltmayı test edin

Kuruluşunuzun güvenlik ekibinin bir parçası olarak, nasıl çalışacaklarını görmek için saldırı yüzeyi azaltma özelliklerini denetim modunda çalışacak şekilde yapılandırabilirsiniz. Denetim modunda aşağıdaki ASR güvenlik özelliklerini etkinleştirebilirsiniz:

- Saldırı yüzeyini azaltma kuralları
- Exploit Protection
- Ağ koruması
- Denetimli klasör erişimi
- Cihaz denetimi

Denetim modu, özelliği etkinleştirmiş olsaydınız neler *olacağının* kaydını görmenizi sağlar.

Özelliklerin nasıl çalışacağını test ederken denetim modunu etkinleştirebilirsiniz. Yalnızca test için denetim modunun etkinleştirilmesi, denetim modunun iş kolu uygulamalarınızı etkilemesini önlemeye yardımcı olur. Ayrıca belirli bir süre içinde kaç şüpheli dosya değişikliği girişimi gerçekleştiği hakkında da bir fikir edinebilirsiniz.

Özellikler uygulamaların, betiklerin veya dosyaların değiştirilmesini engellemez veya engellemez. Ancak Windows Olay Günlüğü, özelliklerin tamamen etkin olduğu gibi olayları kaydeder. Denetim moduyla, etkinse özelliğin neleri etkileyeceğini görmek için olay günlüğünü gözden geçirebilirsiniz.

Denetlenen girdileri bulmak için Microsoft **Windows** \> **Windows Defender** \> **İşletimsel** **Uygulamalar ve Hizmetler'e** \>  \> gidin.

Her olayla ilgili daha fazla ayrıntı almak için Uç Nokta için Defender'ı kullanın. Bu ayrıntılar özellikle saldırı yüzeyi azaltma kurallarını araştırmak için yararlıdır. Uç Nokta için Defender konsolunu kullanmak [, uyarı zaman çizelgesi ve araştırma senaryolarının bir parçası olarak sorunları araştırmanıza](investigate-alerts.md) olanak tanır.

grup ilkesi, PowerShell ve yapılandırma hizmeti sağlayıcılarını (CSP) kullanarak denetim modunu etkinleştirebilirsiniz.

| Denetim seçenekleri | Denetim modunu etkinleştirme | Olayları görüntüleme |
|---|---|---|
| Denetim tüm olaylar için geçerlidir | [Denetimli klasör erişimini etkinleştirin](enable-controlled-folders.md) | [Denetimli klasör erişim olayları](evaluate-controlled-folder-access.md#review-controlled-folder-access-events-in-windows-event-viewer) |
| Denetim tek tek kurallar için geçerlidir | [1. Adım: Denetim modunu kullanarak ASR kurallarını test edin](attack-surface-reduction-rules-deployment-test.md#step-1-test-asr-rules-using-audit) | [2. Adım: Saldırı yüzeyi azaltma kuralları raporlama sayfasını anlama](attack-surface-reduction-rules-deployment-test.md#step-2-understand-the-attack-surface-reduction-rules-reporting-page-in-the-microsoft-365-defender-portal) |
| Denetim tüm olaylar için geçerlidir | [Ağ korumasını etkinleştirme](enable-network-protection.md) | [Ağ koruma olayları](evaluate-network-protection.md#review-network-protection-events-in-windows-event-viewer) |
| Denetim, tek tek risk azaltmaları için geçerlidir | [Exploit Protection'i etkinleştirin](enable-exploit-protection.md) | [Güvenlik açığından yararlanma koruma olayları](exploit-protection.md#review-exploit-protection-events-in-windows-event-viewer) |

Örneğin, saldırı yüzeyi azaltma kurallarını etkinleştirmeden (blok modu) önce denetim modunda test edebilirsiniz. Saldırı yüzeyi azaltma (ASR) kuralları yaygın, bilinen saldırı yüzeylerini sağlamlaştırmak için önceden tanımlanmıştır. Saldırı yüzeyi azaltma kurallarını uygulamak için kullanabileceğiniz çeşitli yöntemler vardır. Tercih edilen yöntem aşağıdaki saldırı yüzeyi azaltma (ASR) kuralları dağıtım konularında belgelenmiştir:

- [Saldırı yüzeyini azaltma (ASR) kuralları dağıtımına genel bakış](attack-surface-reduction-rules-deployment.md)
- [Saldırı yüzeyini azaltma (ASR) kuralları dağıtım planı](attack-surface-reduction-rules-deployment-plan.md)
- [Saldırı yüzeyini azaltma (ASR) kuralları testi](attack-surface-reduction-rules-deployment-test.md)
- [Saldırı yüzeyini azaltma (ASR) kurallarını etkinleştirme](attack-surface-reduction-rules-deployment-implement.md)
- [Saldırı yüzeyini azaltma (ASR) kurallarını kullanıma hazır hale getirme](attack-surface-reduction-rules-deployment-operationalize.md)

## <a name="view-attack-surface-reduction-events"></a>Saldırı yüzeyi azaltma olaylarını görüntüleme

Hangi kuralların veya ayarların çalıştığını izlemek için Olay Görüntüleyicisi saldırı yüzeyi azaltma olaylarını gözden geçirin. Ayrıca herhangi bir ayarın çok "gürültülü" olup olmadığını veya günlük iş akışınızı etkilenip etkilemediğini de belirleyebilirsiniz.

Özellikleri değerlendirirken olayları gözden geçirmek kullanışlıdır. Özellikler veya ayarlar için denetim modunu etkinleştirebilir ve ardından tam olarak etkinleştirildiğinde neler olacağını gözden geçirebilirsiniz.

Bu bölümde tüm olaylar, ilişkili özellikleri veya ayarları listelenir ve belirli olaylara filtre uygulamak için özel görünümlerin nasıl oluşturulacağı açıklanır.

E5 aboneliğiniz varsa ve [Uç Nokta için Microsoft Defender kullanıyorsanız](microsoft-defender-endpoint.md) Windows Güvenliği bir parçası olarak olaylar, bloklar ve uyarılar hakkında ayrıntılı raporlama alın.

### <a name="use-custom-views-to-review-attack-surface-reduction-capabilities"></a>Saldırı yüzeyi azaltma özelliklerini gözden geçirmek için özel görünümleri kullanma

Yalnızca belirli özelliklere ve ayarlara yönelik olayları görmek için Windows Olay Görüntüleyicisi özel görünümler oluşturun. En kolay yol, özel görünümü XML dosyası olarak içeri aktarmaktır. XML'yi doğrudan bu sayfadan kopyalayabilirsiniz.

Ayrıca özelliğe karşılık gelen olay alanına el ile de gidebilirsiniz.

#### <a name="import-an-existing-xml-custom-view"></a>Var olan bir XML özel görünümünü içeri aktarma

1. Boş bir .txt dosyası oluşturun ve kullanmak istediğiniz özel görünüm için XML'yi .txt dosyasına kopyalayın. Bunu, kullanmak istediğiniz özel görünümlerin her biri için yapın. Dosyaları aşağıdaki gibi yeniden adlandırın (türü .txt .xml olarak değiştirdiğinizden emin olun):
    - Denetimli klasör erişimi olayları özel görünümü: *cfa-events.xml*
    - Yararlanma koruması olayları özel görünümü: *ep-events.xml*
    - Saldırı yüzeyi azaltma olayları özel görünümü: *asr-events.xml*
    - Ağ/koruma olayları özel görünümü: *np-events.xml*

2. Başlat menüsüne **olay görüntüleyicisi** yazın ve **Olay Görüntüleyicisi** açın.

3. **Eylem** \> **Özel Görünümü İçeri Aktar...** seçeneğini belirleyin.

   > [!div class="mx-imgBorder"]
   > ![Çift görüntüleyici penceresinin sol tarafındaki Özel görünümü içeri aktar seçeneğini vurgulayan animasyon.](images/events-import.gif)

4. İstediğiniz özel görünüm için XML dosyasını ayıkladığınız yere gidin ve seçin.

5. **Aç**'ı seçin.

6. Yalnızca bu özellikle ilgili olayları gösterecek şekilde filtreleyen özel bir görünüm oluşturur.

#### <a name="copy-the-xml-directly"></a>XML'yi doğrudan kopyalama

1. Başlat menüsüne **olay görüntüleyicisi** yazın ve Windows **Olay Görüntüleyicisi** açın.

2. Sol paneldeki **Eylemler'in** altında **Özel Görünüm Oluştur...** öğesini seçin.

   > [!div class="mx-imgBorder"]
   > ![Olay görüntüleyicisi penceresinde özel görünüm oluştur seçeneğini vurgulayan animasyon.](images/events-create.gif)

3. XML sekmesine gidin ve **Sorguyu el ile düzenle'yi** seçin. XML seçeneğini kullanıyorsanız **Filtre** sekmesini kullanarak sorguyu düzenleyemezsiniz uyarısı görürsünüz. **Evet**'i seçin.

4. Olayları filtrelemek istediğiniz özelliğin XML kodunu XML bölümüne yapıştırın.

5. **Tamam**'ı seçin. Filtreniz için bir ad belirtin. Bu, yalnızca bu özellikle ilgili olayları gösterecek şekilde filtreleyen özel bir görünüm oluşturur.

#### <a name="xml-for-attack-surface-reduction-rule-events"></a>Saldırı yüzeyi azaltma kuralı olayları için XML

```xml
<QueryList>
  <Query Id="0" Path="Microsoft-Windows-Windows Defender/Operational">
   <Select Path="Microsoft-Windows-Windows Defender/Operational">*[System[(EventID=1121 or EventID=1122 or EventID=5007)]]</Select>
   <Select Path="Microsoft-Windows-Windows Defender/WHC">*[System[(EventID=1121 or EventID=1122 or EventID=5007)]]</Select>
  </Query>
</QueryList>
```

#### <a name="xml-for-controlled-folder-access-events"></a>Denetimli klasör erişim olayları için XML

```xml
<QueryList>
  <Query Id="0" Path="Microsoft-Windows-Windows Defender/Operational">
   <Select Path="Microsoft-Windows-Windows Defender/Operational">*[System[(EventID=1123 or EventID=1124 or EventID=5007)]]</Select>
   <Select Path="Microsoft-Windows-Windows Defender/WHC">*[System[(EventID=1123 or EventID=1124 or EventID=5007)]]</Select>
  </Query>
</QueryList>
```

#### <a name="xml-for-exploit-protection-events"></a>Açıklardan yararlanma koruması olayları için XML

```xml
<QueryList>
  <Query Id="0" Path="Microsoft-Windows-Security-Mitigations/KernelMode">
   <Select Path="Microsoft-Windows-Security-Mitigations/KernelMode">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Concurrency">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Contention">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Messages">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Operational">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Power">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Render">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Tracing">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/UIPI">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="System">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Security-Mitigations/UserMode">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
  </Query>
</QueryList>
```

#### <a name="xml-for-network-protection-events"></a>Ağ koruma olayları için XML

```xml
<QueryList>
 <Query Id="0" Path="Microsoft-Windows-Windows Defender/Operational">
  <Select Path="Microsoft-Windows-Windows Defender/Operational">*[System[(EventID=1125 or EventID=1126 or EventID=5007)]]</Select>
  <Select Path="Microsoft-Windows-Windows Defender/WHC">*[System[(EventID=1125 or EventID=1126 or EventID=5007)]]</Select>
 </Query>
</QueryList>
```

### <a name="list-of-attack-surface-reduction-events"></a>Saldırı yüzeyi azaltma olaylarının listesi

Tüm saldırı yüzeyi azaltma olayları **, Microsoft > Windows > Uygulamalar ve Hizmet Günlükleri'nin** altında ve ardından aşağıdaki tabloda listelendiği gibi klasör veya sağlayıcı altında bulunur.

Bu olaylara Windows Olay Görüntüleyicisi'nde erişebilirsiniz:

1. **Başlat** menüsünü açın ve **olay görüntüleyicisi** yazın ve **ardından Olay Görüntüleyicisi** sonucunu seçin.
2. **Microsoft > Windows > Uygulama ve Hizmet Günlükleri'ni** genişletin ve aşağıdaki tabloda **Sağlayıcı/kaynak** altında listelenen klasöre gidin.
3. Olayları görmek için alt öğeye çift tıklayın. Aradığınızı bulmak için olayları kaydırın.

   ![Olay Görüntüleyicisi kullanarak gösteren animasyon.](images/event-viewer.gif)

<br>

****

|Özellik|Sağlayıcı/kaynak|Olay Kimliği|Açıklama|
|---|---|:---:|---|
|Exploit Protection|Güvenlik-Risk Azaltmaları (Çekirdek Modu/Kullanıcı Modu)|1|ACG denetimi|
|Exploit Protection|Güvenlik-Risk Azaltmaları (Çekirdek Modu/Kullanıcı Modu)|2|ACG zorlama|
|Exploit Protection|Güvenlik-Risk Azaltmaları (Çekirdek Modu/Kullanıcı Modu)|3|Alt işlemlerin denetimine izin verme|
|Exploit Protection|Güvenlik-Risk Azaltmaları (Çekirdek Modu/Kullanıcı Modu)|4|Alt işlemler bloğuna izin verme|
|Exploit Protection|Güvenlik-Risk Azaltmaları (Çekirdek Modu/Kullanıcı Modu)|5|Düşük bütünlük görüntülerin denetimini engelle|
|Exploit Protection|Güvenlik-Risk Azaltmaları (Çekirdek Modu/Kullanıcı Modu)|6|Düşük bütünlükte görüntüleri engelleme bloğu|
|Exploit Protection|Güvenlik-Risk Azaltmaları (Çekirdek Modu/Kullanıcı Modu)|7|Uzak görüntülerin denetimini engelle|
|Exploit Protection|Güvenlik-Risk Azaltmaları (Çekirdek Modu/Kullanıcı Modu)|8|Uzak görüntüleri engelle bloğu|
|Exploit Protection|Güvenlik-Risk Azaltmaları (Çekirdek Modu/Kullanıcı Modu)|9|win32k sistem çağrıları denetimini devre dışı bırak|
|Exploit Protection|Güvenlik-Risk Azaltmaları (Çekirdek Modu/Kullanıcı Modu)|10|win32k sistem çağrıları bloğunu devre dışı bırakma|
|Exploit Protection|Güvenlik-Risk Azaltmaları (Çekirdek Modu/Kullanıcı Modu)|11|Kod bütünlüğü koruyucusu denetimi|
|Exploit Protection|Güvenlik-Risk Azaltmaları (Çekirdek Modu/Kullanıcı Modu)|12|Kod bütünlüğü koruma bloğu|
|Exploit Protection|Güvenlik-Risk Azaltmaları (Çekirdek Modu/Kullanıcı Modu)|13|EAF denetimi|
|Exploit Protection|Güvenlik-Risk Azaltmaları (Çekirdek Modu/Kullanıcı Modu)|14|EAF zorlama|
|Exploit Protection|Güvenlik-Risk Azaltmaları (Çekirdek Modu/Kullanıcı Modu)|15|EAF+ denetimi|
|Exploit Protection|Güvenlik-Risk Azaltmaları (Çekirdek Modu/Kullanıcı Modu)|16|EAF+ zorlama|
|Exploit Protection|Güvenlik-Risk Azaltmaları (Çekirdek Modu/Kullanıcı Modu)|17|IAF denetimi|
|Exploit Protection|Güvenlik-Risk Azaltmaları (Çekirdek Modu/Kullanıcı Modu)|18|IAF zorlama|
|Exploit Protection|Güvenlik-Risk Azaltmaları (Çekirdek Modu/Kullanıcı Modu)|19|ROP StackPivot denetimi|
|Exploit Protection|Güvenlik-Risk Azaltmaları (Çekirdek Modu/Kullanıcı Modu)|20|ROP StackPivot zorlama|
|Exploit Protection|Güvenlik-Risk Azaltmaları (Çekirdek Modu/Kullanıcı Modu)|21|ROP Çağıranı Denetimi denetleme|
|Exploit Protection|Güvenlik-Risk Azaltmaları (Çekirdek Modu/Kullanıcı Modu)|22|ROP CallerCheck zorlama|
|Exploit Protection|Güvenlik-Risk Azaltmaları (Çekirdek Modu/Kullanıcı Modu)|23|ROP SimExec denetimi|
|Exploit Protection|Güvenlik-Risk Azaltmaları (Çekirdek Modu/Kullanıcı Modu)|24|ROP SimExec zorlama|
|Exploit Protection|WER-Diagnostics|5|CFG Bloğu|
|Exploit Protection|Win32K (Operasyonel)|260|Güvenilmeyen Yazı Tipi|
|Ağ koruması|Windows Defender (Operasyonel)|5007|Ayarlar değiştirildiğinde gerçekleşen olay|
|Ağ koruması|Windows Defender (Operasyonel)|1125|Ağ koruması Denetim modunda tetiklendiğinde gerçekleşen olay|
|Ağ koruması|Windows Defender (Operasyonel)|1126|Ağ koruması Blok modunda tetiklendiğinde gerçekleşen olay|
|Denetimli klasör erişimi|Windows Defender (Operasyonel)|5007|Ayarlar değiştirildiğinde gerçekleşen olay|
|Denetimli klasör erişimi|Windows Defender (Operasyonel)|1124|Denetlenen Denetimli klasör erişimi olayı|
|Denetimli klasör erişimi|Windows Defender (Operasyonel)|1123|Engellenen Denetimli klasör erişimi olayı|
|Denetimli klasör erişimi|Windows Defender (Operasyonel)|1127|Engellenen Denetimli klasör erişimi kesim yazma bloğu olayı|
|Denetimli klasör erişimi|Windows Defender (Operasyonel)|1128|Denetlenen Denetimli klasör erişimi kesimi yazma bloğu olayı|
|Saldırı yüzeyini azaltma|Windows Defender (Operasyonel)|5007|Ayarlar değiştirildiğinde gerçekleşen olay|
|Saldırı yüzeyini azaltma|Windows Defender (Operasyonel)|1122|Denetim modunda kural tetiklendiğinde gerçekleşen olay|
|Saldırı yüzeyini azaltma|Windows Defender (Operasyonel)|1121|Kuralın Blok modunda tetiklenmesi olayı|

>[!NOTE]
> Kullanıcının bakış açısından ASR Uyarı modu bildirimleri, saldırı yüzeyi azaltma kuralları için Bir Windows Bildirim Bildirimi olarak yapılır.
>
> ASR'de Ağ Koruması yalnızca Denetim ve Engelleme modları sağlar.

## <a name="resources-to-learn-more-about-attack-surface-reduction"></a>Saldırı yüzeyini azaltma hakkında daha fazla bilgi edinmek için kaynaklar

Videoda belirtildiği gibi, Uç Nokta için Defender çeşitli saldırı yüzeyi azaltma özellikleri içerir. Daha fazla bilgi edinmek için aşağıdaki kaynakları kullanın:

| Makale | Açıklama |
|:---|:---|
| [Uygulama denetimi](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control) | Uygulamalarınızın çalışması için güven kazanmaları için uygulama denetimini kullanın. |
| [Saldırı yüzeyini azaltma (ASR) kuralları başvurusu](attack-surface-reduction-rules-reference.md) | Her saldırı yüzeyi azaltma kuralı hakkında ayrıntılı bilgi sağlar. |
| [Saldırı yüzeyini azaltma (ASR) kuralları dağıtım kılavuzu](attack-surface-reduction-rules-deployment.md) | Saldırı yüzeyi azaltma kurallarını dağıtmaya yönelik genel bakış bilgilerini ve önkoşulları, ardından test (denetim modu), etkinleştirme (blok modu) ve izleme için adım adım yönergeler sunar. |
| [Denetimli klasör erişimi](controlled-folders.md) | Kötü amaçlı veya şüpheli uygulamaların (dosya şifreleyen fidye yazılımı kötü amaçlı yazılımları dahil) anahtar sistem klasörlerinizdeki dosyalarda değişiklik yapmasını önlemeye yardımcı olun (Microsoft Defender Virüsten Koruma gerektirir). |
| [Cihaz denetimi](device-control-report.md) | Kuruluşunuzdaki çıkarılabilir depolama birimi ve USB sürücüleri gibi cihazlarda kullanılan medyayı izleyerek ve denetleyerek veri kaybına karşı koruma sağlar. |
| [Exploit Protection](exploit-protection.md) | Kuruluşunuzun kullandığı işletim sistemlerinin ve uygulamaların kötüye kullanılmaktan korunmasına yardımcı olun. Yararlanma koruması, üçüncü taraf virüsten koruma çözümleriyle de çalışır. |
| [Donanım tabanlı yalıtım](/windows/security/threat-protection/microsoft-defender-application-guard/md-app-guard-overview) | Sistem başlatılırken ve çalışırken sistemin bütünlüğünü koruyun ve koruyun. Yerel ve uzak kanıtlama aracılığıyla sistem bütünlüğünü doğrulayın. Kötü amaçlı web sitelerine karşı korunmaya yardımcı olmak için Microsoft Edge için kapsayıcı yalıtımını kullanın. |
| [Ağ koruması](network-protection.md) | Kuruluşunuzun cihazlarında ağ trafiğinize ve bağlantınıza yönelik korumayı genişletin. (Microsoft Defender Virüsten Koruma gerektirir). |
| [Saldırı yüzeyini azaltma (ASR) kuralları testi](attack-surface-reduction-rules-deployment-test.md) | Saldırı yüzeyi azaltma kurallarını test etmek için denetim modunu kullanma adımlarını sağlar. |
| [Web koruması](web-protection-overview.md) | Web koruması, cihazlarınızı web tehditlerine karşı korumanıza olanak tanır ve istenmeyen içeriği düzenlemenize yardımcı olur. |
