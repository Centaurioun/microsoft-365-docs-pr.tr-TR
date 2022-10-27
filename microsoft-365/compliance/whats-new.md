---
title: Microsoft Purview risk ve uyumluluk çözümlerindeki yenilikler
description: Uyumluluk merkezine yeni çözümler eklemek, mevcut özellikleri geri bildiriminize göre güncelleştirmek veya yeni ve güncelleştirilmiş belgeleri kullanıma sunan Microsoft Purview, sürekli değişen uyumluluk ortamını takip etme konusunda size yardımcı olur. Bu ay neler yaptığımıza bakın.
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- purview-compliance
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 28e1dedac97d692ae1f797fe4fe4a056a5d4a7b5
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/27/2022
ms.locfileid: "68731491"
---
# <a name="whats-new-in-microsoft-purview-risk-and-compliance-solutions"></a>Microsoft Purview risk ve uyumluluk çözümlerindeki yenilikler

microsoft 365, [Microsoft Purview uyumluluk portalı](microsoft-365-compliance-center.md) yeni çözümler ekleme, mevcut özellikleri geri bildiriminize göre güncelleştirme veya yeni ve güncelleştirilmiş belgeler dağıtma konusunda sürekli değişen uyumluluk ortamını takip etme konusunda size yardımcı olur. Bugün Microsoft Purview'daki yeniliklere göz atmak için aşağıya göz atın.

> [!NOTE]
> Bazı uyumluluk özellikleri müşterilerimiz için farklı hızlarda kullanıma sunulur. Henüz bir özellik görmüyorsanız, [kendinizi hedeflenen sürüme](/office365/admin/manage/release-options-in-office-365) eklemeyi deneyin.

