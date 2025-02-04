---
title: Hassas bilgi türü varlık tanımları
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
search.appverid: MET150
ms.topic: reference
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- tier2
- purview-compliance
hideEdit: true
feedback_system: None
recommendations: false
description: DLP ilkelerinizde kullanmaya hazır birçok hassas bilgi türü vardır. Bu makale, tüm bu hassas bilgi türü varlık tanımlarının listesidir.
ms.openlocfilehash: ebb2481554b0c668ffd27c71a7e1ec32ff529977
ms.sourcegitcommit: 8d3c027592a638f411f87d89772dd3d39e92aab0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/12/2022
ms.locfileid: "68537126"
---
# <a name="sensitive-information-type-entity-definitions"></a>Hassas bilgi türü varlık tanımları

Bu makale, tüm hassas bilgi türü (SIT) varlık tanımlarının listesidir. Her bağlantı sizi belirli bir SIT'in tanımına götürür ve bir DLP ilkesinin her türü algılamak için ne aradığını gösterir. Hassas bilgi türleri hakkında daha fazla bilgi edinmek için bkz [. Hassas bilgi türleri](sensitive-information-type-learn-about.md)

> [!NOTE]
> Doğruluk numarasıyla güvenilirlik düzeyinin (yüksek/orta/düşük) eşlemesi (1 ile 100 arasında sayısal değer)
>
> - Düşük güvenilirlik: 65 veya altı
> - Orta güvenilirlik: 75
> - Yüksek güvenilirlik: 85

