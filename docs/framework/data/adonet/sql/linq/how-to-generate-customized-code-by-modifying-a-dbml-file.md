---
title: "Nasıl yapılır: DBML dosyasını değiştirerek özelleştirilmiş kod oluşturma"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 50ad597a-8598-42d3-82dd-fc7d702ebc37
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 743e938df0b9c7f12a9c3a11a4b5558137add529
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-generate-customized-code-by-modifying-a-dbml-file"></a><span data-ttu-id="493d6-102">Nasıl yapılır: DBML dosyasını değiştirerek özelleştirilmiş kod oluşturma</span><span class="sxs-lookup"><span data-stu-id="493d6-102">How to: Generate Customized Code by Modifying a DBML File</span></span>
<span data-ttu-id="493d6-103">Oluşturabileceğiniz [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] veya C# kaynak kodu bir veritabanı işaretleme dili (.dbml) meta veri dosyasından.</span><span class="sxs-lookup"><span data-stu-id="493d6-103">You can generate [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] or C# source code from a database markup language (.dbml) metadata file.</span></span> <span data-ttu-id="493d6-104">Bu yaklaşım uygulama eşleme kodu oluşturmadan önce varsayılan .dbml dosyasını özelleştirmek için bir fırsat sunar.</span><span class="sxs-lookup"><span data-stu-id="493d6-104">This approach provides an opportunity to customize the default .dbml file before you generate the application mapping code.</span></span> <span data-ttu-id="493d6-105">Bu gelişmiş bir özelliktir.</span><span class="sxs-lookup"><span data-stu-id="493d6-105">This is an advanced feature.</span></span>  
  
 <span data-ttu-id="493d6-106">Bu işlemdeki adımlar aşağıdaki gibidir:</span><span class="sxs-lookup"><span data-stu-id="493d6-106">The steps in this process are as follows:</span></span>  
  
1.  <span data-ttu-id="493d6-107">Bir .dbml dosyası oluşturun.</span><span class="sxs-lookup"><span data-stu-id="493d6-107">Generate a .dbml file.</span></span>  
  
2.  <span data-ttu-id="493d6-108">.Dbml dosyasını değiştirmek için bir düzenleyici kullanın.</span><span class="sxs-lookup"><span data-stu-id="493d6-108">Use an editor to modify the .dbml file.</span></span> <span data-ttu-id="493d6-109">.Dbml dosyanın şema tanımını (.xsd) dosyası için karşı doğrulamalısınız Not [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] .dbml dosyaları.</span><span class="sxs-lookup"><span data-stu-id="493d6-109">Note that the .dbml file must validate against the schema definition (.xsd) file for [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] .dbml files.</span></span> <span data-ttu-id="493d6-110">Daha fazla bilgi için bkz: [LINQ-SQL kod oluşturma](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).</span><span class="sxs-lookup"><span data-stu-id="493d6-110">For more information, see [Code Generation in LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).</span></span>  
  
3.  <span data-ttu-id="493d6-111">Oluştur [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] veya C# kaynak kodu.</span><span class="sxs-lookup"><span data-stu-id="493d6-111">Generate the [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] or C# source code.</span></span>  
  
 <span data-ttu-id="493d6-112">Aşağıdaki örnekler SQLMetal komut satırı aracını kullanın.</span><span class="sxs-lookup"><span data-stu-id="493d6-112">The following examples use the SQLMetal command-line tool.</span></span> <span data-ttu-id="493d6-113">Daha fazla bilgi için bkz: [SqlMetal.exe (kod üretme aracı)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span><span class="sxs-lookup"><span data-stu-id="493d6-113">For more information, see [SqlMetal.exe (Code Generation Tool)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="493d6-114">Örnek</span><span class="sxs-lookup"><span data-stu-id="493d6-114">Example</span></span>  
 <span data-ttu-id="493d6-115">Aşağıdaki kod, Northwind örnek veritabanından .dbml dosyası oluşturur.</span><span class="sxs-lookup"><span data-stu-id="493d6-115">The following code generates a .dbml file from the Northwind sample database.</span></span> <span data-ttu-id="493d6-116">Veritabanı meta veriler için kaynak olarak veritabanının adını veya .mdf dosyasının adını kullanabilirsiniz.</span><span class="sxs-lookup"><span data-stu-id="493d6-116">As source for the database metadata, you can use either the name of the database or the name of the .mdf file.</span></span>  
  
```  
sqlmetal /server:myserver /database:northwind /dbml:mymeta.dbml  
sqlmetal /dbml:mymeta.dbml mydbfile.mdf  
```  
  
## <a name="example"></a><span data-ttu-id="493d6-117">Örnek</span><span class="sxs-lookup"><span data-stu-id="493d6-117">Example</span></span>  
 <span data-ttu-id="493d6-118">Aşağıdaki kod oluşturur [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] veya C# kaynak kodu dosyasının .dbml dosyasından.</span><span class="sxs-lookup"><span data-stu-id="493d6-118">The following code generates [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] or C# source code file from a .dbml file.</span></span>  
  
```  
sqlmetal /namespace:nwind /code:nwind.vb /language:vb DBMLFile.dbml  
sqlmetal /namespace:nwind /code:nwind.cs /language:csharp DBMLFile.dbml  
```  
  
## <a name="see-also"></a><span data-ttu-id="493d6-119">Ayrıca Bkz.</span><span class="sxs-lookup"><span data-stu-id="493d6-119">See Also</span></span>  
 [<span data-ttu-id="493d6-120">LINQ-SQL kod oluşturma</span><span class="sxs-lookup"><span data-stu-id="493d6-120">Code Generation in LINQ to SQL</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md)  
 [<span data-ttu-id="493d6-121">SqlMetal.exe (kod üretme aracı)</span><span class="sxs-lookup"><span data-stu-id="493d6-121">SqlMetal.exe (Code Generation Tool)</span></span>](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)  
 [<span data-ttu-id="493d6-122">Nesne modeli oluşturma</span><span class="sxs-lookup"><span data-stu-id="493d6-122">Creating the Object Model</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)