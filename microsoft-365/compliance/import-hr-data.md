---
title: İk verilerini içeri aktarmak için bağlayıcı ayarlama
description: Yöneticiler, çalışan verilerini kuruluşlarının insan kaynakları (İk) sisteminden Microsoft 365'e aktarmak için bir veri bağlayıcısı ayarlayabilir. Bu, kuruluşunuz için iç tehdit oluşturabilecek belirli kullanıcıların etkinliklerini algılamanıza yardımcı olmak için şirket içi risk yönetimi ilkelerinde İk verilerini kullanmanıza olanak tanır.
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- tier3
- purview-compliance
- data-connectors
ms.custom: admindeeplinkCOMPLIANCE
ms.openlocfilehash: a2c4a26a542af5a10244c24720d1b410152888a7
ms.sourcegitcommit: ab45f2963e0635ff2cb9670f6f7b4c784f6a250e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/02/2022
ms.locfileid: "68812041"
---
# <a name="set-up-a-connector-to-import-hr-data"></a>İk verilerini içeri aktarmak için bağlayıcı ayarlama

kullanıcının istifası veya kullanıcının iş düzeyindeki bir değişiklik gibi olaylarla ilgili insan kaynakları (İk) verilerini içeri aktarmak için Microsoft Purview uyumluluk portalı bir veri bağlayıcısı ayarlayabilirsiniz. daha sonra İk verileri, kuruluşunuzdaki kullanıcılar tarafından olası kötü amaçlı etkinlikleri veya veri hırsızlığını tanımlamanıza yardımcı olabilecek risk göstergeleri oluşturmak için [insider risk yönetimi çözümü](insider-risk-management.md) tarafından kullanılabilir.

Insider risk yönetimi ilkelerinin risk göstergeleri oluşturmak için kullanabileceği İk verileri için bağlayıcı ayarlamak, İk verilerini içeren bir CSV dosyası oluşturmak, kimlik doğrulaması için kullanılan Azure Active Directory'de bir uygulama oluşturmak, uyumluluk portalında bir İk veri bağlayıcısı oluşturmak ve ardından CSV dosyalarındaki İk verilerini kullanılabilir hale getirmek için csv dosyalarına alan bir betik (zamanlanmış olarak) çalıştırmaktır öğesini insider risk yönetimi çözümüne ekleyin.

