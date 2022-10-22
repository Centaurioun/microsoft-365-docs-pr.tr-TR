---
title: Eğitilebilir sınıflandırıcı tanımları
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- purview-compliance
- tier2
- m365solution-mip
- m365initiative-compliance
ms.custom: admindeeplinkMAC
search.appverid:
- MOE150
- MET150
description: Bu, hassas bilgileri bulmak için tüm eğitilebilir sınıflandırıcıların, tanımlarının ve aradıkları tüm dosya türlerinin listesidir
ms.openlocfilehash: d62e3e9b32a7ab977c0b052725b472ac326967f3
ms.sourcegitcommit: a250d043a2e42ecbc7b86147468d1660af5a6ba7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2022
ms.locfileid: "68673161"
---
# <a name="trainable-classifiers-definitions"></a>Eğitilebilir sınıflandırıcı tanımları

Microsoft Purview, önceden eğitilmiş birden çok sınıflandırıcı ile birlikte gelir.  Microsoft Purview uyumluluk portalı **Veri sınıflandırması** \> **Eğitilebilir sınıflandırıcılar** görünümünde durumuyla `Ready to use`birlikte görünürler\>.


- **Yetişkin, müstehcen ve gory**: Bu tür görüntüleri algılar. Görüntülerin boyutu 50 kilobayt (KB) ile 4 megabayt (MB) arasında olmalı ve yükseklik x genişlik boyutlarında 50 x 50 pikselden büyük olmalıdır. Tarama ve algılama, Exchange Online e-posta iletileri ile Microsoft Teams kanalları ve sohbetleri için desteklenir. .jpeg, .png, .gif ve .bmp dosyalarındaki içeriği algılar.

- **Sözleşmeler**: İfşa etmeme sözleşmeleri, iş beyanları, kredi ve kira sözleşmeleri, istihdam ve rekabet dışı sözleşmeler gibi yasal sözleşmelerle ilgili içeriği algılar. .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt, .one, .msg, .eml dosyalarındaki içeriği algılar.

- **Banka Ekstresi (önizleme)**: Belirli bir süre içinde hesap bilgileri, depozitolar, para çekme işlemleri, hesap bakiyesi, tahakkuk eden faiz ve banka ücretleri dahil olmak üzere bir banka hesabının finansal işlemini içeren öğeleri algılar. .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt dosyalarındaki içeriği algılar.

- **Bütçe (önizleme)**: Bir kuruluşun gelir ve giderleri de dahil olmak üzere bütçe belgelerini, bütçe tahminlerini ve geçerli bütçe deyimlerini algılar. .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt, .one, .eml, .pptx, .pptm, .ppt, .potx, .potm, .pot, .ppsx, .ppsm, .ppam, .ppa, .xlsx, .xlsm, .xlsb, .xls, .csv, .xltx, .xltm, .xltm, .xltm, .xlam, .xla dosyaları.

- **İş Planı (önizleme):** İş fırsatı, sonuçları elde etme planı, pazar çalışması ve rakip analizi dahil olmak üzere bir iş planının bileşenlerini algılar. .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt, .one, .eml, .pptx, .pptm, .ppt, .potx, .potm, .pot, .ppsx, .ppsm, .ppsm, .ppam, .ppa dosyalarındaki içeriği algılar.

- **İnşaat belirtimleri (önizleme)**: Fabrikalar, tesisler, ticari ofisler, havaalanları, yollar gibi ticari ve endüstriyel projeler için inşaat belirtimlerini algılar. Kalite, miktar, yapı malzemesi türleri, süreçler vb. ile ilgili yönergeleri yakalar. .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt, .one, .msg, .eml, .pptx, .pptm, .ppt, .potx, .potm, .pot, .ppsx, .ppsm, .ppss, .ppam, .ppa dosyalarındaki içeriği algılar.

- **Kurumsal Sabotaj (önizleme)**: Şirket varlıklarına veya mülklerine zarar verme veya bunları yok etme eylemlerinden bahsedebilecek iletileri algılar. Bu sınıflandırıcı, müşterilerin NERC Kritik Altyapı Koruması standartları gibi mevzuat uyumluluğu yükümlülüklerini yönetmelerine veya Washington eyaletinde bölüm 9.05 RCW gibi eyalet düzenlemelerine göre durumlarını yönetmelerine yardımcı olabilir. .msg, .docx, .pdf, .txt, .rtf, .jpeg, .jpg, .png, .gif, .bmp, .svg dosyalarındaki içeriği algılar.  
> [!IMPORTANT] 
> Önizleme aşamasındayken, bu sınıflandırıcı bilinen bir sorun nedeniyle büyük hacimli toplu gönderen/bülten içeriği yakalayabilir. Önizleme aşamasındayken, büyük hacimli toplu gönderen/bülten içeriğini ele almak **için, İleti dışlanması gereken etki alanlarının listesiyle bu etki alanlarının hiçbirine gönderilmez koşulunu** ekleyebilirsiniz. 

