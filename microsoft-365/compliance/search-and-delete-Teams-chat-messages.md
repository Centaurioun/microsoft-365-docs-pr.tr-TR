---
title: Teams'de sohbet iletilerini arama ve silme
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 3526fd06-b45f-445b-aed4-5ebd37b3762a
description: Microsoft Teams'de sohbet iletilerini aramak ve temizlemek ve Teams'deki veri taşması olaylarına yanıt vermek için eBulma (Premium) ve Microsoft Graph Gezgini'ni kullanın.
ms.openlocfilehash: 372293e11ee16498746da69c824a91abd108f2cf
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/06/2022
ms.locfileid: "66862249"
---
# <a name="search-and-purge-chat-messages-in-teams-preview"></a>Teams'de sohbet iletilerini arama ve temizleme (Önizleme)

Microsoft Teams'de sohbet iletilerini aramak ve silmek için eKeşif (Premium) ve Microsoft Graph Gezgini'ni kullanabilirsiniz. Bu, hassas bilgileri veya uygunsuz içeriği bulup kaldırmanıza yardımcı olabilir. Bu arama ve temizleme iş akışı, Teams sohbet iletileri aracılığıyla gizli veya kötü amaçlı bilgiler içeren içerik yayımlandığında veri taşması olayına yanıt vermenizi de sağlar.

> [!NOTE]
> Bu makale Microsoft 365 Kurumsal kuruluşlar için geçerlidir. ABD Kamu bulutu (GCC, GCC High ve DoD dahil) için destek yakında sunulacaktır.

## <a name="before-you-search-and-purge-chat-messages"></a>Sohbet iletilerini aramadan ve temizlemeden önce

- Bir eBulma (Premium) olayı oluşturmak ve sohbet iletilerini aramak için koleksiyonları kullanmak için, Microsoft Purview uyumluluk portalı **eBulma Yöneticisi** rol grubunun üyesi olmanız gerekir. Sohbet iletilerini silmek için **Size Arama ve Temizleme** rolü atanmalıdır. Bu rol, varsayılan olarak Veri Araştırmacısı ve Kuruluş Yönetimi rol gruplarına atanır. Daha fazla bilgi için bkz. [eBulma izinleri atama](assign-ediscovery-permissions.md).
- Arama ve temizleme, kiracınızdaki konuşmalar için desteklenir. Teams Connect Sohbeti (Dış Erişim veya Federasyon) konuşmaları desteği bazı durumlarda arabirimde etkinleştirilir ancak istendiği gibi çalışmaz.
- Posta kutusu başına bir kerede en fazla 10 öğe kaldırılabilir. Sohbet iletilerini arama ve kaldırma özelliği bir olay yanıtı aracı olması amaçlandığından, bu sınır sohbet iletilerinin hızla kaldırılmasına yardımcı olur.

## <a name="search-and-purge-workflow"></a>İş akışını arama ve temizleme

Teams sohbet iletilerini arama ve temizleme işlemi şu şekildedir:

![Teams sohbet iletilerini aramak ve temizlemek için iş akışı.](../media/TeamsSearchAndPurgeWorkflow.png)

## <a name="step-1-create-a-case-in-ediscovery-premium"></a>1. Adım: eBulma'da servis talebi oluşturma (Premium)

İlk adım, arama ve temizleme işlemini yönetmek için eBulma'da (Premium) bir servis talebi oluşturmaktır. Servis talebi oluşturma hakkında bilgi için bkz. [Yeni servis talebi biçimini kullanma](advanced-ediscovery-new-case-format.md).

## <a name="step-2-create-a-draft-collection"></a>2. Adım: Taslak koleksiyonu oluşturma

Bir servis talebi oluşturduktan sonra bir sonraki adım, temizlemek istediğiniz Teams sohbet iletilerini aramak için bir taslak koleksiyon oluşturmaktır. Gerçekleştirdiğiniz temizleme işlemi 5. Adım, taslak koleksiyonda bulunan tüm öğeleri temizler.

eBulma (Premium) uygulamasında *koleksiyon* , temizlemek istediğiniz sohbet iletilerini içeren Teams içerik konumlarının eBulma aramasıdır. Önceki adımda oluşturduğunuz durumda taslak koleksiyonu oluşturun. Daha fazla bilgi için bkz. [Taslak koleksiyonu oluşturma](create-draft-collection.md).

### <a name="data-sources-for-chat-messages"></a>Sohbet iletileri için veri kaynakları

Temizlemeniz gereken sohbet iletisinin türüne bağlı olarak hangi veri kaynaklarının arandığını belirlemek için aşağıdaki tabloyu kullanın.

