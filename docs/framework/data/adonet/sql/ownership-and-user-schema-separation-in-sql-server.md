---
title: "Sahipliği ve SQL Server'daki kullanıcı şema ayırma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 242830c1-31b5-4427-828c-cc22ff339f30
caps.latest.revision: "6"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 168eaf9bc0bbac80cbd1e2bb0538aab89d262a49
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="ownership-and-user-schema-separation-in-sql-server"></a><span data-ttu-id="97c14-102">Sahipliği ve SQL Server'daki kullanıcı şema ayırma</span><span class="sxs-lookup"><span data-stu-id="97c14-102">Ownership and User-Schema Separation in SQL Server</span></span>
<span data-ttu-id="97c14-103">SQL Server güvenlik çekirdek kavramı nesne sahipleri değiştirilemeyen bunları yönetme izni olmasıdır.</span><span class="sxs-lookup"><span data-stu-id="97c14-103">A core concept of SQL Server security is that owners of objects have irrevocable permissions to administer them.</span></span> <span data-ttu-id="97c14-104">Bir nesne sahibinden ayrıcalıkları kaldırılamıyor ve içindeki nesneleri sahipseniz kullanıcıların veritabanından bırakılamıyor.</span><span class="sxs-lookup"><span data-stu-id="97c14-104">You cannot remove privileges from an object owner, and you cannot drop users from a database if they own objects in it.</span></span>  
  
## <a name="user-schema-separation"></a><span data-ttu-id="97c14-105">Kullanıcı şema ayırma</span><span class="sxs-lookup"><span data-stu-id="97c14-105">User-Schema Separation</span></span>  
 <span data-ttu-id="97c14-106">Kullanıcı şema ayrımı veritabanı nesne izinleri yönetme daha fazla esneklik sağlar.</span><span class="sxs-lookup"><span data-stu-id="97c14-106">User-schema separation allows for more flexibility in managing database object permissions.</span></span> <span data-ttu-id="97c14-107">A *şema* ayrı ad alanında Grup nesnelerine sağlayan bir adlandırılmış veritabanı nesneleri için kapsayıcıdır.</span><span class="sxs-lookup"><span data-stu-id="97c14-107">A *schema* is a named container for database objects, which allows you to group objects into separate namespaces.</span></span> <span data-ttu-id="97c14-108">Örneğin, AdventureWorks örnek veritabanı şemaları, üretim, satış ve İnsanKaynakları içerir.</span><span class="sxs-lookup"><span data-stu-id="97c14-108">For example, the AdventureWorks sample database contains schemas for Production, Sales, and HumanResources.</span></span>  
  
 <span data-ttu-id="97c14-109">Nesnelere başvurma için dört bölümden oluşan sözdizimini şema adını belirtir.</span><span class="sxs-lookup"><span data-stu-id="97c14-109">The four-part naming syntax for referring to objects specifies the schema name.</span></span>  
  
```  
Server.Database.DatabaseSchema.DatabaseObject  
```  
  
### <a name="schema-owners-and-permissions"></a><span data-ttu-id="97c14-110">Şema sahipleri ve izinleri</span><span class="sxs-lookup"><span data-stu-id="97c14-110">Schema Owners and Permissions</span></span>  
 <span data-ttu-id="97c14-111">Şemalar tarafından herhangi bir veritabanı asıl sahip olabilir ve tek bir sorumlusu birden çok şema sahip olabilir.</span><span class="sxs-lookup"><span data-stu-id="97c14-111">Schemas can be owned by any database principal, and a single principal can own multiple schemas.</span></span> <span data-ttu-id="97c14-112">Güvenlik kuralları şemadaki tüm nesneler tarafından alınan bir bir şemaya uygulayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="97c14-112">You can apply security rules to a schema, which are inherited by all objects in the schema.</span></span> <span data-ttu-id="97c14-113">Bir şema için erişim izinleri ayarladıktan sonra yeni nesneler şemaya eklendikçe bu izinleri otomatik olarak uygulanır.</span><span class="sxs-lookup"><span data-stu-id="97c14-113">Once you set up access permissions for a schema, those permissions are automatically applied as new objects are added to the schema.</span></span> <span data-ttu-id="97c14-114">Kullanıcıların varsayılan şema atanabilir ve birden çok veritabanı kullanıcıları aynı şema paylaşabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="97c14-114">Users can be assigned a default schema, and multiple database users can share the same schema.</span></span>  
  
 <span data-ttu-id="97c14-115">Geliştiriciler bir şemada bulunan nesneler oluşturduğunuzda varsayılan olarak şema, geliştirici sahibi güvenlik sorumlusu tarafından nesneleri sahibi olur.</span><span class="sxs-lookup"><span data-stu-id="97c14-115">By default, when developers create objects in a schema, the objects are owned by the security principal that owns the schema, not the developer.</span></span> <span data-ttu-id="97c14-116">Nesne sahipliği YETKİLENDİRME Transact-SQL ALTER deyimiyle aktarılabilir.</span><span class="sxs-lookup"><span data-stu-id="97c14-116">Object ownership can be transferred with ALTER AUTHORIZATION Transact-SQL statement.</span></span> <span data-ttu-id="97c14-117">İzinleri yönetme için karmaşıklık ekler bu önerilmez çünkü rağmen bir şema, farklı kullanıcılara ait ve şeması için atanan'den daha ayrıntılı izinlere sahip nesneleri de içerebilir.</span><span class="sxs-lookup"><span data-stu-id="97c14-117">A schema can also contain objects that are owned by different users and have more granular permissions than those assigned to the schema, although this is not recommended because it adds complexity to managing permissions.</span></span> <span data-ttu-id="97c14-118">Nesneleri Şemalar arasında taşınabilir ve Şema sahipliğini sorumluları arasında aktarılabilir.</span><span class="sxs-lookup"><span data-stu-id="97c14-118">Objects can be moved between schemas, and schema ownership can be transferred between principals.</span></span> <span data-ttu-id="97c14-119">Veritabanı kullanıcıları şemaları etkilemeden bırakılabilir.</span><span class="sxs-lookup"><span data-stu-id="97c14-119">Database users can be dropped without affecting schemas.</span></span>  
  
