---
title: Veri Kaybı Önleme ilkesi başvurusu
f1.keywords: CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 03/02/2022
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- SPO160
- MET150
ms.assetid: 6501b5ef-6bf7-43df-b60d-f65781847d6c
ms.collection:
- M365-security-compliance
- SPO_Content
recommendations: false
description: DLP ilkesi bileşeni ve yapılandırma başvurusu
ms.custom: seo-marvel-apr2021
ms.openlocfilehash: 9d0b8489c303b7786cdd7443ebc6f41507e6487e
ms.sourcegitcommit: 34910ea9318289d78c35b0e7990238467c05384b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/10/2022
ms.locfileid: "67306712"
---
# <a name="data-loss-prevention-policy-reference"></a>Veri Kaybı Önleme ilkesi başvurusu

Microsoft Purview Veri Kaybı Önleme (DLP) ilkelerinin yapılandırılması gereken birçok bileşen vardır. Etkili bir ilke oluşturmak için, her bileşenin amacını ve yapılandırmasının ilkenin davranışını nasıl değiştirdiğini anlamanız gerekir. Bu makale, DLP ilkesinin ayrıntılı anatomisini sağlar.

## <a name="policy-templates"></a>İlke şablonları 

DLP ilkesi şablonları dört kategoriye önceden sıralanır:

- **Finansal** bilgi türlerini algılayıp koruyabilenler.
- **Tıbbi ve sağlık** bilgilerini algılayıp koruyabilen bilgiler.
- **Gizlilik** bilgileri türlerini algılayıp koruyabilenler.
- Diğer ilkelerden biri kuruluşunuzun ihtiyaçlarını karşılamıyorsa kendi ilkenizi oluşturmak için kullanabileceğiniz **özel** bir şablon.

Bu tabloda, tüm ilke şablonları ve bunların kapsadıkları hassas bilgi türleri (SIT) listelenir. 

güncelleştirme: 23.06.2021