> [!TIP]
> Diğer yönetim merkezlerinde neler olduğuyla ilgileniyor musunuz? Şu makalelere göz atın:
>
> - [Microsoft 365 yönetim merkezi'deki yenilikler](/office365/admin/whats-new-in-preview)
> - [SharePoint yönetim merkezindeki yenilikler](/sharepoint/what-s-new-in-admin-center)
> - [Microsoft 365 Defender'daki yenilikler](../security/defender/whats-new.md)
>
> Ayrıca başlatılan, kullanıma sunulan, geliştirilen, iptal edilen veya daha önce yayımlanan Microsoft 365 özellikleri hakkında bilgi edinmek için Microsoft 365 [Yol Haritası'nı](https://www.microsoft.com/microsoft-365/roadmap) ziyaret edin.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="october-2022"></a>Ekim 2022

### <a name="communication-compliance"></a>İletişim uyumluluğu

- **Önizlemede**: [Insider risk yönetimiyle yeni iletişim uyumluluğu tümleştirmesi](/microsoft-365/compliance/communication-compliance#integration-with-insider-risk-management-preview). İletişim uyumluluğu artık iletilerde algılanan azaltma sinyallerini insider risk yönetimi azaltma ilkelerine sağlayabilir. İletişim uyumluluk ilkesi tarafından iletilerde algılanan azaltma, kullanıcıları insider risk yönetimi ilkeleri kapsamına almak için tetikleyici bir olay olarak görev görür.

### <a name="insider-risk-management"></a>İçeriden risk yönetimi

- **Önizlemede**: Insider risk yönetimi, kuruluşunuzun hassas verilerin yetkisiz veri sızdırması gibi olası veri risklerini daha iyi azaltmasına, anlamasına ve yanıtlamasına yardımcı olmak için cihazlar arasında özelleştirilebilir görsel etkinlik yakalamaya olanak tanıyan [adli kanıt](/microsoft-365/compliance/insider-risk-management-forensic-evidence) sağlar.
- **Önizlemede**: *Dışlanan kullanıcılar tarafından veri sızıntıları* veya kullanıcı ilkesi şablonlarının *güvenlik ilkesi ihlalleri* kullanılırken iletişim uyumluluğuyla Insider risk yönetimi [tümleştirmesi](/microsoft-365/compliance/communication-compliance#integration-with-insider-risk-management-preview). İletişim uyumluluğu artık iletilerde algılanan azaltma sinyallerini insider risk yönetimi azaltma ilkelerine sağlayabilir.
- **Önizlemede**: Yeni [satır içi uyarı özelleştirmesi](/microsoft-365/compliance/insider-risk-management-settings#inline-alert-customization-preview) , analistlerin ve araştırmacıların uyarıları gözden geçirirken ilkeleri hızla düzenlemesine olanak tanır.
- İlke tarafından algılanan tüm etkinliklere mi yoksa yalnızca öncelik içeriği içeren etkinliklere mi risk puanları atamayı seçmenizi sağlayan yeni öncelikli [içerik puanlama güncelleştirmeleri](/microsoft-365/compliance/insider-risk-management-policies#prioritize-content-in-policies) .
- Güvenlik ekipleri artık bir kullanıcı bir dizi gerçekleştirdiğinde ortaya çıkarma amacıyla 'veri sızıntıları' ilkesindeki bir [güvenlik tetikleyicisini özelleştirerek](/microsoft-365/compliance/insider-risk-management-policies#policy-templates) daha riskli kabul edilebilecek kullanıcı eylemlerine yanıt vermelerini sağlayabilir.
- Yeni güncelleştirmeler artık güvenlik ekiplerinin diğer gerekli ilke göstergesi seçimleri olmadan [dizilerle](/microsoft-365/compliance/insider-risk-management-policies#sequence-detection-preview) ilkeler oluşturmasına olanak tanır.

### <a name="data-lifecycle-management-and-records-management"></a>Veri yaşam döngüsü yönetimi ve kayıt yönetimi

- **Genel kullanılabilirlik (GA):**[Saklama süresinin sonunda](retention-settings.md#relabeling-at-the-end-of-the-retention-period) yeniden etiketleme.
- **Genel kullanılabilirlik (GA)**: [Kaydın kilidi açıldı](declare-records.md#configuring-retention-labels-to-declare-records).
- **Genel kullanılabilirlik (GA):** Kullanıcılar artık yayımlanmış bekletme etiketlerini [doğrudan Teams'deki](create-apply-retention-labels.md#applying-retention-labels-using-microsoft-365-groups) dosyalara uygulayabilir.
- Yeni bekletme desteği deyimleri: Teams için bekletme ilkeleri [sohbeti kendimle](https://support.microsoft.com/office/start-a-chat-in-teams-0c71b32b-c050-4930-a887-5afbe742b3d8?storagetype=live#bkmk_chatwithself) birlikte destekler özellik ve [video klipleri](https://support.microsoft.com/office/record-a-video-clip-in-teams-0c57dae5-2974-4214-9c46-7a2136386f1c) ve Yammer destek [hikayesi gönderileri](https://support.microsoft.com/office/overview-of-storyline-for-yammer-and-viva-engage-530e4e66-9f1c-4be1-b371-08ea40dc4b69) için bekletme ilkeleri.
- Bekletme ilkeleri hatalarla karşılaşıyorsa ürün içi deneyim iyileştirildi: Artık ayrıntılar bölmesinde hatanın ayrıntılı bir açıklamasını görürsünüz. Bu, sorunu çözebilecek ürün içi eylemlerle birlikte sunulur. Örneğin, geçersiz konumları kaldırın ve ilkeyi yeniden eşitleyin.

### <a name="microsoft-priva"></a>Microsoft Priva

- **Önizlemede**: Gizlilik Risk Yönetimi'ndeki [veri aktarım ilkeleri](/privacy/priva/risk-management-policy-data-transfer) artık ek esnek sınır koşulları sunuyor: kullanıcıların Azure Active Directory özniteliklerine göre aktarımları algılama, farklı Microsoft 365 gruplarındaki kullanıcılar arasında aktarımlar ve SharePoint siteleri arasında aktarımlar.

### <a name="on-premises-scanner"></a>Şirket içi tarayıcı
- **Önizlemede**: Azure Information Protection (AIP) şirket içi tarayıcısı tarayıcı **Microsoft Purview Bilgi Koruması** yeniden adlandırılıyor ve [yapılandırma Microsoft Purview uyumluluk portalı taşınıyor](/information-protection/deploy-aip-scanner-configure-install).

### <a name="sensitivity-labels"></a>Duyarlılık etiketleri
- Eylem çağrısı: Müşteri Deneyimi Mühendisliği (CxE) ekibimizden bir [geçiş playbook'u](https://microsoft.github.io/ComplianceCxE/playbooks/AIP2MIPPlaybook) ile Office uygulamaları için AIP eklentisinden geçiş yapmanıza yardımcı olacak geçiş [kılavuzu](sensitivity-labels-aip.md)
- **Genel kullanılabilirlik (GA):** Bir siteye daha sıkı erişim koşulları uygulamak için Azure AD Koşullu Erişim ilkeleriyle çalışan etiket [grupları ve site ayarları](sensitivity-labels-teams-groups-sites.md#how-to-configure-groups-and-site-settings) için kimlik doğrulama bağlamları.
- **Genel kullanılabilirlik (GA):**[PowerShell kullanarak site paylaşım izinleri](sensitivity-labels-teams-groups-sites.md#configure-site-sharing-permissions-by-using-powershell-advanced-settings).
- **Kullanıma sunulma**: [Panoya kopyanın engellenmesi, SharePoint ve OneDrive'daki etiketlenmiş ve şifrelenmiş dosyalar için kabul edilir ve](sensitivity-labels-sharepoint-onedrive-files.md#limitations) senaryoların yeniden etiketlenmesi için bazı özel durumlar hariçtir.
- **Önizlemede**: Office uygulamaları için AIP eklentisi [varsayılan olarak devre dışıdır](sensitivity-labels-aip.md#how-to-disable-the-aip-add-in-to-use-built-in-labeling-for-office-apps) ve bu varsayılanı geçersiz kılmak için yeni bir ayar gerektirir.
- Destek deyimi: Bu hizmetler için duyarlılık etiketlerini etkinleştirdikten sonra [SharePoint ve OneDrive için desteklenen dosya türleri](sensitivity-labels-sharepoint-onedrive-files.md#supported-file-types).
- [Birlikte yazma](sensitivity-labels-coauthoring.md#prerequisites) ve Azure Information Protection birleşik etiketleme istemcisi ve tarayıcısı için yeni önkoşul: Birlikte yazma özelliğiyle aynı kiracıda Çift Anahtar Şifrelemesi kullanılması desteklenmez.

## <a name="september-2022"></a>Eylül 2022

### <a name="communication-compliance"></a>İletişim uyumluluğu

- [İletişim uyumluluğunu kullanmaya başlama](/microsoft-365/compliance/communication-compliance-configure): Önerilen eylemler ve hızlandırılmış ekleme için yeni güncelleştirmeler. Önerilen eylemler, kuruluşunuzun iletişim uyumluluğunu hızlı bir şekilde kullanmaya başlamasına yardımcı olabilir.
- [İletişim uyumluluk uyarılarını araştırma ve düzeltme](/microsoft-365/compliance/communication-compliance-investigate-remediate): Düz metin görünümü için anahtar sözcük vurgulama desteğine yönelik yeni güncelleştirme. Şu anda yalnızca İngilizce dilinde kullanılabilen anahtar sözcük vurgulama, uzun iletilerde ve eklerde ilginizi çeken alana yönlendirmenize yardımcı olabilir.
- [İletişim uyumluluk raporlarını ve denetimlerini kullanın](/microsoft-365/compliance/communication-compliance-reports-audits): İletişim uyumluluk raporlarını görüntülemek ve yönetmek için gereken izinlere ilişkin netleştirmeler. Raporları görüntülemek ve yönetmek için kullanıcıların *İletişim Uyumluluğu Görüntüleyicileri* rol grubuna atanması gerekir.
 
### <a name="compliance-manager"></a>Uyumluluk Yöneticisi

- [Uyumluluk Yöneticisi şablonları listesi](/microsoft-365/compliance/compliance-manager-templates-list): ISM Sürüm 3.5 - Official ile Avustralya Bilgi Güvenliği Kayıtlı Değerlendirici Programı (IRAP) için yeni şablon eklendi.

### <a name="data-classification"></a>Veri Sınıflandırma

- [Sınıflandırıcı doğruluğunu artırma (önizleme)](data-classification-increase-accuracy.md) - Bu makalede, sınıflandırıcı tarafından eşleştirilen öğelerin doğru pozitif (Eşleşme) veya hatalı pozitif (Eşleşme değil) olup olmadığını onaylama ve Eşleşme veya Eşleşme geri bildirimi sağlama işlemleri gösterilir. Bu geri bildirimi, doğruluğu artırmak için sınıflandırıcılarınızı ayarlamak için kullanabilirsiniz. Ayrıca, Microsoft'un sağladığı sınıflandırıcıların doğruluğunu artırmaya yardımcı olmak istiyorsanız, belgenin ve Eşleştir, Eşleşme değil geri bildiriminin redakte edilmiş sürümlerini Microsoft'a gönderebilirsiniz.

### <a name="data-lifecycle-management-and-records-management"></a>Veri yaşam döngüsü yönetimi ve kayıt yönetimi

- Önizlemede: Bekletme etiketleri artık özel eylemleri ve diğer çözümlerle tümleştirmeyi desteklemek için bekletme süresinin sonunda bir Power Automate akışı çalıştırmayı destekliyor. Daha fazla bilgi için bkz. [Saklama süresinin sonunda ne olacağını özelleştirme](retention-label-flow.md).
- Değerlendirme gözden geçirmesinden geçen kayıt yönetimi öğeleri için, uyumluluk portalının Disposition alanında bu öğeyi seçtiğinizde, yeni bir İlerleme sütunu öğenin durumunu görüntüler. Bu durum "Silinmek üzere onaylandı, 'SharePoint/OneDrive'dan silinme bekleniyor' veya 'Exchange'den silinme bekleniyor' veya "Kalıcı Olarak Silindi" olabilir. Bir öğe, değerlendirme gözden geçirme işleminin bir parçası olarak kalıcı silme için onaylandığında, bu silme işleminin tamamlanması 15 güne kadar sürebilir ve bu yeni sütun, ilerleme durumunu izlemenize yardımcı olur.
- [Arşivleme için posta kutusunu etkinleştirme](enable-archive-mailboxes.md) yapılandırması yeni Exchange yönetim merkezine (EAC) taşınıyor ve yönergeler buna uygun olarak güncelleştirildi.
- Şu anda, otomatik uygulama bekletme etiketleri için eğitilebilir sınıflandırıcılar uyarlamalı kapsamlarla desteklenmemektedir. Geçici bir çözüm olarak, bu yapılandırma bileşimi için statik kapsamlar kullanın.
- [Posta kutuları için arşiv ve silme ilkesini özelleştirme](set-up-an-archive-and-deletion-policy-for-mailboxes.md) yönergeleri, yalnızca Microsoft 365 saklama ile elde edilmeyecek bir sonuca sahip bekletme etiketlerini içerecek şekilde güncelleştirilir.

### <a name="data-loss-prevention"></a>Veri kaybı önleme

- [Veri kaybı önleme ilkesi karmaşık kural tasarımı (önizleme) tasarlama](dlp-policy-design.md#complex-rule-design-preview) - DLP kural oluşturucusu boole mantığını (AND, OR, NOT) ve iç içe grupları destekler. Bu yeni işlevsellikte size yol gösteren yeni video ve içerik eklendi.

### <a name="sensitivity-labels"></a>Duyarlılık etiketleri
- Word, Excel ve PowerPoint'te [PDF desteği](sensitivity-labels-office-apps.md#pdf-support) artık Windows Güncel Kanalı ve Aylık Kurumsal Kanal'da kullanılabilir.
- Mevcut belgeler için varsayılan etiket artık Geçerli Kanal ve Aylık Kurumsal Kanal'da Mac ve Windows'a tamamen dağıtılarak AIP eklentisiyle eşlik sağlanır.
- Önizlemede: Office uygulamalarında yeni [duyarlılık çubuğu](sensitivity-labels-office-apps.md#sensitivity-bar) ve [etiket renkleri](sensitivity-labels-office-apps.md#label-colors) desteği, ek işlevlerle AIP eklentisiyle eşlik sağlar.
- Önizlemede: AIP eklentisiyle eşlik sağlayan Windows için [S/MIME desteği](sensitivity-labels-office-apps.md#configure-a-label-to-apply-smime-protection-in-outlook) . Mac ve mobil için destek artık tamamen kullanıma hazır.
- Önizlemede: Otomatik etiketleme ilkeleri (tüm iş yükleri) için eğitilebilir sınıflandırıcılar.

### <a name="trainable-classifiers"></a>Eğitilebilir sınıflandırıcılar

- [Eğitilebilir sınıflandırıcı tanımları](classifier-tc-definitions.md)  - 20'den fazla yeni sınıflandırıcı eklendiğinden, tüm eğitilebilir sınıflandırıcıların tanımları bu yeni makaleye ayrılmıştır.

## <a name="august-2022"></a>Ağustos 2022

### <a name="compliance-manager"></a>Uyumluluk Yöneticisi

- [İyileştirme eylemlerini güncelleştirin ve uyumluluk verilerini Uyumluluk Yöneticisi'ne getirin](compliance-manager-update-actions.md) - Aynı anda birden çok iyileştirme eylemini güncelleştirmeye yönelik yeni işlevsellik, kuruluşların diğer sistemlerde tamamlanan uyumluluk çalışmalarını orada izlemek üzere Uyumluluk Yöneticisi'ne getirmesine de olanak tanır.
- [Uyumluluk Yöneticisi'nde iyileştirme eylemleriyle çalışma](compliance-manager-improvement-actions.md) - Kullanıcılar artık geliştirme eyleminin uygulanması veya test çalışmalarının kanıtı olarak bir bağlantı/URL içerebilir.

### <a name="compliance-offerings--service-assurance"></a>Hizmet güvencesi & uyumluluk teklifleri

- [Microsoft 365 değişiklik yönetimi](/compliance/assurance/assurance-microsoft-365-change-management) - Microsoft hizmetlerinde kod ve kod dışı değişiklikleri kapsayan yeni güvence konusu.
- **Japonya CS Gold Mark teklifi konusu** - kullanımdan kaldırıldı, sertifikasyon yenilenmedi.

### <a name="data-lifecycle-management-and-records-management"></a>Veri yaşam döngüsü yönetimi ve kayıt yönetimi

- [Exchange (eski)](data-lifecycle-management.md#exchange-legacy-features) yapılandırması, **Veri yaşam döngüsü yönetimi** altında Klasik Exchange yönetim merkezinden (EAC) Microsoft Purview uyumluluk portalı taşınıyor. Mevcut veri yaşam döngüsü yönetimi özellikleri, **Microsoft 365** adlı yeni bir alt düğüm altında bulunur.
- Bulut ekleri için (şu anda önizlemede kullanıma sunuluyor), kopya oluşturulmadan ve etiketlenmeden önce orijinal dosyanın kullanıcılar tarafından silinmesine karşı koruma sağlamak için, silinen dosyaların Koruma Saklama kitaplığında otomatik ve geçici olarak tutulması. Daha fazla bilgi için bkz. [Bulut ekleriyle bekletme nasıl çalışır](retention-policies-sharepoint.md#how-retention-works-with-cloud-attachments)?

### <a name="data-loss-prevention"></a>Veri kaybı önleme

- [Uç nokta veri kaybını önlemeyi kullanmaya başlama](endpoint-dlp-getting-started.md) - daha erişilebilir makale adları için güncelleştirilmiş bağlantılar
- [Uç nokta veri kaybını önleme -](endpoint-dlp-learn-about.md) daha erişilebilir makale adları için güncelleştirilmiş bağlantılar hakkında bilgi edinin; desteklenen dosya türleriyle ilgili güncelleştirilmiş kılavuz; diğer uygulamaya kopyalama yönergeleri güncelleştirildi
- [Veri kaybı önleme uyarılarını paylaşma](dlp-share-alerts.md) (önizleme) - yeni
- [Uç nokta DLP ayarlarını yapılandırma](dlp-configure-endpoint-settings.md) - Hassas Hizmet Etki Alanlarının GA'sı
- [Veri kaybı önleme ilkesi başvurusu](dlp-policy-reference.md) - Hassas Hizmet Etki Alanlarının GA'sı
- [Uç nokta veri kaybını önlemeyi kullanma](endpoint-dlp-using.md) - Hassas Hizmet Etki Alanlarının GA'sı

### <a name="insider-risk-management"></a>İçeriden risk yönetimi

- [Insider risk yönetimi ilkeleri oluşturma ve yönetme](/microsoft-365/compliance/insider-risk-management-policies#general-risky-browser-usage-preview): Genel önizleme için yeni Riskli tarayıcı kullanım ilkesi şablonu. Bu ilke, tehdit oluşturan siteleri ziyaret etme (örneğin kimlik avı siteleri) veya yetişkinlere yönelik içerik içeren siteleri ziyaret etme gibi kuruluşunuzun kabul edilebilir kullanım ilkesini ihlal eden web'e gözatma için risk puanlamanın algılanması ve etkinleştirilmesine yardımcı olabilir.
- [Insider risk yönetimi ilkeleri oluşturma ve yönetme](/microsoft-365/compliance/insider-risk-management-policies#quick-policies-from-recommended-actions-preview) -Genel önizleme için yeni hızlı ilke şablonları. Genel *veri sızıntıları* veya Veri hırsızlığı yapılandırmasını hızlandırmak için hızlı bir ilkeyi *kullanarak kullanıcılar ilkesinden ayrılabilirsiniz*.
- [Insider risk yönetimi ayarlarını kullanmaya başlama](/microsoft-365/compliance/insider-risk-management-settings#intelligent-detections): Akıllı algılama ayarlarında yeni dışlama ve sınıflandırıcılar desteği.

### <a name="microsoft-priva"></a>Microsoft Priva

- [Microsoft Priva deneme kullanım kılavuzu](/privacy/priva/priva-trial-playbook) - son belge güncelleştirmeleriyle uyumlu hale getirmek için yenilenen ve basitleştirilmiş yönergeler

### <a name="sensitive-information-types"></a>Hassas Bilgi Türleri

- [Hassas bilgi türü iş akışı klasik deneyimiyle tam veri eşleştirmesi oluşturma](sit-create-edm-sit-classic-ux-workflow.md) - yeni
- [Yeni deneyim için EDM SIT örnek dosyasını oluşturma](sit-create-edm-sit-unified-ux-sample-file.md) - yeni
- [Yeni deneyimi kullanarak EDM SIT oluşturma](sit-create-edm-sit-unified-ux-schema-rule-package.md) - yeni
- [Hassas bilgi türü iş akışıyla tam veri eşleşmesi oluşturma yeni deneyim](sit-create-edm-sit-unified-ux-workflow.md) - yeni
- Aşağıdaki konularda yeni ve klasik EDM SIT oluşturma deneyimi için rehberlik eklendi:
  - [Tam veri eşleşmesine dayalı hassas bilgi türlerini kullanmaya başlama](sit-get-started-exact-data-match-based-sits-overview.md)
  - [Tam veri eşleşmesi hassas bilgi türü/kural paketi oluşturma](sit-get-started-exact-data-match-create-rule-package.md)
  - [Tam veri eşleşmesine dayalı hassas bilgi türleri için tam veri eşleşmesi şeması oluşturma](sit-get-started-exact-data-match-create-schema.md)
  - [Tam veri eşleşmesine dayalı hassas bilgi türleri için kaynak verilerini dışa aktarma](sit-get-started-exact-data-match-export-data.md)
  - [Tam veri eşleşmeli hassas bilgi türleri için hassas bilgi kaynak tablosu karması oluşturma ve karşıya yükleme](sit-get-started-exact-data-match-hash-upload.md)
  - [Tam veri eşleşmesi hassas bilgi türünü test etme](sit-get-started-exact-data-match-test.md)
  - [Hassas bilgi türleriyle tam olarak eşleşen veriler hakkında bilgi edinin](sit-learn-about-exact-data-match-based-sits.md)
- [Hassas bilgi türü sınırları](sit-limits.md) - yeni

### <a name="sensitivity-labels"></a>Duyarlılık etiketleri

- Genel kullanıma sunuldu (GA) ve artık kabul etmeniz gerekmiyor: Mobil cihazlar (iOS ve Android, en düşük sürümlerle), [duyarlılık etiketleriyle şifrelenmiş dosyalar için birlikte yazmayı](sensitivity-labels-coauthoring.md) destekler.
- Windows'da Word, Excel, PowerPoint için Geçerli Kanal 2208+ ile GA: [PDF desteği](sensitivity-labels-office-apps.md#pdf-support). Gerektiğinde PDF'ye yazdırmayı engellemek için Outlook desteği Beta Kanalı'na dağıtılıyor.
- Windows için Current Channel 2208+ ve macOS için 16.63+ ile GA'ya dağıtım: Mevcut belgeler için varsayılan etiket.
- Önizlemede: [Otomatik etiketleme ilkeleri](apply-sensitivity-label-automatically.md) için eğitilebilir sınıflandırıcılar.
- Dış Kimlikler kiracılar arası erişim ayarları, Koşullu Erişim ilkeleri ve konuk hesapları hakkındaki bilgileri içeren [şifrelenmiş içerik için Azure AD yapılandırma](encryption-azure-ad-configuration.md) yönergeleri.

## <a name="july-2022"></a>Temmuz 2022

### <a name="compliance-manager"></a>Uyumluluk Yöneticisi

- [Uyumluluk Yöneticisi şablonları listesi](compliance-manager-templates-list.md) - Asia-Pacific ülkeler kategorisine "Hong Kong - Bankacılık Uygulaması ve Ödeme Kartı Kodu" için yeni premium şablon eklendi.

### <a name="compliance-offerings--service-assurance"></a>Hizmet güvencesi & uyumluluk teklifleri

- [Microsoft 365'te SharePoint ve OneDrive veri dayanıklılığı](/compliance/assurance/assurance-sharepoint-onedrive-data-resiliency) - blob depolama dayanıklılığında yapılan değişiklikler bölümü.

### <a name="data-lifecycle-management-and-records-management"></a>Veri yaşam döngüsü yönetimi ve kayıt yönetimi

- Senaryolar için eklenen ayrıntılarla birlikte [birleştirilmiş lisanslama bölümü](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#microsoft-purview-data-lifecycle-management--microsoft-purview-records-management).
- SharePoint belge sürümlerinin saklanması artık Koruma Bekletme kitaplığında ayrı dosyalar kullanmaz. Daha fazla bilgi için, [belge sürümleriyle bekletme nasıl çalışır](retention-policies-sharepoint.md#how-retention-works-with-document-versions)? güncelleştirilmiş belgelere bakın.
- [SharePoint veya OneDrive'a geçiş yaptığınız kayıtları doğrulama](records-management.md#validating-migrated-records) yönergeleri.
- [SEC 17a-4(f), FINRA 4511(c) ve CFTC 1.31(c)-(d)](retention-regulatory-requirements.md#sec-17a-4f-finra-4511c-and-cftc-131c-d)için Cohasset Değerlendirme raporu güncelleştirildi.
- Bu özellik GA'da kullanıma sunulmaya başlandığından Teams paylaşılan kanalları için bekletme ilkelerine yönelik önizleme bildirimleri kaldırıldı.

### <a name="data-loss-prevention"></a>Veri Kaybı Önleme

- [DLP ilkesi başvurusu](dlp-policy-reference.md#blocking-and-notifications-in-sharepoint-online-and-onedrive-for-business) - SharePoint Online'da engelleme ve bildirimler hakkında yeni bölüm eklendi ve müşteri yükseltmelerine yanıt olarak OneDrive İş. Hassas hizmet etki alanlarının genel önizlemesini destekleyecek şekilde güncelleştirildi. Power BI desteği güncelleştirildi. Eğitilebilir sınıflandırıcılar için güncelleştirilmiş destek.
- [Uç nokta DLP ayarlarını yapılandırma](dlp-configure-endpoint-settings.md#sensitive-service-domains) - hassas hizmet etki alanları genel önizlemesinin genel önizleme sürümünü destekleyen yeni içerik eklendi. URL eşleştirme davranışı güncelleştirildi.
- [Uç nokta DLP'sini kullanma](endpoint-dlp-using.md#scenario-6-monitor-or-restrict-user-activities-on-sensitive-service-domains) - hassas hizmet etki alanlarının genel önizleme sürümünü destekleyen yeni senaryo içeriği. Güncelleştirilmiş abonelik bilgileri.

### <a name="ediscovery"></a>Ediscovery

- [eBulma için anahtar sözcük sorguları ve arama koşulları](keyword-queries-and-search-conditions.md) - değiştirilen bilgiler kaldırıldı.

### <a name="sensitive-information-types"></a>Hassas bilgi türleri

- [Hassas bilgi türü varlık tanımları](sensitive-information-type-entity-definitions.md) - 41 yeni kimlik bilgisi tarama SID'sini destekleyen 41 yeni SIT varlık tanımı ekledik. SIT varlık tanımları içeriği tek bir monolitik makaleden daha kolay başvurulabilen ve desteklenebilir tek tek makalelere dönüştürüldü. 42 yeni kimlik bilgisi tarama SID'si de dahil olmak üzere toplamda 303 makale vardır.

### <a name="sensitivity-labels"></a>Duyarlılık etiketleri

- Önizlemede: [SharePoint belge kitaplığı için varsayılan duyarlılık etiketi](sensitivity-labels-sharepoint-default-label.md).
- Önizlemede: Kullanıcıların izin atamasına izin vermek üzere bir duyarlılık etiketi yapılandırıldığında Windows için [kuruluş genelindeki özel](encryption-sensitivity-labels.md#support-for-organization-wide-custom-permissions) izinler. Daha fazla bilgi için bkz.  [Kuruluş genelindeki özel izinler için destek](encryption-sensitivity-labels.md#support-for-organization-wide-custom-permissions).
- Şimdi Windows için Geçerli Kanal'a (Önizleme) dağıtılıyor: Mevcut belgeler için varsayılan etiket.
- Artık Semi-Annual Enterprise Channel ile kullanılabilir: [Duyarlılık etiketleriyle şifrelenmiş dosyalar için birlikte yazma](sensitivity-labels-coauthoring.md).
- Duyarlılık etiketini yapılandırırken gördüğünüz "Dosyalar & e-postalar" etiket [kapsamı adı](sensitivity-labels.md#label-scopes) artık "Öğeler"dir.

## <a name="june-2022"></a>Haziran 2022

### <a name="compliance-manager"></a>Uyumluluk Yöneticisi

- [Microsoft Purview Uyumluluk Yöneticisi uyarıları ve uyarı ilkeleri](compliance-manager-alert-policies.md) - uyarı ilkeleri oluşturma veya düzenleme izinlerine sahip üç AAD rolü eklendi.
- [Microsoft Purview için Yapılandırma Çözümleyicisi](compliance-manager-mcca.md) - Daha önce 'Microsoft Uyumluluk Yapılandırma Çözümleyicisi' olarak adlandırılan Bu Kullanmaya Başlama aracı için yeni ad ve güncelleştirilmiş başvuru bağlantıları.

### <a name="data-loss-prevention"></a>Veri Kaybı Önleme

- Microsoft Purview markalı ekran görüntüleri için çok sayıda sayfa güncelleştirmesi.

### <a name="data-lifecycle-management-and-records-management"></a>Veri yaşam döngüsü yönetimi ve kayıt yönetimi

- Önizlemede: [Kayıt yönetimi için Microsoft Graph API](compliance-extensibility.md#microsoft-graph-api-for-records-management-preview)

### <a name="microsoft-priva"></a>Microsoft Priva

- [Konu Hakları İstekleri - önemli güncelleştirmeler](/privacy/priva/subject-rights-requests) ve her ilerleme adımında kullanıcılara daha iyi yardımcı olmak için SRR içeriğinin yeniden yapılandırılması; aşağıdaki ayrıntılara bakın.
  - [Priva Konu Hakkı Talepleri hakkında bilgi edinin](/privacy/priva/subject-rights-requests)- müşteri değeri dağılımının daha net bir şekilde ifade edilmesi ve SRR işleminin genel ana hattı.
  - [İş akışını ve ayrıntı sayfalarını anlama](/privacy/priva/subject-rights-requests-workflow) - bir isteği tamamlama adımlarını ifade eder, el ile otomatik ilerlemeyi belirtir ve ayrıntılı içeriğe bağlanır; bölümünde, yeni "Geçmiş" sekmesi de dahil olmak üzere bir isteğin ayrıntılar sayfasının nasıl yorumlanıp çalışılıp çalışıla çalıştığı açıklanır.
  - [İstek oluşturma ve arama ayarlarını tanımlama](/privacy/priva/subject-rights-requests-create) - Artık istek oluşturmanın iki yolu olduğunu açıklayan alt başlıklarla yeni çerçeveleme: kılavuzlu bir işlem kullanarak özel bir yöntem aracılığıyla ve arama parametreleri duruma en uygun içeriği almayı hedefleyen bir şablon kullanmanın yeni özelliğiyle.
  - [Veri tahmini ve alma](/privacy/priva/subject-rights-requests-data-retrieval) - bazı isteklerin neden veri tahmini aşamasında durakladığını ve sonuç olarak aramayı nasıl ayarlayabileceğinizi açıklar; ayrıca, otomatik olarak veri alma işlemine geçmeden önce duraklatmak için bir isteğin nasıl ayarlanacağı da açıklanmaktadır.
  - [Konu hakları isteğinin verilerini gözden geçirme](/privacy/priva/subject-rights-requests-data-review) - yeni içeri aktarma dosyası özellikleri, kullanıcıların Microsoft olmayan 365 konumlarından veya arama tarafından alınmayan dosyaları Toplanan veriler sekmesine getirmesine olanak tanır.
  - [Raporlar oluşturma ve kapatma istekleri](/privacy/priva/subject-rights-requests-reports) - son veri paketleri oluşturulduğunda ve bunların ne tür dosyalar içerdiğini açıklar.
  - [Microsoft Graph API ve Power Automate aracılığıyla tümleştirin ve genişletin](/privacy/priva/subject-rights-requests-automate). Bu önceki Power Automate sayfasının başlığını ve genişletilmiş sayfa içeriğini daha önce başka bir sayfada yaşayan Graph API içerik ve başvuru bağlantılarını içerecek şekilde düzeltti.

### <a name="sensitive-information-types"></a>Hassas Bilgi Türleri

- [Tam veri eşleşmesi tabanlı hassas bilgi türleri hakkında bilgi edinin](sit-learn-about-exact-data-match-based-sits.md) . EDM'nin desteklediği hizmetlere ilişkin bölüm eklendi.

### <a name="sensitivity-labels"></a>Duyarlılık etiketleri

- Önizlemede: Belgeleri PDF biçimine dönüştürmeyi, etiketi herhangi bir görsel işaretle ve şifrelemeyle devralmayı içeren [Office uygulamaları için PDF desteği](sensitivity-labels-office-apps.md#pdf-support). PDF'ye yazdır desteklenmez ve etiket ilkeleri zorunlu etiketleme için yapılandırılmışsa bu seçenek kullanıcılar için kullanılamaz duruma gelir.
- Önizlemede: Kullanıcıların etiket ilkelerinin etiketi kaldırmak veya düşürmek için gerekçe gerektirecek şekilde yapılandırıldığında gördüğü iletişim kutusu, kullanıcıları yazılan yanıtlarının hassas veriler içermemesi gerektiği konusunda uyaracak şekilde güncelleştirilir. [Etiket ilkelerinin yapabilecekleri](sensitivity-labels.md#what-label-policies-can-do) bölümündeki ekran görüntüsü, üretim kullanımı için Office dağıtım kanallarına giden bu güncelleştirilmiş iletişim kutusunu gösterir.
- Önizlemede: [Outlook'un S/MIME koruması uygulama desteği](sensitivity-labels-office-apps.md#configure-a-label-to-apply-smime-protection-in-outlook) istemci platformlarında kullanıma sunulmaya yeni başlıyor.
- [Otomatik etiketleme ilkeleri](apply-sensitivity-label-automatically.md#creating-an-auto-labeling-policy) için, belirli bir gün içinde düzenlenmezse ilkeyi otomatik olarak açabilen yeni bir ayardır.

### <a name="trainable-classifiers"></a>Eğitilebilir Sınıflandırıcılar

- [Eğitilebilir sınıflandırıcılar hakkında bilgi edinin](classifier-learn-about.md) : Adult, Racy, Gory images trainable classifier eklendi.

## <a name="may-2022"></a>Mayıs 2022

### <a name="communication-compliance"></a>İletişim uyumluluğu

- [İletişim uyumluluk raporları ve denetimleri](communication-compliance-reports-audits.md) - dışarı aktarılan raporlar için güncelleştirilmiş dosya boyutu sınırları.
- [İletişim uyumluluk ilkeleri](communication-compliance-policies.md) - kullanıcı tarafından bildirilen iletilerin devre dışı bırakılması/etkinleştirilmesi ve Teams ve Exchange için net bir işlemenin netleştirilmesi.

### <a name="compliance-manager"></a>Uyumluluk Yöneticisi

- [Uyarılar ve uyarı ilkeleri](compliance-manager-alert-policies.md) - Tüm kuruluşlar için varsayılan puan değişikliği ilkesini açıklayan yeni bölüm.
- [İyileştirme eylemleriyle çalışma](compliance-manager-improvement-actions.md) - uygulama durumu ve test durumu için durum durumları netleştirildiğinden, otomatik olarak test edilen eylemlerle el ile test edilen eylemler arasında ikinci durum ayrımı yapılır.
- [Şablonlar listesi](compliance-manager-templates-list.md) - Avrupa, Orta Doğu ve Afrika (EMEA) bölgesine iki yeni şablon eklendi: Katar Ulusal Bilgi Güvencesi (NIA) ve BAE Veri Gizliliği Yasası.

### <a name="compliance-offerings--service-assurance"></a>Hizmet güvencesi & uyumluluk teklifleri

- [Microsoft Güvenlik Geliştirme Yaşam Döngüsü](/compliance/assurance/assurance-microsoft-security-development-lifecycle) - Microsoft hizmetleri için yeni SDL güvencesi konusu.

### <a name="data-lifecycle-management-and-records-management"></a>Veri yaşam döngüsü yönetimi ve kayıt yönetimi

- Şu anda önizleme sürümünde kullanıma sunulmuştur: [Saklama süresinin sonundaki yeni yeniden etiketleme seçeneği](retention-settings.md#relabeling-at-the-end-of-the-retention-period).
- Yeni dağıtım kılavuzu: [Microsoft Purview ile veri idaresi çözümü dağıtma](data-governance-solution.md)
- Kaynak posta kutularının hem statik kapsamlar hem de uyarlamalı kapsamlar için Exchange saklama ve silme için desteklendiğini onaylamak için belgelerde düzeltme. Statik kapsamlar için kaynak posta kutuları kuruluş genelindeki ilkeye (Tümü varsayılanı) varsayılan olarak eklenir.
- Son kullanıcılar için yeni belgeler: [Çevrimiçi arşiv posta kutularıyla e-posta depolamayı yönetme](https://support.services.microsoft.com/office/manage-email-storage-with-online-archive-mailboxes-1cae7d17-7813-4fe8-8ca2-9a5494e9a721)

### <a name="data-loss-prevention"></a>Veri kaybı önleme

- [DLP ilkeleri için e-posta bildirimleri ve ilke ipuçları gönderin](use-notifications-and-policy-tips.md) . Bildirimi neyin tetiklediği ve bunları kimlerin alabileceği hakkında yeni bilgiler eklendi.

### <a name="information-barriers"></a>Bilgi engelleri

- [Bilgi engelleri hakkında bilgi engelleri hakkında bilgi edinin](information-barriers.md): Konuların yeniden düzenlenmiş yapısı ve yeni IB kullanıcı arabirimi deneyimi desteği içerecek şekilde güncelleştirilmiş Exchange Online desteği ve sınırlamaları için açıklama eklendi. [](information-barriers-policies.md)

### <a name="insider-risk-management"></a>İçeriden risk yönetimi

- [Insider risk yönetimi ayarlarını kullanmaya başlama](insider-risk-management-settings.md) - yeni Bulut uygulaması için Defender göstergeleri, özel eşiklerde tetikleme olayı olarak yeni anomali, yeni dosya uzantısı öncelik belirlemesi ve duyarlılık etiketleri ilke desteği için yönergeler eklendi.
- [Insider risk yönetimi örnekleri](insider-risk-management-cases.md) - eBulma olayı kılavuzuna yükseltmeyi açıklığa kavuşturdu.

### <a name="microsoft-priva"></a>Microsoft Priva

- Rolleri ve uygunluğu netleştirmek için [ücretsiz Priva deneme sürümü](/privacy/priva/priva-trial) - yeni evrensel Microsoft 365 deneme hüküm ve koşullarının ve küçük güncelleştirmelerin güncelleştirilmiş bağlantısı hakkında bilgi edinin.
- [Priva kullanmaya başlama - Priva](/privacy/priva/priva-setup) kullanılabilirliğiyle ilgili sınırlamaları belirten bölüm eklendi.

### <a name="sensitive-information-types"></a>Hassas Bilgi Türleri

- Müşteri yükseltmesinden, EDM'nin desteklendiği bölgeleri ve kiracınızın bölgesini bulma yordamlarını ekleyen [hassas bilgi türleriyle tam veri eşleşmesi hakkında bilgi edinin](sit-learn-about-exact-data-match-based-sits.md).
- [EDM SIT kural paketi oluşturma](sit-get-started-exact-data-match-create-rule-package.md) - şema makalesinden 'belirli veri türleriyle çalışma' eklendi.
- [EDM SIT için Şema Oluştur](sit-get-started-exact-data-match-create-schema.md) - 'belirli veri türleriyle çalışma' kaldırıldı.
- [DLP ilkelerinizde adlandırılmış varlıkları kullanın](named-entities-use.md)- Microsoft Defender for Cloud Apps için destek deyimi eklendi.

### <a name="sensitivity-labels"></a>Duyarlılık etiketleri

- Otomatik [etiketleme ayarlarını otomatik etiketleme ilkesine](apply-sensitivity-label-automatically.md#convert-your-label-settings-into-an-auto-labeling-policy) otomatik olarak dönüştürmek için etiket oluşturma veya düzenleme işleminin sonundaki yeni seçenek.
- SharePoint ve OneDrive için otomatik etiketleme ilkeleri artık dosyayı son değiştiren hesap artık Azure AD mevcut olmadığında şifreleme içeren etiketler uygulayabilir.
- Kapsayıcı etiketleri Office 365 Content Delivery Networks (CDN) için desteklenir.
- [Etiketleri kaldırma ve silmeye yönelik](create-sensitivity-labels.md#removing-and-deleting-labels) açıklamalar.
- Yeni [yaygın senaryolar](get-started-with-sensitivity-labels.md#common-scenarios-for-sensitivity-labels):
  - Sql veritabanı sütunlarını dosyalar ve e-postalar için kullanılan duyarlılık etiketlerini kullanarak etiketleyin; böylece kuruluş, dışarı aktarıldığında yapılandırılmış verileri korumaya devam eden birleşik bir etiketleme çözümüne sahip olur
  - Kişisel verileri içeren içeriğin paylaşıldığına ve korunması gerektiğini belirten bir uyarı aldıktan sonra dosyaya duyarlılık etiketi uygulama

### <a name="changes-to-product-names"></a>Ürün adlarına yapılan değişiklikler

Günümüzün merkezi olmayan, veri açısından zengin çalışma alanının zorluklarını karşılamak için, tüm veri varlığınızı anlamanıza, yönetmenize ve korumanıza yardımcı olan kapsamlı bir çözüm kümesi olan [Microsoft Purview'u](https://aka.ms/microsoftpurview) kullanıma sunuyoruz. Bu yeni marka ailesi, eski Microsoft Purview Veri Eşlemesi ve müşterilerin zaten güvendiği Microsoft 365 uyumluluk portföyünün özelliklerini bir araya getirerek kuruluşunuz için birleşik veri idaresi ve risk yönetimi sağlar.

| **Eski Ad** | **Yeni Ad** | **Açıklama** |
|:----------------|:-------------|:----------------|
| Microsoft 365 Gelişmiş Denetim <br><br> Microsoft 365 Temel Denetimi | Microsoft Purview Denetim (Premium) <br><br> Microsoft Purview Denetim (Standart)| Denetim çözümleri, kuruluşların güvenlik olaylarına, adli araştırmalara, iç araştırmalara ve uyumluluk yükümlülüklerine etkili bir şekilde yanıt vermelerine yardımcı olmak için tümleşik bir çözüm sağlar. Daha fazla bilgi edinmek için bkz. [Microsoft Purview Gelişmiş Denetimi (Premium)](advanced-audit.md) ve [Microsoft Purview Gelişmiş Denetimi (Standart)](set-up-basic-audit.md). |
| Microsoft 365 İletişim Uyumluluğu | Microsoft Purview İletişim Uyumluluğu | İletişim Uyumluluğu, şirket iletişim kanalları ve ilke ihlallerini hızla algılamanıza, yakalamanıza ve düzeltme eylemleri gerçekleştirmenize yardımcı olarak riskleri en aza indirmenize yardımcı olur. Daha fazla bilgi için bkz. [Microsoft Purview İletişim Uyumluluğu](communication-compliance-solution-overview.md). |
| Microsoft Uyumluluk Yöneticisi | Microsoft Purview Uyumluluk Yöneticisi | Uyumluluk Yöneticisi, veri koruma risklerinizin envanterini almaktan denetimleri uygulama, düzenlemeler ve sertifikalarla güncel kalma ve denetçilere raporlama gibi karmaşıklıkları yönetmeye kadar uyumluluk yolculuğunuz boyunca size yardımcı olabilir. Daha fazla bilgi için bkz. [Microsoft Purview Uyumluluk Yöneticisi](compliance-manager.md). |
| Microsoft 365 Müşteri Anahtarı | Microsoft Purview Müşteri Anahtarı | Müşteri Anahtarı, yetkisiz sistemler veya personel tarafından verilerin görüntülenmesine karşı ek koruma sağlar ve Microsoft veri merkezlerinde BitLocker disk şifrelemesini tamamlar. Daha fazla bilgi için bkz. [Microsoft Purview Müşteri Anahtarı](customer-key-overview.md). |
| Office 365 Müşteri Kasası | Microsoft Purview Müşteri Kasası | Müşteri Kasası, Microsoft'un açık onayınız olmadan hizmet işlemleri yapmak için içeriğinize erişememesini sağlar. Müşteri Kasası sizi Microsoft'un yalnızca yetkili isteklerin içeriğinize erişim izni vermek için kullandığı onay iş akışı sürecine getirir. Daha fazla bilgi için bkz. [Microsoft Purview Müşteri Kasası](customer-lockbox-requests.md). |
| Veri Kaybı Önleme | Microsoft Purview Veri Kaybı Önleme | DLP, kullanıcıların verileri sahip olmaması gereken kişilerle uygunsuz bir şekilde paylaşmasını engelleyerek hassas verilerin korunmasına ve riskin azaltılmasına yardımcı olur. Daha fazla bilgi için bkz. [Microsoft Purview Veri Kaybı Önleme](dlp-learn-about-dlp.md). |
| Microsoft 365 için Çift Anahtar Şifrelemesi | Microsoft Purview Çift Anahtar Şifrelemesi | Çift Anahtar Şifrelemesi (DKE), korumalı içeriğe erişmek için iki anahtarı birlikte kullanır. Microsoft, bir anahtarı Microsoft Azure içinde tutar, siz de diğer anahtarı elinizde bulundurursunuz. Daha fazla bilgi edinmek için bkz. [Microsoft Purview Çift Anahtar Şifrelemesi](double-key-encryption.md) |
| Microsoft 365 Bilgi Engelleri | Microsoft Purview Bilgi Engelleri | Bilgi Engelleri, iç bilgileri korumak için kuruluşunuz içindeki belirli kişiler arasındaki iletişimi ve işbirliğini kısıtlayan bir çözümdür. Daha fazla bilgi için bkz. [Microsoft Purview Bilgi Engelleri](information-barriers-solution-overview.md). |
| Microsoft Bilgi Koruması | Microsoft Purview Bilgi Koruması | Bilgi koruması, hassas bilgileri nerede yaşarsa yaşasın veya nereye giderse gitsin keşfetmenize, sınıflandırmanıza ve korumanıza yardımcı olur. Daha fazla bilgi için bkz. [Microsoft Purview Bilgi Koruması](information-protection.md). |
| Microsoft Bilgi İdaresi | Microsoft Purview Veri Yaşam Döngüsü Yönetimi | Veri yaşam döngüsü yönetimi, saklamanız ve silmeniz gereken içeriği saklamanız için araçlar ve özellikler sağlar. Daha fazla bilgi için bkz. [Microsoft Purview Veri Yaşam Döngüsü Yönetimi](data-lifecycle-management.md). |
| Microsoft 365 Insider Risk Management | Microsoft Purview İçeriden Risk Yönetimi | Insider risk yönetimi, riskli kullanıcı etkinliklerini hızla tanımlamanıza, önceliklendirmenize ve harekete geçirmenize yardımcı olmak için hizmetin ve üçüncü taraf göstergelerin tamamını kullanır. Daha fazla bilgi için bkz. [Microsoft Purview İçeriden Risk Yönetimi](insider-risk-management.md). |
| Office 365 İleti Şifrelemesi | Microsoft Purview İleti Şifrelemesi | İleti Şifreleme ile kuruluşunuz, kuruluşunuzun içindeki ve dışındaki kişiler arasında şifreli e-posta iletileri gönderebilir ve alabilir. Daha fazla bilgi için bkz. [Microsoft Purview İleti Şifrelemesi](ome.md). |
| Microsoft 365'te Privileged Access Management | Microsoft Purview Privileged Access Management | Privileged Access Management, kuruluşunuzun ihlallere karşı korunmasına yardımcı olur ve hassas verilere veya kritik yapılandırma ayarlarına erişimi sınırlayarak uyumluluk en iyi yöntemlerini karşılamaya yardımcı olur. Daha fazla bilgi için bkz. [Microsoft Purview Privileged Access Management](privileged-access-management-solution-overview.md). |
| Microsoft veri bağlayıcıları | Microsoft Purview veri bağlayıcıları | Microsoft 365, yöneticilerin Microsoft 365 kuruluşunuzdaki posta kutularına microsoft dışı, üçüncü taraf verileri sosyal medya platformlarından, anlık ileti platformlarından ve belge işbirliği platformlarından içeri aktarmak ve arşivlemek için veri bağlayıcılarını kullanmasına olanak tanır. Daha fazla bilgi için bkz. [Microsoft Purview veri bağlayıcıları](compliance-extensibility.md). |
| Microsoft 365 Gelişmiş eKeşif <br><br> Microsoft 365 Core eKeşif | Microsoft Purview eKeşif (Premium) <br><br> Microsoft Purview eKeşif (Standart) | Elektronik bulma veya eBulma, yasal davalarda kanıt olarak kullanılabilecek elektronik bilgileri tanımlama ve teslim etme işlemidir. Daha fazla bilgi için bkz. [Microsoft Purview eKeşif (Premium)](overview-ediscovery-20.md) ve [Microsoft Purview eKeşif (Standart)](get-started-core-ediscovery.md). |
| Microsoft 365 uyumluluk merkezi | Microsoft Purview uyumluluk portalı | Microsoft 365 E5 Uyumluluk paketindeki çözümlere ve çözüm kataloğuna erişmek için portalı Yönetici. Daha fazla bilgi için bkz. [Microsoft Purview uyumluluk portalı](microsoft-365-compliance-center.md). |
