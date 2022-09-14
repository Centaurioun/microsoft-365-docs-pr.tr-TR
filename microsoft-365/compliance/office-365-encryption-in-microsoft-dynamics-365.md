---
title: Microsoft Dynamics 365'te şifreleme
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: ''
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: Microsoft'un microsoft veritabanında beklerken ve aktarım sırasında Microsoft Dynamics 365'teki müşteri verilerini korumak için şifreleme teknolojisini nasıl kullandığını öğrenin.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ba3dbef73b7674364f19e83befdbb8cdfe417ad6
ms.sourcegitcommit: 437461fa1d38ff9bb95dd8a1c5f0b94e8111ada2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67678811"
---
# <a name="encryption-in-microsoft-dynamics-365"></a>Microsoft Dynamics 365'te şifreleme

Microsoft, Dynamics 365'teki müşteri verilerini bir Microsoft veri merkezinde beklerken ve kullanıcı cihazları ile veri merkezlerimiz arasında aktarım sırasında korumak için şifreleme teknolojisini kullanır. Müşteriler ve Microsoft veri merkezleri arasında kurulan bağlantılar şifrelenir ve tüm genel uç noktaların güvenliği endüstri standardı TLS kullanılarak sağlanır. TLS, masaüstü bilgisayarlar ve veri merkezleri arasında veri gizliliği ve bütünlüğü sağlamaya yardımcı olmak için güvenlik açısından gelişmiş bir tarayıcıdan sunucuya bağlantı kurar. Veri şifreleme etkinleştirildikten sonra kapatılamaz. Daha fazla bilgi için bkz [. Alan düzeyinde veri şifrelemesi](/previous-versions/dynamicscrm-2016/developers-guide/dn481562(v=crm.8)).

Dynamics 365, kullanıcı adları ve e-posta parolaları gibi hassas bilgiler içeren bir dizi varsayılan varlık özniteliği için standart Microsoft SQL Server hücre düzeyinde şifreleme kullanır. Bu özellik, kuruluşların FIPS 140-2 ile ilişkili uyumluluk gereksinimlerini karşılamaya yardımcı olabilir. Alan düzeyinde veri şifrelemesi, dynamics 365 örneği ile e-posta hizmeti arasında tümleştirmeyi etkinleştirmek için kullanıcı adlarını ve parolaları depolaması gereken [Microsoft Dynamics CRM Email Yönlendiricisi'ni](/previous-versions/dynamicscrm-2016/administering-dynamics-365/hh699800(v=crm.8)) kullanan senaryolarda özellikle önemlidir.

Dynamics 365'in tüm örnekleri, diske yazıldığında (bekleyen) verilerin gerçek zamanlı şifrelemesini gerçekleştirmek için [Microsoft SQL Server Saydam Veri Şifrelemesi'ni](/sql/relational-databases/security/encryption/transparent-data-encryption) (TDE) kullanır. TDE SQL Server, Azure SQL Veritabanı ve Azure SQL Data Warehouse veri dosyalarını şifreler. Varsayılan olarak, Microsoft Dynamics 365 örnekleriniz için veritabanı şifreleme anahtarlarını depolar ve yönetir. (Dynamics 365 for Financials tarafından kullanılan anahtarlar .NET Framework Veri Koruma API'si tarafından oluşturulur.)

Dynamics 365 Yönetim Merkezi'ndeki anahtarları yönetme özelliği, yöneticilere Dynamics 365 örnekleriyle ilişkili veritabanı şifreleme anahtarlarını kendi kendine yönetme olanağı sağlar. (Kendi kendine yönetilen veritabanı şifreleme anahtarları yalnızca Microsoft Dynamics 365 için Ocak 2017 güncelleştirmesinde kullanılabilir ve sonraki sürümlerde kullanılamayabilir. Daha fazla bilgi için bkz [. Dynamics 365 (çevrimiçi) örneğinizin şifreleme anahtarlarını yönetme](/dynamics365/customer-engagement/admin/manage-encryption-keys-instance).) Anahtar yönetimi özelliği, HSM'de depolananlar gibi hem PFX hem de BYOK şifreleme anahtarı dosyalarını destekler. (İnternet üzerinden HSM korumalı anahtar oluşturma ve aktarma hakkında daha fazla bilgi için bkz. [Azure Key Vault için HSM korumalı anahtar oluşturma ve aktarma](/azure/key-vault/key-vault-hsm-protected-keys).)

Şifreleme anahtarını karşıya yükleme seçeneğini kullanmak için hem genel hem de özel şifreleme anahtarı gerekir.

Anahtar yönetimi özelliği, şifreleme anahtarlarını güvenli bir şekilde depolamak için Azure Key Vault kullanarak şifreleme anahtarı yönetiminin karmaşıklığını azaltır. Azure Key Vault, bulut uygulamaları ve hizmetleri tarafından kullanılan şifreleme anahtarlarının ve gizli dizilerin korunmasına yardımcı olur. Anahtar yönetimi özelliği, Azure Key Vault aboneliğinizin olmasını gerektirmez ve çoğu durumda kasa içinde Dynamics 365 için kullanılan şifreleme anahtarlarına erişmeniz gerekmez.
