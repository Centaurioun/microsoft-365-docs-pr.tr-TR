---
title: bağlantı dizesi varlık tanımını SQL Server
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
- M365-security-compliance
hideEdit: true
feedback_system: None
recommendations: false
description: bağlantı dizesine duyarlı bilgi türü varlık tanımını SQL Server.
ms.openlocfilehash: 503b2bae244cec8de5da29228f6517433a162ca1
ms.sourcegitcommit: 5aed330d8af523f0dffe5e392f1c79f047e38172
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/21/2022
ms.locfileid: "66948738"
---
# <a name="sql-server-connection-string"></a>SQL Server bağlantı dizesi

## <a name="format"></a>Biçim

, , `User ID``uid`veya `UserId` dizesini `User Id`ve ardından aşağıdaki desende özetlenen karakterleri ve dizeleri ekleyin.

## <a name="pattern"></a>Desen

- , , `User ID``uid`veya dizesi `User Id``UserId`
- 1-200 arasında küçük veya büyük harf, rakam, simge, özel karakter veya boşluk birleşimi
- dize `Password` veya `pwd` burada `pwd` küçük harf bulunmaz
- eşittir işareti (=)
- dolar işareti ($), yüzde simgesi (%), simgeden büyük (>), simge (@), tırnak işareti ("), noktalı virgül (;), sol ayraç([) veya sol köşeli ayraç ({) olmayan herhangi bir karakter
- noktalı virgül (;), eğik çizgi (/) veya tırnak işareti (") olmayan 7-128 karakterden oluşan herhangi bir birleşim
- noktalı virgül (;) veya tırnak işareti (")

## <a name="checksum"></a>Sağlama toplamı

Hayır

## <a name="definition"></a>Tanım

DLP ilkesi, 300 karaktere yakın olduğunda bu tür hassas bilgileri algılamıştır:

- Normal ifade `CEP_Regex_SQLServerConnectionString` , desenle eşleşen içeriği bulur.
- anahtar `CEP_GlobalFilter` sözcüğü bulunamadı.
- Normal ifade `CEP_PasswordPlaceHolder` , desenle eşleşen içeriği bulmaz.
- Normal ifade `CEP_CommonExampleKeywords` , desenle eşleşen içeriği bulmaz.

```sql
<!---SQL Server Connection String>
<Entity id="e76b6205-d3cb-46f2-bd63-c90153f2f97d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_SQLServerConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_GlobalFilter" />
            <Match idRef="CEP_PasswordPlaceHolder" />
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
    </Pattern>
</Entity>
```

## <a name="keywords"></a>Anahtar Sözcükler

### <a name="cep_globalfilter"></a>CEP_GlobalFilter

- bazı parolalar
- somepassword
- secretPassword
- Örnek

### <a name="cep_passwordplaceholder"></a>CEP_PasswordPlaceHolder

Bu hassas bilgi türü, bu anahtar sözcükleri anahtar sözcük listesi değil normal bir ifade kullanarak tanımlar.

- `Password` veya `pwd` ardından 0-2 boşluk, eşittir işareti (=), 0-2 boşluk ve yıldız (*) -OR-
- `Password` veya `pwd` ardından:
    - Eşittir işareti (=)
    - Küçüktür simgesi (<)
    - Büyük veya küçük harf, basamak, yıldız işareti (*), kısa çizgi (-), altı çizili (_) veya boşluk karakteri olan 1-200 karakterden oluşan herhangi bir birleşim
    - Büyüktür simgesi (>)

### <a name="cep_commonexamplekeywords"></a>CEP_CommonExampleKeywords

Bu hassas bilgi türü, bu anahtar sözcükleri anahtar sözcük listesi değil normal bir ifade kullanarak tanımlar.

- Contoso
- Fabrikam
- Northwind
- Sandbox
- Onebox
- Localhost
- 127.0.0.1
- testacs.<!--no-hyperlink-->Com
- s-int.<!--no-hyperlink-->Net