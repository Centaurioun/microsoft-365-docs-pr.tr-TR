---
title: Uç Nokta için Microsoft Defender
description: Uç Nokta için Microsoft Defender, gelişmiş kalıcı tehditlere karşı savunmaya yardımcı olan bir kurumsal uç nokta güvenlik platformudur.
keywords: Uç Nokta için Microsoft Defender giriş, Uç Nokta için Microsoft Defender giriş, siber güvenlik, gelişmiş kalıcı tehdit, kurumsal güvenlik, makine davranış sensörü, bulut güvenliği, analiz, tehdit zekası, saldırı yüzeyi azaltma, yeni nesil koruma, otomatik araştırma ve düzeltme, microsoft tehdit uzmanları, güvenli puan, gelişmiş avcılık, Microsoft 365 Defender, siber tehdit avcılığı
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: high
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier1
ms.custom: intro-overview
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 40450ed20daaa4c3520386aad7d6a416b8b84889
ms.sourcegitcommit: 4e42bafee965446f44f7f57d1defed2b9b24fce8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2022
ms.locfileid: "68234046"
---
# <a name="microsoft-defender-for-endpoint"></a>Uç Nokta için Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Şunlar için geçerlidir:**

- [Uç Nokta için Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender Güvenlik Açığı Yönetimi](../defender-vulnerability-management/index.yml)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Uç Nokta için Microsoft Defender'ı deneyimlemek ister misiniz? [Ücretsiz deneme için kaydolun.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Uç Nokta için Microsoft Defender, kurumsal ağların gelişmiş tehditleri engellemesine, algılamasına, araştırmasına ve yanıtlamasına yardımcı olmak için tasarlanmış bir kurumsal uç nokta güvenlik platformudur.

> [!TIP]
> Uç Nokta için Microsoft Defender, Uç Nokta için Defender Plan 1 ve Plan 2 şeklinde iki planda kullanılabilir. Plan 2 için yeni bir Microsoft Defender Güvenlik Açığı Yönetimi eklentisi kullanıma sunuldu.
>
> Yeni Defender Güvenlik Açığı Yönetimi eklentisi de dahil olmak üzere her planda bulunan özellikler ve özellikler hakkında daha fazla bilgi için bkz. [Uç Nokta için Microsoft Defender planlarını karşılaştırma](defender-endpoint-plan-1-2.md).

<p><p>

Uç Nokta için Defender hakkında daha fazla bilgi edinmek için aşağıdaki videoyu izleyin:

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4wDob]

Uç Nokta için Defender, Windows 10 ve Microsoft'un sağlam bulut hizmetinde yerleşik olarak bulunan aşağıdaki teknoloji bileşimini kullanır:

- **Uç nokta davranış algılayıcıları**: Windows 10 eklenmiş olan bu algılayıcılar işletim sisteminden davranış sinyallerini toplar ve işler ve bu algılayıcı verilerini özel, yalıtılmış, bulut Uç Nokta için Microsoft Defender örneğine gönderir.

- **Bulut güvenlik analizi**: Windows ekosistemi, kurumsal bulut ürünleri (Office 365 gibi) ve çevrimiçi varlıklar genelinde büyük veri, cihaz öğrenmesi ve benzersiz Microsoft optiklerinden yararlanma, davranış sinyalleri içgörülere, algılamalara ve gelişmiş tehditlere yönelik önerilen yanıtlara çevrilir.

- **Tehdit bilgileri**: Microsoft avcıları, güvenlik ekipleri tarafından oluşturulan ve iş ortakları tarafından sağlanan tehdit zekası tarafından geliştirilen tehdit bilgileri, Uç Nokta için Defender'ın saldırgan araçlarını, tekniklerini ve yordamlarını tanımlamasını ve toplanan algılayıcı verilerinde gözlemlendiğinde uyarılar oluşturmasını sağlar.