- **Müşteri şikayetleri**: Müşteri şikayetleri sınıflandırıcısı, kuruluşunuzun ürünleri veya hizmetleri hakkında yapılan geri bildirimleri ve şikayetleri algılar. Bu sınıflandırıcı, Tüketici Finansal Koruma Bürosu ve Gıda ve İlaç Yönetimi gereksinimleri gibi şikayetlerin tespiti ve önceliklendirmesi ile ilgili mevzuat gereksinimlerini karşılamanıza yardımcı olabilir. İletişim Uyumluluğu için .msg ve .eml dosyalarındaki içeriği algılar. Microsoft Purview Bilgi Koruması hizmetlerinin geri kalanında .docx, .pdf, .txt, .rtf, .jpg, .jpeg, .png, .gif, .bmp, .svg dosyalarındaki içeriği algılar.

- **Ayrımcılık**: Açık ayrımcı dili algılar ve diğer topluluklarla karşılaştırıldığında Afrikalı Amerikalı/Siyah topluluklara karşı ayrımcı dile duyarlıdır. Bu, İletişim Uyumluluğu için geçerlidir; metin tabanlı bir sınıflandırıcıdır.

- **Çalışan disiplini eylem dosyaları (önizleme): Çalışanların** yanlış işlemesine, kural ihlaline veya düşük performansa yanıt olarak bir azarlama veya düzeltici eylem de dahil olmak üzere disiplin eylemiyle ilgili dosyaları algılar. .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt, .one, .msg, .eml dosyalarındaki içeriği algılar.

- **Çalışan Sigortası dosyaları (önizleme):Çalışan** sağlık sigortası ve iş yeri engellilik sigortası ile ilgili belgeleri algılar. .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt, .one, .msg, .eml, .pptx, .pptm, .ppt, .potx, .potm, .pot, .ppsx, .ppsm, .ppss, .ppam, .ppa dosyalarındaki içeriği algılar.

- **İstihdam Sözleşmesi (önizleme):** Başlangıç tarihi, maaş, tazminat, iş görevleri gibi ayrıntıları içeren iş sözleşmesini algılar. .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt dosyalarındaki içeriği algılar.

- **Finans**: Kurumsal finans, muhasebe, ekonomi, bankacılık ve yatırım kategorilerindeki içeriği algılar. .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt, .one, .msg, .eml, .pptx, .pptm, .ppt, .potx, .potm, .pot, .ppsx, .ppsm, .ppam, .ppa, .xlsx, .xlsm, .xlsb, .xls, .csv, .xltx, .xltm, .xltm, .xlam, .xla dosyaları.

- **Finansal Denetim Raporları (önizleme):** Bir kuruluşta hem dış hem de iç denetimle ilgili finansal denetimle ilgili dosyaları, belgeleri ve raporları algılar. .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt, .one, .msg, .eml dosyalarındaki içeriği algılar.

- **Finansal Tablo (önizleme)**: Gelir tablosu, bilanço, nakit akışı tablosu, özkaynaktaki değişikliklerin bildirimi gibi finansal tabloları algılar. .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt, .xlsx, .xlsm, .xlsb, .xls, .csv, .xltx, .xltm, .xltm, .xltm, .xlam, .xla dosyalarındaki içeriği algılar.

- **Hediyeler & eğlence (önizleme)**: Hizmet karşılığında hediye veya eğlence alışverişi önerebilecek iletileri algılar ve bu da rüşvetle ilgili düzenlemeleri ihlal eder. Bu sınıflandırıcı, müşterilerin Yabancı Bozuk Uygulamalar Yasası (FCPA), Birleşik Krallık Rüşvet Yasası ve FINRA Kural 2320 gibi mevzuat uyumluluğu yükümlülüklerini yönetmelerine yardımcı olabilir. .msg, .docx, .pdf, .txt, .rtf, .jpeg, .jpg, .png, .gif, .bmp, .svg dosyalarındaki içeriği algılar.
> [!IMPORTANT] 
> Önizleme aşamasındayken, bu sınıflandırıcı bilinen bir sorun nedeniyle büyük hacimli toplu gönderen/bülten içeriği yakalayabilir. Önizleme aşamasındayken, büyük hacimli toplu gönderen/bülten içeriğini ele almak **için, İleti dışlanması gereken etki alanlarının listesiyle bu etki alanlarının hiçbirine gönderilmez koşulunu** ekleyebilirsiniz. 