### <a name="built-in-schemas"></a><span data-ttu-id="97c14-120">Yerleşik şemaları</span><span class="sxs-lookup"><span data-stu-id="97c14-120">Built-In Schemas</span></span>  
 <span data-ttu-id="97c14-121">SQL Server yerleşik veritabanı kullanıcıları ve rolleri olarak aynı ada sahip on önceden tanımlanmış şemalar ile birlikte gelir.</span><span class="sxs-lookup"><span data-stu-id="97c14-121">SQL Server ships with ten pre-defined schemas that have the same names as the built-in database users and roles.</span></span> <span data-ttu-id="97c14-122">Bunlar çoğunlukla geriye dönük uyumluluk için mevcut.</span><span class="sxs-lookup"><span data-stu-id="97c14-122">These exist mainly for backward compatibility.</span></span> <span data-ttu-id="97c14-123">Bunları gerekmiyorsa sabit veritabanı rollerinin aynı adları olan şemaları düşürebilir.</span><span class="sxs-lookup"><span data-stu-id="97c14-123">You can drop the schemas that have the same names as the fixed database roles if you do not need them.</span></span> <span data-ttu-id="97c14-124">Şu şemalardan bırakılamıyor:</span><span class="sxs-lookup"><span data-stu-id="97c14-124">You cannot drop the following schemas:</span></span>  
  
-   `dbo`  
  
-   `guest`  
  
-   `sys`  
  
-   `INFORMATION_SCHEMA`  
  
 <span data-ttu-id="97c14-125">Modeli veritabanından bırakın, yeni veritabanları görünmez.</span><span class="sxs-lookup"><span data-stu-id="97c14-125">If you drop them from the model database, they will not appear in new databases.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="97c14-126">`sys` Ve `INFORMATION_SCHEMA` şemaları sistem nesneleri için ayrılmıştır.</span><span class="sxs-lookup"><span data-stu-id="97c14-126">The `sys` and `INFORMATION_SCHEMA` schemas are reserved for system objects.</span></span> <span data-ttu-id="97c14-127">Bu şemalarda nesneler oluşturamaz ve bunları bırakılamıyor.</span><span class="sxs-lookup"><span data-stu-id="97c14-127">You cannot create objects in these schemas and you cannot drop them.</span></span>  
  