|Kategori|Şablon | Oturup |
|---------|---------|---------|
|Finansal| Avustralya Finansal Verileri| - [SWIFT kodu](sit-defn-swift-code.md) </br> -  [Avustralya vergi dosyası numarası](sit-defn-australia-tax-file-number.md) </br> - [Avustralya banka hesap numarası](sit-defn-australia-bank-account-number.md) </br> - [Kredi kartı numarası](sit-defn-credit-card-number.md)|
|Finansal| Kanada Finansal verileri |- [Kredi kartı numarası](sit-defn-credit-card-number.md) </br> - [Kanada banka hesap numarası](sit-defn-canada-bank-account-number.md)|
|Finansal| Fransa Finansal verileri |- [Kredi kartı numarası](sit-defn-credit-card-number.md) </br> - [AB banka kartı numarası](sit-defn-eu-debit-card-number.md)|
|Finansal| Almanya Finansal Verileri |- [Kredi kartı numarası](sit-defn-credit-card-number.md) </br> - [AB banka kartı numarası](sit-defn-eu-debit-card-number.md)|
|Finansal| İsrail Finansal Verileri |- [İsrail banka hesap numarası](sit-defn-israel-bank-account-number.md) </br> - [SWIFT kodu](sit-defn-swift-code.md) </br> - [Kredi kartı numarası](sit-defn-credit-card-number.md)|
|Finansal| Japonya Finansal Verileri |- [Japonya banka hesap numarası](sit-defn-japan-bank-account-number.md)</br> - [Kredi kartı numarası](sit-defn-credit-card-number.md)|
|Finansal| PCI Veri Güvenliği Standardı (PCI DSS)|- [Kredi kartı numarası](sit-defn-credit-card-number.md)|
|Finansal| Suudi Arabistan Siber Suçlarla Mücadele Yasası|- [SWIFT kodu](sit-defn-swift-code.md) </br> - [Uluslararası bankacılık hesap numarası (IBAN)](sit-defn-international-banking-account-number.md)|
|Finansal| Suudi Arabistan Finansal Verileri |- [Kredi kartı numarası](sit-defn-credit-card-number.md) </br> - [SWIFT kodu](sit-defn-swift-code.md) </br> - [Uluslararası bankacılık hesap numarası (IBAN)](sit-defn-international-banking-account-number.md)|
|Finansal| Birleşik Krallık Finansal Verileri|- [Kredi kartı numarası](sit-defn-credit-card-number.md) </br> - [AB banka kartı numarası](sit-defn-eu-debit-card-number.md) </br> - [SWIFT kodu](sit-defn-swift-code.md)|
|Finansal| ABD Finansal Verileri|- [Kredi kartı numarası](sit-defn-credit-card-number.md) </br> - [ABD banka hesap numarası](sit-defn-us-bank-account-number.md)</br> - [ABA Yönlendirme Numarası](sit-defn-aba-routing.md)|
|Finansal| ABD Federal Ticaret Komisyonu (FTC) Tüketici Kuralları|- [Kredi kartı numarası](sit-defn-credit-card-number.md) </br> - [ABD banka hesap numarası](sit-defn-us-bank-account-number.md)</br> - [ABA Yönlendirme Numarası](sit-defn-aba-routing.md)|
|Finansal| U.S. Gramm-Leach-Bliley Act (GLBA) Enhanced|- [Kredi kartı numarası](sit-defn-credit-card-number.md) </br> - [ABD banka hesap numarası](sit-defn-us-bank-account-number.md)</br> - [ABD Bireysel Vergi Mükellefi Kimlik Numarası (ITIN)](sit-defn-us-individual-taxpayer-identification-number.md)  </br> - [ABD sosyal güvenlik numarası (SSN)](sit-defn-us-social-security-number.md)</br> - [ABD/Birleşik Krallık pasaport numarası](sit-defn-us-uk-passport-number.md) </br> -[ABD ehliyet numarası](sit-defn-us-drivers-license-number.md)</br> - [Tüm Tam Adlar](sit-defn-all-full-names.md)</br> - [ABD Fiziksel Adresleri](sit-defn-us-physical-addresses.md)|
|Finansal| ABD Gramm-Leach-Bliley Yasası (GLBA)|- [Kredi kartı numarası](sit-defn-credit-card-number.md) </br> - [ABD banka hesap numarası](sit-defn-us-bank-account-number.md)</br> - [ABD Bireysel Vergi Mükellefi Kimlik Numarası (ITIN)](sit-defn-us-individual-taxpayer-identification-number.md)  </br> - [ABD sosyal güvenlik numarası (SSN)](sit-defn-us-social-security-number.md)|
|Tıbbi ve sağlık| Avustralya Sağlık Kayıtları Yasası (HRIP Yasası) Geliştirildi |- [Avustralya vergi dosyası numarası](sit-defn-australia-tax-file-number.md)</br> - [Avustralya tıbbi hesap numarası](sit-defn-australia-medical-account-number.md)</br> - [Tüm Tam Adlar](sit-defn-all-full-names.md) </br> - [Tüm Tıbbi Hüküm ve Koşullar](sit-defn-all-medical-terms-conditions.md) </br> - [Avustralya Fiziksel Adresleri](sit-defn-australia-physical-addresses.md)|
|Tıbbi ve sağlık| Avustralya Sağlık Kayıtları Yasası (HRIP Yasası)|- [Avustralya vergi dosyası numarası](sit-defn-australia-tax-file-number.md) </br> - [Avustralya tıbbi hesap numarası](sit-defn-australia-medical-account-number.md)|
|Tıbbi ve sağlık| Kanada Sağlık Bilgileri Yasası (HIA) |- [Kanada pasaport numarası](sit-defn-canada-passport-number.md) </br> - [Kanada sosyal sigorta numarası](sit-defn-canada-social-insurance-number.md) </br> - [Kanada sağlık hizmeti numarası](sit-defn-canada-health-service-number.md) </br> - [Kanada Kişisel Sağlık Kimlik Numarası](sit-defn-canada-personal-health-identification-number.md)|
|Tıbbi ve sağlık| Kanada Kişisel Sağlık Bilgileri Yasası (PHIA) Manitoba|- [Kanada sosyal sigorta numarası](sit-defn-canada-social-insurance-number.md) </br> - [Kanada sağlık hizmeti numarası](sit-defn-canada-health-service-number.md) </br> - [Kanada Kişisel Sağlık Kimlik Numarası](sit-defn-canada-personal-health-identification-number.md)|
|Tıbbi ve sağlık| Kanada Kişisel Sağlık Yasası (PHIPA) Ontario |- [Kanada pasaport numarası](sit-defn-canada-passport-number.md) </br> - [Kanada sosyal sigorta numarası](sit-defn-canada-social-insurance-number.md) </br> - [Kanada sağlık hizmeti numarası](sit-defn-canada-health-service-number.md) </br> - [Kanada Kişisel Sağlık Kimlik Numarası](sit-defn-canada-personal-health-identification-number.md)|
|Tıbbi ve sağlık| BK Tıbbi Raporlara Erişim Yasası|- [Birleşik Krallık ulusal sağlık hizmeti numarası](sit-defn-uk-national-health-service-number.md) </br> - [Birleşik Krallık ulusal sigorta numarası (NINO)](sit-defn-uk-national-insurance-number.md)|
|Tıbbi ve sağlık| ABD Sağlık Sigortası Yasası (HIPAA) Geliştirildi|</br> - [Uluslararası hastalık sınıflandırması (ICD-9-CM)](sit-defn-international-classification-of-diseases-icd-9-cm.md) </br> - [Uluslararası hastalık sınıflandırması (ICD-10-CM)](sit-defn-international-classification-of-diseases-icd-10-cm.md) </br> - [Tüm Tam Adlar](sit-defn-all-full-names.md) </br> - [Tüm Tıbbi Hüküm ve Koşullar](sit-defn-all-medical-terms-conditions.md) </br> - [ABD Fiziksel Adresleri](sit-defn-us-physical-addresses.md)|
|Tıbbi ve sağlık| ABD Sağlık Sigortası Yasası (HIPAA)| - [Uluslararası hastalık sınıflandırması (ICD-9-CM)](sit-defn-international-classification-of-diseases-icd-9-cm.md) </br> - [Uluslararası hastalık sınıflandırması (ICD-10-CM)](sit-defn-international-classification-of-diseases-icd-10-cm.md)|
|Gizlilik| Gelişmiş Avustralya Gizlilik Yasası|- [Avustralya ehliyet numarası](sit-defn-australia-drivers-license-number.md) </br> - [Avustralya pasaport numarası](sit-defn-australia-passport-number.md) </br> - [Tüm Tam Adlar](sit-defn-all-full-names.md) </br> - [Tüm Tıbbi Hüküm ve Koşullar](sit-defn-all-medical-terms-conditions.md) </br> - [Avustralya Fiziksel Adresleri](sit-defn-australia-physical-addresses.md)|
|Gizlilik| Avustralya Gizlilik Yasası|- [Avustralya sürücü lisans numarası](sit-defn-australia-drivers-license-number.md)</br> - [Avustralya pasaport numarası](sit-defn-australia-passport-number.md)|
|Gizlilik| Avustralya Kişisel Bilgiler (PII) Verileri|- [Avustralya vergi dosyası numarası](sit-defn-australia-tax-file-number.md) </br> - [Avustralya ehliyet numarası](sit-defn-australia-drivers-license-number.md)|
|Gizlilik| Kanada Kişisel Bilgiler (PII) Verileri|- [Kanada ehliyet numarası](sit-defn-canada-drivers-license-number.md) </br> - [Kanada banka hesap numarası](sit-defn-canada-bank-account-number.md) </br> - [Kanada pasaport numarası](sit-defn-canada-passport-number.md) </br> - [Kanada sosyal sigorta numarası](sit-defn-canada-social-insurance-number.md) </br> - [Kanada sağlık hizmeti numarası](sit-defn-canada-health-service-number.md) </br> - [Kanada Kişisel Sağlık Kimlik Numarası](sit-defn-canada-personal-health-identification-number.md)|
|Gizlilik| Kanada Kişisel Information Protection Yasası (PIPA)|- [Kanada pasaport numarası](sit-defn-canada-passport-number.md) </br> - [Kanada sosyal sigorta numarası](sit-defn-canada-social-insurance-number.md) </br> - [Kanada sağlık hizmeti numarası](sit-defn-canada-health-service-number.md) </br> - [Kanada Kişisel Sağlık Kimlik Numarası](sit-defn-canada-personal-health-identification-number.md)|
|Gizlilik| Kanada Kişisel Information Protection Yasası (PIPEDA)|- [Kanada ehliyet numarası](sit-defn-canada-drivers-license-number.md) </br> - [Kanada banka hesap numarası](sit-defn-canada-bank-account-number.md) </br> - [Kanada pasaport numarası](sit-defn-canada-passport-number.md) </br> - [Kanada sosyal sigorta numarası](sit-defn-canada-social-insurance-number.md) </br> - [Kanada sağlık hizmeti numarası](sit-defn-canada-health-service-number.md) </br> - [Kanada Kişisel Sağlık Kimlik Numarası](sit-defn-canada-personal-health-identification-number.md)|
|Gizlilik| Fransa Veri Koruma Yasası|- [Fransa ulusal kimlik kartı (CNI)](sit-defn-france-national-id-card.md)</br> - [Fransa sosyal güvenlik numarası (INSEE)](sit-defn-france-social-security-number.md)|
|Gizlilik| Fransa Kişisel Bilgiler (PII) Verileri|- [Fransa sosyal güvenlik numarası (INSEE)](sit-defn-france-social-security-number.md) </br> - [Fransa ehliyet numarası](sit-defn-france-drivers-license-number.md) </br> - [Fransa pasaport numarası](sit-defn-france-passport-number.md) </br> - [Fransa ulusal kimlik kartı (CNI)](sit-defn-france-national-id-card.md)|
|Gizlilik| Genel Veri Koruma Yönetmeliği (GDPR) Geliştirildi|- [Avusturya Fiziksel Adresleri](sit-defn-austria-physical-addresses.md) </br> - [Belçika Fiziksel Adresleri](sit-defn-belgium-physical-addresses.md) </br> - [Bulgaristan Fiziksel Adresleri](sit-defn-bulgaria-physical-addresses.md) </br> - [Hırvatistan Fiziksel Adresleri](sit-defn-croatia-physical-addresses.md) </br> - [Kıbrıs Fiziksel Adresleri](sit-defn-cyprus-physical-addresses.md) </br> - [Çek Cumhuriyeti Fiziksel Adresleri](sit-defn-czech-republic-physical-addresses.md)</br> - [Danimarka Fiziksel Adresleri](sit-defn-denmark-physical-addresses.md)</br> - [Estonya Fiziksel Adresleri](sit-defn-estonia-physical-addresses.md)</br> - [Finlandiya Fiziksel Adresleri](sit-defn-finland-physical-addresses.md)</br> - [Fransa Fiziksel Adresleri](sit-defn-france-physical-addresses.md)</br> - [Almanya Fiziksel Adresleri](sit-defn-germany-physical-addresses.md)</br> - [Yunanistan Fiziksel Adresleri](sit-defn-greece-physical-addresses.md)</br> - [Macaristan Fiziksel Adresleri](sit-defn-hungary-physical-addresses.md)</br> - [İrlanda Fiziksel Adresleri](sit-defn-ireland-physical-addresses.md)</br> - [İtalya Fiziksel Adresleri](sit-defn-italy-physical-addresses.md)</br> - [Letonya Fiziksel Adresleri](sit-defn-latvia-physical-addresses.md)</br> - [Litvanya Fiziksel Adresleri](sit-defn-lithuania-physical-addresses.md)</br> - [Lüksemburg Fiziksel Adresleri](sit-defn-luxemburg-physical-addresses.md)</br> - [Malta Fiziksel Adresleri](sit-defn-malta-physical-addresses.md)</br> - [Hollanda Fiziksel Adresleri](sit-defn-netherlands-physical-addresses.md)</br> - [Polonya Fiziksel Adresleri](sit-defn-poland-physical-addresses.md)</br> - [Portekizce Fiziksel Adresler](sit-defn-portugal-physical-addresses.md)</br> - [Romanya Fiziksel Adresleri](sit-defn-romania-physical-addresses.md)</br> - [Slovakya Fiziksel Adresleri](sit-defn-slovakia-physical-addresses.md)</br> - [Slovenya Fiziksel Adresleri](sit-defn-slovenia-physical-addresses.md)</br> - [İspanya Fiziksel Adresleri](sit-defn-spain-physical-addresses.md)</br> - [İsveç Fiziksel Adresleri](sit-defn-sweden-physical-addresses.md)</br> - [Avusturya Sosyal Güvenlik Numarası](sit-defn-austria-social-security-number.md) </br> - [Fransa Sosyal Güvenlik Numarası (INSEE)](sit-defn-france-social-security-number.md)</br> - [Yunanistan Sosyal Güvenlik Numarası (AMKA)](sit-defn-greece-social-security-number.md)</br> - [Macar Sosyal Güvenlik Numarası (TAJ)](sit-defn-hungary-social-security-number.md)</br> - [İspanya Sosyal Güvenlik Numarası (SSN)](sit-defn-spain-social-security-number.md)</br> - [Avusturya Kimlik Kartı](sit-defn-austria-identity-card.md) </br> - [Kıbrıs Kimlik Kartı](sit-defn-cyprus-identity-card.md) </br> - [Almanya Kimlik Kartı Numarası](sit-defn-germany-identity-card-number.md)</br> - [Malta Kimlik Kartı Numarası](sit-defn-malta-identity-card-number.md)</br> - [Fransa Ulusal Kimlik Kartı (CNI)](sit-defn-france-national-id-card.md)</br> - [Yunanistan Ulusal Kimlik Kartı](sit-defn-greece-national-id-card.md)</br> - [Finlandiya Ulusal Kimliği](sit-defn-finland-national-id.md)</br> - [Polonya Ulusal Kimliği (PESEL)](sit-defn-poland-national-id.md)</br> - [İsveç Ulusal Kimliği](sit-defn-sweden-national-id.md)</br> - [Hırvatistan Kişisel Kimlik (OIB) Numarası](sit-defn-croatia-personal-identification-number.md) </br> - [Çek Kişisel Kimlik Numarası](sit-defn-czech-personal-identity-number.md)</br> - [Danimarka Kişisel Kimlik Numarası](sit-defn-denmark-personal-identification-number.md)</br> - [Estonya Kişisel Kimlik Kodu](sit-defn-estonia-personal-identification-code.md)</br> - [Macaristan Kişisel Kimlik Numarası](sit-defn-hungary-personal-identification-number.md)</br> - [Luxemburg Ulusal Kimlik Numarası gerçek kişiler](sit-defn-luxemburg-national-identification-number-natural-persons.md)</br> - [Luxemburg Ulusal Kimlik Numarası (Gerçek olmayan kişiler)](sit-defn-luxemburg-national-identification-number-non-natural-persons.md)</br> - [İtalya Mali Kodu](sit-defn-italy-fiscal-code.md)</br> - [Letonya Kişisel Kodu](sit-defn-latvia-personal-code.md)</br> - [Litvanya Kişisel Kodu](sit-defn-lithuania-personal-code.md)</br> - [Romanya Kişisel Sayısal Kodu (CNP)](sit-defn-romania-personal-numeric-code.md)</br> - [Hollanda VatandaşLık Hizmeti (BSN) Numarası](sit-defn-netherlands-citizens-service-number.md)</br> - [İrlanda Kişisel Kamu Hizmeti (PPS) Numarası](sit-defn-ireland-personal-public-service-number.md)</br> - [Bulgaristan Tekdüzen Sivil Numarası](sit-defn-bulgaria-uniform-civil-number.md) </br> - [Belçika Ulusal Numarası](sit-defn-belgium-national-number.md) </br> - [İspanya DNI](sit-defn-spain-dni.md)</br> - [Slovenya Benzersiz Ana Vatandaş Numarası](sit-defn-slovenia-unique-master-citizen-number.md)</br> - [Slovakya Kişisel Numarası](sit-defn-slovakia-personal-number.md)</br> - [Portekiz Vatandaş Kart Numarası](sit-defn-portugal-citizen-card-number.md)</br> - [Malta Vergi Kimlik Numarası](sit-defn-malta-tax-identification-number.md)</br> - [Avusturya Vergi Kimlik Numarası](sit-defn-austria-tax-identification-number.md) </br> - [Kıbrıs Vergi Kimlik Numarası](sit-defn-cyprus-tax-identification-number.md) </br> -[Fransa Vergi Kimlik Numarası (numéro SPI.)](sit-defn-france-tax-identification-number.md)</br> - [Almanya Vergi Kimlik Numarası](sit-defn-germany-tax-identification-number.md)</br> - [Yunan Vergi Kimlik Numarası](sit-defn-greece-tax-identification-number.md)</br> - [Macaristan Vergi Kimlik Numarası](sit-defn-hungary-tax-identification-number.md)</br> - [Hollanda Vergi Kimlik Numarası](sit-defn-netherlands-tax-identification-number.md)</br> - [Polonya Vergi Kimlik Numarası](sit-defn-poland-tax-identification-number.md)</br> - [Portekiz Vergi Kimlik Numarası](sit-defn-portugal-tax-identification-number.md)</br> - [Slovenya Vergi Kimlik Numarası](sit-defn-slovenia-tax-identification-number.md)</br> - [İspanya Vergi Kimlik Numarası](sit-defn-spain-tax-identification-number.md)</br> - [İsveç Vergi Kimlik Numarası](sit-defn-sweden-tax-identification-number.md)</br> - [Avusturya Sürücü Belgesi](sit-defn-austria-drivers-license-number.md) </br> - [Belçika Ehliyet Numarası](sit-defn-belgium-drivers-license-number.md) </br> - [Bulgaristan Ehliyet Numarası](sit-defn-bulgaria-drivers-license-number.md) </br> - [Hırvatistan Ehliyet Numarası](sit-defn-croatia-drivers-license-number.md) </br> - [Kıbrıs Ehliyet Numarası](sit-defn-cyprus-drivers-license-number.md) </br> - [Çek Ehliyet Numarası](sit-defn-czech-drivers-license-number.md) </br> - [Danimarka Ehliyet Numarası](sit-defn-denmark-drivers-license-number.md)</br> - [Estonya Sürücü Lisans Numarası](sit-defn-estonia-drivers-license-number.md)</br> - [Finlandiya Ehliyet Numarası](sit-defn-finland-drivers-license-number.md)</br> - [Fransa Ehliyet Numarası](sit-defn-france-drivers-license-number.md)</br> - [Alman Sürücü Belgesi Numarası](sit-defn-germany-drivers-license-number.md)</br> - [Yunanistan Ehliyet Numarası](sit-defn-greece-drivers-license-number.md) </br> - [Macaristan Ehliyet Numarası](sit-defn-hungary-drivers-license-number.md)</br> - [İrlanda Ehliyet Numarası](sit-defn-ireland-drivers-license-number.md)</br> - [İtalya Ehliyet Numarası](sit-defn-italy-drivers-license-number.md)</br> - [Letonya Ehliyet Numarası](sit-defn-latvia-drivers-license-number.md)</br> - [Litvanya Sürücü Belgesi Numarası](sit-defn-lithuania-drivers-license-number.md)</br> - [Luxemburg Ehliyet Numarası](sit-defn-luxemburg-drivers-license-number.md)</br> - [Malta Sürücü Belgesi Numarası](sit-defn-malta-drivers-license-number.md)</br> - [Hollanda Ehliyet Numarası](sit-defn-netherlands-drivers-license-number.md)</br> - [Polonya Sürücü Belgesi Numarası](sit-defn-poland-drivers-license-number.md)</br> - [Portekiz Sürücü Ehliyeti Numarası](sit-defn-portugal-drivers-license-number.md)</br> - [Romanya Ehliyet Numarası](sit-defn-romania-drivers-license-number.md)</br> - [Slovakya Sürücü Ehliyeti Numarası](sit-defn-slovakia-drivers-license-number.md)</br> - [Slovenya Ehliyet Numarası](sit-defn-slovenia-drivers-license-number.md)</br> - [İspanya Ehliyet Numarası](sit-defn-spain-drivers-license-number.md)</br> - [İsveç Ehliyet Numarası](sit-defn-sweden-drivers-license-number.md)</br> - [Avusturya Pasaport Numarası](sit-defn-austria-passport-number.md) </br> - [Belçika Pasaport Numarası](sit-defn-belgium-passport-number.md) </br> - [Bulgaristan Pasaport Numarası](sit-defn-bulgaria-passport-number.md) </br> - [Hırvatistan Pasaport Numarası](sit-defn-croatia-passport-number.md) </br> - [Kıbrıs Pasaport Numarası](sit-defn-cyprus-passport-number.md) </br> - [Çek Cumhuriyeti Pasaport Numarası](sit-defn-czech-passport-number.md) </br> - [Danimarka Pasaport Numarası](sit-defn-denmark-passport-number.md)</br> - [Estonya Pasaport Numarası](sit-defn-estonia-passport-number.md)</br> - [Finlandiya Pasaport Numarası](sit-defn-finland-passport-number.md)</br> - [Fransa Pasaport Numarası](sit-defn-france-passport-number.md)</br> - [Alman Pasaport Numarası](sit-defn-germany-passport-number.md)</br> - [Yunanistan Pasaport Numarası](sit-defn-greece-passport-number.md)</br> - [Macaristan Pasaport Numarası](sit-defn-hungary-passport-number.md)</br> - [İrlanda Pasaport Numarası](sit-defn-ireland-passport-number.md)</br> - [İtalya Pasaport Numarası](sit-defn-italy-passport-number.md)</br> - [Letonya Pasaport Numarası](sit-defn-latvia-passport-number.md)</br> - [Litvanya Pasaport Numarası](sit-defn-lithuania-passport-number.md)</br> - [Luxemburg Pasaport Numarası](sit-defn-luxemburg-passport-number.md)</br> - [Malta Pasaport Numarası](sit-defn-malta-passport-number.md)</br> - [Hollanda Pasaport Numarası](sit-defn-netherlands-passport-number.md)</br> - [Polonya Pasaportu](sit-defn-poland-passport-number.md)</br> - [Portekiz Pasaport Numarası](sit-defn-portugal-passport-number.md)</br> - [Romanya Pasaport Numarası](sit-defn-romania-passport-number.md)</br> - [Slovakya Pasaport Numarası](sit-defn-slovakia-passport-number.md)</br> - [Slovenya Pasaport Numarası](sit-defn-slovenia-passport-number.md)</br> - [İspanya Pasaport Numarası](sit-defn-spain-passport-number.md)</br> - [İsveç Pasaport Numarası](sit-defn-sweden-passport-number.md)</br> - [AB Banka Kartı Numarası](sit-defn-eu-debit-card-number.md)</br> - [Tüm Tam Adlar](sit-defn-all-full-names.md)|
|Gizlilik| Genel Veri Koruma Yönetmeliği (GDPR)|- [AB banka kartı numarası](sit-defn-eu-debit-card-number.md) </br> - [AB ehliyet numarası](sit-defn-eu-drivers-license-number.md) </br> - [AB ulusal kimlik numarası](sit-defn-eu-national-identification-number.md)</br> - [AB pasaport numarası](sit-defn-eu-passport-number.md) </br> - [AB sosyal güvenlik numarası veya eşdeğer kimlik](sit-defn-eu-social-security-number-equivalent-identification.md)</br> - [AB Vergi kimlik numarası](sit-defn-eu-tax-identification-number.md)|
|Gizlilik| Almanya Kişisel Bilgiler (PII) Verileri|- [Almanya ehliyet numarası](sit-defn-germany-drivers-license-number.md) </br> - [Almanya pasaport numarası](sit-defn-germany-passport-number.md)| 
|Gizlilik| İsrail Kişisel Bilgiler (PII) Verileri|- [İsrail ulusal kimlik numarası](sit-defn-israel-national-identification-number.md)| 
|Gizlilik| İsrail'de Gizliliğin Korunması|- [İsrail ulusal kimlik numarası](sit-defn-israel-national-identification-number.md)</br> - [İsrail banka hesap numarası](sit-defn-israel-bank-account-number.md)|
|Gizlilik| Japonya Kişisel Bilgiler (PII) Verileri geliştirildi|- [Japonya Sosyal Sigorta Numarası (SIN)](sit-defn-japan-social-insurance-number.md)</br> - [Japonya Numaram - Kişisel](sit-defn-japan-my-number-personal.md)</br> - [Japonya pasaport numarası](sit-defn-japan-passport-number.md)</br> - [Japonya ehliyet numarası](sit-defn-japan-drivers-license-number.md)</br> - [Tüm Tam Adlar](sit-defn-all-full-names.md)</br> - [Japonya Fiziksel Adresleri](sit-defn-all-physical-addresses.md)|
|Gizlilik| Japonya Kişisel Bilgiler (PII) Verileri|- [Japonya'da ikamet eden kayıt numarası](sit-defn-japan-resident-registration-number.md) </br> - [Japonya Sosyal Sigorta Numarası (SIN)](sit-defn-japan-social-insurance-number.md)|
|Gizlilik| Japonya Kişisel Bilgilerin Korunması Geliştirildi|- [Japonya Sosyal Sigorta Numarası (SIN)](sit-defn-japan-social-insurance-number.md) </br> - [Japonya Numaram - Kişisel](sit-defn-japan-my-number-personal.md)</br> - [Japonya pasaport numarası](sit-defn-japan-passport-number.md) </br> - [Japonya ehliyet numarası](sit-defn-japan-drivers-license-number.md)</br> - [Tüm Tam Adlar](sit-defn-all-full-names.md)</br> - [Japonya Fiziksel Adresleri](sit-defn-all-physical-addresses.md)|
|Gizlilik| Japonya Kişisel Bilgilerin Korunması|- [Japonya'da ikamet eden kayıt numarası](sit-defn-japan-resident-registration-number.md)</br> - [Japonya Sosyal Sigorta Numarası (SIN)](sit-defn-japan-social-insurance-number.md)|
|Gizlilik| Suudi Arabistan Kişisel Olarak Tanımlanabilir (PII) Verileri|- [Suudi Arabistan Ulusal Kimliği](sit-defn-saudi-arabia-national-id.md)|
|Gizlilik| BK Veri Koruma Yasası|- [Birleşik Krallık ulusal sigorta numarası (NINO)](sit-defn-uk-national-insurance-number.md) </br> - [ABD/Birleşik Krallık pasaport numarası](sit-defn-us-uk-passport-number.md) </br> - [SWIFT kodu](sit-defn-swift-code.md)|
|Gizlilik| BK Gizlilik ve Elektronik İletişim Düzenlemeleri|- [SWIFT kodu](sit-defn-swift-code.md)|
|Gizlilik| BK Kişisel Bilgiler (PII) Verileri|- [Birleşik Krallık ulusal sigorta numarası (NINO)](sit-defn-uk-national-insurance-number.md) </br> - [ABD/Birleşik Krallık pasaport numarası](sit-defn-us-uk-passport-number.md)|
|Gizlilik| BK Kişisel Bilgiler Çevrimiçi Uygulama Kodu (PIOCP)|- [Birleşik Krallık ulusal sigorta numarası (NINO)](sit-defn-uk-national-insurance-number.md) </br> - [Birleşik Krallık ulusal sağlık hizmeti numarası](sit-defn-uk-national-health-service-number.md) </br> - [SWIFT kodu](sit-defn-swift-code.md)|
|Gizlilik| ABD Vatanseverlik Yasası Geliştirildi|- [Kredi kartı numarası](sit-defn-credit-card-number.md) </br> - [ABD banka hesap numarası](sit-defn-us-bank-account-number.md)</br> - [ABD Bireysel Vergi Mükellefi Kimlik Numarası (ITIN)](sit-defn-us-individual-taxpayer-identification-number.md)  </br> - [ABD sosyal güvenlik numarası (SSN)](sit-defn-us-social-security-number.md)</br> - [Tüm Tam Adlar](sit-defn-all-full-names.md)</br> - [ABD Fiziksel Adresleri](sit-defn-us-physical-addresses.md)|
|Gizlilik| ABD Vatanseverlik Yasası|- [Kredi kartı numarası](sit-defn-credit-card-number.md) </br> - [ABD banka hesap numarası](sit-defn-us-bank-account-number.md)</br> - [ABD Bireysel Vergi Mükellefi Kimlik Numarası (ITIN)](sit-defn-us-individual-taxpayer-identification-number.md)  </br> - [ABD sosyal güvenlik numarası (SSN)](sit-defn-us-social-security-number.md)|
|Gizlilik| ABD Kişisel Bilgiler (PII) Verileri İyileştirilmiş|- [ABD Bireysel Vergi Mükellefi Kimlik Numarası (ITIN)](sit-defn-us-individual-taxpayer-identification-number.md)  </br> - [ABD sosyal güvenlik numarası (SSN)](sit-defn-us-social-security-number.md)</br> - [ABD/Birleşik Krallık pasaport numarası](sit-defn-us-uk-passport-number.md)</br> - [Tüm Tam Adlar](sit-defn-all-full-names.md)</br> - [ABD Fiziksel Adresleri](sit-defn-us-physical-addresses.md)|
|Gizlilik| ABD Kişisel Bilgiler (PII) Verileri|- [ABD Bireysel Vergi Mükellefi Kimlik Numarası (ITIN)](sit-defn-us-individual-taxpayer-identification-number.md)  </br> - [ABD sosyal güvenlik numarası (SSN)](sit-defn-us-social-security-number.md)</br> - [ABD/Birleşik Krallık pasaport numarası](sit-defn-us-uk-passport-number.md)|
|Gizlilik| ABD Eyalet İhlali Bildirim Yasaları Geliştirildi|- [Kredi kartı numarası](sit-defn-credit-card-number.md) </br> - [ABD banka hesap numarası](sit-defn-us-bank-account-number.md)</br> -[ABD ehliyet numarası](sit-defn-us-drivers-license-number.md) </br> - [ABD sosyal güvenlik numarası (SSN)](sit-defn-us-social-security-number.md)</br> - [Tüm Tam Adlar](sit-defn-all-full-names.md) </br> - [ABD/Birleşik Krallık pasaport numarası](sit-defn-us-uk-passport-number.md)</br> - [Tüm Tıbbi Hüküm ve Koşullar](sit-defn-all-medical-terms-conditions.md)|
|Gizlilik| ABD Eyalet İhlali Bildirim Yasaları|- [Kredi kartı numarası](sit-defn-credit-card-number.md) </br> - [ABD banka hesap numarası](sit-defn-us-bank-account-number.md)</br> -[ABD ehliyet numarası](sit-defn-us-drivers-license-number.md) </br> - [ABD sosyal güvenlik numarası (SSN)](sit-defn-us-social-security-number.md)|
|Gizlilik| ABD Devlet Sosyal Güvenlik Numarası Gizlilik Yasaları|- [ABD sosyal güvenlik numarası (SSN)](sit-defn-us-social-security-number.md)|

## <a name="locations"></a>Konum

DLP ilkesi, birden çok konumda hassas bilgiler içeren öğeleri bulabilir ve koruyabilir.

|Konum  |Kapsamı dahil et/hariç tut  |Veri durumu  |Ek önkoşullar |
|---------|---------|---------|---------|
|Çevrimiçi exchange e-postası |dağıtım grubu | hareket halindeki veriler| Hayır |
|SharePoint online siteleri   |Site       | bekleyen veriler </br> kullanımdaki veriler | Hayır|
|hesapları OneDrive İş| hesap veya dağıtım grubu |bekleyen veriler </br> kullanımdaki veriler|Hayır|
|Teams sohbeti ve kanal iletileri     | hesap veya dağıtım grubu |hareket halindeki veriler </br> kullanımdaki veriler |  Hayır       |
|Bulut Uygulamaları için Microsoft Defender   | bulut uygulaması örneği       |bekleyen veriler         | - [Microsoft dışı bulut uygulamaları için veri kaybı önleme ilkelerini kullanma](dlp-use-policies-non-microsoft-cloud-apps.md#use-data-loss-prevention-policies-for-non-microsoft-cloud-apps)        |
|Aygıtları  |kullanıcı veya grup         |bekleyen veriler </br>  kullanımdaki veriler </br>  hareket halindeki veriler         |- [Uç nokta veri kaybını önleme hakkında bilgi edinin](endpoint-dlp-learn-about.md) </br>- [Uç nokta veri kaybı önlemeyi kullanmaya başlama](endpoint-dlp-getting-started.md) </br>- [Information Protection için cihaz ara sunucusu ve internet bağlantısı ayarlarını yapılandırma](device-onboarding-configure-proxy.md#configure-device-proxy-and-internet-connection-settings-for-information-protection) |
|Şirket içi depolar (dosya paylaşımları ve SharePoint)    |Depo         | bekleyen veriler         | - [Şirket içi veri kaybı önleme tarayıcısı hakkında bilgi edinin](dlp-on-premises-scanner-learn.md) </br> - [Şirket içi veri kaybı önleme tarayıcısını kullanmaya başlama](dlp-on-premises-scanner-get-started.md#get-started-with-the-data-loss-prevention-on-premises-scanner)         |
|Power BI| Çalışma alanları | kullanımdaki veriler | Hayır|

Exchange'e belirli dağıtım gruplarını dahil etmeyi seçerseniz, DLP ilkesinin kapsamı yalnızca bu grubun üyeleriyle tamamlanır. Benzer şekilde bir dağıtım grubunu dışlamak, bu dağıtım grubunun tüm üyelerini ilke değerlendirmesinin dışında tutar. İlkenin kapsamını dağıtım listelerinin, dinamik dağıtım gruplarının ve güvenlik gruplarının üyelerine göre belirleyebilirsiniz. DLP ilkesi bu tür 50'den fazla ekleme ve dışlama içeremez.

Belirli SharePoint sitelerini veya OneDrive hesaplarını dahil etmeyi veya hariç tutmayı seçerseniz, DLP ilkesi bu tür 100'den fazla ekleme ve dışlama içeremez. Bu sınır mevcut olsa da, kuruluş genelinde bir ilke veya tüm konumlar için geçerli olan bir ilke uygulayarak bu sınırı aşabilirsiniz.

Belirli OneDrive hesaplarını veya gruplarını dahil etmeyi veya hariç tutmayı seçerseniz, DLP ilkesi 100'den fazla kullanıcı hesabı veya dahil etme veya dışlama olarak 50 grup içeremez.

### <a name="location-support-for-how-content-can-be-defined"></a>İçeriğin nasıl tanımlanabileceği için konum desteği

DLP ilkeleri hassas öğeleri hassas bilgi türüyle (SIT) veya duyarlılık etiketiyle veya bekletme etiketiyle eşleştirerek algılar. Her konum, hassas içerik tanımlamanın farklı yöntemlerini destekler. İlkedeki konumları birleştirdiğinizde içeriğin nasıl tanımlandığı, tek bir konumla tanımlanma biçiminden farklı olabilir. 

> [!IMPORTANT]
> İlke için birden çok konum seçtiğinizde, içerik tanımı kategorisi için "hayır" değeri "evet" değerinden önceliklidir. Örneğin, yalnızca SharePoint sitelerini seçtiğinizde, ilke hassas öğelerin bir veya daha fazla SIT ile, duyarlılık etiketiyle veya bekletme etiketiyle algılanmasını destekler. Ancak, SharePoint sitelerini ***ve*** Teams sohbet ve kanal iletileri konumlarını seçtiğinizde, ilke yalnızca SIT ile hassas öğelerin algılanması desteğine sahip olur.

|Konum| İçerik SIT ile tanımlanabilir| İçerik tanımlanabilir duyarlılık etiketi| İçerik bekletme etiketiyle tanımlanabilir|
|---------|---------|---------|---------|
|Çevrimiçi exchange e-postası|Evet| Evet| Hayır|
|SharePoint online siteleri| Evet| Evet| Evet|
|hesapları OneDrive İş| Evet| Evet| Evet|
|Teams Sohbet ve Kanal iletileri | Evet| Hayır| Hayır|
|Aygıtları |Evet | Evet|  Hayır|
|Bulut Uygulamaları için Microsoft Defender | Evet| Evet| Evet|
|Şirket içi depolar| Evet| Evet| Hayır|
|Power BI|Evet | Evet| Hayır|

> [!NOTE]
> DLP, hassas belgeleri algılamak için bir koşul olarak eğitilebilir sınıflandırıcıların kullanılmasını (önizlemede) destekler. İçerik Exchange Online, SharePoint Online siteleri, OneDrive İş hesapları, Teams Sohbeti ve Kanalları ve Cihazlar'daki eğitilebilir sınıflandırıcılar tarafından tanımlanabilir. Daha fazla bilgi için bkz [. Eğitilebilir Sınıflandırıcılar](classifier-learn-about.md).

> [!NOTE]
> DLP, e-postalarda ve eklerde duyarlılık etiketlerini algılamayı destekler. Daha fazla bilgi için bkz. [DLP ilkelerinde koşul olarak duyarlılık etiketlerini kullanma](dlp-sensitivity-label-as-condition.md#use-sensitivity-labels-as-conditions-in-dlp-policies).

## <a name="rules"></a>Kurallar

<!--This section introduces the classifications of content that, when detected, can be protected. Link out to [Learn about sensitive information types]() and [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md#sensitive-information-type-entity-definitions) as well as labels (cross referenced by supporting workload). It will touch on the purpose of multiple conditions, confidence levels (link out to [more on confidence levels](sensitive-information-type-learn-about.md#more-on-confidence-levels)) and confidence levels video. How to use the confidence level to change the behavior of a policy in conjunction with the instance count.  eg. if you want your policy to trigger when it encounters situation DEF, set your conditions like HIJ.-->
<!--
- What is a rule in the context of a Policy?
- when and why should I have more than one rule?
- The purpose of rule groups
- How do I tune the behavior of a Policy through the tuning of rules
- what's in a rule-->

Kurallar, DLP ilkelerinin iş mantığıdır. Şunlardan oluşur:

- Eşleştirildiğinde ilkeyi tetikleyen [**koşullar**](#conditions)
- [**Koşulların özel durumları**](#exceptions)
- [**İlke**](#actions) tetiklendiğinde yapılması gereken eylemler
- [**Bir**](#user-notifications-and-policy-tips) ilkeyi tetikleyen bir işlem yaparken kullanıcılarınızı bilgilendirmek ve kuruluşunuzun hassas bilgilerin nasıl ele alındığını öğrenmek için onları eğitmeye yardımcı olan kullanıcı bildirimleri
- Yönetici tarafından yapılandırıldığında [**Kullanıcı Geçersiz Kılmaları**](#user-overrides), kullanıcıların bir engelleme eylemini seçmeli olarak geçersiz kılmasına izin verir
- Kural eşleşmesi gerçekleştiğinde yöneticileri ve diğer önemli paydaşları bilgilendiren [**Olay Raporları**](#incident-reports)
- Kural değerlendirmesinin önceliğini tanımlayan ve daha fazla kural ve ilke işlemeyi durdurabilen [**Ek Seçenekler**](#additional-options).

 İlke bir veya daha fazla kural içerir. Kurallar, her ilkedeki en yüksek öncelikli kuraldan başlayarak sırayla yürütülür.

### <a name="the-priority-by-which-rules-are-processed"></a>Kuralların işlenme önceliği

#### <a name="hosted-service-workloads"></a>Barındırılan hizmet iş yükleri

Exchange Online, SharePoint Online ve OneDrive İş gibi barındırılan hizmet iş yükleri için her kurala oluşturulduğu sırada bir öncelik atanır. Bu, ilk oluşturulan kuralın ilk önceliğe sahip olduğu, ikinci oluşturulan kuralın ikinci önceliğe sahip olduğu vb. anlamına gelir.
  
![Öncelik sırasına göre kurallar](../media/dlp-rules-in-priority-order.png)

İçerik kurallara göre değerlendirildiğinde, kurallar öncelik sırasına göre işlenir. İçerik birden çok kuralla eşleşiyorsa, *en* kısıtlayıcı eyleme sahip olan ilk kural değerlendirilir. Örneğin, içerik aşağıdaki kuralların tümüyle eşleşiyorsa, kural *3* en yüksek öncelikli ve en kısıtlayıcı kural olduğundan zorlanır:
  
- Kural 1: Yalnızca kullanıcılara bildirir
- Kural 2: Kullanıcılara bildirir, erişimi kısıtlar ve kullanıcı geçersiz kılmalarına izin verir
- *Kural 3: Kullanıcılara bildirir, erişimi kısıtlar ve kullanıcı geçersiz kılmalarına izin vermez*
- Kural 4: Erişimi kısıtlar

Kurallar 1, 2 ve 4 değerlendirilir ancak uygulanmaz. Bu örnekte, tüm kuralların eşleşmeleri denetim günlüklerine kaydedilir ve yalnızca en kısıtlayıcı kural uygulansa bile DLP raporlarında gösterilir.

Belirli bir koruma gereksinimini karşılamak için bir kural kullanabilir ve ardından belirli bir düzenlemeye uymak için gereken tüm kurallar gibi ortak koruma gereksinimlerini gruplandırmak için bir DLP ilkesi kullanabilirsiniz.
  
Örneğin, Sağlık Sigortası Taşınabilirlik ve Sorumluluk Yasası'na (HIPAA) tabi bilgilerin varlığını algılamanıza yardımcı olan bir DLP ilkeniz olabilir. Bu DLP ilkesi, kuruluşunuzun dışındaki kişilerle paylaşılan bu hassas bilgileri içeren herhangi bir belgeyi (koşullar) bulup belgeye erişimi engelleyip bir bildirim (eylemler) göndererek tüm SharePoint Online sitelerinde ve tüm OneDrive İş sitelerinde (nerede) HIPAA verilerinin (ne olduğu) korunmasına yardımcı olabilir. Bu gereksinimler tek tek kurallar olarak depolanır ve yönetimi ve raporlamayı basitleştirmek için bir DLP ilkesi olarak gruplandırılır.
  
![Diyagram, DLP ilkesinin konumlar ve kurallar içerdiğini gösterir](../media/c006860c-2d00-42cb-aaa4-5b5638d139f7.png)

#### <a name="for-endpoints"></a>Uç noktalar için

Uç noktalardaki kuralların önceliği, oluşturulduğu sıraya göre de atanır. Bu, ilk oluşturulan kuralın ilk önceliğe sahip olduğu, ikinci oluşturulan kuralın ikinci önceliğe sahip olduğu vb. anlamına gelir. 

Uç nokta üzerindeki bir dosya birden çok DLP ilkesiyle eşleştiğinde, [uç nokta etkinliklerinde](endpoint-dlp-learn-about.md#endpoint-activities-you-can-monitor-and-take-action-on) en kısıtlayıcı zorlamayla etkinleştirilen ilk kural, içeriğe uygulanan kuraldır. Örneğin, içerik aşağıdaki kuralların tümüyle eşleşiyorsa, en kısıtlayıcı olduğu için 2. kural diğer kurallardan önceliklidir.

- Kural 1: Yalnızca tüm etkinlikleri denetler
- *Kural 2: tüm etkinlikleri engeller*
- Kural 3: Son kullanıcının geçersiz kılma seçeneğiyle tüm etkinlikleri engeller

Aşağıdaki örnekte Kural 1, en kısıtlayıcı olduğu için diğer eşleşen kurallardan önceliklidir.

- *Kural 1: etkinliği engeller ve kullanıcı geçersiz kılmaya izin vermez*
- Kural 2: etkinliği engeller ve kullanıcı geçersiz kılmalarına izin verir
- Kural 3: Yalnızca tüm etkinlikleri denetler
- Kural 4: zorlama yok

Diğer tüm kurallar değerlendirilir ancak eylemleri uygulanmaz. Denetim günlükleri, dosyaya uygulanan en kısıtlayıcı kuralı gösterir. Eşleşen birden fazla kural varsa ve bunlar eşit derecede kısıtlayıcıysa, dosyaya hangi kuralın uygulanacağını ilke ve kural önceliği yönetir.

### <a name="conditions"></a>Koşul -ları

Koşullar kapsayıcıdır ve kuralın ne aramasını istediğinizi ve bu öğelerin kullanıldığı bağlamı tanımladığınız yerdir. Kurala &#8212;, *buna* benzeyen ve *bu şekilde kullanılan* bir öğe bulduğunuzda &#8212; bir eşleşme olduğunu ve ilkedeki eylemlerin geri kalanının bu öğe üzerinde gerçekleştirilmesi gerektiğini söyler. Farklı risk düzeylerine farklı eylemler atamak için koşulları kullanabilirsiniz. Örneğin, şirket içinde paylaşılan hassas içerik daha düşük riskli olabilir ve kuruluş dışındaki kişilerle paylaşılan hassas içerikten daha az eylem gerektirebilir.

> [!NOTE]
> Konak kuruluşun Active Directory veya Azure Active Directory kiracısında konuk olmayan hesapları olan kullanıcılar, kuruluşun içindeki kişiler olarak kabul edilir. 

#### <a name="content-contains"></a>İçerik içeriği

 Tüm konumlar **İçerik içerir** koşulunu destekler. Her içerik türünün birden çok örneğini seçebilir ve **bunlardan herhangi birini** (mantıksal VEYA) veya **Bunların tümü** (mantıksal AND) işleçlerini kullanarak koşulları daha da daraltabilirsiniz:

- [hassas bilgi türleri](sensitive-information-type-learn-about.md#learn-about-sensitive-information-types)
- [duyarlılık etiketleri](sensitivity-labels.md)
- [bekletme etiketleri](retention.md#using-a-retention-label-as-a-condition-in-a-dlp-policy)
- [Eğitilebilir Sınıflandırıcılar](classifier-learn-about.md) (önizlemede) 

ilkeyi uygulamayı seçtiğiniz [konumlara](#location-support-for-how-content-can-be-defined) bağlı olarak.

Kural yalnızca seçtiğiniz **duyarlılık etiketlerinin** ve **bekletme etiketlerinin** varlığını arar.

SID'ler, gerekirse değiştirebileceğiniz önceden tanımlanmış bir [**güvenilirlik düzeyine**](https://www.microsoft.com/videoplayer/embed/RE4Hx60) sahiptir. Daha fazla bilgi için bkz. [Güvenilirlik düzeyleri hakkında daha fazla bilgi](sensitive-information-type-learn-about.md#more-on-confidence-levels).

> [!IMPORTANT]
> SID'lerin, en fazla benzersiz örnek sayısı parametresini tanımlamanın iki farklı yolu vardır. Daha fazla bilgi edinmek için bkz [. SIT için örnek sayısı desteklenen değerler](create-a-custom-sensitive-information-type.md#instance-count-supported-values-for-sit).

#### <a name="condition-context"></a>Koşul bağlamı

Kullanılabilir bağlam seçenekleri, seçtiğiniz konuma bağlı olarak değişir. Birden çok konum seçerseniz, yalnızca konumların ortak olduğu koşullar kullanılabilir.

##### <a name="conditions-exchange-supports"></a>Exchange'in desteklediği koşullar

- İçerik içeriği
- İçerik Microsoft 365'ten paylaşılır
- İçerik şu kaynaktan alınır:
- Gönderen IP adresi
- Gönderen ilke ipucunu geçersiz kıldı mı?
- Gönderen
- Gönderen etki alanı
- Gönderen adresi sözcükler içeriyor
- Gönderen adresi desenler içeriyor
- Sender AD Özniteliği sözcükler veya tümcecikler içeriyor
- Gönderen AD Özniteliği desenleri eşleştirir
- Gönderen,
- E-posta eklerinin içeriği taranamadı
- E-posta eklerinin içeriği taramayı tamamlamadı
- Ek parola korumalı
- Dosya uzantısı
- Alıcı,
- Alıcı etki alanı
- Alıcı
- Alıcı adresi sözcükler içeriyor
- Alıcı adresi desenleri eşleştirir
- Alıcı AD Özniteliği sözcükler veya tümcecikler içeriyor
- Alıcı AD Özniteliği desenleri eşleştirir
- Belge adı sözcükler veya tümcecikler içeriyor
- Belge adı desenler ile eşleşir
- Belge özelliği şudur:
- Belge boyutu eşittir veya büyüktür
- Belge içeriği sözcükler veya tümcecikler içeriyor
- Belge içeriği desenler ile eşleşir
- Konu sözcükleri veya tümcecikleri içerir
- Konu desenleri eşleştirir
- Konu veya Gövde sözcükleri veya tümcecikleri içerir
- Konu veya gövde desenleri eşleştirir
- İçerik karakter kümesi sözcükler içeriyor
- Üst bilgi sözcükler veya tümcecikler içeriyor
- Üst bilgi desenleri eşleştirir
- İleti boyutu eşittir veya büyüktür
- İleti türü:
- İletinin önemi

##### <a name="conditions-sharepoint-supports"></a>SharePoint'in desteklediği koşullar
 
- İçerik içeriği
- İçerik Microsoft 365'ten paylaşılır
- Oluşturan belge
- Üyesi tarafından oluşturulan belge
- Belge adı sözcükler veya tümcecikler içeriyor
- Belge adı desenler ile eşleşir
- Belge boyutu üst
- Belge özelliği şudur:
- Dosya uzantısı

##### <a name="conditions-onedrive-accounts-supports"></a>OneDrive hesaplarının desteklediği koşullar

- İçerik içeriği
- İçerik Microsoft 365'ten paylaşılır
- Oluşturan belge
- Üyesi tarafından oluşturulan belge
- Belge adı sözcükler veya tümcecikler içeriyor
- Belge adı desenler ile eşleşir
- Belge boyutu üst
- Belge özelliği şudur:
- Dosya uzantısı

##### <a name="conditions-teams-chat-and-channel-messages-supports"></a>Teams sohbet ve kanal iletilerinin desteklediği koşullar

- İçerik içeriği
- İçerik Microsoft 365'ten paylaşılır
- Gönderen 
- Gönderen etki alanı 
- Alıcı etki alanı 
- Alıcı 

##### <a name="conditions-devices-supports"></a>Cihazların desteklediği koşullar

- İçerik içeriği
- (önizleme) Kullanıcı Edge'den hassas bir web sitesine erişmiş. Daha fazla bilgi için bkz[. Senaryo 6 Hassas hizmet etki alanlarındaki kullanıcı etkinliklerini izleme veya kısıtlama (önizleme).](endpoint-dlp-using.md#scenario-6-monitor-or-restrict-user-activities-on-sensitive-service-domains-preview)
- Dosya uzantısı
- Dosya türü:
- Bkz [. üzerinde izleyebileceğiniz ve eylem gerçekleştirebileceğiniz uç nokta etkinlikleri](endpoint-dlp-learn-about.md#endpoint-activities-you-can-monitor-and-take-action-on)

##### <a name="conditions-microsoft-defender-for-cloud-apps-supports"></a>Microsoft Defender for Cloud Apps desteklediği koşullar

- İçerik içeriği
- İçerik Microsoft 365'ten paylaşılır

##### <a name="conditions-on-premises-repositories-supports"></a>Şirket içi depoların desteklediği koşullar

- İçerik içeriği
- Dosya uzantısı
- Belge özelliği şudur:

##### <a name="conditions-powerbi-supports"></a>PowerBI'ın desteklediği koşullar

- İçerik içeriği

#### <a name="condition-groups"></a>Koşul grupları

Bazen, tek bir SIT ile tanımlanan ABD Sosyal Güvenlik Numarası içeren tüm içerikler gibi yalnızca bir şeyi tanımlamak için bir kurala ihtiyacınız vardır. Ancak tanımlamaya çalıştığınız öğe türlerinin daha karmaşık olduğu ve bu nedenle tanımlanmasının daha zor olduğu birçok senaryoda, koşulları tanımlamada daha fazla esneklik gerekir.

Örneğin, ABD Sağlık Sigortası Yasası'na (HIPAA) tabi içeriği tanımlamak için şunları aramanız gerekir:
  
- ABD Sosyal Güvenlik Numarası veya Uyuşturucu Uygulama Kurumu (DEA) Numarası gibi belirli türde hassas bilgiler içeren içerik.
    
    Ve
    
- Bir hastanın bakımıyla ilgili iletişim veya sağlanan tıbbi hizmetlerin açıklamaları gibi tanımlanması daha zor olan içerikler. Bu içeriğin tanımlanması için Uluslararası Hastalık Sınıflandırması (ICD-9-CM veya ICD-10-CM) gibi büyük anahtar sözcük listelerinden anahtar sözcüklerin eşleşmesi gerekir.
    
Bu tür verileri, koşulları gruplandırarak ve gruplar arasında mantıksal işleçler (AND, OR) kullanarak tanımlayabilirsiniz.
    
**ABD Sağlık Sigortası Yasası (HIPPA)** için koşullar şu şekilde gruplandırılır:

![HIPPA ilke koşulları](../media/dlp-rules-condition-groups-booleans.png)

İlk grup, ve tek tek tanımlayan SCT'leri, ikinci grup ise tıbbi tanıyı tanımlayan SID'leri içerir.

### <a name="exceptions"></a>Özel durum

Kurallarda özel durumlar, bir öğeyi ilkenin dışında tutmak için kullanılan koşulları tanımlar. Mantıksal olarak, kapsayıcı koşullar ve bağlamdan sonra değerlendirilen özel koşullar. Kurala &#8212; böyle *görünen ve bir* *eşleşme gibi kullanılan* bir öğe bulduğunuzda ve ilkedeki eylemlerin geri kalan kısmının bu öğe üzerinde gerçekleştirilip gerçekleştirilmediğini söyler&#8212; 

Örneğin, HIPPA ilkesine uygun olarak, belçika sürücü lisans numarası içeren herhangi bir öğeyi dışlamak için aşağıdaki gibi kuralı değiştirebiliriz:

![Dışlamalar içeren HIPPA ilkesi](../media/dlp-rule-exceptions.png)

Konum tarafından desteklenen özel durum koşulları, tüm ekleme koşullarıyla aynıdır ve tek fark desteklenen her koşula "Eğer hariç" öğesinin önceden eklenmesidir. Kural yalnızca özel durumlar içeriyorsa, dışlama ölçütlerini karşılamayan tüm e-postalara veya dosyalara uygulanır.

Tüm konumlar kapsayıcı koşulu desteklediği gibi:

- İçerik içeriği

özel durum şöyle olacaktır:

- **İçeriğin** 

### <a name="actions"></a>Eylem 

Kapsayıcı ***koşullar** _ ve özel _*_durum_*_ filtreleri aracılığıyla bunu yapan tüm öğelere, kuralda tanımlanan _*_tüm eylemler_*_ uygulanır. Eylemi desteklemek için gerekli seçenekleri yapılandırmanız gerekir. Örneğin, _ *Erişimi kısıtla veya Microsoft 365 konumlarındaki içeriği şifrele* eylemiyle Exchange'i* seçerseniz şu seçenekler arasından seçim yapmanız gerekir:

- Kullanıcıların paylaşılan SharePoint, OneDrive ve Teams içeriğine erişmesini engelleme
    - Herkesi engelleyin. Yalnızca içerik sahibi, son değiştirici ve site yöneticisinin erişimi devam eder
    - Yalnızca kuruluşunuzun dışındaki kişileri engelleyin. Kuruluşunuz içindeki kullanıcıların erişimi devam eder.
- E-posta iletilerini şifreleme (yalnızca Exchange'deki içerik için geçerlidir)

Bir kuralda kullanılabilen eylemler, seçilen konumlara bağlıdır. İlkenin uygulanacağı tek bir konum seçerseniz, kullanılabilir eylemler aşağıda listelenmiştir.

> [!IMPORTANT]
> SharePoint Online ve OneDrive İş konumları için belgeler, belgenin tüm dış kullanıcılar için paylaşılıp paylaşılmadığına bakılmaksızın hassas bilgiler algılandığında proaktif olarak engellenir ve iç kullanıcılar belgeye erişmeye devam eder.

#### <a name="exchange-location-actions"></a>Exchange konumu eylemleri

- Microsoft 365 konumlarındaki içeriğe erişimi kısıtlama veya içeriği şifreleme
- Üst bilgileri ayarlama
- Üst bilgiyi kaldır
- İletiyi belirli kullanıcılara yeniden yönlendirme
- Onay için iletiyi gönderenin yöneticisine iletme
- Onay için iletiyi belirli onaylayanlara iletme
- Alıcıyı Alıcı kutusuna ekleme
- Bilgi kutusuna alıcı ekleme
- Gizli kutusuna alıcı ekleme
- Gönderenin yöneticisini alıcı olarak ekleme
- O365 İleti Şifrelemesi ve hak koruması kaldırıldı
- Email Konusu
- Email Konusunu Değiştir
- HTML Bildirimi Ekle

#### <a name="sharepoint-sites-location-actions"></a>SharePoint siteleri konum eylemleri

- Microsoft 365 konumlarındaki içeriğe erişimi kısıtlama veya içeriği şifreleme

#### <a name="onedrive-account-location-actions"></a>OneDrive hesap konumu eylemleri

- Microsoft 365 konumlarındaki içeriğe erişimi kısıtlama veya içeriği şifreleme

#### <a name="teams-chat-and-channel-messages-actions"></a>Teams Sohbet ve Kanal İletileri eylemleri

- Microsoft 365 konumlarındaki içeriğe erişimi kısıtlama veya içeriği şifreleme

#### <a name="devices-actions"></a>Cihaz eylemleri

<!-- - Restrict access or encrypt the content in Microsoft 365 locations-->
- (önizleme) Kullanıcılar Windows cihazlarında Microsoft Edge tarayıcısında hassas web sitelerine eriştiğinde etkinlikleri denetle veya kısıtla. Daha fazla bilgi için bkz[. Senaryo 6 Hassas hizmet etki alanlarındaki kullanıcı etkinliklerini izleme veya kısıtlama (önizleme).](endpoint-dlp-using.md#scenario-6-monitor-or-restrict-user-activities-on-sensitive-service-domains-preview)
- Windows cihazlarında etkinlikleri denetleme veya kısıtlama

kullanmak `Audit or restrict activities on Windows devices`için **, DLP ayarlarında** ve bunları kullanmak istediğiniz ilkede seçenekleri yapılandırmanız gerekir. Daha fazla bilgi için bkz [. Kısıtlı uygulamalar ve uygulama grupları](dlp-configure-endpoint-settings.md#restricted-apps-and-app-groups) .

Cihazların konumu birçok alt etkinlik (koşul) ve eylem sağlar. Daha fazla bilgi edinmek için bkz [. İzleyebileceğiniz ve üzerinde işlem yapabileceğiniz uç nokta etkinlikleri](endpoint-dlp-learn-about.md#endpoint-activities-you-can-monitor-and-take-action-on).

**Windows cihazlarında etkinlikleri denetle veya kısıtla'yı** seçtiğinizde, kullanıcı etkinliklerini hizmet etki alanına veya tarayıcıya göre kısıtlayabilir ve DLP'nin gerçekleştirilir eylemlerin kapsamını belirleyebilirsiniz:

- Tüm uygulamalar
- Tanımladığınız kısıtlı uygulamaların listesine göre
- Tanımladığınız kısıtlı bir uygulama grubu (önizleme).

##### <a name="service-domain-and-browser-activities"></a>Hizmet etki alanı ve tarayıcı etkinlikleri

**İzin Ver/Engelle bulut hizmeti etki alanlarını** ve **İzin Verilmeyen tarayıcılar** listesini yapılandırdığınızda (bkz [. Hassas verilere yönelik tarayıcı ve etki alanı kısıtlamaları](dlp-configure-endpoint-settings.md#browser-and-domain-restrictions-to-sensitive-data)) ve kullanıcı korumalı bir dosyayı bulut hizmeti etki alanına yüklemeyi veya izin verilmeyen bir tarayıcıdan erişmeyi denediğinde, ilke eylemini , `Block with override`veya `Block` etkinliği olarak `Audit only`yapılandırabilirsiniz.

##### <a name="file-activities-for-all-apps"></a>Tüm uygulamalar için dosya etkinlikleri

**Tüm uygulamalar için Dosya etkinlikleri** seçeneğiyle **, Dosya etkinliklerini kısıtlama** veya **Belirli etkinliklere kısıtlama uygula'yı** seçersiniz. Belirli etkinliklere kısıtlama uygulamayı seçtiğinizde, burada seçtiğiniz eylemler bir kullanıcı DLP korumalı bir öğeye eriştiğinde uygulanır. Bu kullanıcı etkinliklerinde DLP'ye `Audit only`, `Block with override`( `Block` eylemleri) söyleyebilirsiniz:

- **Panoya kopyala**
- **USB çıkarılabilir sürücüye kopyalama** 
- **Ağ paylaşımına kopyalama**
- **Yazdırma**
- **İzin verilmeyen bir Bluetooth uygulamasını kullanarak kopyalama veya taşıma**
- **Uzak masaüstü hizmetleri**


##### <a name="restricted-app-activities"></a>Kısıtlı uygulama etkinlikleri  

Daha önce İzin verilmeyen uygulamalar olarak adlandırılan uygulama listesini, kısıtlama uygulamak istediğiniz Uç Nokta DLP ayarlarında tanımlarsınız. Kullanıcı, listedeki bir uygulamayı kullanarak DLP korumalı bir dosyaya erişmeye çalıştığında, , `Block with override`veya `Block` etkinliği yapabilirsiniz`Audit only`. **Kısıtlı uygulama etkinliklerinde** tanımlanan DLP eylemleri, uygulama kısıtlı uygulama grubunun üyesiyse geçersiz kılınabilir. Ardından kısıtlı uygulama grubunda tanımlanan eylemler uygulanır.

##### <a name="file-activities-for-apps-in-restricted-app-groups-preview"></a>Kısıtlı uygulama gruplarındaki uygulamalar için dosya etkinlikleri (önizleme)

Sınırlı uygulama gruplarınızı Uç Nokta DLP ayarlarında tanımlar ve ilkelerinize kısıtlanmış uygulama grupları eklersiniz. bir ilkeye kısıtlı bir uygulama grubu eklediğinizde, şu seçeneklerden birini belirlemeniz gerekir:

- Dosya etkinliğini kısıtlama
- Tüm etkinliklere kısıtlama uygulama
- Belirli bir etkinliğe kısıtlama uygulama

*Kısıtlamaları uygula* seçeneklerinden birini belirlediğinizde ve kullanıcı kısıtlanmış uygulama grubunda yer alan bir uygulamayı kullanarak DLP korumalı bir dosyaya erişmeye çalıştığında, , `Block with override`veya `Block` etkinliğine göre yapabilirsiniz`Audit only`. Burada tanımladığınız DLP eylemleri **, Uygulamanın tüm uygulamaları için Kısıtlı uygulama etkinlikleri** ve **Dosya etkinlikleri** bölümünde tanımlanan eylemleri geçersiz kılar.

Daha fazla bilgi için bkz [. Kısıtlı uygulamalar ve uygulama grupları](dlp-configure-endpoint-settings.md#restricted-apps-and-app-groups) . 

#### <a name="microsoft-defender-for-cloud-apps-actions"></a>eylemleri Microsoft Defender for Cloud Apps

- Microsoft 365 konumlarındaki içeriğe erişimi kısıtlama veya içeriği şifreleme
- Üçüncü Taraf Uygulamalarını Kısıtlama

#### <a name="on-premises-repositories-actions"></a>Şirket içi depo eylemleri

- Erişimi kısıtlama veya şirket içi dosyaları kaldırma

#### <a name="powerbi-actions"></a>PowerBI eylemleri

- Kullanıcılara e-posta ve ilke ipuçlarıyla bildirme
- Yöneticiye uyarı gönderme

#### <a name="actions-available-when-you-combine-locations"></a>Konumları birleştirdiğinizde kullanılabilen eylemler

İlkenin uygulanacağı Exchange'i ve başka bir tek konumu seçerseniz,

- Microsoft 365 konumlarındaki içeriğe erişimi kısıtlama veya içeriği şifreleme

ve

- Exchange olmayan konum için tüm eylemler

eylemler kullanılabilir olacaktır.

İlkenin uygulanacağı iki veya daha fazla Exchange dışı konum seçerseniz,

- Microsoft 365 konumlarındaki içeriğe erişimi kısıtlama veya içeriği şifreleme

Ve

- Exchange olmayan konumlar için tüm eylemler 

eylemler kullanılabilir olacaktır.

Örneğin, Konum olarak Exchange ve Cihazlar'ı seçerseniz şu eylemler kullanılabilir:

- Microsoft 365 konumlarındaki içeriğe erişimi kısıtlama veya içeriği şifreleme
- Windows cihazlarında etkinlikleri denetleme veya kısıtlama

Cihazlar'ı ve Microsoft Defender for Cloud Apps seçerseniz şu eylemler kullanılabilir:

- Microsoft 365 konumlarındaki içeriğe erişimi kısıtlama veya içeriği şifreleme
- Windows cihazlarında etkinlikleri denetleme veya kısıtlama
- Üçüncü Taraf Uygulamalarını Kısıtlama

Bir eylemin etkili olup olmayacağı, ilke modunu nasıl yapılandırdığınıza bağlıdır. **İlk** olarak test et seçeneğini belirleyerek ilke ipucunu göstererek veya göstermeden ilkeyi test modunda çalıştırmayı seçebilirsiniz. İlkeyi oluşturulduktan bir saat sonra hemen **aç seçeneğini** belirleyerek çalıştırmayı seçebilir veya yalnızca kaydetmeyi ve daha sonra geri dönmek için **Kapalı tut** seçeneğini belirleyebilirsiniz. 


<!-- This section needs to explain that the actions available depend on the locations selected AND that the observed behavior of a policy is produced through an interaction of the configured actions AND the configured status (off, test, apply) of a policy. It will detail the purpose of each of the available actions and the location/desired outcome interaction and provide examples eg. how to use the Restrict Third Party apps in the context of a policy that is applied to endpoints so that users can't use a upload content to a third party site or the interaction of on-premises scanner with restrict access or remove on-premises files.  Also what happens when I select multiple locations? provide abundant examples for most common scenarios-->


### <a name="user-notifications-and-policy-tips"></a>Kullanıcı bildirimleri ve ilke ipuçları

<!--This section introduces the business need for user notifications, what they are, their benefit, how to use them, how to customize them, and links out to 

- https://docs.microsoft.com/en-us/microsoft-365/compliance/use-notifications-and-policy-tips?view=o365-worldwide
- https://docs.microsoft.com/en-us/microsoft-365/compliance/dlp-policy-tips-reference?view=o365-worldwide

for where they are used/expected behavior-->

<!--You can use notifications and overrides to educate your users about DLP policies and help them remain compliant without blocking their work. For example, if a user tries to share a document containing sensitive information, a DLP policy can both send them an email notification and show them a policy tip in the context of the document library that allows them to override the policy if they have a business justification.-->

Kullanıcı, bir kuralın koşullarını ve özel durumlarını karşılayan bir bağlamda hassas bir öğe üzerinde eylem gerçekleştirmeye çalıştığında, kullanıcı bildirim e-postaları ve bağlam ilkesi ipucu açılır pencereleri aracılığıyla bu öğe hakkında bilgi edinebilirsiniz. Bu bildirimler, farkındalığı artırdığından ve kişilerin kuruluşunuzun DLP ilkeleri hakkında eğitilmesine yardımcı olduğundan yararlıdır.

Örneğin, kişisel bilgileri (PII) içeren ve bir konukla paylaşılan OneDrive İş bir sitedeki Excel çalışma kitabı gibi içerikler.

![İleti çubuğu, Excel 2016 ilke ipucunu gösterir](../media/7002ff54-1656-4a6c-993f-37427d6508c8.png)

> [!IMPORTANT]
> - Bildirim e-postaları korumasız gönderilir.
> - Email bildirimleri yalnızca Microsoft 365 hizmetleri için desteklenir.

#### <a name="email-notifications-support-by-selected-location"></a>Seçilen konuma göre bildirim desteği Email

|Seçili konum  |desteklenen Email bildirimleri  |
|---------|---------|
|Aygıtları     |- Desteklenmez         |
|Exchange + Cihazlar     |- Exchange için desteklenir </br>- Cihazlar için desteklenmez  |
|Exchange    |- Desteklenir        |
|SharePoint + Cihazlar  |- SharePoint için desteklenir </br>- Cihazlar için desteklenmez         |
|SharePoint    |- Desteklenir |
|Exchange + SharePoint    |- Exchange için desteklenir </br>- SharePoint için desteklenir  |
|Cihazlar + SharePoint + Exchange    |- Cihazlar için desteklenmez </br>- SharePoint için desteklenir </br> Exchange için desteklenir |
|Teams    |- Desteklenmez |
|OneDrive İş   |- Desteklenir         |
|OneDrive İş + Cihazlar     |- OneDrive İş için desteklenir </br>- Cihazlar için desteklenmez         |
|Power-BI|- Desteklenmez|
|Bulut Uygulamaları için Microsoft Defender|- Desteklenmez|
|Şirket içi depolar|- Desteklenmez|

Ayrıca kişilere [ilkeyi geçersiz kılma](#user-overrides) seçeneği de verebilirsiniz; böylece geçerli bir iş ihtiyaçları varsa veya ilke yanlış pozitif algılarsa engellenmez.

Kullanıcı bildirimleri ve ilke ipuçları yapılandırma seçenekleri, seçtiğiniz izleme konumlarına bağlı olarak değişir. Şunu seçtiyseniz:

- Exchange
- SharePoint
- OneDrive
- Teams Sohbeti ve Kanalı
- Bulut Uygulamaları için Defender





Çeşitli Microsoft uygulamaları için kullanıcı bildirimlerini etkinleştirebilir/devre dışı bırakabilirsiniz, bkz. [Veri Kaybı Önleme ilkesi ipuçları başvurusu](dlp-policy-tips-reference.md#data-loss-prevention-policy-tips-reference)

- İlke ipucuyla bildirimleri etkinleştirebilir/devre dışı bırakabilirsiniz.
    - veya içeriğini gönderen, paylaşan veya son değiştiren kullanıcıya e-posta bildirimleri gönderme
    - belirli kişilere bildirme

ve e-posta metnini, konusunu ve ilke ipucu metnini özelleştirin.

![Exchange, SharePoint, OneDrive, Teams Sohbet ve Kanal ile Cloud Apps için Defender için kullanılabilen kullanıcı bildirimi ve ilke ipucu yapılandırma seçenekleri](../media/dlp-user-notification-non-devices.png)

Yalnızca cihazlar'ı seçtiyseniz Exchange, SharePoint, OneDrive, Teams Sohbet ve Kanal ile Cloud Apps için Defender'da kullanılabilen tüm seçeneklerin yanı sıra Windows 10 cihazda görünen bildirim başlığını ve içeriği özelleştirme seçeneğini de alırsınız.

![Cihazlar için kullanılabilen kullanıcı bildirimi ve ilke ipucu yapılandırma seçenekleri](../media/dlp-user-notification-devices.png)  

Bu parametreleri kullanarak metnin başlığını ve gövdesini özelleştirebilirsiniz. Gövde metni şunları destekler:

|Ortak ad  |Parametre  |Örnek
|---------|---------|---------|
|dosya adı     |%%FileName%% | Contoso belge 1 |
|işlem adı     |%%ProcessName%% | Word |
|ilke adı     |%%PolicyName%%| Contoso çok gizli |
|Eylem | %%AppliedActions%% | panodaki belge içeriğini başka bir uygulamaya yapıştırma |

**%%AppliedActions%%** bu değerleri ileti gövdesiyle değiştirmektedir:


|eylem ortak adı |%%AppliedActions%% parametresi için yerine değer girildi |
|---------|---------|
|kaldırılabilir depolamaya kopyalama    |*çıkarılabilir depolama birimine yazma*         |
|ağ paylaşımına kopyalama     |*ağ paylaşımına yazma*         |
|Yazdırma     |*Baskı*         |
|panodan yapıştırma  |*panodan yapıştırma*         |
|bluetooth üzerinden kopyalama   |*Bluetooth üzerinden aktarma*         |
|izin verilmeyen bir uygulamayla açma     |*bu uygulamayla açma*         |
|uzak masaüstüne kopyalama (RDP)     |*uzak masaüstüne aktarma*         |
|izin verilmeyen bir web sitesine yükleme     |*bu siteye yükleniyor*         |
|öğeye izin verilmeyen bir tarayıcı üzerinden erişme     |*bu tarayıcıyla açma*         |

Bu özelleştirilmiş metni kullanma

*%%AppliedActions%% %%ProcessName%% aracılığıyla %%FileName%% dosya adı kuruluşunuz tarafından kullanılamaz. %%PolicyName%% ilkesini atlamak istiyorsanız 'İzin Ver' seçeneğine tıklayın* 

bu metni özelleştirilmiş bildirimde üretir:

*panodan yapıştırma Dosya Adı: WINWORD.EXE aracılığıyla Contoso doc 1'e kuruluşunuz izin vermez. Contoso son derece gizli ilkesini atlamak istiyorsanız 'İzin Ver' düğmesine tıklayın*
 

> [!NOTE]
> Şirket içi konumu için kullanıcı bildirimleri ve ilke ipuçları kullanılamıyor

> [!NOTE]
> Yalnızca en yüksek önceliğe ve en kısıtlayıcı kurala ait ilke ipucu gösterilir. Örneğin, içeriğe erişimi engelleyen bir kuraldan gelen ilke ipucu, yalnızca bildirim gönderen bir kuraldan gelen ilke ipucu üzerinden gösterilir. Bu, kişilerin ilke ipuçlarının art arda görülmesini önler.

Bildirim ve ipucu metnini özelleştirme de dahil olmak üzere kullanıcı bildirimi ve ilke ipucu yapılandırması ve kullanımı hakkında daha fazla bilgi edinmek için bkz. 
- [E-posta bildirimleri gönderin ve DLP ilkeleri için ilke ipuçlarını gösterin](use-notifications-and-policy-tips.md#send-email-notifications-and-show-policy-tips-for-dlp-policies).
  
<!--The email can notify the person who sent, shared, or last modified the content and, for site content, the primary site collection administrator and document owner. In addition, you can add or remove whomever you choose from the email notification.
  
In addition to sending an email notification, a user notification displays a policy tip:
  
- In Outlook and Outlook on the web.
    
- For the document on a SharePoint Online or OneDrive for Business site.
    
- In Excel, PowerPoint, and Word, when the document is stored on a site included in a DLP policy.
    
The email notification and policy tip explain why content conflicts with a DLP policy. If you choose, the email notification and policy tip can allow users to override a rule by reporting a false positive or providing a business justification. This can help you educate users about your DLP policies and enforce them without preventing people from doing their work. Information about overrides and false positives is also logged for reporting (see below about the DLP reports) and included in the incident reports (next section), so that the compliance officer can regularly review this information.
  
Here's what a policy tip looks like in a OneDrive for Business account.
  
![Policy tip for a document in a OneDrive account](../media/f9834d35-94f0-4511-8555-0fe69855ce6d.png)

 To learn more about user notifications and policy tips in DLP policies, see [Use notifications and policy tips](use-notifications-and-policy-tips.md).

> [!NOTE]
> The default behavior of a DLP policy, when there is no alert configured, is not to alert or trigger. This applies only to default information types. For custom information types, the system will alert even if there is no action defined in the policy.
-->

#### <a name="blocking-and-notifications-in-sharepoint-online-and-onedrive-for-business"></a>SharePoint Online ve OneDrive İş'da engelleme ve bildirimler

Bu tabloda, Kapsamı SharePoint Online ve OneDrive İş olan ilkeler için DLP engelleme ve bildirim davranışı gösterilir.

|Koşul -ları  |Eylemler yapılandırması |Kullanıcı Bildirimi yapılandırması|Olay Raporları yapılandırması |Engelleme ve Bildirim davranışı|
|---------|---------|---------|---------|---------|
|- **İçerik Microsoft 365'ten paylaşılır** </br>- **kuruluşum dışındaki kişilerle**     |Hiçbir eylem yapılandırılmadı         |- **Kullanıcı bildirimleri** **Açık** olarak ayarlandı </br>- **İlke ipucu seçiliyken Office 365 hizmetindeki kullanıcılara bildirme** </br>- **İçeriği gönderen, paylaşan veya en son değiştiren kullanıcıyı bilgilendirin**         |- **Kural eşleşmesi açık olarak ayarlandığında yöneticilere uyarı gönderme**  </br>- **Bir etkinlik, açık olarak ayarlanan kuralla her eşleştiğinde uyarı gönder**  </br>- **İlke eşleşmesi Açık olarak ayarlandığında sizi bilgilendirmek için e-posta olay raporlarını kullanın**          |- Bildirimler yalnızca bir dosya bir dış kullanıcıyla paylaşıldığında ve bir dış kullanıcı dosyaya eriştiğinde gönderilir.  |
|- **İçerik Microsoft 365'ten paylaşılır** </br>- **yalnızca kuruluşumdaki kişilerle**        | Hiçbir eylem yapılandırılmadı         |-  **Kullanıcı bildirimleri** **Açık** olarak ayarlandı   </br>- **İlke ipucu seçiliyken Office 365 hizmetindeki kullanıcılara bildirme**  </br>- **İçeriği gönderen, paylaşan veya en son değiştiren kullanıcıyı bilgilendirin**    |  - **Kural eşleşmesi açık olarak ayarlandığında yöneticilere uyarı gönderme**  </br>- **Bir etkinlik kuralla her eşleştiğinde uyarı gönder** seçili durumda </br>- **İlke eşleşmesi Açık olarak ayarlandığında sizi bilgilendirmek için e-posta olay raporlarını kullanın**        |- Bir dosya karşıya yüklendiğinde bildirimler gönderilir |
|- **İçerik Microsoft 365'ten paylaşılır** </br>- **kuruluşum dışındaki kişilerle**    | - **Microsoft 365 konumlarındaki içeriği kısıtlama veya içeriği şifreleme** seçili </br>- **Kullanıcıların e-posta almasını veya paylaşılan SharePoint, OneDrive ve Teams dosyalarına erişmesini engelle** seçili </br>- **Yalnızca kuruluşunuz dışındaki kişilerin seçilmesini engelle**          |- **Kullanıcı bildirimleri** **Açık** olarak ayarlandı </br>- **İlke ipucu seçiliyken Office 365 hizmetindeki kullanıcılara bildirme** </br>- **İçeriği gönderen, paylaşan veya en son değiştiren kullanıcıyı bilgilendirin**  |  - **Kural eşleşmesi açık olarak ayarlandığında yöneticilere uyarı gönderme**  </br>- **Bir etkinlik kuralla her eşleştiğinde uyarı gönder** seçili durumda </br>- **İlke eşleşmesi Açık olarak ayarlandığında sizi bilgilendirmek için e-posta olay raporlarını kullanın**              | - Karşıya yüklenir yüklenmez hassas bir dosyaya erişim engellenir </br>- İçerik Microsoft 365'ten kuruluşum dışındaki kişilerle paylaşıldığında gönderilen bildirimler         |
|- **İçerik Microsoft 365'ten paylaşılır** </br>- **kuruluşum dışındaki kişilerle** |  - **Microsoft 365 konumlarındaki içeriği kısıtlama veya içeriği şifreleme** seçili </br>- **Kullanıcıların e-posta almasını veya paylaşılan SharePoint, OneDrive ve Teams dosyalarına erişmesini engelle** seçili </br>- **Herkesin** seçilmesini engelle        | - **Kullanıcı bildirimleri** **Açık** olarak ayarlandı </br>- **İlke ipucu seçiliyken Office 365 hizmetindeki kullanıcılara bildirme** </br>- **İçeriği gönderen, paylaşan veya en son değiştiren kullanıcıyı bilgilendirin**         | - **Kural eşleşmesi açık olarak ayarlandığında yöneticilere uyarı gönderme**  </br>- **Bir etkinlik kuralla her eşleştiğinde uyarı gönder** seçili durumda </br>- **İlke eşleşmesi Açık olarak ayarlandığında sizi bilgilendirmek için e-posta olay raporlarını kullanın**         |Bir dosya bir dış kullanıcıyla paylaşıldığında ve bir dış kullanıcı bu dosyaya eriştiğinde bildirimler gönderilir.         |
|- **İçerik Microsoft 365'ten paylaşılır** </br>- **kuruluşum dışındaki kişilerle**     |- **Microsoft 365 konumlarındaki içeriği kısıtlama veya içeriği şifreleme** seçili </br>- **Yalnızca "Bağlantıya sahip herkes" seçeneğiyle içeriğe erişim izni verilen kişileri engelle** seçeneği belirlenir.         |  - **Kullanıcı bildirimleri** **Açık** olarak ayarlandı </br>- **Office 365 hizmetindeki kullanıcılara bir ilke ipucu** seçildiğini bildirin.  </br>- **İçeriği gönderen, paylaşan veya en son değiştiren kullanıcıyı bilgilendirin**     |- **Kural eşleşmesi açık olarak ayarlandığında yöneticilere uyarı gönderme**    </br>- **Bir etkinlik kuralla her eşleştiğinde uyarı gönder** seçili durumda </br>- **İlke eşleşmesi Açık olarak ayarlandığında sizi bilgilendirmek için e-posta olay raporlarını kullanın**        |Bir dosya karşıya yüklenir yüklenmez bildirimler gönderilir         |


### <a name="user-overrides"></a>Kullanıcı geçersiz kılmaları

**Kullanıcı geçersiz kılmalarının** amacı, kullanıcılara, çalışmalarına devam edebilmeleri için Exchange, SharePoint, OneDrive veya Teams'deki hassas öğeler üzerinde eylemleri engelleyen gerekçeyle, DLP ilkesini atlayacak bir yol sunmaktır. Kullanıcı geçersiz kılmaları yalnızca **Office 365 hizmetlerindeki kullanıcılara bir ilke ipucuyla bildir** seçeneği etkinleştirildiğinde etkinleştirilir, bu nedenle kullanıcı geçersiz kılmaları Bildirimler ve İlke ipuçlarıyla el ele gider. 

![DLP ilkesi için kullanıcı geçersiz kılma seçenekleri](../media/dlp-user-overrides.png)

> [!NOTE]
> Şirket içi depolar konumu için kullanıcı geçersiz kılmaları kullanılamaz.

Genellikle, kuruluşunuz bir ilkeyi ilk dağıttığında kullanıcı geçersiz kılmaları yararlıdır. Geçersiz kılma gerekçelerinden ve hatalı pozitif sonuçların belirlenmesinden elde ettiğiniz geri bildirim, ilkenin ayarlanmasına yardımcı olur. 

<!-- This section covers what they are and how to best use them in conjunction with Test/Turn it on right away and link out to where to find the business justification for the override (DLP reports?  https://docs.microsoft.com/en-us/microsoft-365/compliance/view-the-dlp-reports?view=o365-worldwide)  https://docs.microsoft.com/en-us/microsoft-365/compliance/view-the-dlp-reports?view=o365-worldwide#view-the-justification-submitted-by-a-user-for-an-override-->

- En kısıtlayıcı kuraldaki ilke ipuçları kişilerin kuralı geçersiz kılmasına izin verirse, bu kuralın geçersiz kılınmış olması, içeriğin eşleştirilen diğer kuralları da geçersiz kılar.
 
<!--![User notifications and user overrides sections of DLP rule editor](../media/37b560d4-6e4e-489e-9134-d4b9daf60296.png)-->
 
Kullanıcı geçersiz kılmaları hakkında daha fazla bilgi edinmek için bkz:

- [Geçersiz kılma için kullanıcı tarafından gönderilen gerekçeyi görüntüleme](view-the-dlp-reports.md#view-the-justification-submitted-by-a-user-for-an-override)

### <a name="incident-reports"></a>Olay raporları

<!--DLP interacts with other M365 information protection services, like IR. Link this to a process outline for triaging/managing/resolving DLP incidents


https://docs.microsoft.com/en-us/microsoft-365/compliance/view-the-dlp-reports?view=o365-worldwide
https://docs.microsoft.com/en-us/microsoft-365/compliance/dlp-configure-view-alerts-policies?view=o365-worldwide-->

Bir kural eşleştirildiğinde, uyumluluk yöneticinize (veya seçtiğiniz kişilere) olayın ayrıntılarını içeren bir olay raporu gönderebilirsiniz. Rapor, eşleşen öğe, kuralla eşleşen gerçek içerik ve içeriği son değiştiren kişinin adı hakkında bilgi içerir. E-posta iletileri için rapor, DLP ilkesiyle eşleşen özgün iletiyi ek olarak da içerir.

DLP, olay bilgilerini [insider risk yönetimi](insider-risk-management.md) gibi diğer Microsoft Purview bilgi koruma hizmetlerine iletir. Olay bilgilerini insider risk yönetimine almak için **Olay raporları** önem düzeyini **Yüksek** olarak ayarlamanız gerekir.

<!--![Page for configuring incident reports](../media/31c6da0e-981c-415e-91bf-d94ca391a893.png)-->

Bir etkinlik bir kuralla her eşleştiğinde uyarılar gönderilebilir. Bu uyarılar gürültülü olabilir veya belirli bir süre içindeki eşleşme sayısına veya öğe hacmine göre daha az uyarıya toplanabilir.

![bir kural her eşleştiğinde veya zaman içinde daha az rapora toplendiğinde uyarı gönderme](../media/dlp-incident-reports-aggregation.png)

DLP, e-postayı SharePoint Online'dan veya OneDrive İş öğeden farklı tarar. SharePoint Online'da ve OneDrive İş, DLP hem mevcut öğeleri hem de yeni öğeleri tarar ve bir eşleşme bulunduğunda bir olay raporu oluşturur. Exchange Online'da DLP yalnızca yeni e-posta iletilerini tarar ve ilke eşleşmesi varsa bir rapor oluşturur. DLP, posta kutusunda veya arşivde depolanan önceden var olan e-posta öğelerini ***taramaz veya eşleştirmez*** .

### <a name="additional-options"></a>Ek seçenekler

bir ilkede birden çok kuralınız varsa, düzenlemekte olduğunuz kuralla bir eşleşme olup olmadığını denetlemek ve kuralın değerlendirilme önceliğini ayarlamak için **Ek seçenekleri** kullanabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

- [Veri kaybı önleme hakkında daha fazla bilgi edinme](dlp-learn-about-dlp.md#learn-about-data-loss-prevention)
- [Veri kaybı önlemeyi planlama (DLP)](dlp-overview-plan-for-dlp.md#plan-for-data-loss-prevention-dlp)
- [Bir şablondan DLP ilkesi oluşturma](create-a-dlp-policy-from-a-template.md#create-a-dlp-policy-from-a-template)
- [Bir DLP ilkesi oluşturma, test etme ve ayarlama](create-test-tune-dlp-policy.md#create-test-and-tune-a-dlp-policy)