<center><h2>Uç Nokta için Microsoft Defender</center></h2>
<table>
<tr>
<td><a href="#tvm"><center><img src="images/logo-mdvm.png" alt="Vulnerability Management"> <br><b> Core Defender Güvenlik Açığı Yönetimi</b></center></a></td>
<td><a href="#asr"><center><img src="images/asr-icon.png" alt="Attack surface reduction"><br><b>Saldırı yüzeyini azaltma</b></center></a></td>
<td><center><a href="#ngp"><img src="images/ngp-icon.png" alt="Next-generation protection"><br> <b>Yeni nesil koruma</b></a></center></td>
<td><center><a href="#edr"><img src="images/edr-icon.png" alt="Endpoint detection and response"><br> <b>Uç nokta algılama ve yanıt</b></a></center></td>
<td><center><a href="#ai"><img src="images/air-icon.png" alt="Automated investigation and remediation"><br> <b>Otomatik araştırma ve düzeltme</b></a></center></td>
<td><center><a href="#mte"><img src="images/mte-icon.png" alt="Microsoft Threat Experts"><br> <b>Microsoft Tehdit Uzmanları</b></a></center></td>
</tr>
<tr>
<td colspan="7">
<a href="#apis"><center><b>Merkezi yapılandırma ve yönetim, API'ler</a></b></center></td>
</tr>
<tr>
<td colspan="7"><a href="#mtp"><center><b>Microsoft 365 Defender</a></center></b></td>
</tr>
</table>
<br>

<p></p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vnC4?rel=0]

> [!TIP]
> - Uç Nokta için Defender: [Uç Nokta için Microsoft Defender'deki yenilikler](whats-new-in-microsoft-defender-endpoint.md) konusundaki en son iyileştirmeler hakkında bilgi edinin.
> - Uç Nokta için Microsoft Defender son MITRE değerlendirmesinde sektör lideri optik ve algılama özelliklerini göstermiştir. Okuma: [MITRE ATT&CK tabanlı değerlendirmeden alınan içgörüler](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).


> [!IMPORTANT]
> Windows olmayan platformlardaki özellikler Windows'un özelliklerinden farklı olabilir. Windows dışı platformlar için hangi özelliklerin kullanılabilir olduğu hakkında daha fazla bilgi için bkz. [Windows dışı platformlar için Uç Nokta için Microsoft Defender](/microsoft-365/security/defender-endpoint/non-windows).

<a name="tvm"></a>

**[Core Defender Güvenlik Açığı Yönetimi](../defender-vulnerability-management/defender-vulnerability-management.md)**

Yerleşik temel güvenlik açığı yönetimi özellikleri, uç nokta güvenlik açıklarının ve yanlış yapılandırmaların keşfi, değerlendirmesi, önceliklendirilmesi ve düzeltilmesi için modern bir risk tabanlı yaklaşım kullanır. Güvenlik duruşunuzu değerlendirme ve riski azaltma becerinizi daha da geliştirmek amacıyla Plan 2 için yeni bir Defender Güvenlik Açığı Yönetimi eklentisi kullanıma sunulmuştur.

Kullanabileceğiniz farklı güvenlik açığı yönetimi özellikleri hakkında daha fazla bilgi için bkz. [Microsoft Defender Güvenlik Açığı Yönetimi tekliflerini karşılaştırma](../defender-vulnerability-management/defender-vulnerability-management-capabilities.md).

<a name="asr"></a>

**[Saldırı yüzeyini azaltma](overview-attack-surface-reduction.md)**

Saldırı yüzeyi azaltma özellikleri kümesi, yığındaki ilk savunma hattını sağlar. Yapılandırma ayarlarının düzgün ayarlandığından ve güvenlik açığından yararlanma azaltma tekniklerinin uygulandığından emin olarak, özellikler saldırılara ve kötüye kullanıma karşı dayanıklıdır. Bu özellik kümesi, kötü amaçlı IP adreslerine, etki alanlarına ve URL'lere erişimi düzenleyen [ağ korumasını](network-protection.md) ve [web korumasını](web-protection-overview.md) da içerir.

<a name="ngp"></a>

**[Yeni nesil koruma](next-generation-protection.md)**

Ağınızın güvenlik çevresini daha da güçlendirmek için Uç Nokta için Microsoft Defender her türlü yeni tehdidi yakalamak için tasarlanmış yeni nesil korumayı kullanır.

<a name="edr"></a>

**[Uç nokta algılama ve yanıt](overview-endpoint-detection-response.md)**

Uç nokta algılama ve yanıt özellikleri, ilk iki güvenlik sütununu geçmiş olabilecek gelişmiş tehditleri algılamak, araştırmak ve yanıtlamak için kullanılır. [Gelişmiş tehdit avcılığı](advanced-hunting-overview.md) , ihlalleri proaktif olarak bulmanıza ve özel algılamalar oluşturmanıza olanak tanıyan sorgu tabanlı bir tehdit avcılığı aracı sağlar.

<a name="ai"></a>

**[Otomatik araştırma ve düzeltme](automated-investigations.md)**

Uç Nokta için Microsoft Defender, gelişmiş saldırılara hızlı bir şekilde yanıt verebilmekle birlikte, uyarı hacmini dakikalar içinde azaltmaya yardımcı olan otomatik araştırma ve düzeltme özellikleri sunar.

<a name="ss"></a>

**[Cihazlar için Microsoft Güvenlik Puanı](tvm-microsoft-secure-score-devices.md)**

Uç Nokta için Defender, kurumsal ağınızın güvenlik durumunu dinamik olarak değerlendirmenize, korumasız sistemleri belirlemenize ve kuruluşunuzun genel güvenliğini geliştirmek için önerilen eylemleri gerçekleştirmenize yardımcı olan Cihazlar için Microsoft Güvenli Puanı içerir.

<a name="mte"></a>

**[Microsoft Tehdit Uzmanları](microsoft-threat-experts.md)**

Uç Nokta için Microsoft Defender'ın yeni yönetilen tehdit avcılığı hizmeti proaktif avcılık, öncelik belirleme ve Güvenlik operasyon merkezlerinin (SOC' ler) tehditleri hızla ve doğru bir şekilde tanımlayıp yanıtlamasını daha da güçlendiren ek bağlam ve içgörüler sağlar.