| Bu tür sohbetler için...|Bu veri kaynağında ara...|
|:---------|:---------|
|Teams 1:1 sohbetleri     |Sohbet katılımcılarının posta kutusu.|
|Teams grup sohbetleri     |Sohbet katılımcılarının posta kutuları.|
|Teams kanalları (standart ve paylaşılan) |Üst ekiple ilişkilendirilmiş posta kutusu.|
|Teams özel kanalları |Özel kanal üyelerinin posta kutusu.|

> [!NOTE]
> 4. Adımda, posta kutusuna atanan ve silmek istediğiniz sohbet iletilerinin türünü içeren saklama ve bekletme ilkelerini de tanımlamanız ve kaldırmanız gerekir.

### <a name="tips-for-searching-for-chat-messages"></a>Sohbet iletilerini arama ipuçları

Teams sohbet konuşmalarının en kapsamlı koleksiyonunun (1:1 ve grup sohbetleri ve standart, paylaşılan ve özel sohbetlerden sohbetler dahil) sağlanmasına yardımcı olmak için **Tür** koşulunu kullanın ve taslak koleksiyon için arama sorgusunu oluştururken **Anlık iletiler** seçeneğini belirleyin. Ayrıca, koleksiyonun kapsamını arama temizleme araştırmanızla ilgili öğelere daraltmak için bir tarih aralığı veya birkaç anahtar sözcük de eklemenizi öneririz.

**Tür** ve **Tarih** seçeneklerini kullanan örnek sorgunun ekran görüntüsü aşağıda verilmiştir:

   ![Teams içeriğini toplamak için sorgulayın.](..\media\TeamsConditionsQueryType.png)

Daha fazla bilgi için bkz. [Koleksiyonlar için arama sorguları oluşturma](building-search-queries.md).

## <a name="step-3-review-and-verify-chat-messages-to-purge"></a>3. Adım: Temizlemek için sohbet iletilerini gözden geçirme ve doğrulama

