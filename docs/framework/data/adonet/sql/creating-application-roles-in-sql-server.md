---
title: "SQL Server uygulama rolleri oluşturma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 27442435-dfb2-4062-8c59-e2960833a638
caps.latest.revision: "9"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 632b25408db8556dd9604f653f975bccbea75e2b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="creating-application-roles-in-sql-server"></a><span data-ttu-id="c8ee8-102">SQL Server uygulama rolleri oluşturma</span><span class="sxs-lookup"><span data-stu-id="c8ee8-102">Creating Application Roles in SQL Server</span></span>
<span data-ttu-id="c8ee8-103">Uygulama rolleri veritabanı rolü veya kullanıcı yerine bir uygulama izinleri atamak için bir yol sağlar.</span><span class="sxs-lookup"><span data-stu-id="c8ee8-103">Application roles provide a way to assign permissions to an application instead of a database role or user.</span></span> <span data-ttu-id="c8ee8-104">Kullanıcılar veritabanına bağlanmak, uygulama rolünü etkinleştirmek ve uygulamaya verilen izinler varsayalım.</span><span class="sxs-lookup"><span data-stu-id="c8ee8-104">Users can connect to the database, activate the application role, and assume the permissions granted to the application.</span></span> <span data-ttu-id="c8ee8-105">Uygulama rolü verilen izinler yürürlükte bağlantısı süresince değil.</span><span class="sxs-lookup"><span data-stu-id="c8ee8-105">The permissions granted to the application role are in force for the duration of the connection.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c8ee8-106">Bir istemci uygulaması bir uygulama rolü adı ve parola bağlantı dizesindeki sağlayan olduğunda uygulama rolleri etkinleştirilir.</span><span class="sxs-lookup"><span data-stu-id="c8ee8-106">Application roles are activated when a client application supplies an application role name and a password in the connection string.</span></span> <span data-ttu-id="c8ee8-107">Parola istemci bilgisayarda depolanması gerekir çünkü iki katmanlı uygulamada bir güvenlik açığı sunar.</span><span class="sxs-lookup"><span data-stu-id="c8ee8-107">They present a security vulnerability in a two-tier application because the password must be stored on the client computer.</span></span> <span data-ttu-id="c8ee8-108">Böylece uygulama kullanıcılar tarafından erişilemez, bir üç katmanlı uygulama parolası depolayabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="c8ee8-108">In a three-tier application, you can store the password so that it cannot be accessed by users of the application.</span></span>  
  
## <a name="application-role-features"></a><span data-ttu-id="c8ee8-109">Uygulama rolü özellikleri</span><span class="sxs-lookup"><span data-stu-id="c8ee8-109">Application Role Features</span></span>  
 <span data-ttu-id="c8ee8-110">Uygulama rolleri aşağıdaki özelliklere sahiptir:</span><span class="sxs-lookup"><span data-stu-id="c8ee8-110">Application roles have the following features:</span></span>  
  
-   <span data-ttu-id="c8ee8-111">Veritabanı rolleri farklı olarak, hiçbir üyeleri uygulama rolleri içerir.</span><span class="sxs-lookup"><span data-stu-id="c8ee8-111">Unlike database roles, application roles contain no members.</span></span>  
  
-   <span data-ttu-id="c8ee8-112">Uygulama rolleri uygulama rol adı ve parola için uygulamanın sağladığı olduğunda etkinleşir `sp_setapprole` sistem saklı yordamı.</span><span class="sxs-lookup"><span data-stu-id="c8ee8-112">Application roles are activated when an application supplies the application role name and a password to the `sp_setapprole` system stored procedure.</span></span>  
  
-   <span data-ttu-id="c8ee8-113">Parola istemci bilgisayarda depolanan ve çalışma zamanında sağlanan; bir uygulama rolü içinde SQL Server etkinleştirilemiyor.</span><span class="sxs-lookup"><span data-stu-id="c8ee8-113">The password must be stored on the client computer and supplied at run time; an application role cannot be activated from inside of SQL Server.</span></span>  
  
-   <span data-ttu-id="c8ee8-114">Parola şifrelenmez.</span><span class="sxs-lookup"><span data-stu-id="c8ee8-114">The password is not encrypted.</span></span> <span data-ttu-id="c8ee8-115">Parametre parolası tek yönlü bir karma depolanır.</span><span class="sxs-lookup"><span data-stu-id="c8ee8-115">The parameter password is stored as a one-way hash.</span></span>  
  
-   <span data-ttu-id="c8ee8-116">Etkinleştirilen sonra uygulama rolü edinilen izinleri bağlantı boyunca etkin kalır.</span><span class="sxs-lookup"><span data-stu-id="c8ee8-116">Once activated, permissions acquired through the application role remain in effect for the duration of the connection.</span></span>  
  
-   <span data-ttu-id="c8ee8-117">Uygulama rolü verilen izinler devralır `public` rol.</span><span class="sxs-lookup"><span data-stu-id="c8ee8-117">The application role inherits permissions granted to the `public` role.</span></span>  
  