> [!IMPORTANT]
> Uç Nokta için Defender müşterilerinin proaktif Hedefli Saldırı Bildirimleri almak ve isteğe bağlı uzmanlarla işbirliği yapmak için Microsoft Tehdit Uzmanları yönetilen tehdit avcılığı hizmetine başvurmaları gerekir. İsteğe Bağlı Uzmanlar bir eklenti hizmetidir. Microsoft Tehdit Uzmanları yönetilen tehdit avcılığı hizmetine kabul edildikten sonra hedeflenen Saldırı Bildirimleri her zaman dahil edilir.
>
> Henüz kaydolmadıysanız ve avantajlarını yaşamak istiyorsanız, uygulamak için **Ayarlar** \> **Genel** \> **Gelişmiş özellikler** \> **Microsoft Tehdit Uzmanları** gidin. Kabul edildikten sonra, Hedefli Saldırı Bildirimleri'nin avantajlarından yararlanır ve İsteğe Bağlı Uzmanlar'ın 90 günlük denemesini başlatırsınız. tam bir İsteğe Bağlı Uzmanlar aboneliği almak için Microsoft temsilcinize başvurun.

<a name="apis"></a>

**[Merkezi yapılandırma ve yönetim, API'ler](management-apis.md)**

Uç Nokta için Microsoft Defender mevcut iş akışlarınızla tümleştirin.

<a name="mtp"></a>

**[Microsoft çözümleriyle tümleştirme](threat-protection-integration.md)**

Uç Nokta için Defender, aşağıdakiler de dahil olmak üzere çeşitli Microsoft çözümleriyle doğrudan tümleştirilir:

- Bulut için Microsoft Defender
- Microsoft Sentinel
- Intune
- Bulut Uygulamaları için Microsoft Defender
- Kimlik için Microsoft Defender
- Office için Microsoft Defender
- Skype Kurumsal

**[Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)**

Microsoft 365 Defender, Uç Nokta için Defender ve çeşitli Microsoft güvenlik çözümleriyle gelişmiş saldırıları algılamak, önlemek, araştırmak ve otomatik olarak yanıtlamak için uç nokta, kimlik, e-posta ve uygulamalar arasında yerel olarak tümleşen birleşik bir ihlal öncesi ve sonrası kurumsal savunma paketi oluşturur.


## <a name="training-for-security-analysts"></a>Güvenlik analistleri için eğitim

Microsoft Learn'ün bu öğrenme yolu ile Uç Nokta için Defender'ı ve kuruluşunuzun uç noktaları (cihazlarınız ve sistemleriniz) genelindeki tehditleri önlemeye, algılamaya, araştırmaya ve yanıtlamaya nasıl yardımcı olabileceğini anlayabilirsiniz.

|Eğitim:|Microsoft 365 Defender ile siber saldırıları algılama ve yanıtlama|
|---|---|
|![Microsoft 365 Defender eğitim simgesi.](../../media/microsoft-365-defender/m365-defender-secure-organization.svg)|Uç Nokta için Defender, güvenlik açığı yönetimi, uç nokta koruması, uç nokta algılama ve yanıt, mobil tehdit savunması ve yönetilen hizmetleri tek, birleşik bir platformda sunan bir uç nokta güvenlik çözümüdür.<p> 2 sa 25 dk - Öğrenme Yolu - 9 Modül|

> [!div class="nextstepaction"]
> [Başlangıç >](/training/paths/defender-endpoint-fundamentals/)