- **Taciz**: Irk, etnik köken, din, ulusal köken, cinsiyet, cinsel yönelim, yaş, engellilik gibi bir veya birden çok kişiyi hedefleyen saldırgan davranışla ilgili belirli bir rahatsız edici dil metin öğesi kategorisini algılar. .msg, .docx, .pdf, .txt, .rtf, .jpeg, .jpg, .png, .gif, .bmp, .svg dosyalarındaki içeriği algılar.

- **Sağlık/Tıbbi formlar (önizleme)**: Bir hastanın kabul ayrıntıları, tıbbi geçmişi, hasta bilgileri ve önceki yetkilendirme isteğinin sistematik belgeleri için kullanılan ve genellikle tıbbi/sağlık hizmetlerinde kullanılan çeşitli form ve dosyaları algılar. .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt, .one, .msg, .eml, .pptx, .pptm, .ppt, .potx, .potm, .pot, .ppsx, .ppsm, .ppss, .ppam, .ppa dosyalarındaki içeriği algılar.

- **Sağlık**: Tıbbi hizmetler, tanılar, tedavi, talepler gibi tıbbi ve sağlık yönetimi açısından içeriği algılar. .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt, .one, .msg, .eml, .pptx, .pptm, .ppt, .potx, .potm, .pot, .ppsx, .ppsm, .ppam, .ppa, .xlsx, .xlsm, .xlsb, .xls, .csv, .xltx, .xltm, .xltm, .xlam, .xla dosyaları.

- **İk**: İnsan kaynaklarıyla ilgili işe alım, görüşme, işe alma, eğitim, değerlendirme, uyarı ve sonlandırma kategorilerindeki içeriği algılar. .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt, .one, .msg, .eml, .pptx, .pptm, .ppt, .potx, .potm, .pot, .ppsx, .ppsm, .ppam, .ppa, .xlsx, .xlsm, .xlsb, .xls, .csv, .xltx, .xltm, .xltm, .xlam, .xla dosyaları.

- **Fatura (önizleme)**: Satın alma işleminin listelenmiş özetini, borç bakiyesini, geçerli ödeme tarihini ve çeşitli ödeme yöntemlerini içeren faturaları algılar. .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt, .one, .eml, .xlsx, .xlsm, .xlsb, .xls, .csv, .xltx, .xltm, .xlt, .xlam, .xla dosyalarındaki içeriği algılar.

- **IP**: Ticari sırlar ve benzer gizli bilgiler gibi Fikri Mülkiyetle ilgili kategorilerdeki içeriği algılar. .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt, .one, .msg, .eml, .pptx, .pptm, .ppt, .potx, .potm, .pot, .ppsx, .ppsm, .ppam, .ppa, .xlsx, .xlsm, .xlsb, .xls, .csv, .xltx, .xltm, .xltm, .xlam, .xla dosyaları.

- **BT**: Ağ ayarları, bilgi güvenliği, donanım ve yazılım gibi Bilgi Teknolojisi ve Siber Güvenlik kategorilerindeki içeriği algılar. .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt, .one, .msg, .eml, .pptx, .pptm, .ppt, .potx, .potm, .pot, .ppsx, .ppsm, .ppam, .ppa, .xlsx, .xlsm, .xlsb, .xls, .csv, .xltx, .xltm, .xltm, .xlam, .xla dosyaları.

- **Yasal işler**: Dava, yasal süreç, yasal yükümlülük, yasal terminoloji, hukuk ve mevzuat gibi hukuk işleri ile ilgili kategorilerdeki içeriği algılar. .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt, .one, .msg, .eml dosyalarındaki içeriği algılar.

- **Lisans Sözleşmesi (önizleme): Lisans** sözleşmelerini algılar, lisans veren için kullanım ve tazminat hüküm ve koşullarını içerir. .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt dosyalarındaki içeriği algılar.

- **Kredi Sözleşmeleri ve teklif mektupları (önizleme)**: Kredi sözleşmelerini, teklif mektuplarını ve belgede yer alan hüküm ve koşulları algılar. .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt, .one, .msg, .eml dosyalarındaki içeriği algılar.