Daha önce belirtildiği gibi, 5. Adımdaki temizleme işlemi koleksiyon tarafından döndürülen öğeleri siler. Bu nedenle, koleksiyonun yalnızca temizlemek istediğiniz öğeleri döndürdüğünden emin olmak için taslak koleksiyon sonuçlarını gözden geçirmeniz önemlidir. Taslak koleksiyondaki öğelerin bir örneğini gözden geçirmek için Taslak koleksiyonu [oluşturma](create-draft-collection.md#next-steps-after-a-draft-collection-is-complete) bölümündeki "Taslak koleksiyonu tamamlandıktan sonraki adımlar" bölümüne bakın.

Ayrıca, koleksiyon tarafından döndürülen öğeleri içeren veri kaynaklarının listesini oluşturmak için koleksiyon istatistiklerini (özellikle En Önemli Konumlar istatistikleri) kullanabilirsiniz. Arama sonuçlarını içeren veri kaynaklarından bekletme ve saklama ilkelerini kaldırmak için sonraki adımda bu listeyi kullanın. Daha fazla bilgi için bkz [. Koleksiyon istatistikleri ve raporları](collection-statistics-reports.md).

## <a name="step-4-remove-holds-and-retention-policies-from-data-sources"></a>4. Adım: Veri kaynaklarından saklama ve saklama ilkelerini kaldırma

Bir posta kutusundan sohbet iletilerini temizlemeden önce, hedef posta kutusuna atanan bekletme veya saklama ilkesini kaldırmanız gerekir. Aksi takdirde, silmeye çalıştığınız sohbet korunur.

Silmek istediğiniz sohbet iletilerini içeren posta kutularının listesini kullanın ve bu posta kutularına atanmış bir bekletme veya bekletme ilkesi olup olmadığını belirleyin ve sonra bekletme veya bekletme ilkesini kaldırın. 7. Adımda posta kutularına yeniden atayabilmek için kaldırdığınız saklama veya saklama ilkesini tanımladığınızdan emin olun.

Ayrı tutma ve bekletme ilkelerini tanımlama ve kaldırma hakkında yönergeler için, bulut tabanlı posta kutularının [Kurtarılabilir Öğeler klasöründeki Öğeleri silme](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-3-remove-all-holds-from-the-mailbox) bölümündeki "3. Adım: Posta kutusundan tüm ayrı tutmaları kaldırma" bölümüne bakın.

## <a name="step-5-purge-chat-messages-from-teams"></a>5. Adım: Teams'den sohbet iletilerini temizleme

Artık sohbet iletilerini Teams'den temizlemeye hazırsınız. Aşağıdaki üç görevi gerçekleştirmek için Microsoft Graph Gezgini'ni kullanacaksınız:

1. 1. Adımda oluşturduğunuz eBulma (Premium) servis talebinin kimliğini alın. 2. Adımda oluşturulan koleksiyonu içeren durum budur.

2. 2. Adımda oluşturduğunuz ve 3. Adımda arama sonuçlarını doğruladığınız koleksiyonun kimliğini alın. Bu koleksiyondaki arama sorgusu temizlenecek sohbet iletilerini döndürür.

3. Koleksiyon tarafından döndürülen sohbet iletilerini temizleme.

Graph Explorer'ı kullanma hakkında bilgi için bkz. [Microsoft Graph API'lerini denemek için Graph Gezgini'ni kullanma](/graph/graph-explorer/graph-explorer-overview).

> [!IMPORTANT]
> Microsoft Graph'ta /beta sürümü altındaki API'ler değiştirilebilir. Bu API'lerin üretim uygulamalarında kullanılması desteklenmez. Bir API'nin v1.0'da kullanılabilir olup olmadığını belirlemek için Sürüm seçiciyi kullanın.

> [!IMPORTANT]
> Graph Gezgini'nde bu üç görevi gerçekleştirmek için eKeşif.Read.All ve eKeşif.ReadWrite.All izinlerini onaylamanız gerekebilir. Daha fazla bilgi için [Graf Gezgini ile çalışma](/graph/graph-explorer/graph-explorer-features#consent-to-permissions) bölümündeki "İzinlere onay verme" bölümüne bakın.

### <a name="get-the-case-id"></a>Servis talebi kimliğini alma

1. <https://developer.microsoft.com/graph/graph-explorer> Microsoft Purview uyumluluk portalı **Arama ve Temizleme** rolü atanmış bir hesapla Graph Gezgini'ne gidin ve bu hesapta oturum açın.

2. eBulma (Premium) olayının kimliğini almak için aşağıdaki GET isteğini çalıştırın. İstek sorgusunun adres çubuğundaki değeri `https://graph.microsoft.com/beta/compliance/ediscovery/cases` kullanın. API sürümü açılan listesinde **v1.0'ı** seçtiğinizden emin olun.

   ![Olay kimliği için GET isteği.](..\media\GraphGetRequestForCaseId.png)

   Bu istek **, Yanıt önizleme** sekmesinde kuruluşunuzdaki tüm servis talepleri hakkında bilgi döndürür.

3. eBulma (Premium) servis talebini bulmak için yanıtta ilerleyin. Olayı tanımlamak için **displayName** özelliğini kullanın.

   ![Büyük/küçük harf kimliğiyle yanıt.](..\media\GraphResponseForCaseId.png)

4. İlgili kimliği kopyalayın (veya kopyalayıp bir metin dosyasına yapıştırın). Koleksiyon kimliğini almak için sonraki görevde bu kimliği kullanacaksınız.

> [!TIP]
> Servis talebi kimliğini almak için önceki yordamı kullanmak yerine servis talebini Microsoft Purview uyumluluk portalı açabilir ve URL'den servis talebi kimliğini kopyalayabilirsiniz.

### <a name="get-the-collection-id"></a>Koleksiyon kimliğini alma

1. Graph Explorer'da, 2. Adımda oluşturduğunuz koleksiyonun kimliğini almak için aşağıdaki GET isteğini çalıştırın ve temizlemek istediğiniz öğeleri içerir. İstek sorgusunun adres çubuğundaki değeri `https://graph.microsoft.com/beta/compliance/ediscovery/cases('caseId')/sourceCollections` kullanın; burada CaseId, önceki yordamda aldığınız kimliktir. Büyük/küçük harf kimliğini parantezler ve tek tırnak işaretleri ile çevrelemeye özen gösterin.

   ![Koleksiyon kimliği için GET isteği.](..\media\GraphGetRequestForCollectionId.png)

   Bu istek **, Yanıt önizleme** sekmesindeki örnekteki tüm koleksiyonlar hakkında bilgi döndürür.

2. Temizlemek istediğiniz öğeleri içeren koleksiyonu bulmak için yanıtı kaydırın. 3. Adımda oluşturduğunuz koleksiyonu tanımlamak için **displayName** özelliğini kullanın.

   ![Koleksiyon kimliğine sahip yanıt.](..\media\GraphResponseForCollectionId.png)

   Yanıtta, koleksiyondaki arama sorgusu **contentQuery** özelliğinde görüntülenir. Bu sorgu tarafından döndürülen öğeler sonraki görevde temizlenir.

3. İlgili kimliği kopyalayın (veya kopyalayıp bir metin dosyasına yapıştırın). Sohbet iletilerini temizlemek için bir sonraki görevde bu kimliği kullanacaksınız.

### <a name="purge-the-chat-messages"></a>Sohbet iletilerini temizleme

1. Graph Explorer'da, 2. Adımda oluşturduğunuz koleksiyon tarafından döndürülen öğeleri temizlemek için aşağıdaki POST isteğini çalıştırın. İstek sorgusunun adres çubuğundaki değeri `https://graph.microsoft.com/beta/compliance/ediscovery/cases('caseId')/sourceCollections('collectionId')/purgeData` kullanın; burada caseId ve collectionId, önceki yordamlarda elde ettiğiniz kimliklerdir. Kimlik değerlerini parantezler ve tek tırnak işaretleri ile çevrelemeye özen gösterin.

      ![Koleksiyon tarafından döndürülen öğeleri silmek için POST isteği.](..\media\GraphPOSTRequestToPurgeItems.png)

   POST isteği başarılı olursa, isteğin kabul edildiğine ilişkin yeşil bir başlıkta http yanıt kodu görüntülenir.

   ![Temizleme isteği için yanıt.](..\media\GraphResponseForPurge.png)

  purgeData hakkında daha fazla bilgi için bkz. [sourceCollection: purgeData](/graph/api/ediscovery-sourcecollection-purgedata).

## <a name="step-6-verify-chat-messages-are-purged"></a>6. Adım: Sohbet iletilerinin temizlendiğini doğrulama

Sohbet iletilerini temizlemek için POST isteğini çalıştırdıktan sonra, bu iletiler Teams istemcisinden kaldırılır ve bir yöneticinin iletiyi kaldırdığını belirten otomatik olarak oluşturulan bir iletiyle değiştirilir. Bu iletinin bir örneği için bu makaledeki [Son kullanıcı deneyimi](#end-user-experience) bölümüne bakın.

Temizlenen sohbet iletileri, gizli bir posta kutusu klasörü olan SubstrateHolds klasörüne taşınır. Temizlenmiş sohbet iletileri en az 1 gün boyunca orada depolanır ve zamanlayıcı işi bir sonraki çalıştırıldığında (genellikle 1-7 gün arasında) kalıcı olarak silinir. Daha fazla bilgi için bkz. [Microsoft Teams için bekletme hakkında bilgi edinin](retention-policies-teams.md).

## <a name="step-7-reapply-holds-and-retention-policies-to-data-sources"></a>7. Adım: Veri kaynaklarına saklama ve saklama ilkelerini yeniden uygulama

Sohbet iletilerinin Temizlendiğini ve Teams istemcisinden kaldırıldığını doğruladıktan sonra, 4. Adımda kaldırdığınız saklama ve saklama ilkelerini yeniden uygulayın.

<!--
## Deleting chat messages in federated environments

Admins can use the procedures in this article to search and delete Teams chat messages in federated environments. However, you must adhere to the following guidelines. These guidelines are based on the organizational ownership of the conversation thread that contains the messages you want to delete. An organization is the owner of a conversation thread that is started by a user in that organization. In other words, when a user starts a chat, the user's organization becomes the owner of the conversation thread.

- Admins can delete the compliance copy in conversation threads owned by their organization. That means compliance copies are purged when the admin who purges the chat messages in Step 5 is in the same organization as the user who initiated the conversation thread that contains the purged messages. If a conversation thread has users in two organizations, compliance copies for the other organization will be retained.

- If a conversation thread has users in two organizations, purged chat messages are removed from the Teams client in both organizations.

- The only way to purge chat messages from user mailboxes in your organization for chat messages in conversation threads owned by another organization is to use retention policies for Teams. For more information, see [Learn about retention for Microsoft Teams](retention-policies-teams.md).
-->

## <a name="end-user-experience"></a>Son kullanıcı deneyimi

Silinen sohbet iletileri için kullanıcılar otomatik olarak oluşturulan "Bu ileti bir yönetici tarafından silindi" iletisini görür.

![Teams istemcisinde temizlenmiş sohbet iletisinin görünümü.](..\media\TeamsPurgeTombstone.png)

Önceki ekran görüntüsündeki ileti, silinen sohbet iletisinin yerini alır.

> [!NOTE]
> Son kullanıcıysanız ve bir sohbet iletisi silinmişse daha fazla bilgi için yöneticinize başvurun.