-   <span data-ttu-id="c8ee8-118">Bir üyesi değilse `sysadmin` sabit sunucu rolünün bir uygulama rolü etkinleştirir, güvenlik bağlamı, uygulama rolü bağlantı boyunca geçer.</span><span class="sxs-lookup"><span data-stu-id="c8ee8-118">If a member of the `sysadmin` fixed server role activates an application role, the security context switches to that of the application role for the duration of the connection.</span></span>  
  
-   <span data-ttu-id="c8ee8-119">Oluşturursanız, bir `guest` hesap bir uygulama rolü olan bir veritabanında, uygulama rolü veya onu çağırma oturumlarının herhangi bir veritabanı kullanıcı hesabı oluşturma gerekmez.</span><span class="sxs-lookup"><span data-stu-id="c8ee8-119">If you create a `guest` account in a database that has an application role, you do not need to create a database user account for the application role or for any of the logins that invoke it.</span></span> <span data-ttu-id="c8ee8-120">Uygulama rolleri başka bir veritabanı yalnızca IF doğrudan erişebileceği bir `guest` hesap ikinci veritabanında var</span><span class="sxs-lookup"><span data-stu-id="c8ee8-120">Application roles can directly access another database only if a `guest` account exists in the second database</span></span>  
  
-   <span data-ttu-id="c8ee8-121">Oturum açma adları, SYSTEM_USER gibi dönüş yerleşik işlevler uygulama rolü çağrılan oturum açma adını döndürür.</span><span class="sxs-lookup"><span data-stu-id="c8ee8-121">Built-in functions that return login names, such as SYSTEM_USER, return the name of the login that invoked the application role.</span></span> <span data-ttu-id="c8ee8-122">Veritabanı kullanıcı adlarını döndürmek yerleşik işlevler uygulama rolün adını döndürür.</span><span class="sxs-lookup"><span data-stu-id="c8ee8-122">Built-in functions that return database user names return the name of the application role.</span></span>  
  
### <a name="the-principle-of-least-privilege"></a><span data-ttu-id="c8ee8-123">En az ayrıcalık prensibi</span><span class="sxs-lookup"><span data-stu-id="c8ee8-123">The Principle of Least Privilege</span></span>  
 <span data-ttu-id="c8ee8-124">Parola ihlal edilmesi durumunda uygulama rolleri yalnızca gerekli izinleri verilmelidir.</span><span class="sxs-lookup"><span data-stu-id="c8ee8-124">Application roles should be granted only required permissions in case the password is compromised.</span></span> <span data-ttu-id="c8ee8-125">İzinleri `public` rol bir uygulama rolü kullanarak herhangi bir veritabanında iptal.</span><span class="sxs-lookup"><span data-stu-id="c8ee8-125">Permissions to the `public` role should be revoked in any database using an application role.</span></span> <span data-ttu-id="c8ee8-126">Devre dışı `guest` herhangi bir veritabanı hesabı erişmesini Arayanların uygulama rolünün istemiyorsanız.</span><span class="sxs-lookup"><span data-stu-id="c8ee8-126">Disable the `guest` account in any database you do not want callers of the application role to have access to.</span></span>  
  
### <a name="application-role-enhancements"></a><span data-ttu-id="c8ee8-127">Uygulama rolü geliştirmeleri</span><span class="sxs-lookup"><span data-stu-id="c8ee8-127">Application Role Enhancements</span></span>  
 <span data-ttu-id="c8ee8-128">Yürütme bağlamı bağlantı havuzu devre dışı bırakmak için gereken kaldırma bir uygulama rolü etkinleştirdikten sonra özgün çağırana değiştirilebilir.</span><span class="sxs-lookup"><span data-stu-id="c8ee8-128">The execution context can be switched back to the original caller after activating an application role, removing the need to disable connection pooling.</span></span> <span data-ttu-id="c8ee8-129">`sp_setapprole` Yordamı çağıran hakkında bağlam bilgilerini içeren bir tanımlama bilgisi oluşturur Yeni bir seçenek vardır.</span><span class="sxs-lookup"><span data-stu-id="c8ee8-129">The `sp_setapprole` procedure has a new option that creates a cookie, which contains context information about the caller.</span></span> <span data-ttu-id="c8ee8-130">Çağırarak oturum döndürebilirsiniz `sp_unsetapprole` yordamı, tanımlama bilgisi geçirme.</span><span class="sxs-lookup"><span data-stu-id="c8ee8-130">You can revert the session by calling the `sp_unsetapprole` procedure, passing it the cookie.</span></span>  
  
## <a name="application-role-alternatives"></a><span data-ttu-id="c8ee8-131">Uygulama rolü alternatifleri</span><span class="sxs-lookup"><span data-stu-id="c8ee8-131">Application Role Alternatives</span></span>  
 <span data-ttu-id="c8ee8-132">Uygulama rolleri olası bir güvenlik açığı sunan bir parola güvenlik üzerinde bağlıdır.</span><span class="sxs-lookup"><span data-stu-id="c8ee8-132">Application roles depend on the security of a password, which presents a potential security vulnerability.</span></span> <span data-ttu-id="c8ee8-133">Parolalar uygulama kodunda katıştırılmış tarafından kullanıma sunulan veya diske kaydedilir.</span><span class="sxs-lookup"><span data-stu-id="c8ee8-133">Passwords may be exposed by being embedded in application code or saved on disk.</span></span>  
  
 <span data-ttu-id="c8ee8-134">Aşağıdaki alternatifleri isteyebilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="c8ee8-134">You may want to consider the following alternatives.</span></span>  
  