- **Birleştirme ve Alma Dosyaları (önizleme):** Bu sınıflandırıcı amaç mektubu, terim sayfaları ve ilgili dosyalar da dahil olmak üzere belgeleri algılar. .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt, .one, .msg, .eml dosyalarındaki içeriği algılar.

- **Üretim toplu iş kayıtları (önizleme):** Bu sınıflandırıcı, üretim sürecinin tamamı ve ürün toplu işleminin geçmişiyle ilgili ayrıntıları içeren üretim toplu iş belgelerini algılar. .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt, .one, .msg, .eml dosyalarındaki içeriği algılar.

- **Toplantı Notları** (önizleme): Bu sınıflandırıcı toplantı notlarını algılar. .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt, .one, .msg, .eml, .pptx, .pptm, .ppt, .potx, .potm, .pot, .ppsx, .ppsm, .ppss, .ppam, .ppa dosyalarındaki içeriği algılar.

- **Kara para aklama (önizleme)**: Gelirlerin kaynağını veya hedefini gizlemek veya gizlemek için para aklama veya etkileşim önerebilecek işaretleri algılar. Bu sınıflandırıcı, müşterilerin Banka Gizlilik Yasası, ABD Vatanseverlik Yasası, FINRA Kural 3310 ve 2020 Para AklamaYla Mücadele Yasası gibi mevzuat uyumluluğu yükümlülüklerini yönetmelerine yardımcı olabilir. .msg, .docx, .pdf, .txt, .rtf, .jpeg, .jpg, .png, .gif, .bmp, .svg dosyalarındaki içeriği algılar.
> [!IMPORTANT] 
> Önizleme aşamasındayken, bu sınıflandırıcı bilinen bir sorun nedeniyle büyük hacimli toplu gönderen/bülten içeriği yakalayabilir. Önizleme aşamasındayken, büyük hacimli toplu gönderen/bülten içeriğini ele almak **için, İleti dışlanması gereken etki alanlarının listesiyle bu etki alanlarının hiçbirine gönderilmez koşulunu** ekleyebilirsiniz. 

- **Ağ Tasarımı dosyaları (önizleme)**: Bu sınıflandırıcı, çeşitli ağ bileşenleri, nasıl bağlandıkları, mimarileri dahil olmak üzere bilgisayar ağları hakkındaki teknik belgeleri algılar nasıl performans gösterdikleri ve nerede sorun giderdikleri .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt, .one, .msg, .eml, .pptx, .pptm, .ppt, .potx, .potm, .pot, .ppsx, .ppsm, .ppsm, .ppam, .ppa dosyalarındaki içeriği algılar.

- **Gizlilik Sözleşmesi (önizleme):** Bu sınıflandırıcı, gizlilik sözleşmelerini algılar. .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt dosyalarındaki içeriği algılar.

- **Paystub (önizleme)**: Bu sınıflandırıcı paystub/maaş ekstresi dosyalarını algılar. .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt, .xlsx, .xlsm, .xlsb, .xls, .csv, .xltx, .xltm, .xltm, .xltm, .xlam, .xla dosyalarındaki içeriği algılar.

- **Tedarik**: Teklif verme, alıntılama, satın alma ve mal ve hizmet tedariki için ödeme kategorilerindeki içeriği algılar. .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt, .one, .msg, .eml, .xlsx, .xlsm, .xlsb, .xls, .csv, .xltx, .xltm, .xlt, .xlam, .xla dosyalarındaki içeriği algılar.

- **Proje Belgeleri (önizleme):** Bu sınıflandırıcı proje planlama belgelerini, proje kiralama belgelerini ve zamanlamalarını içeren proje raporlarını ve belgelerini algılar. .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt, .one, .msg, .eml, .pptx, .pptm, .ppt, .potx, .potm, .pot, .ppsx, .ppsm, .ppss, .ppam, .ppa dosyalarındaki içeriği algılar.

- **Küfür**: Çoğu kişiyi utandıran ifadeler içeren belirli bir rahatsız edici dil metin öğeleri kategorisini algılar. .msg, .docx, .pdf, .txt, .rtf, .jpeg, .jpg, .png, .gif, .bmp, .svg dosyalarındaki içeriği algılar.