- [ABA yönlendirme numarası](sit-defn-aba-routing.md)
- [Tüm kimlik bilgileri](sit-defn-all-creds.md)
- [Tüm tam adlar](sit-defn-all-full-names.md)
- [Tüm tıbbi hüküm ve koşullar](sit-defn-all-medical-terms-conditions.md)
- [Tüm Fiziksel Adresler](sit-defn-all-physical-addresses.md)
- [Amazon S3 İstemci Gizli Erişim Anahtarı](sit-defn-amazon-s3-client-secret-access-key.md)
- [Arjantin ulusal kimlik (DNI) numarası](sit-defn-argentina-national-identity-numbers.md)
- [Arjantin Benzersiz Vergi Tanımlama Anahtarı (CUIT/CUIL)](sit-defn-argentina-unique-tax-identification-key.md)
- [makine anahtarını ASP.NET](sit-defn-asp-net-machine-key.md) 
- [Avustralya banka hesap numarası](sit-defn-australia-bank-account-number.md)
- [Avustralya iş numarası](sit-defn-australia-business-number.md)
- [Avustralya şirket numarası](sit-defn-australia-business-number.md)
- [Avustralya ehliyet numarası](sit-defn-australia-drivers-license-number.md)
- [Avustralya tıbbi hesap numarası](sit-defn-australia-medical-account-number.md)
- [Avustralya pasaport numarası](sit-defn-australia-passport-number.md)
- [Avustralya fiziksel adresleri](sit-defn-australia-physical-addresses.md)
- [Avustralya vergi dosyası numarası](sit-defn-australia-tax-file-number.md)
- [Avusturya ehliyet numarası](sit-defn-austria-drivers-license-number.md)
- [Avusturya kimlik kartı](sit-defn-austria-identity-card.md)
- [Avusturya pasaport numarası](sit-defn-austria-passport-number.md)
- [Avusturya fiziksel adresleri](sit-defn-austria-physical-addresses.md)
- [Avusturya sosyal güvenlik numarası](sit-defn-austria-social-security-number.md)
- [Avusturya vergi kimlik numarası](sit-defn-austria-tax-identification-number.md)
- [Avusturya katma değer vergisi](sit-defn-austria-value-added-tax.md)
- [Azure AD istemci erişim belirteci](sit-defn-azure-ad-client-access-token.md) 
- [Azure AD gizli anahtarı](sit-defn-azure-ad-client-secret.md)
- [kullanıcı kimlik bilgilerini Azure AD](sit-defn-azure-ad-user-credentials.md)
- [dağıtım parolasını Azure App Service](sit-defn-azure-app-service-deployment-password.md)
- [Paylaşılan erişim anahtarını Azure Batch](sit-defn-azure-batch-shared-access-key.md)
- [Azure Bot Framework gizli anahtarı](sit-defn-azure-bot-framework-secret-key.md)
- [Azure Bot hizmeti uygulama gizli dizisi](sit-defn-azure-bot-service-app-secret.md)
- [Azure Bilişsel Arama API anahtarı](sit-defn-azure-cognitive-search-api-key.md)
- [Azure Bilişsel Hizmet anahtarı](sit-defn-azure-cognitive-service-key.md)
- [Azure Container Registry erişim anahtarı](sit-defn-azure-container-registry-access-key.md)
- [Azure COSMOS DB hesabı erişim anahtarı](sit-defn-azure-cosmos-db-account-access-key.md) 
- [Azure Databricks kişisel erişim belirteci](sit-defn-azure-databricks-personal-access-token.md)
- [Azure DevOps uygulama gizli dizisi](sit-defn-azure-devops-app-secret.md)
- [Azure DevOps kişisel erişim belirteci](sit-defn-azure-devops-personal-access-token.md)
- [Azure DocumentDB kimlik doğrulaması anahtarı](sit-defn-azure-document-db-auth-key.md)
- [Azure EventGrid erişim anahtarı](sit-defn-azure-eventgrid-access-key.md) 
- [Azure İşlev Yöneticisi / API anahtarı](sit-defn-azure-function-master-api-key.md) 
- [Azure IAAS veritabanı bağlantısı dizesi ve Azure SQL bağlantısı dizesi](sit-defn-azure-iaas-database-connection-string-azure-sql-connection-string.md)
- [Azure IoT bağlantı dizesi](sit-defn-azure-iot-connection-string.md)
- [Azure IoT paylaşılan erişim anahtarı](sit-defn-azure-iot-shared-access-key.md)
- [Azure Logic app paylaşılan erişim imzası](sit-defn-azure-logic-app-shared-access-signature.md) 
- [Azure Machine Learning web hizmeti API anahtarı](sit-defn-azure-machine-learning-web-service-api-key.md) 
- [Azure Haritalar abonelik anahtarı](sit-defn-azure-maps-subscription-key.md) 
- [Azure yayımlama ayarı parolası](sit-defn-azure-publish-setting-password.md)
- [Azure Redis önbellek bağlantı dizesi](sit-defn-azure-redis-cache-connection-string.md)
- [Azure Redis önbellek bağlantı dizesi parolası](sit-defn-azure-redis-cache-connection-string-password.md)
- [Azure SAS](sit-defn-azure-sas.md)
- [Azure service bus bağlantı dizesi](sit-defn-azure-service-bus-connection-string.md)
- [Azure service bus paylaşılan erişim imzası](sit-defn-azure-service-bus-shared-access-signature.md) 
- [Azure Paylaşılan Erişim anahtarı / Web Kancası belirteci](sit-defn-azure-shared-access-key-web-hook-token.md) 
- [Azure SignalR erişim anahtarı](sit-defn-azure-signalr-access-key.md)
- [Azure SQL bağlantı dizesi](sit-defn-azure-sql-connection-string.md)
- [Azure depolama hesabı erişim anahtarı](sit-defn-azure-storage-account-access-key.md)
- [Azure depolama hesabı anahtarı](sit-defn-azure-storage-account-key.md)
- [Azure Depolama hesabı anahtarı (genel)](sit-defn-azure-storage-account-key-generic.md)
- [Azure Depolama hesabı paylaşılan erişim imzası](sit-defn-azure-storage-account-shared-access-signature.md)
- [Yüksek riskli kaynaklar için Azure Depolama hesabı paylaşılan erişim imzası](sit-defn-azure-storage-account-shared-access-signature-high-risk-resources.md)
- [Azure abonelik yönetimi sertifikası](sit-defn-azure-subscription-management-certificate.md)
- [Belçika ehliyet numarası](sit-defn-belgium-drivers-license-number.md)
- [Belçika ulusal numarası](sit-defn-belgium-national-number.md)
- [Belçika pasaport numarası](sit-defn-belgium-passport-number.md)
- [Belçika fiziksel adresleri](sit-defn-belgium-physical-addresses.md)
- [Belçika katma değer vergi numarası](sit-defn-belgium-value-added-tax-number.md)
- [Kan testi koşulları](sit-defn-blood-test-terms.md)
- [Marka ilaç adları](sit-defn-brand-medication-names.md)
- [Brezilya CPF numarası](sit-defn-brazil-cpf-number.md)
- [Brezilya tüzel kişilik numarası (CNPJ)](sit-defn-brazil-legal-entity-number.md)
- [Brezilya ulusal kimlik kartı (RG)](sit-defn-brazil-national-identification-card.md)
- [Brezilya fiziksel adresleri](sit-defn-brazil-physical-addresses.md)
- [Bulgaristan ehliyet numarası](sit-defn-bulgaria-drivers-license-number.md)
- [Bulgaristan pasaport numarası](sit-defn-bulgaria-passport-number.md)
- [Bulgaristan fiziksel adresleri](sit-defn-bulgaria-physical-addresses.md)
- [Bulgaristan üniforma sivil numarası](sit-defn-bulgaria-uniform-civil-number.md)
- [Kanada banka hesap numarası](sit-defn-canada-bank-account-number.md)
- [Kanada ehliyet numarası](sit-defn-canada-drivers-license-number.md)
- [Kanada sağlık hizmeti numarası](sit-defn-canada-health-service-number.md)
- [Kanada pasaport numarası](sit-defn-canada-passport-number.md)
- [Kanada kişisel sağlık kimlik numarası (PHIN)](sit-defn-canada-personal-health-identification-number.md)
- [Kanada fiziksel adresleri](sit-defn-canada-physical-addresses.md)
- [Kanada sosyal sigorta numarası](sit-defn-canada-social-insurance-number.md)
- [Şili kimlik kartı numarası](sit-defn-chile-identity-card-number.md)
- [Çin mukim kimlik kartı (PRC) numarası](sit-defn-china-resident-identity-card-number.md)
- [Gizli anahtar / API anahtarı](sit-defn-client-secret-api-key.md)
- [Kredi kartı numarası](sit-defn-credit-card-number.md)
- [Hırvatistan ehliyet numarası](sit-defn-croatia-drivers-license-number.md)
- [Hırvatistan kimlik kartı numarası](sit-defn-croatia-identity-card-number.md)
- [Hırvatistan pasaport numarası](sit-defn-croatia-passport-number.md)
- [Hırvatistan kişisel kimlik (OIB) numarası](sit-defn-croatia-personal-identification-number.md)
- [Hırvatistan fiziksel adresleri](sit-defn-croatia-physical-addresses.md)
- [Kıbrıs ehliyet numarası](sit-defn-cyprus-drivers-license-number.md)
- [Kıbrıs kimlik kartı](sit-defn-cyprus-identity-card.md)
- [Kıbrıs pasaport numarası](sit-defn-cyprus-passport-number.md)
- [Kıbrıs fiziksel adresleri](sit-defn-cyprus-physical-addresses.md)
- [Kıbrıs vergi kimlik numarası](sit-defn-cyprus-tax-identification-number.md)
- [Çek ehliyet numarası](sit-defn-czech-drivers-license-number.md)
- [Çek pasaport numarası](sit-defn-czech-passport-number.md)
- [Çek kişisel kimlik numarası](sit-defn-czech-personal-identity-number.md)
- [Çek Cumhuriyeti fiziksel adresleri](sit-defn-czech-republic-physical-addresses.md)
- [Danimarka ehliyet numarası](sit-defn-denmark-drivers-license-number.md)
- [Danimarka pasaport numarası](sit-defn-denmark-passport-number.md)
- [Danimarka kişisel kimlik numarası](sit-defn-denmark-personal-identification-number.md)
- [Danimarka fiziksel adresleri](sit-defn-denmark-physical-addresses.md)
- [Hastalıklar](sit-defn-diseases.md)
- [Uyuşturucuyla Mücadele Ajansı (DEA) numarası ](sit-defn-drug-enforcement-agency-number.md)
- [Estonya ehliyet numarası](sit-defn-estonia-drivers-license-number.md)
- [Estonya pasaport numarası](sit-defn-estonia-passport-number.md)
- [Estonya Kişisel Kimlik Kodu](sit-defn-estonia-personal-identification-code.md)
- [Estonya fiziksel adresleri](sit-defn-estonia-physical-addresses.md)
- [AB banka kartı numarası](sit-defn-eu-debit-card-number.md)
- [AB ehliyet numarası](sit-defn-eu-drivers-license-number.md)
- [AB ulusal kimlik numarası](sit-defn-eu-national-identification-number.md)
- [AB pasaport numarası](sit-defn-eu-passport-number.md)
- [AB sosyal güvenlik numarası veya eşdeğer kimlik](sit-defn-eu-social-security-number-equivalent-identification.md)
- [AB Vergi kimlik numarası](sit-defn-eu-tax-identification-number.md)
- [Finlandiya ehliyet numarası](sit-defn-finland-drivers-license-number.md)
- [Finlandiya Avrupa sağlık sigortası numarası](sit-defn-finland-european-health-insurance-number.md)
- [Finlandiya ulusal kimliği](sit-defn-finland-national-id.md)
- [Finlandiya pasaport numarası](sit-defn-finland-passport-number.md)
- [Finlandiya fiziksel adresleri](sit-defn-finland-physical-addresses.md)
- [Fransa ehliyet numarası](sit-defn-france-drivers-license-number.md)
- [Fransa sağlık sigortası numarası](sit-defn-france-health-insurance-number.md)
- [Fransa ulusal kimlik kartı (CNI)](sit-defn-france-national-id-card.md)
- [Fransa pasaport numarası](sit-defn-france-passport-number.md)
- [Fransa fiziksel adresleri](sit-defn-france-physical-addresses.md)
- [Fransa sosyal güvenlik numarası (INSEE)](sit-defn-france-social-security-number.md)
- [Fransa vergi kimlik numarası](sit-defn-france-tax-identification-number.md)
- [Fransa katma değer vergi numarası](sit-defn-france-value-added-tax-number.md)
- [Genel parola](sit-defn-general-password.md)
- [Genel Simetrik anahtar](sit-defn-general-symmetric-key.md)
- [Genel ilaç adları](sit-defn-generic-medication-names.md)
- [Almanya ehliyet numarası](sit-defn-germany-drivers-license-number.md)
- [Almanya kimlik kartı numarası](sit-defn-germany-identity-card-number.md)
- [Almanya pasaport numarası](sit-defn-germany-passport-number.md)
- [Almanya fiziksel adresleri](sit-defn-germany-physical-addresses.md)
- [Almanya vergi kimlik numarası](sit-defn-germany-tax-identification-number.md)
- [Almanya katma değer vergi numarası](sit-defn-germany-value-added-tax-number.md)
- [GitHub Kişisel Erişim Belirteci](sit-defn-github-personal-access-token.md) 
- [Google API anahtarı](sit-defn-google-api-key.md)
- [Yunanistan ehliyet numarası](sit-defn-greece-drivers-license-number.md)
- [Yunanistan ulusal kimlik kartı](sit-defn-greece-national-id-card.md)
- [Yunanistan pasaport numarası](sit-defn-greece-passport-number.md)
- [Yunanistan fiziksel adresleri](sit-defn-greece-physical-addresses.md)
- [Yunanistan Sosyal Güvenlik Numarasını (AMKA)](sit-defn-greece-social-security-number.md)
- [Yunanistan vergi kimlik numarası](sit-defn-greece-tax-identification-number.md)
- [Hong Kong kimlik kartı (HKID) numarası](sit-defn-hong-kong-identity-card-number.md)
- [Http yetkilendirme üst bilgisi](sit-defn-http-authorization-header.md)
- [Macaristan ehliyet numarası](sit-defn-hungary-drivers-license-number.md)
- [Macaristan pasaport numarası](sit-defn-hungary-passport-number.md)
- [Macaristan kişisel kimlik numarası](sit-defn-hungary-personal-identification-number.md)
- [Macaristan fiziksel adresleri](sit-defn-hungary-physical-addresses.md)
- [Macaristan sosyal güvenlik numarası (TAJ)](sit-defn-hungary-social-security-number.md)
- [Macaristan vergi kimlik numarası](sit-defn-hungary-tax-identification-number.md)
- [Macaristan katma değer vergi numarası](sit-defn-hungary-value-added-tax-number.md)
- [İzlanda fiziksel adresleri](sit-defn-iceland-physical-addresses.md)
- [Sosyal Güvenlik Kapsamında ABD Engellilik Değerlendirmesinde Listelenen Bozukluklar](sit-defn-impairments-us-disability-evaluation-under-social-security.md)
- [Hindistan Ehliyet Numarası](sit-defn-india-drivers-license-number.md)
- [Hindistan GST Numarası](sit-defn-india-gst-number.md)
- [Hindistan kalıcı hesap numarası (PAN)](sit-defn-india-permanent-account-number.md)
- [Hindistan benzersiz tanımlama (Aadhaar) numarası](sit-defn-india-unique-identification-number.md)
- [Hindistan Seçmen Kimlik Kartı](sit-defn-india-voter-id-card.md)
- [Endonezya kimlik kartı (KTP) numarası](sit-defn-indonesia-identity-card-number.md)
- [Uluslararası bankacılık hesap numarası (IBAN)](sit-defn-international-banking-account-number.md)
- [Uluslararası hastalık sınıflandırması (ICD-10-CM)](sit-defn-international-classification-of-diseases-icd-10-cm.md)
- [Uluslararası hastalık sınıflandırması (ICD-9-CM)](sit-defn-international-classification-of-diseases-icd-9-cm.md)
- [IP adresi](sit-defn-ip-address.md)
- [IP Adresi v4](sit-defn-ip-address-v4.md)
- [IP Adresi v6](sit-defn-ip-address-v6.md)
- [İrlanda ehliyet numarası](sit-defn-ireland-drivers-license-number.md)
- [İrlanda pasaport numarası](sit-defn-ireland-passport-number.md)
- [İrlanda kişisel kamu hizmeti (PPS) numarası](sit-defn-ireland-personal-public-service-number.md)
- [İrlanda fiziksel adresleri](sit-defn-ireland-physical-addresses.md)
- [İsrail banka hesap numarası](sit-defn-israel-bank-account-number.md)
- [İsrail ulusal kimlik numarası](sit-defn-israel-national-identification-number.md)
- [İtalya ehliyet numarası](sit-defn-italy-drivers-license-number.md)
- [İtalya mali kodu](sit-defn-italy-fiscal-code.md)
- [İtalya pasaport numarası](sit-defn-italy-passport-number.md)
- [İtalya fiziksel adresleri](sit-defn-italy-physical-addresses.md)
- [İtalya katma değer vergi numarası](sit-defn-italy-value-added-tax-number.md)
- [Japonya banka hesap numarası](sit-defn-japan-bank-account-number.md)
- [Japonya ehliyet numarası](sit-defn-japan-drivers-license-number.md)
- [Japonya Numaram - Kurumsal](sit-defn-japan-my-number-corporate.md)
- [Japonya Numaram - Kişisel](sit-defn-japan-my-number-personal.md)
- [Japonya pasaport numarası](sit-defn-japan-passport-number.md)
- [Japonya fiziksel adresleri](sit-defn-japan-physical-addresses.md)
- [Japonya konut kartı numarası](sit-defn-japan-residence-card-number.md)
- [Japonya mukim kayıt numarası](sit-defn-japan-resident-registration-number.md)
- [Japonya sosyal sigorta numarası (SIN)](sit-defn-japan-social-insurance-number.md)
- [Laboratuvar testi koşulları](sit-defn-lab-test-terms.md)
- [Letonya ehliyet numarası](sit-defn-latvia-drivers-license-number.md)
- [Letonya pasaport numarası](sit-defn-latvia-passport-number.md)
- [Letonya kişisel kodu](sit-defn-latvia-personal-code.md)
- [Letonya fiziksel adresleri](sit-defn-latvia-physical-addresses.md)
- [Liechtenstein fiziksel adresleri](sit-defn-liechtenstein-physical-addresses.md)
- [Tıbbi koşullarla ilgili yaşam tarzları](sit-defn-lifestyles-relate-to-medical-conditions.md)
- [Litvanya ehliyet numarası](sit-defn-lithuania-drivers-license-number.md)
- [Litvanya pasaport numarası](sit-defn-lithuania-passport-number.md)
- [Litvanya kişisel kodu](sit-defn-lithuania-personal-code.md)
- [Litvanya fiziksel adresleri](sit-defn-lithuania-physical-addresses.md)
- [Luxemburg ehliyet numarası](sit-defn-luxemburg-drivers-license-number.md)
- [Lüksemburg ulusal kimlik numarası (gerçek kişiler)](sit-defn-luxemburg-national-identification-number-natural-persons.md)
- [Lüksemburg ulusal kimlik numarası (gerçek olmayan kişiler)](sit-defn-luxemburg-national-identification-number-non-natural-persons.md)
- [Lüksemburg pasaport numarası](sit-defn-luxemburg-passport-number.md)
- [Lüksemburg fiziksel adresleri](sit-defn-luxemburg-physical-addresses.md)
- [Malezya kimlik kartı numarası](sit-defn-malaysia-identification-card-number.md)
- [Malta ehliyet numarası](sit-defn-malta-drivers-license-number.md)
- [Malta kimlik kartı numarası](sit-defn-malta-identity-card-number.md)
- [Malta pasaport numarası](sit-defn-malta-passport-number.md)
- [Malta fiziksel adresleri](sit-defn-malta-physical-addresses.md)
- [Malta vergi kimlik numarası](sit-defn-malta-tax-identification-number.md)
- [Tıbbi uzmanlıklar](sit-defn-medical-specialities.md)
- [Medicare (Tıbbi Bakım Sigortası) Faydalanıcı Kimlik (MBI) kartı](sit-defn-medicare-beneficiary-Identifier-card.md)
- [Meksika Benzersiz Nüfus Kayıt Defteri Kodu (CURP)](sit-defn-mexico-unique-population-registry-code.md)
- [Microsoft Bing haritalar anahtarı](sit-defn-microsoft-bing-maps-key.md)
- [Hollanda vatandaşlık hizmeti (BSN) numarası](sit-defn-netherlands-citizens-service-number.md)
- [Hollanda ehliyet numarası](sit-defn-netherlands-drivers-license-number.md)
- [Hollanda pasaport numarası](sit-defn-netherlands-passport-number.md)
- [Hollanda fiziksel adresleri](sit-defn-netherlands-physical-addresses.md)
- [Hollanda vergi kimlik numarası](sit-defn-netherlands-tax-identification-number.md)
- [Hollanda katma değer vergi numarası](sit-defn-netherlands-value-added-tax-number.md)
- [Yeni Zelanda banka hesap numarası](sit-defn-new-zealand-bank-account-number.md)
- [Yeni Zelanda ehliyet numarası](sit-defn-new-zealand-drivers-license-number.md)
- [Yeni Zelanda iç gelir numarası](sit-defn-new-zealand-inland-revenue-number.md)
- [Yeni Zelanda sağlık bakanlığı numarası](sit-defn-new-zealand-ministry-of-health-number.md)
- [Yeni Zelanda fiziksel adresleri](sit-defn-new-zealand-physical-addresses.md)
- [Yeni Zelanda sosyal yardım numarası](sit-defn-new-zealand-social-welfare-number.md)
- [Norveç kimlik numarası](sit-defn-norway-identification-number.md)
- [Norveç fiziksel adresleri](sit-defn-norway-physical-addresses.md)
- [Filipinler pasaport numarası](sit-defn-philippines-passport-number.md)
- [Filipinler birleşik çok amaçlı kimlik numarası](sit-defn-philippines-unified-multi-purpose-identification-number.md)
- [Polonya ehliyet numarası](sit-defn-poland-drivers-license-number.md)
- [Polonya kimlik kartı](sit-defn-poland-identity-card.md)
- [Polonya ulusal kimliği (PESEL)](sit-defn-poland-national-id.md)
- [Polonya pasaport numarası](sit-defn-poland-passport-number.md)
- [Polonya fiziksel adresleri](sit-defn-poland-physical-addresses.md)
- [Polonya REGON numarası](sit-defn-poland-regon-number.md)
- [Polonya vergi kimlik numarası](sit-defn-poland-tax-identification-number.md)
- [Portekiz vatandaşlık kart numarası](sit-defn-portugal-citizen-card-number.md)
- [Portekiz ehliyet numarası](sit-defn-portugal-drivers-license-number.md)
- [Portekiz pasaport numarası](sit-defn-portugal-passport-number.md)
- [Portekiz fiziksel adresleri](sit-defn-portugal-physical-addresses.md)
- [Portekiz vergi kimlik numarası](sit-defn-portugal-tax-identification-number.md)
- [Katar kimlik kartı numarası](sit-defn-qatari-id-card-number.md)
- [Romanya ehliyet numarası](sit-defn-romania-drivers-license-number.md)
- [Romanya pasaport numarası](sit-defn-romania-passport-number.md)
- [Romanya kişisel sayısal kodu (CNP)](sit-defn-romania-personal-numeric-code.md)
- [Romanya fiziksel adresleri](sit-defn-romania-physical-addresses.md)
- [Rusya pasaport numarası yurt içi](sit-defn-russia-passport-number-domestic.md)
- [Rusya pasaport numarası uluslararası](sit-defn-russia-passport-number-international.md)
- [Suudi Arabistan Ulusal Kimliği](sit-defn-saudi-arabia-national-id.md)
- [Singapur ulusal kayıt kimlik kartı (NRIC) numarası](sit-defn-singapore-national-registration-identity-card-number.md)
- [Slack erişim belirteci](sit-defn-slack-access-token.md)
- [Slovakya sürücü ehliyeti numarası](sit-defn-slovakia-drivers-license-number.md)
- [Slovakya pasaport numarası](sit-defn-slovakia-passport-number.md)
- [Slovakya kişisel numarası](sit-defn-slovakia-personal-number.md)
- [Slovakya fiziksel adresleri](sit-defn-slovakia-physical-addresses.md)
- [Slovenya ehliyet numarası](sit-defn-slovenia-drivers-license-number.md)
- [Slovenya pasaport numarası](sit-defn-slovenia-passport-number.md)
- [Slovenya fiziksel adresleri](sit-defn-slovenia-physical-addresses.md)
- [Slovenya vergi kimlik numarası](sit-defn-slovenia-tax-identification-number.md)
- [Slovenya Benzersiz Birincil Vatandaşlık Numarası](sit-defn-slovenia-unique-master-citizen-number.md)
- [Güney Afrika kimlik numarası](sit-defn-south-africa-identification-number.md)
- [Güney Kore mukim kayıt numarası](sit-defn-south-korea-resident-registration-number.md)
- [İspanya DNI](sit-defn-spain-dni.md)
- [İspanya ehliyet numarası](sit-defn-spain-drivers-license-number.md)
- [İspanya pasaport numarası](sit-defn-spain-passport-number.md)
- [İspanya fiziksel adresleri](sit-defn-spain-physical-addresses.md)
- [İspanya sosyal güvenlik numarası (SSN)](sit-defn-spain-social-security-number.md)
- [İspanya vergi kimlik numarası](sit-defn-spain-tax-identification-number.md)
- [SQL Server bağlantı dizesi](sit-defn-sql-server-connection-string.md)
- [Cerrahi prosedürler](sit-defn-surgical-procedures.md)
- [İsveç ehliyet numarası](sit-defn-sweden-drivers-license-number.md)
- [İsveç ulusal kimliği](sit-defn-sweden-national-id.md)
- [İsveç pasaport numarası](sit-defn-sweden-passport-number.md)
- [İsveç fiziksel adresleri](sit-defn-sweden-physical-addresses.md)
- [İsveç vergi kimlik numarası](sit-defn-sweden-tax-identification-number.md)
- [SWIFT kodu](sit-defn-swift-code.md)
- [İsviçre fiziksel adresleri](sit-defn-switzerland-physical-addresses.md)
- [İsviçre SSN AHV numarası](sit-defn-switzerland-ssn-ahv-number.md)
- [Tayvan ulusal kimlik numarası](sit-defn-taiwan-national-identification-number.md)
- [Tayvan pasaport numarası](sit-defn-taiwan-passport-number.md)
- [Tayvan mukim sertifikası (ARC/TARC) numarası](sit-defn-taiwan-resident-certificate-number.md)
- [Tay nüfus kimlik kodu](sit-defn-thai-population-identification-code.md)
- [Türkiye ulusal kimlik numarası](sit-defn-turkey-national-identification-number.md)
- [Türkiye fiziksel adresleri](sit-defn-turkey-physical-addresses.md)
- [İlaç türleri](sit-defn-types-of-medication.md)
- [Birleşik Krallık ehliyet numarası](sit-defn-uk-drivers-license-number.md)
- [Birleşik Krallık seçim rulosu numarası](sit-defn-uk-electoral-roll-number.md)
- [Birleşik Krallık ulusal sağlık hizmeti numarası](sit-defn-uk-national-health-service-number.md)
- [Birleşik Krallık ulusal sigorta numarası (NINO)](sit-defn-uk-national-insurance-number.md)
- [Birleşik Krallık fiziksel adresleri](sit-defn-uk-physical-addresses.md)
- [Birleşik Krallık Benzersiz Vergi Mükellefi Başvuru Numarası](sit-defn-uk-unique-taxpayer-reference-number.md)
- [ABD banka hesap numarası](sit-defn-us-bank-account-number.md)
- [ABD ehliyet numarası](sit-defn-us-drivers-license-number.md)
- [ABD bireysel vergi mükellefi kimlik numarası (ITIN)](sit-defn-us-individual-taxpayer-identification-number.md)
- [ABD fiziksel adresleri](sit-defn-us-physical-addresses.md)
- [ABD sosyal güvenlik numarası (SSN)](sit-defn-us-social-security-number.md)
- [ABD/Birleşik Krallık pasaport numarası](sit-defn-us-uk-passport-number.md)
- [Ukrayna pasaportu yurt içi](sit-defn-ukraine-passport-domestic.md)
- [Ukrayna pasaportu uluslararası](sit-defn-ukraine-passport-international.md)
- [Kullanıcı oturum açma kimlik bilgileri](sit-defn-user-login-credentials.md)
- [X.509 sertifikası özel anahtarı](sit-defn-x-509-certificate-private-key.md)