> [!IMPORTANT]
> İk bağlayıcısının yeni bir sürümü artık genel önizleme için kullanılabilir. Yeni bir İk bağlayıcısı oluşturmak veya iç risk yönetimine yönelik sağlık ilkesi [senaryosuna yönelik yeni çalışan profili senaryosuna](#csv-file-for-employee-profile-data-preview) yönelik verileri içeri aktarmak için uyumluluk portalındaki **Veri bağlayıcıları** sayfasına gidin, **Bağlayıcılar** sekmesini seçin ve ardından kurulumu başlatmak için **İk (önizleme) > bağlayıcı ekle'yi** seçin. Mevcut İk bağlayıcıları herhangi bir kesinti olmadan çalışmaya devam edecektir.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="before-you-begin"></a>Başlamadan önce

- Hangi İk senaryolarının ve verilerin Microsoft 365'e aktarılacağını belirleyin. Bu, kaç CSV dosyası ve İk bağlayıcısı oluşturmanız gerektiğini ve CSV dosyalarının nasıl oluşturulup yapılandırılacağını belirlemenize yardımcı olur. İçeri aktardığınız İk verileri, uygulamak istediğiniz insider risk yönetimi ilkeleri tarafından belirlenir. Daha fazla bilgi için bkz. 1. Adım.

- Kuruluşunuzun İk sisteminden (ve düzenli olarak) verilerin nasıl alınacağını veya dışarı aktarıldığını belirleyin ve 1. Adımda oluşturduğunuz CSV dosyalarına ekleyin. 4. Adımda çalıştırdığınız betik, CSV dosyalarındaki İk verilerini Microsoft buluta yükler.

- 3. Adımda İk bağlayıcısını oluşturan kullanıcıya Veri Bağlayıcısı Yönetici rolü atanmalıdır. Bu rol, uyumluluk portalındaki **Veri bağlayıcıları sayfasına bağlayıcı** eklemek için gereklidir. Bu rol varsayılan olarak birden çok rol grubuna eklenir. Bu rol gruplarının listesi için Microsoft 365 Defender ve [Microsoft Purview uyumluluk portallarındaki Roller ve rol grupları bölümündeki "Defender ve uyumluluk portallarındaki roller](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-defender-and-compliance-portals)" bölümüne bakın. Alternatif olarak, kuruluşunuzdaki bir yönetici özel bir rol grubu oluşturabilir, Veri Bağlayıcısı Yönetici rolünü atayabilir ve ardından uygun kullanıcıları üye olarak ekleyebilir. Yönergeler için, [Microsoft Purview uyumluluk portalı İzinler](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group) bölümündeki "Özel rol grubu oluşturma" bölümüne bakın.

- 4. Adımda çalıştırdığınız örnek betik, İk verilerinizi Microsoft buluta yükleyerek insider risk yönetimi çözümü tarafından kullanılabilmesini sağlar. Bu örnek betik, herhangi bir Microsoft standart destek programı veya hizmeti altında desteklenmez. Örnek betik, herhangi bir garanti olmadan OLDUĞU GIBI sağlanır. Microsoft, satılabilirlik veya belirli bir amaca uygunlukla ilgili zımni garantiler dahil ancak bunlarla sınırlı olmaksızın tüm zımni garantileri de reddeder. Örnek betiğin ve belgelerin kullanımından veya performansından kaynaklanan tüm risk sizinle kalır. Hiçbir durumda Microsoft, yazarları veya betiklerin oluşturulması, üretimi veya teslimi ile ilgili herhangi bir kişi, örnek betiklerin veya belgelerin kullanımından veya kullanılamama durumundan kaynaklanan herhangi bir zarardan (bunlarla sınırlı olmaksızın, iş kârı kaybı, iş kesintisi, iş bilgisi kaybı veya diğer maddi kayıplar dahil) sorumlu tutulamaz,  Microsoft'a bu tür hasarlar olabileceği bildirilmiş olsa bile.

- Bu bağlayıcı, Microsoft 365 US Government bulutundaki GCC ortamlarında kullanılabilir. Üçüncü taraf uygulamalar ve hizmetler, kuruluşunuzun müşteri verilerini Microsoft 365 altyapısının dışında olan ve bu nedenle Microsoft Purview ve veri koruma taahhütleri kapsamında olmayan üçüncü taraf sistemlerde depolamayı, iletmeyi ve işlemeyi içerebilir. Microsoft, üçüncü taraf uygulamalara bağlanmak için bu ürünün kullanıldığının, bu üçüncü taraf uygulamaların FEDRAMP uyumlu olduğunu ifade ettiğini ifade etmemektedir. GCC ortamında İk bağlayıcısı ayarlamaya yönelik adım adım yönergeler için bkz. [US Government'da İk verilerini içeri aktarmak için bağlayıcı ayarlama](import-hr-data-US-government.md).

## <a name="step-1-prepare-a-csv-file-with-your-hr-data"></a>1. Adım: İk verilerinizle csv dosyası hazırlama

İlk adım, bağlayıcının Microsoft 365'e aktaracağı İk verilerini içeren bir CSV dosyası oluşturmaktır. Bu veriler, insider risk çözümü tarafından olası risk göstergelerini oluşturmak için kullanılacaktır. Aşağıdaki İk senaryolarına ilişkin veriler Microsoft 365'e aktarılabilir:

- Çalışan istifası. Kuruluşunuzdan ayrılan çalışanlar hakkında bilgi.

- İş düzeyi değişiklikleri. Çalışanlar için promosyonlar ve indirgemeler gibi iş düzeyi değişiklikleri hakkında bilgi.

- Performans incelemeleri. Çalışan performansı hakkında bilgi.

- Performans geliştirme planları. Çalışanlar için performans geliştirme planları hakkında bilgi.

- Çalışan profili (önizleme). Bir çalışan hakkında genel bilgiler.

İçeri aktaracak İk verilerinin türü, insider risk yönetimi ilkesine ve uygulamak istediğiniz ilgili ilke şablonuna bağlıdır. Aşağıdaki tabloda, her ilke şablonu için hangi İk veri türünün gerekli olduğu gösterilmektedir:

|  İlke şablonu |  İk veri türü |
|:------------------------------|:--------------------------------|
| Ayrılan kullanıcılar tarafından veri hırsızlığı | Çalışan istifaları|
| Veri sızıntıları                             | Geçerli değil|
| Öncelikli kullanıcılara göre veri sızıntıları                   | Geçerli değil |
| Riskli kullanıcılar tarafından veri sızıntıları                | İş düzeyi değişiklikleri, Performans incelemeleri, Performans geliştirme planları|
| Güvenlik ilkesi ihlalleri             | Geçerli değil |
| Ayrılan kullanıcıların güvenlik ilkesi ihlalleri  | Çalışan istifaları|
| Öncelikli kullanıcılara göre güvenlik ilkesi ihlalleri   | Geçerli değil|
| Riskli kullanıcıların güvenlik ilkesi ihlalleri| İş düzeyi değişiklikleri, Performans incelemeleri, Performans geliştirme planları |
| E-postada rahatsız edici dil                    | Geçerli değil |
| Sağlık politikası| Çalışan profili |
|||

Insider risk yönetimine yönelik ilke şablonları hakkında daha fazla bilgi için bkz. [Insider risk yönetimi ilkeleri](insider-risk-management-policies.md#policy-templates).

Her İk senaryosu için, bir veya daha fazla CSV dosyasında ilgili İk verilerini sağlamanız gerekir. Insider risk yönetimi uygulamanız için kullanılacak CSV dosyalarının sayısı bu bölümün ilerleyen bölümlerinde ele alınmalıdır.

Gerekli İk verileriyle CSV dosyasını oluşturduktan sonra, 4. Adımda betiği çalıştırdığınız yerel bilgisayarda depolayın. Ayrıca CSV dosyasının her zaman en güncel bilgileri içerdiğinden emin olmak için bir güncelleştirme stratejisi uygulamanız gerekir. Böylece betiği çalıştırdığınızda en güncel İk verileri Microsoft buluta yüklenir ve insider risk yönetimi çözümü tarafından erişilebilir.

> [!IMPORTANT]
> Aşağıdaki bölümlerde açıklanan sütun adları gerekli parametreler değildir, yalnızca örneklerdir. CSV dosyalarınızda herhangi bir sütun adını kullanabilirsiniz. Ancak, BIR CSV dosyasında kullandığınız sütun adları, 3. Adımda İk bağlayıcısını oluştururken veri türüyle *eşlenmelidir* . Ayrıca, aşağıdaki bölümlerde yer alan örnek CSV dosyalarının Not Defteri görünümünde görüntülendiğini unutmayın. Csv dosyalarını Microsoft Excel'de görüntülemek ve düzenlemek çok daha kolaydır.

Aşağıdaki bölümlerde her İk senaryosu için gerekli CSV verileri açıklanmaktadır.

### <a name="csv-file-for-employee-resignation-data"></a>Çalışanların istifa verileri için CSV dosyası

Aşağıda çalışan istifa verilerine yönelik bir CSV dosyası örneği verilmiştir.

```text
EmailAddress,ResignationDate,LastWorkingDate
sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,2019-04-29T15:18:02.4675041+05:30
pilarp@contoso.com,2019-04-24T09:15:49Z,2019-04-29T15:18:02.7117540
```

Aşağıdaki tabloda, çalışan istifa verileri için CSV dosyasındaki her sütun açıklanmaktadır.

|  Sütun   |   Açıklama |
|:------------|:----------------|
|**Emailaddress**| Sonlandırılan kullanıcının e-posta adresini (UPN) belirtir.|
| **İstifaTarihi** | Kullanıcının çalışma tarihinin kuruluşunuzda resmi olarak sonlandırıldığını belirtir. Örneğin, bu tarih kullanıcının kuruluşunuzdan ayrılma hakkında bildirimde bulunacağı tarih olabilir. Bu tarih, kişinin son iş günü tarihinden farklı olabilir. Şu tarih biçimini kullanın: `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm`[ISO 8601 tarih ve saat biçimidir](https://www.iso.org/iso-8601-date-and-time-format.html).|
| **LastWorkingDate** | Sonlandırılan kullanıcının son çalışma gününü belirtir. Şu tarih biçimini kullanın: `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm`[ISO 8601 tarih ve saat biçimidir](https://www.iso.org/iso-8601-date-and-time-format.html).|
|||

### <a name="csv-file-for-job-level-changes-data"></a>İş düzeyi değişiklik verileri için CSV dosyası

İşte iş düzeyi değişiklik verilerine yönelik bir CSV dosyası örneği.

```text
EmailAddress,EffectiveDate,OldLevel,NewLevel
sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,Level 61 - Sr. Manager,Level 60- Manager
pillar@contoso.com,2019-04-23T15:18:02.4675041+05:30,Level 62 - Director,Level 60- Sr. Manager
```

Aşağıdaki tabloda, iş düzeyi değişiklik verileri için CSV dosyasındaki her sütun açıklanmaktadır.

|  Sütun | Açıklama |
|:--------- |:------------- |
| **Emailaddress**  | Kullanıcının e-posta adresini (UPN) belirtir.|
| **EffectiveDate** | Kullanıcının iş düzeyinin resmi olarak değiştirildiği tarihi belirtir. Şu tarih biçimini kullanın: `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm`[ISO 8601 tarih ve saat biçimidir](https://www.iso.org/iso-8601-date-and-time-format.html).|
| **Açıklamalar**| Değerlendiricinin iş düzeyinin değiştirilmesi hakkında sağladığı açıklamaları belirtir. 200 karakterlik bir sınır girebilirsiniz. Bu parametre isteğe bağlıdır. CSV dosyasına eklemeniz gerekmez.|
| **OldLevel**| Kullanıcının iş düzeyini değiştirilmeden önce belirtir. Bu bir serbest metin parametresidir ve kuruluşunuz için hiyerarşik taksonomi içerebilir. Bu parametre isteğe bağlıdır. CSV dosyasına eklemeniz gerekmez.|
| **NewLevel**| Değiştirildikten sonra kullanıcının iş düzeyini belirtir. Bu bir serbest metin parametresidir ve kuruluşunuz için hiyerarşik taksonomi içerebilir. Bu parametre isteğe bağlıdır. CSV dosyasına eklemeniz gerekmez.|
|||

### <a name="csv-file-for-performance-review-data"></a>Performans gözden geçirme verileri için CSV dosyası

Performans verilerine yönelik bir CSV dosyası örneği aşağıda verilmiştır.

```text
EmailAddress,EffectiveDate,Remarks,Rating
sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,Met expectations but bad attitude,2-Below expectation
pillar@contoso.com,2019-04-23T15:18:02.4675041+05:30, Multiple conflicts with the team
```

Aşağıdaki tabloda, performans gözden geçirme verileri için CSV dosyasındaki her sütun açıklanmaktadır.

|  Sütun | Açıklama |
|:----------|:--------------|
| **Emailaddress**  | Kullanıcının e-posta adresini (UPN) belirtir.|
| **EffectiveDate** | Kullanıcının performans gözden geçirmesinin sonucu hakkında resmi olarak bilgilendirildiği tarihi belirtir. Bu, performans gözden geçirme döngüsünün sona ertiği tarih olabilir. Şu tarih biçimini kullanın: `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm`[ISO 8601 tarih ve saat biçimidir](https://www.iso.org/iso-8601-date-and-time-format.html).|
| **Açıklamalar**| Değerlendiricinin performans gözden geçirmesi için kullanıcıya sağladığı tüm açıklamaları belirtir. Bu, 200 karakter sınırı olan bir metin parametresidir. Bu parametre isteğe bağlıdır. CSV dosyasına eklemeniz gerekmez.|
| **Değerlendirme**| Performans gözden geçirmesi için sağlanan derecelendirmeyi belirtir. Bu bir metin parametresidir ve kuruluşunuzun değerlendirmeyi tanımak için kullandığı serbest biçimli metinleri içerebilir. Örneğin, "3 Beklentileri karşılandı" veya "2 Ortalamanın altında". Bu, 25 karakter sınırına sahip bir metin parametresidir. Bu parametre isteğe bağlıdır. CSV dosyasına eklemeniz gerekmez.|
|||

### <a name="csv-file-for-performance-improvement-plan-data"></a>Performans geliştirme planı verileri için CSV dosyası

Performans geliştirme planı verilerine yönelik veriler için bir CSV dosyası örneği aşağıda verilmiştır.

```text
EmailAddress,EffectiveDate,ImprovementRemarks,PerformanceRating
sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,Met expectation but bad attitude,2-Below expectation
pillar@contoso.com,2019-04-23T15:18:02.4675041+05:30, Multiple conflicts with the team
```

Aşağıdaki tabloda, performans gözden geçirme verileri için CSV dosyasındaki her sütun açıklanmaktadır.

|  Sütun |  Açıklama |
|:----------|:---------------|
| **Emailaddress**  | Kullanıcının e-posta adresini (UPN) belirtir.|
| **EffectiveDate** | Kullanıcının performans geliştirme planı hakkında resmi olarak bilgilendirildiği tarihi belirtir. Şu tarih biçimini kullanmanız gerekir: `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm`[, ISO 8601 tarih ve saat biçimidir](https://www.iso.org/iso-8601-date-and-time-format.html).|
| **Açıklamalar**| Değerlendiricinin performans geliştirme planı hakkında sağladığı tüm açıklamaları belirtir. Bu, 200 karakter sınırı olan bir metin parametresidir. Bu isteğe bağlı bir parametredir. CSV dosyasına eklemeniz gerekmez. |
| **Değerlendirme**| Performans gözden geçirmesi ile ilgili tüm derecelendirmeleri veya diğer bilgileri belirtir. Bu bir metin parametresidir ve kuruluşunuzun değerlendirmeyi tanımak için kullandığı herhangi bir serbest biçimli metin içerebilir. Örneğin, "3 Beklentileri karşılandı" veya "2 Ortalamanın altında". Bu, 25 karakter sınırına sahip bir metin parametresidir. Bu isteğe bağlı bir parametredir. CSV dosyasına eklemeniz gerekmez.|
|||

### <a name="csv-file-for-employee-profile-data-preview"></a>Çalışan profili verileri için CSV dosyası (önizleme)

> [!NOTE]
> Çalışan profili verileri için İk bağlayıcısı oluşturma özelliği genel önizleme aşamasındadır. Çalışan profili verilerini destekleyen bir İk bağlayıcısı oluşturmak için uyumluluk portalındaki **Veri bağlayıcıları** sayfasına gidin, **Bağlayıcılar** sekmesini ve ardından Bağlayıcı  > **İk (önizleme) ekle'yi** seçin. [3. Adım: İk bağlayıcısı oluşturma başlığı altında bağlayıcı oluşturma adımlarını](#step-3-create-the-hr-connector) izleyin.

Burada çalışan profili verilerine yönelik bir CSV dosyası örneği verilmiştir.

```text
EmailAddress,UserName,EmployeeFirstName,EmployeeLastName,EmployeeAddLine1,EmployeeAddLine2,EmployeeCity,EmployeeState,EmployeeZipCode,EmployeeDept,EmployeeType,EmployeeRole
jackq@contoso.com,jackq,jack,qualtz,50 Oakland Ave,#206,City,Florida,32104,Orthopaedic,Regular,Nurse
```

Aşağıdaki tabloda, çalışan profili verileri için CSV dosyasındaki her sütun açıklanmaktadır.

|  Sütun |  Açıklama |
|:----------|:---------------|
| Emailaddress<sup>*</sup>    | Çalışanın kullanıcı asıl adı (UPN) veya e-posta adresi.|
| EmployeeFirstName<sup>*</sup>   | Çalışanın adı.|
| EmployeeLastName<sup>*</sup>   | Çalışanın soyadı.|
| EmployeeAddressLine1<sup>*</sup>    | Çalışanın sokak adresi.|
| EmployeeAddressLine2   | Çalışan için daire numarası gibi ikincil adres bilgileri.|
| EmployeeCity | Çalışan için ikamet şehri.|
| EmployeeState | Çalışan için ikamet durumu.|
| EmployeeZipCode<sup>*</sup>  | Çalışan için posta kodu. |
| EmployeeCountry| Çalışan için ikamet ülkesi.|
| EmployeeDepartment | Kuruluşun çalışan departmanı.|
| EmployeeType |Normal, Muaf veya Yüklenici gibi çalışan için çalışma türü.|
| EmployeeRole |Çalışanların kuruluştaki rolü, ataması veya iş unvanı.|
|||

> [!NOTE]
> <sup>*</sup> Bu sütun zorunludur. Zorunlu bir sütun eksikse CSV dosyası doğrulanmaz ve dosyadaki diğer veriler içeri aktarılamaz.

Yalnızca çalışan profili verilerini içeri aktaran bir İk bağlayıcısı oluşturmanızı öneririz. Bu bağlayıcı için, tercihen 15-20 günde bir çalışan profili verilerini sık sık yenilediğinizden emin olun. Çalışan profili kayıtları son 30 gün içinde güncelleştirilmezse silinir.

### <a name="determining-how-many-csv-files-to-use-for-hr-data"></a>İk verileri için kaç CSV dosyası kullanılacağını belirleme

3. Adım'da, her İk veri türü için ayrı bağlayıcılar oluşturmayı veya tüm veri türleri için tek bağlayıcı oluşturmayı seçebilirsiniz. Bir İk senaryosu için veri içeren ayrı CSV dosyaları kullanabilirsiniz (önceki bölümlerde açıklanan CSV dosyalarının örnekleri gibi). Alternatif olarak, iki veya daha fazla İk senaryosu için veri içeren tek bir CSV dosyası kullanabilirsiniz. İk verileri için kaç CSV dosyası kullanacağınızı belirlemenize yardımcı olacak bazı yönergeler aşağıdadır.

- Uygulamak istediğiniz insider risk yönetimi ilkesi birden çok İk veri türü gerektiriyorsa, tüm gerekli veri türlerini içeren tek bir CSV dosyası kullanmayı göz önünde bulundurun.

- İk verilerini oluşturma veya toplama yöntemi CSV dosyalarının sayısını belirleyebilir. Örneğin, İk bağlayıcısını yapılandırmak için kullanılan farklı İk veri türleri kuruluşunuzdaki tek bir İk sisteminde bulunuyorsa, verileri tek bir CSV dosyasına aktarabilirsiniz. Ancak veriler farklı İk sistemleri arasında dağıtılıyorsa verileri farklı CSV dosyalarına aktarmak daha kolay olabilir. Örneğin, Çalışan istifa verileri İş düzeyinden veya Performans gözden geçirme verilerinden farklı bir İk sisteminde bulunabilir. Bu durumda, verileri tek bir CSV dosyasında el ile birleştirmek yerine ayrı CSV dosyalarına sahip olmak daha kolay olabilir. Bu nedenle, İk sistemlerinizden verileri nasıl aldığınız veya dışarı aktardığınız, ihtiyacınız olan CSV dosyalarının sayısını belirleyebilir.

- Genel bir kural olarak, oluşturmanız gereken İk bağlayıcılarının sayısı CSV dosyasındaki veri türlerine göre belirlenir. Örneğin, bir CSV dosyası insider risk yönetimi uygulamanızı desteklemek için gereken tüm veri türlerini içeriyorsa, yalnızca bir İk bağlayıcısına ihtiyacınız vardır. Ancak her birinde tek bir veri türü içeren iki ayrı CSV dosyanız varsa iki İk bağlayıcısı oluşturmanız gerekir. Bunun bir istisnası, BIR CSV dosyasına **HRScenario** sütunu eklerseniz (sonraki bölüme bakın), farklı CSV dosyalarını işleyebilen tek bir İk bağlayıcısı yapılandırabilmenizdir.

### <a name="configuring-a-single-csv-file-for-multiple-hr-data-types"></a>Birden çok İk veri türü için tek bir CSV dosyası yapılandırma

Tek bir CSV dosyasına birden çok İk veri türü ekleyebilirsiniz. Uyguladığınız insider risk yönetimi çözümü birden çok İk veri türü gerektiriyorsa veya veri türleri kuruluşunuzdaki tek bir İk sisteminde bulunuyorsa bu yararlı olur. Daha az CSV dosyası olması, oluşturmak ve yönetmek için her zaman daha az İk bağlayıcısına sahip olmanıza olanak tanır.

Birden çok veri türüne sahip bir CSV dosyasını yapılandırma gereksinimleri şunlardır:

- Her veri türü için gerekli sütunları (ve bunları kullanıyorsanız isteğe bağlı) ve üst bilgi satırına karşılık gelen sütun adını eklemeniz gerekir. Veri türü bir sütuna karşılık gelmiyorsa, değeri boş bırakabilirsiniz.

- Birden çok İk verisi türüne sahip bir CSV dosyası kullanmak için İk bağlayıcısının CSV dosyasındaki hangi satırların hangi tür İk verilerini içerdiğini bilmesi gerekir. Bu, CSV dosyasına ek bir **HRScenario** sütunu eklenerek gerçekleştirilir. Bu sütundaki değerler, her satırdaki İk verilerinin türünü tanımlar. Örneğin İk senaryolarına karşılık gelen değerler İstifa\`, İş düzeyi değişikliği\`, \`Performans gözden geçirmesi\`, \`\`Performans geliştirme planı\` ve \`Çalışan profili\` olabilir\`.

- HRScenario** sütunu içeren birden çok CSV dosyanız varsa, her dosyanın aynı sütun adını ve belirli İk senaryolarını tanımlayan değerleri kullandığından emin olun.

Aşağıdaki örnekte **HRScenario** sütununu içeren bir CSV dosyası gösterilmektedir. HRScenario sütunundaki değerler, karşılık gelen satırdaki veri türünü tanımlar. Aşağıdaki örnek, dört İk senaryosu \`olan İstifa\`, \`İş düzeyi değişikliği\`, \`Performans incelemesi\` ve \`Performans iyileştirme planını\` kapsar.

```text
HRScenario,EmailAddress,ResignationDate,LastWorkingDate,EffectiveDate,Remarks,Rating,OldLevel,NewLevel
Resignation,sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,2019-04-29T15:18:02.4675041+05:30,,,,
Resignation,pilarp@contoso.com,2019-04-24T09:15:49Z,2019-04-29T15:18:02.7117540,,,,
Job level change,sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,,,,,Level 61 Sr. Manager, Level 60 Manager
Job level change,pillarp@contoso.com,2019-04-23T15:18:02.4675041+05:30,,,,,Level 62 Director,Level 60 Sr Manager
Performance review,sarad@contoso.com,,,2019-04-23T15:18:02.4675041+05:30,Met expectation but bad attitude,2 Below expectations,,
Performance review,pillarp@contoso.com,,,2019-04-23T15:18:02.4675041+05:30, Multiple conflicts with the team,,
Performance improvement plan,sarad@contoso.com,,,2019-04-23T15:18:02.4675041+05:30,Met expectations but bad attitude,2 Below expectations,,
Performance improvement plan,pillarp@contoso.com,,,2019-04-23T15:18:02.4675041+05:30,Multiple conflicts with the team,,
```

> [!NOTE]
> 3. Adımda bağlayıcıyı ayarlarken CSV dosyanızdaki sütunun adını İk veri türünü tanımlayan sütun olarak eşlediğiniz için, İk veri türünü tanımlayan sütun için herhangi bir ad kullanabilirsiniz. Bağlayıcıyı ayarlarken veri türü sütunu için kullanılan değerleri de eşleyeceksiniz.

### <a name="adding-the-hrscenario-column-to-a-csv-file-that-contains-a-single-data-type"></a>HRScenario sütununu tek bir veri türü içeren csv dosyasına ekleme

Kuruluşunuzun İk sistemlerine ve İk verilerini CSV dosyasına nasıl aktaracağınız temelinde, tek bir İk veri türü içeren birden çok CSV dosyası oluşturmanız gerekebilir. Bu durumda, farklı CSV dosyalarından verileri içeri aktarmak için tek bir İk bağlayıcısı oluşturabilirsiniz. Bunu yapmak için CSV dosyasına bir HRScenario sütunu eklemeniz ve İk veri türünü belirtmeniz gerekir. Ardından her CSV dosyası için betiği çalıştırabilirsiniz, ancak bağlayıcı için aynı iş kimliğini kullanabilirsiniz. Bkz. [4. Adım](#step-4-run-the-sample-script-to-upload-your-hr-data).

## <a name="step-2-create-an-app-in-azure-active-directory"></a>2. Adım: Azure Active Directory'de uygulama oluşturma

Sonraki adım, Azure Active Directory'de (Azure AD) yeni bir uygulama oluşturmak ve kaydetmektir. Uygulama, 3. Adımda oluşturduğunuz İk bağlayıcısına karşılık gelir. Bu uygulamanın oluşturulması, Azure AD çalıştığında ve kuruluşunuza erişmeye çalıştığında İk bağlayıcısının kimliğini doğrulamasını sağlar. Bu uygulama, İk verilerinizi Microsoft buluta yüklemek için 4. Adımda çalıştırdığınız betiğin kimliğini doğrulamak için de kullanılır. Bu Azure AD uygulamasını oluştururken aşağıdaki bilgileri kaydettiğinizden emin olun. Bu değerler 3. Adım ve 4. Adım'da kullanılır.

- Azure AD uygulama kimliği (*uygulama kimliği* veya *istemci kimliği* olarak da adlandırılır)

- Azure AD uygulama gizli dizisi (*istemci gizli dizisi* olarak da adlandırılır)

- Kiracı Kimliği ( *dizin kimliği* olarak da adlandırılır)

Azure AD'da uygulama oluşturmaya yönelik adım adım yönergeler için bkz. [Uygulamayı Microsoft kimlik platformu kaydetme](/azure/active-directory/develop/quickstart-register-app).

## <a name="step-3-create-the-hr-connector"></a>3. Adım: İk bağlayıcısını oluşturma

Sonraki adım, uyumluluk portalında bir İk bağlayıcısı oluşturmaktır. Betiği 4. Adımda çalıştırdıktan sonra, oluşturduğunuz İk bağlayıcısı CSV dosyasındaki İk verilerini Microsoft 365 kuruluşunuza alır. Bağlayıcı oluşturmadan önce İk senaryolarının ve her biri için ilgili CSV sütun adlarının bir listesine sahip olduğunuzdan emin olun. Bağlayıcıyı yapılandırırken her senaryo için gereken verileri CSV dosyanızdaki gerçek sütun adlarına eşlemeniz gerekir. Alternatif olarak, bağlayıcıyı yapılandırırken örnek bir CSV dosyasını karşıya yükleyebilirsiniz ve sihirbaz sütunların adını gerekli veri türleriyle eşlemenize yardımcı olur.

Bu adımı tamamladıktan sonra bağlayıcıyı oluştururken oluşturulan iş kimliğini kopyaladığınızdan emin olun. Betiği çalıştırdığınızda iş kimliğini kullanacaksınız.

1. Uyumluluk portalına gidin ve <a href="https://go.microsoft.com/fwlink/p/?linkid=2173865" target="_blank">**Veri bağlayıcıları'nı**</a> seçin.

2. **Veri bağlayıcıları** sayfasında **İk (önizleme)** öğesini seçin.

3. **İk (önizleme)** sayfasında **Bağlayıcı ekle'yi** seçin.

4. **Bağlantıyı kur** sayfasında aşağıdakileri yapın ve **ardından İleri'yi** seçin:

   1. 2. Adımda oluşturduğunuz Azure uygulamasının Azure AD uygulama kimliğini yazın veya yapıştırın.

   2. İk bağlayıcısı için bir ad yazın.

5. İk senaryoları sayfasında, verilerini içeri aktarmak istediğiniz bir veya daha fazla İk senaryosu seçin ve ardından **İleri'yi** seçin.

   ![Bir veya daha fazla İk senaryosu seçin.](../media/HRConnectorScenarios.png)

6. Dosya eşleme yöntemi sayfasında, gerekirse bir dosya türü seçin ve ardından aşağıdaki seçeneklerden birini belirleyin ve **ardından İleri'yi** seçin.

   - **Örnek bir dosyayı karşıya yükleyin**. Bu seçeneği seçerseniz Örnek **dosyayı karşıya yükle'yi** seçerek 1. Adımda hazırladığınız CSV dosyasını karşıya yükleyin. Bu seçenek, csv dosyanızdaki sütun adlarını daha önce seçtiğiniz İk senaryolarının veri türleriyle eşlemek üzere açılan listeden hızla seçmenize olanak tanır.

   VEYA

   - **Eşleme ayrıntılarını el ile sağlayın**. Bu seçeneği belirlerseniz, daha önce seçtiğiniz İk senaryolarının veri türleriyle eşlemek için CSV dosyanızdaki sütunların adını yazmanız gerekir.

7. Dosya eşleme ayrıntıları sayfasında, örnek bir CSV dosyasını karşıya yükleyip yüklemediğinize ve bağlayıcıyı tek bir İk senaryosu için mi yoksa birden çok senaryo için mi yapılandırdığınıza bağlı olarak aşağıdakilerden birini yapın. Örnek bir dosyayı karşıya yüklediyseniz, sütun adlarını yazmanız gerekmez. Bunları açılan listeden seçersiniz.

    - Önceki adımda tek bir İk senaryosu seçtiyseniz, 1. Adımda oluşturduğunuz CSV dosyasındaki sütun üst bilgisi adlarını ( *parametreler* olarak da adlandırılır) uygun kutuların her birine yazın. Yazdığınız sütun adları büyük/küçük harfe duyarlı değildir, ancak CSV dosyanızdaki sütun adları boşluk içeriyorsa boşluk eklemeyi unutmayın. Daha önce açıklandığı gibi, bu kutulara yazdığınız adlar CSV dosyanızdaki parametre adlarla eşleşmelidir. Örneğin, aşağıdaki ekran görüntüsü, 1. Adımda gösterilen çalışan istifa İk senaryosu için örnek CSV dosyasındaki parametre adlarını gösterir.

    - Yukarıdaki adımda birden çok veri türü seçtiyseniz, CSV dosyanızda İk veri türünü tanımlayacak tanımlayıcı sütun adını girmeniz gerekir. Tanımlayıcı sütun adını girdikten sonra, bu İk veri türünü tanımlayan değeri yazın ve 1. Adımda oluşturduğunuz CSV dosyalarından seçilen veri türleri için sütun üst bilgisi adlarını seçili her veri türü için uygun kutuların her birine yazın. Daha önce açıklandığı gibi, bu kutulara yazdığınız adlar CSV dosyanızdaki sütun adlarla eşleşmelidir.

8. **Gözden Geçir** sayfasında ayarlarınızı gözden geçirin ve ardından **Son'u** seçerek bağlayıcıyı oluşturun.

   Bağlayıcının oluşturulduğunu onaylayan bir durum sayfası görüntülenir. Bu sayfa, İk verilerinizi karşıya yüklemek için örnek betiği çalıştırmak için sonraki adımı tamamlamanız gereken iki önemli öğe içerir.

   ![örnek betik için iş kimliğini ve github bağlantısını içeren sayfayı gözden geçirin.](../media/HRConnector_Confirmation.png)

   1. **İş Kimliği.** Sonraki adımda betiği çalıştırmak için bu iş kimliğine ihtiyacınız olacaktır. Bu sayfadan veya bağlayıcı açılır sayfasından kopyalayabilirsiniz.

   2. **Örnek betiğin bağlantısı.** Örnek betike erişmek için GitHub sitesine gitmek için **buradaki** bağlantıyı seçin (bağlantı yeni bir pencere açar). 4. Adım'da betiği kopyalayabilmeniz için bu pencereyi açık tutun. Alternatif olarak, betiği çalıştırdığınızda yeniden erişebilmek için hedefe yer işareti ekleyebilir veya URL'yi kopyalayabilirsiniz. Bu bağlantı bağlayıcı açılır sayfasında da kullanılabilir.

9. **Bitti'yi** seçin.

   Yeni bağlayıcı **Bağlayıcılar** sekmesindeki listede görüntülenir.

10. Yeni oluşturduğunuz İk bağlayıcısını seçerek bağlayıcıyla ilgili özellikleri ve diğer bilgileri içeren açılır sayfayı görüntüleyin.

   ![Yeni İk bağlayıcısı için açılır sayfa.](../media/HRConnectorWizard7.png)

Henüz yapmadıysanız **, Azure Uygulaması Kimliği** ve **Bağlayıcı iş kimliği** değerlerini kopyalayabilirsiniz. Sonraki adımda betiği çalıştırmak için bunlara ihtiyacınız olacaktır. Betiği açılır sayfadan da indirebilirsiniz (veya sonraki adımda bağlantıyı kullanarak indirebilirsiniz.)

**Dosya eşleme** sayfasında tanımladığınız Azure Uygulaması kimliğini veya sütun üst bilgisi adlarını değiştirmek için **Düzenle'yi** de seçebilirsiniz.

## <a name="step-4-run-the-sample-script-to-upload-your-hr-data"></a>4. Adım: İk verilerinizi karşıya yüklemek için örnek betiği çalıştırın

İk bağlayıcısını ayarlamanın son adımı, CSV dosyasındaki (1. Adımda oluşturduğunuz) İk verilerini Microsoft buluta yükleyecek örnek bir betik çalıştırmaktır. Özellikle betik, verileri İk bağlayıcısına yükler. Betiği çalıştırdıktan sonra, 3. Adımda oluşturduğunuz İk bağlayıcısı İk verilerini Microsoft 365 kuruluşunuza aktarır ve burada Insider risk yönetimi çözümü gibi diğer uyumluluk araçları tarafından erişilebilir. Betiği çalıştırdıktan sonra, en güncel çalışan sonlandırma verilerinin Microsoft buluta yüklenmesi için günlük olarak otomatik olarak çalıştırılacak bir görev zamanlamayı göz önünde bulundurun. Bkz. [Betiği otomatik olarak çalışacak şekilde zamanlama](#optional-step-6-schedule-the-script-to-run-automatically).

1. GitHub sitesine örnek betikle erişmek için önceki adımda açık bıraktığınız pencereye gidin. Alternatif olarak, yer işaretli siteyi açın veya kopyaladığınız URL'yi kullanın. Betike [buradan](https://github.com/microsoft/m365-compliance-connector-sample-scripts/blob/main/sample_script.ps1) da erişebilirsiniz.

2. Betiği metin görünümünde görüntülemek için **Ham** düğmesini seçin.

3. Örnek betikteki tüm satırları kopyalayın ve bir metin dosyasına kaydedin.

4. Gerekirse kuruluşunuzun örnek betiğini değiştirin.

5. metin dosyasını Windows PowerShell betik dosyası olarak kaydetmek için ; örneğin, `HRConnector.ps1`bir dosya adı soneki `.ps1`kullanın. Alternatif olarak, betik için GitHub dosya adını kullanabilirsiniz.`upload_termination_records.ps1`

6. Yerel bilgisayarınızda bir komut istemi açın ve betiği kaydettiğiniz dizine gidin.

7. CSV dosyasındaki İk verilerini Microsoft buluta yüklemek için aşağıdaki komutu çalıştırın; örneğin:

    ```powershell
    .\HRConnector.ps1 -tenantId <tenantId> -appId <appId>  -appSecret <appSecret>  -jobId <jobId>  -filePath '<filePath>'
    ```

   Aşağıdaki tabloda, bu betikle kullanılacak parametreler ve bunların gerekli değerleri açıklanmaktadır. Önceki adımlarda elde ettiğiniz bilgiler bu parametrelerin değerlerinde kullanılır.

   | Parametre | Açıklama |
   |:-----|:-----|:-----|
   |`tenantId`|Bu, 2. Adımda edindiğiniz Microsoft 365 kuruluşunuzun kimliğidir. Ayrıca kuruluşunuzun kiracı kimliğini Azure AD yönetim merkezindeki **Genel Bakış** dikey penceresinden de edinebilirsiniz. Bu, kuruluşunuzu tanımlamak için kullanılır.|
   |`appId` |Bu, 2. Adımda Azure AD oluşturduğunuz uygulamanın Azure AD uygulama kimliğidir. Bu, Azure AD tarafından betik Microsoft 365 kuruluşunuza erişmeye çalıştığında kimlik doğrulaması için kullanılır. | 
   |`appSecret`|Bu, 2. Adımda Azure AD oluşturduğunuz uygulamanın Azure AD uygulama gizli dizisidir. Bu, kimlik doğrulaması için de kullanılır.|
   |`jobId`|Bu, 3. Adımda oluşturduğunuz İk bağlayıcısının iş kimliğidir. Bu, Microsoft buluta yüklenen İk verilerini İk bağlayıcısıyla ilişkilendirmek için kullanılır.|
   |`filePath`|Bu, 1. Adımda oluşturduğunuz dosyanın (betikle aynı sistemde depolanan) dosya yoludur. Dosya yolunda boşluklardan kaçınmaya çalışın; aksi takdirde tek tırnak işareti kullanın.|
   |||

   Aşağıda, her parametre için gerçek değerleri kullanan İk bağlayıcı betiğinin söz dizimi örneği verilmiştir:

   ```powershell
    .\HRConnector.ps1 -tenantId d5723623-11cf-4e2e-b5a5-01d1506273g9 -appId 29ee526e-f9a7-4e98-a682-67f41bfd643e -appSecret MNubVGbcQDkGCnn -jobId b8be4a7d-e338-43eb-a69e-c513cd458eba -filePath 'C:\Users\contosoadmin\Desktop\Data\employee_termination_data.csv'
    ```

   Karşıya yükleme başarılı olursa, betik **Karşıya Yükleme Başarılı** iletisini görüntüler.

   > [!NOTE]
   > Yürütme ilkeleri nedeniyle önceki komutu çalıştırırken sorun yaşıyorsanız, yürütme ilkelerini ayarlama hakkında yönergeler için [Bkz. Yürütme İlkeleri Hakkında](/powershell/module/microsoft.powershell.core/about/about_execution_policies) ve [Set-ExecutionPolicy](/powershell/module/microsoft.powershell.security/set-executionpolicy) .

## <a name="step-5-monitor-the-hr-connector"></a>5. Adım: İk bağlayıcısını izleme

İk bağlayıcısını oluşturduktan ve İk verilerinizi karşıya yüklemek için betiği çalıştırdıktan sonra bağlayıcıyı görüntüleyebilir ve uyumluluk portalında karşıya yükleme durumunu karşıya yükleyebilirsiniz. Betiği düzenli olarak çalışacak şekilde zamanlarsanız, betiğin son çalıştırıldığından sonra geçerli durumu da görüntüleyebilirsiniz.

1. Uyumluluk portalına gidin ve <a href="https://go.microsoft.com/fwlink/p/?linkid=2173865" target="_blank">**Veri bağlayıcıları'nı**</a> seçin.

2. **Bağlayıcılar** sekmesini ve ardından açılır sayfayı görüntülemek için İk bağlayıcısını seçin. Bu sayfa, bağlayıcı hakkındaki özellikleri ve bilgileri içerir.

   ![Özellikler ve durum ile İk bağlayıcı açılır sayfası.](../media/HRConnectorFlyout1.png)

3. **İlerleme Durumu** altında, Bağlayıcının durum günlüğünü açmak (veya kaydetmek) için **Günlüğü indir** bağlantısını seçin. Bu günlük, betiğin her çalıştırıldığında ve CSV dosyasındaki verileri Microsoft buluta yükleyişiyle ilgili bilgileri içerir. 

   ![İk bağlayıcısı günlük dosyası, karşıya yüklenen CSV dosyasındaki sayı satırlarını görüntüler.](../media/HRConnectorLogFile.png)

   alanı, `RecordsSaved` karşıya yüklenen CSV dosyasındaki satır sayısını gösterir. Örneğin, CSV dosyası dört satır içeriyorsa, betik CSV dosyasındaki `RecordsSaved` tüm satırları başarıyla karşıya yüklediyse alanların değeri 4 olur.

4. Adımda betiği çalıştırmadıysanız, **Son içeri aktarma** altında betiği indirme bağlantısı görüntülenir. Betiği indirebilir ve ardından betiği çalıştırmak için adımları izleyebilirsiniz.

## <a name="optional-step-6-schedule-the-script-to-run-automatically"></a>(İsteğe bağlı) 6. Adım: Betiği otomatik olarak çalışacak şekilde zamanlama

Kuruluşunuzdaki en son İk verilerinin insider risk yönetimi çözümü gibi araçlar tarafından kullanılabildiğinden emin olmak için, betiği günde bir kez gibi yinelenen bir şekilde otomatik olarak çalışacak şekilde zamanlamanızı öneririz. Bu, kuruluşunuzdan ayrılan çalışanlar hakkında en son bilgileri içermesi için CSV dosyasındaki İk verilerini benzer (aynı değilse) bir zamanlamayla güncelleştirmenizi de gerektirir. Amaç, İk bağlayıcısının bunu insider risk yönetimi çözümüne sunabilmesi için en güncel İk verilerini karşıya yüklemektir.

Betiği her gün otomatik olarak çalıştırmak için Windows'ta Görev Zamanlayıcı uygulamasını kullanabilirsiniz.

1. Yerel bilgisayarınızda Windows **Başlat** düğmesini seçin ve **görev zamanlayıcı** yazın.

2. **Görev Zamanlayıcı** uygulamasını seçerek açın.

3. **Eylemler** bölümünde **Görev Oluştur'u** seçin.

4. **Genel** sekmesinde, zamanlanan görev için açıklayıcı bir ad yazın; örneğin İk **BağlayıcıSı Betiği**. İsteğe bağlı bir açıklama da ekleyebilirsiniz.

5. **Güvenlik seçenekleri'nin** altında aşağıdakileri yapın:

   1. Betiğin yalnızca bilgisayarda oturum açtığınızda mı yoksa oturum açtığınızda mı çalıştırılmadığını mı belirleyebilirsiniz.

   1. **En yüksek ayrıcalıklarla çalıştır** onay kutusunun seçili olduğundan emin olun.

6. **Tetikleyiciler** sekmesini seçin, **Yeni'yi** seçin ve ardından aşağıdaki işlemleri yapın:

   1. **Ayarlar'ın** altında **Günlük** seçeneğini belirleyin ve ardından betiği ilk kez çalıştırmak için bir tarih ve saat seçin. Betik her gün belirtilen saatte çalıştırılır.

   1. **Gelişmiş ayarlar'ın** altında **Etkin** onay kutusunun seçili olduğundan emin olun.

   1. **Tamam**'ı seçin.

7. **Eylemler** sekmesini seçin, **Yeni'yi** seçin ve ardından aşağıdaki işlemleri yapın:

   ![İk bağlayıcısı betiği için yeni bir zamanlanmış görev oluşturmak için eylem ayarları.](../media/HRConnectorScheduleTask1.png)

   1. **Eylem** açılan listesinde **Program başlat'ın** seçili olduğundan emin olun.

   1. **Program/betik** kutusunda **Gözat'ı** seçin ve aşağıdaki konuma gidin ve yolun kutuda görüntülenmesi için seçin: `C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe`.

   1. **Bağımsız değişken ekle (isteğe bağlı)** kutusunda, 4. Adımda çalıştırdığınız betik komutunu yapıştırın. Örneğin, `.\HRConnector.ps1 -tenantId "d5723623-11cf-4e2e-b5a5-01d1506273g9" -appId "c12823b7-b55a-4989-faba-02de41bb97c3" -appSecret "MNubVGbcQDkGCnn"  -jobId "e081f4f4-3831-48d6-7bb3-fcfab1581458" -filePath "C:\Users\contosoadmin\Desktop\Data\employee_termination_data.csv"`

   1. Başlangıç yeri **(isteğe bağlı)** kutusuna, 4. Adımda çalıştırdığınız betiğin klasör konumunu yapıştırın. Örneğin, `C:\Users\contosoadmin\Desktop\Scripts`.

   1. Yeni eylemin ayarlarını kaydetmek için **Tamam'ı** seçin.

8. **Görev Oluştur** penceresinde **Tamam'ı** seçerek zamanlanmış görevi kaydedin. Kullanıcı hesabı kimlik bilgilerinizi girmeniz istenebilir.

   Yeni görev Görev Zamanlayıcı Kitaplığı'nda görüntülenir.

   ![Yeni görev Görev Zamanlayıcı Kitaplığı'nda görüntülenir.](../media/HRConnectorTaskSchedulerLibrary.png)

   Betiğin en son çalıştırıldığı ve bir sonraki çalıştırma zamanlaması görüntülenir. Görevi düzenlemek için çift seçebilirsiniz.

   Ayrıca, uyumluluk merkezindeki ilgili İk bağlayıcısının açılır sayfasında betiğin en son ne zaman çalıştığını da doğrulayabilirsiniz.

## <a name="optional-step-7-upload-data-using-power-automate-templates"></a>(İsteğe bağlı) 7. Adım: Power Automate şablonlarını kullanarak verileri karşıya yükleme

Power Automate şablonlarını kullanarak İk verilerini karşıya yükleyebilir ve tetikleyicileri tanımlayabilirsiniz. Örneğin, SharePoint veya OneDrive konumlarında yeni İk bağlayıcı dosyaları kullanılabilir olduğunda tetiklenebilecek bir Power Automate şablonu yapılandırabilirsiniz. Ayrıca Azure Key Vault'da Azure AD uygulama gizli dizisi (**2. Adımda** oluşturulur) gibi gizli bilgileri depolayıp kimlik doğrulaması için Power Automate ile kullanarak da bu işlemi kolaylaştırabilirsiniz.

OneDrive İş'da yeni dosyalar kullanıma sunulduğunda İk verilerini otomatik olarak karşıya yüklemek için aşağıdaki adımları tamamlayın:

1.  [GitHub sitesinden](https://github.com/microsoft/m365-compliance-connector-sample-scripts/blob/main/ImportHRDataforIRM.zip)*ImportHRDataforIRM.zip* paketini indirin.
2. [Power Automate'te](https://make.preview.powerautomate.com) **Akışlarım'a** gidin.
3.  **İçeri aktar'ı** seçin ve *ImportHRDataforIRM.zip* paketini karşıya yükleyin.
4.  Paket karşıya yüklendikten sonra içeriği güncelleştirin (adı & OneDrive İş bağlantı) ve **İçeri Aktar'ı** seçin.

    ![Power Automate akış içeri aktarma.](../media/hr-connector-pa-import-flow.png)

5.  **Akışı aç'ı** seçin ve parametreleri güncelleştirin. Aşağıdaki tabloda, bu Power Automate Flow'da kullanılacak parametreler ve bunların gerekli değerleri açıklanmaktadır. Önceki adımlarda elde ettiğiniz bilgiler bu parametrelerin değerlerinde kullanılır.

    |**Parametre**|**Açıklama**|
    |:------------|:--------------|
    | Uygulama Kimliği | Bu, **2. Adımda** Azure AD oluşturduğunuz uygulamanın Azure AD uygulama kimliğidir. Bu, Azure AD tarafından betik Microsoft 365 kuruluşunuza erişmeye çalıştığında kimlik doğrulaması için kullanılır. |
    | Uygulama Gizli Dizisi | Bu, **2. Adımda** Azure AD oluşturduğunuz uygulamanın Azure AD uygulama gizli dizisidir. Bu kimlik doğrulaması için kullanılır. |
    | Dosya konumu | Bu, Power Automate'in bu akışı tetikleme amacıyla 'yeni dosya oluşturuldu' etkinliklerini izlediği OneDrive İş konumdur.|
    | İş Kimliği | **3. Adımda** oluşturulan İk bağlayıcısının tanımlayıcısı. Bu, Microsoft buluta yüklenen İk verilerini İk bağlayıcısıyla ilişkilendirmek için kullanılır. |
    | Kiracı Kimliği | **2. Adım'da** edinilen Microsoft 365 kuruluşunuzun tanımlayıcısı. Ayrıca kuruluşunuzun kiracı kimliğini Azure AD yönetim merkezindeki **Genel Bakış** dikey penceresinden de edinebilirsiniz. Bu, kuruluşunuzu tanımlamak için kullanılır. |
    | Urı | Bu parametrenin değerinin *https://webhook.ingestion.office.com/api/signals* |

    ![Power Automate akışı.](../media/hr-connector-pa-flow.png)

6.  **Kaydet**'i seçin.
7.  **Akışa genel bakış'a** gidin ve **Aç'ı** seçin.

    ![Power Automate akışını açın.](../media/hr-connector-pa-turn-on.png)

8.  OneDrive İş klasörünüze yeni bir dosya yükleyerek akışı el ile test edin ve başarıyla çalıştığını doğrulayın. Bu işlem, akışın tetiklenebilmesi için karşıya yüklemeden birkaç dakika sonra gerçekleşebilir.

    ![Power Automate akış testi.](../media/hr-connector-pa-test.png)

9.  Artık İk bağlayıcısını **5. Adım'da** açıklandığı gibi izleyebilirsiniz.

Gerekirse, SharePoint'te ve Power Automate Akışları tarafından desteklenen diğer veri kaynaklarında dosya kullanılabilirliğine ve değişiklik olaylarına göre tetikleyiciler oluşturmak için akışı güncelleştirebilirsiniz.

## <a name="existing-hr-connectors"></a>Mevcut İk bağlayıcıları

13 Aralık 2021'de İk bağlayıcıları için çalışan profili veri senaryosu yayınlandı. Bu tarihten önce bir İk bağlayıcısı oluşturduysanız, İk verilerinizin Microsoft buluta aktarılmaya devam etmesi için mevcut örnekleri veya kuruluşunuzun İk bağlayıcılarını geçiririz. Bu işlevselliği korumak için hiçbir şey yapmanız gerekmez. Bu bağlayıcıları kesinti olmadan kullanmaya devam edebilirsiniz.

Çalışan profili veri senaryosu uygulamak istiyorsanız yeni bir İk bağlayıcısı oluşturup gerektiği gibi yapılandırabilirsiniz. Yeni bir İk bağlayıcısı oluşturduktan sonra, bu makalede daha önce açıklanan [çalışan profili verileriyle](#csv-file-for-employee-profile-data-preview) yeni bağlayıcının iş kimliğini ve CSV dosyalarını kullanarak betiği çalıştırın.