- **Düzenleme harmanlaması (önizleme)**: Hassas bilgilerin gizlenmeye çalışılması gibi mevzuata karşı koruma gereksinimlerini ihlal eden iletileri algılar. Bu sınıflandırıcı, müşterilerin Sherman Antitrust Act gibi mevzuat uyumluluğu yükümlülüklerini yönetmelerine yardımcı olabilir. Menkul Kıymetler Değişim Yasası 1933, 1934 Menkul Kıymetler Borsası Yasası, 1940 Yatırım Danışmanları Yasası, Federal Komisyon Yasası ve Robinson-Patman Yasası. .msg, .docx, .pdf, .txt, .rtf, .jpeg, .jpg, .png, .gif, .bmp, .svg dosyalarındaki içeriği algılar.
> [!IMPORTANT] 
> Önizleme aşamasındayken, bu sınıflandırıcı bilinen bir sorun nedeniyle büyük hacimli toplu gönderen/bülten içeriği yakalayabilir. Önizleme aşamasındayken, büyük hacimli toplu gönderen/bülten içeriğini ele almak **için, İleti dışlanması gereken etki alanlarının listesiyle bu etki alanlarının hiçbirine gönderilmez koşulunu** ekleyebilirsiniz. 

- **Sürdür**: Bu sınıflandırıcı özgeçmişi algılar. Özgeçmiş, bir iş başvuru sahibinin işveren sağladığı ve adayın önceki iş deneyimi, eğitimi ve başarılarının ayrıntılı bir bildirimine sahip olduğu bir belgedir. .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf .txt dosyalarındaki içeriği algılar.

- **Satış ve gelir (önizleme)**: Bu sınıflandırıcı kuruluşlar için satış raporlarını, gelir/gelir tablosu ve satış/talep tahmin raporlarını algılar. .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt, .one, .pptx, .pptm, .ppt, .potx, .potm, .pot, .ppsx, .ppsm, .ppsm, .ppam, .ppa dosyalarındaki içeriği algılar.

- **Yazılım Ürün Geliştirme Dosyaları (önizleme)**: Bu sınıflandırıcı ürün gereksinimleri belgesi, ürün testi ve planlaması, test çalışmaları ve test raporları dahil olmak üzere yazılım geliştirmede kullanılan dosyaları algılar. .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt, .one, .msg, .eml dosyalarındaki içeriği algılar.

- **Kaynak kodu**: GitHub'da bilgisayar programlama dilleri yazılmış bir dizi yönerge ve deyim içeren öğeleri algılar: ActionScript, C, C#, C++, Clojure, CoffeeScript, Go, Haskell, Java, JavaScript, Lua, MATLAB, Objective-C, Perl, PHP, Python, R, Ruby, Scala, Shell, Swift, TeX, Vim Betiği. .msg, .as, .h, .c, .cs, .cc, .cpp, .hpp, .cxx, .hh, .c++, .clj, .edn, .cljc, .cljs, .coffee, .litcoffee, .go, .hs, .lhs, .java, .jar, .js, .mjs, .lua, .m, .mm, .pl, .pm, .t, .xs, .pod, .php, .phar, .php4, .pyc, . R, .r, .rda, . RData, .rds, .rb, .scala, .sc, .sh, .swift dosyaları.

  > [!NOTE]
  > Kaynak Kodu, metnin büyük kısmının kaynak kodu olduğunu algılamak için eğitilir. Düz metinle kesişen kaynak kodu metnini algılamaz.

- **Çalışma Bildirimi (önizleme):** Bu sınıflandırıcı, her iki taraf için gereksinimler, sorumluluklar, hüküm ve koşullar gibi ayrıntıları içeren çalışma bildirimini algılar. .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt dosyalarındaki içeriği algılar.

- **Hisse senedi işleme (önizleme): Hisse** senedi fiyatını işleme girişimi önerebilecek hisse senetlerini satın alma, satma veya tutma önerileri gibi olası hisse senedi işleme işaretlerini algılar. Bu sınıflandırıcı, müşterilerin 1934 Menkul Kıymetler Borsası Yasası, FINRA Kural 2372 ve FINRA Kural 5270 gibi mevzuat uyumluluğu yükümlülüklerini yönetmelerine yardımcı olabilir. .msg, .docx, .pdf, .txt, .rtf, .jpeg, .jpg, .png, .gif, .bmp, .svg dosyalarındaki içeriği algılar.
> [!IMPORTANT] 
> Önizleme aşamasındayken, bu sınıflandırıcı bilinen bir sorun nedeniyle büyük hacimli toplu gönderen/bülten içeriği yakalayabilir. Önizleme aşamasındayken, büyük hacimli toplu gönderen/bülten içeriğini ele almak **için, İleti dışlanması gereken etki alanlarının listesiyle bu etki alanlarının hiçbirine gönderilmez koşulunu** ekleyebilirsiniz.   