-   <span data-ttu-id="c8ee8-135">Kullanım bağlam EXECUTE AS değiştirme NO REVERT ve tanımlama bilgisi ile onun yan tümceleri deyimiyle.</span><span class="sxs-lookup"><span data-stu-id="c8ee8-135">Use context switching with the EXECUTE AS statement with its NO REVERT and WITH COOKIE clauses.</span></span> <span data-ttu-id="c8ee8-136">Bir oturum eşlenmemiş bir veritabanında bir kullanıcı hesabı oluşturabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="c8ee8-136">You can create a user account in a database that is not mapped to a login.</span></span> <span data-ttu-id="c8ee8-137">Ardından bu hesap için izinleri atayın.</span><span class="sxs-lookup"><span data-stu-id="c8ee8-137">You then assign permissions to this account.</span></span> <span data-ttu-id="c8ee8-138">Çünkü izni tabanlı, parola tabanlı oturum açma daha az kullanıcıyla EXECUTE AS kullanarak daha güvenlidir.</span><span class="sxs-lookup"><span data-stu-id="c8ee8-138">Using EXECUTE AS with a login-less user is more secure because it is permission-based, not password-based.</span></span> <span data-ttu-id="c8ee8-139">Daha fazla bilgi için bkz: [kimliğe bürünme SQL Server'daki özelleştirme izinlerle](../../../../../docs/framework/data/adonet/sql/customizing-permissions-with-impersonation-in-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="c8ee8-139">For more information, see [Customizing Permissions with Impersonation in SQL Server](../../../../../docs/framework/data/adonet/sql/customizing-permissions-with-impersonation-in-sql-server.md).</span></span>  
  
-   <span data-ttu-id="c8ee8-140">Saklı yordamlar yordamları yürütmek için yalnızca izin verme sertifikaları ile oturum açın.</span><span class="sxs-lookup"><span data-stu-id="c8ee8-140">Sign stored procedures with certificates, granting only permission to execute the procedures.</span></span> <span data-ttu-id="c8ee8-141">Daha fazla bilgi için bkz: [imzalama saklı yordamlar SQL Server'daki](../../../../../docs/framework/data/adonet/sql/signing-stored-procedures-in-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="c8ee8-141">For more information, see [Signing Stored Procedures in SQL Server](../../../../../docs/framework/data/adonet/sql/signing-stored-procedures-in-sql-server.md).</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="c8ee8-142">Dış Kaynaklar</span><span class="sxs-lookup"><span data-stu-id="c8ee8-142">External Resources</span></span>  
 <span data-ttu-id="c8ee8-143">Daha fazla bilgi için aşağıdaki kaynaklara bakın.</span><span class="sxs-lookup"><span data-stu-id="c8ee8-143">For more information, see the following resources.</span></span>  
  
|<span data-ttu-id="c8ee8-144">Kaynak</span><span class="sxs-lookup"><span data-stu-id="c8ee8-144">Resource</span></span>|<span data-ttu-id="c8ee8-145">Açıklama</span><span class="sxs-lookup"><span data-stu-id="c8ee8-145">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="c8ee8-146">[Uygulama rolleri](http://msdn.microsoft.com/library/ms190998.aspx) SQL Server Çevrimiçi Kitapları'nda</span><span class="sxs-lookup"><span data-stu-id="c8ee8-146">[Application Roles](http://msdn.microsoft.com/library/ms190998.aspx) in SQL Server Books Online</span></span>|<span data-ttu-id="c8ee8-147">Oluşturmayı ve SQL Server 2008'de uygulama rolleri kullanmayı açıklar.</span><span class="sxs-lookup"><span data-stu-id="c8ee8-147">Describes how to create and use application roles in SQL Server 2008.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c8ee8-148">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="c8ee8-148">See Also</span></span>  
 [<span data-ttu-id="c8ee8-149">ADO.NET uygulamalarının güvenliğini sağlama</span><span class="sxs-lookup"><span data-stu-id="c8ee8-149">Securing ADO.NET Applications</span></span>](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [<span data-ttu-id="c8ee8-150">SQL Server güvenlik genel bakış</span><span class="sxs-lookup"><span data-stu-id="c8ee8-150">Overview of SQL Server Security</span></span>](../../../../../docs/framework/data/adonet/sql/overview-of-sql-server-security.md)  
 [<span data-ttu-id="c8ee8-151">SQL Server'daki uygulama güvenlik senaryoları</span><span class="sxs-lookup"><span data-stu-id="c8ee8-151">Application Security Scenarios in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)  
 [<span data-ttu-id="c8ee8-152">ADO.NET yönetilen sağlayıcıları ve veri kümesi Geliştirici Merkezi</span><span class="sxs-lookup"><span data-stu-id="c8ee8-152">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)