#### <a name="the-dbo-schema"></a><span data-ttu-id="97c14-128">Şema dbo</span><span class="sxs-lookup"><span data-stu-id="97c14-128">The dbo Schema</span></span>  
 <span data-ttu-id="97c14-129">`dbo` Schema yeni oluşturulan bir veritabanı için varsayılan şema'dır.</span><span class="sxs-lookup"><span data-stu-id="97c14-129">The `dbo` schema is the default schema for a newly created database.</span></span> <span data-ttu-id="97c14-130">`dbo` Şema sahibi tarafından `dbo` kullanıcı hesabı.</span><span class="sxs-lookup"><span data-stu-id="97c14-130">The `dbo` schema is owned by the `dbo` user account.</span></span> <span data-ttu-id="97c14-131">Varsayılan olarak, bu CREATE kullanıcı Transact-SQL komutuyla oluşturulan kullanıcınız `dbo` kendi varsayılan şema olarak.</span><span class="sxs-lookup"><span data-stu-id="97c14-131">By default, users created with the CREATE USER Transact-SQL command have `dbo` as their default schema.</span></span>  
  
 <span data-ttu-id="97c14-132">Atanan kullanıcıların `dbo` şema devralmaz izinlerini `dbo` kullanıcı hesabı.</span><span class="sxs-lookup"><span data-stu-id="97c14-132">Users who are assigned the `dbo` schema do not inherit the permissions of the `dbo` user account.</span></span> <span data-ttu-id="97c14-133">Hiçbir izinler şemadan kullanıcılar tarafından devralınır; Şema izinlerini şemasında bulunan veritabanı nesneleri tarafından devralınır.</span><span class="sxs-lookup"><span data-stu-id="97c14-133">No permissions are inherited from a schema by users; schema permissions are inherited by the database objects contained in the schema.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="97c14-134">Veritabanı nesneleri, bir bölüm adı kullanarak başvurduğunda SQL Server kullanıcının varsayılan şemasında İlk bakar.</span><span class="sxs-lookup"><span data-stu-id="97c14-134">When database objects are referenced by using a one-part name, SQL Server first looks in the user's default schema.</span></span> <span data-ttu-id="97c14-135">Nesne var. bulunamadı, SQL Server İleri'durur `dbo` şema.</span><span class="sxs-lookup"><span data-stu-id="97c14-135">If the object is not found there, SQL Server looks next in the `dbo` schema.</span></span> <span data-ttu-id="97c14-136">Nesne içinde değilse `dbo` şeması, bir hata döndürülür.</span><span class="sxs-lookup"><span data-stu-id="97c14-136">If the object is not in the `dbo` schema, an error is returned.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="97c14-137">Dış Kaynaklar</span><span class="sxs-lookup"><span data-stu-id="97c14-137">External Resources</span></span>  
 <span data-ttu-id="97c14-138">Nesne sahipliği ve şemaları hakkında daha fazla bilgi için aşağıdaki kaynaklara bakın.</span><span class="sxs-lookup"><span data-stu-id="97c14-138">For more information on object ownership and schemas, see the following resources.</span></span>  
  
|<span data-ttu-id="97c14-139">Kaynak</span><span class="sxs-lookup"><span data-stu-id="97c14-139">Resource</span></span>|<span data-ttu-id="97c14-140">Açıklama</span><span class="sxs-lookup"><span data-stu-id="97c14-140">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="97c14-141">[Kullanıcı şema ayrımı](http://msdn.microsoft.com/library/ms190387.aspx) SQL Server Çevrimiçi Kitapları'nda</span><span class="sxs-lookup"><span data-stu-id="97c14-141">[User-Schema Separation](http://msdn.microsoft.com/library/ms190387.aspx) in SQL Server Books Online</span></span>|<span data-ttu-id="97c14-142">Kullanıcı şema ayırma tarafından sunulan değişiklikler açıklanmaktadır.</span><span class="sxs-lookup"><span data-stu-id="97c14-142">Describes the changes introduced by user-schema separation.</span></span> <span data-ttu-id="97c14-143">Yeni davranış, sahipliği, Katalog görünümleri ve izinleri üzerindeki etkisini içerir.</span><span class="sxs-lookup"><span data-stu-id="97c14-143">Includes new behavior, its impact on ownership, catalog views, and permissions.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="97c14-144">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="97c14-144">See Also</span></span>  
 [<span data-ttu-id="97c14-145">ADO.NET uygulamalarının güvenliğini sağlama</span><span class="sxs-lookup"><span data-stu-id="97c14-145">Securing ADO.NET Applications</span></span>](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [<span data-ttu-id="97c14-146">SQL Server'daki uygulama güvenlik senaryoları</span><span class="sxs-lookup"><span data-stu-id="97c14-146">Application Security Scenarios in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)  
 [<span data-ttu-id="97c14-147">SQL Server kimlik doğrulaması</span><span class="sxs-lookup"><span data-stu-id="97c14-147">Authentication in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/authentication-in-sql-server.md)  
 [<span data-ttu-id="97c14-148">Sunucusu ve SQL Server veritabanı rolleri</span><span class="sxs-lookup"><span data-stu-id="97c14-148">Server and Database Roles in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/server-and-database-roles-in-sql-server.md)  
 [<span data-ttu-id="97c14-149">Yetkilendirme ve SQL Server'daki izinleri</span><span class="sxs-lookup"><span data-stu-id="97c14-149">Authorization and Permissions in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/authorization-and-permissions-in-sql-server.md)  
 [<span data-ttu-id="97c14-150">ADO.NET yönetilen sağlayıcıları ve veri kümesi Geliştirici Merkezi</span><span class="sxs-lookup"><span data-stu-id="97c14-150">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)