- **Vergi: Vergi** planlaması, vergi formları, vergi dosyalama, vergi düzenlemeleri gibi vergiyle ilgili içeriği algılar. .docx, .docm, .doc, .dotx, .dotm, .dot, .pdf, .rtf, .txt, .one, .msg, .eml, .pptx, .pptm, .ppt, .potx, .potm, .pot, .ppsx, .ppsm, .pps, .ppam, .ppa, .xlsx, .xlsm, .xlsb, .xls, .csv, .xltx, .xltm, .xltm, .xlam, .xla dosyaları.

- **Tehdit**: Şiddet uygulama veya bir kişi ya da mülke fiziksel zarar verme ya da zarar verme tehditleriyle ilgili belirli bir rahatsız edici dil metin öğesi kategorisini algılar. .msg, .docx, .pdf, .txt, .rtf, .jpeg, .jpg, .png, .gif, .bmp, .svg dosyalarındaki içeriği algılar.

- **Yetkisiz açıklama (önizleme)**: Açıkça gizli veya dahili olarak belirlenen içeriği içeren bilgilerin yetkisiz kişilere paylaşıldığını algılar. Bu sınıflandırıcı, müşterilerin FINRA Kural 2010 ve SEC Kuralı 10b-5 gibi mevzuat uyumluluğu yükümlülüklerini yönetmelerine yardımcı olabilir. .msg, .docx, .pdf, .txt, .rtf, .jpeg, .jpg, .png, .gif, .bmp, .svg dosyalarındaki içeriği algılar.
> [!IMPORTANT] 
> Önizleme aşamasındayken, bu sınıflandırıcı bilinen bir sorun nedeniyle büyük hacimli toplu gönderen/bülten içeriği yakalayabilir. Önizleme aşamasındayken, büyük hacimli toplu gönderen/bülten içeriğini ele almak **için, İleti dışlanması gereken etki alanlarının listesiyle bu etki alanlarının hiçbirine gönderilmez koşulunu** ekleyebilirsiniz. 





> [!IMPORTANT]
> Yerleşik eğitilebilir ve genel sınıflandırıcıların bu alanlarda terimlerin veya dillerin kapsamlı veya eksiksiz bir listesini sağlamadığını lütfen unutmayın. Ayrıca, dil ve kültürel standartlar sürekli olarak değişir ve bu gerçekler ışığında, Microsoft bu sınıflandırıcıları kendi takdirine bağlı olarak güncelleştirme hakkını saklı tutar. Sınıflandırıcılar kuruluşunuzun bu alanları algılamasına yardımcı olabilir ancak sınıflandırıcılar, kuruluşunuzun bu dilin kullanımını algılama veya ele alma için tek aracı sağlamayı amaçlamamaktadır. Microsoft veya yan kuruluşları değil kuruluşunuz, yerel gizlilik ve diğer geçerli yasalara uyumluluk dahil olmak üzere önceden eğitilmiş bir sınıflandırıcı tarafından tanımlanan tüm içeriklerin izlenmesi, taranması, engellenmesi, kaldırılması ve saklanmasıyla ilgili tüm kararlardan sorumlu kalır. Microsoft, dağıtım ve kullanımdan önce hukuk müşaviri ile danışmayı teşvik eder.

Tehdit, Küfür ve Taciz sınıflandırıcılarımız içeriği şu dillerde tarar:

- Arapça
- Çince (Basitleştirilmiş)
- Çince (Geleneksel)
- Dutch
- English
- French
- German
- Italian
- Korean
- Japanese
- Portekizce
- Spanish

Diğerleri sadece İngilizce.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="see-also"></a>Ayrıca bkz.

- [Bekletme etiketleri](retention.md)
- [Veri kaybı önleme hakkında daha fazla bilgi edinme](dlp-learn-about-dlp.md)
- [Duyarlılık etiketleri](sensitivity-labels.md)
- [Hassas bilgi türü varlık tanımları](sensitive-information-type-entity-definitions.md)
- [Belge parmakla yazdırma](document-fingerprinting.md)
- [Tam veri eşleşmesine dayalı hassas bilgi türleri hakkında daha fazla bilgi edinme](sit-learn-about-exact-data-match-based-sits.md#learn-about-exact-data-match-based-sensitive-information-types)
