---
title: "Nasıl yapılır: bir dosyanın derleme (C#) olup olmadığını belirleme"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: ea5186bb-5bff-4dcb-bde9-d6ba4e2edd00
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 3994dfc7a8c4e615072bf415d0497399309072e3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-determine-if-a-file-is-an-assembly-c"></a>Nasıl yapılır: bir dosyanın derleme (C#) olup olmadığını belirleme
Yönetilen ve bir derleme girdi meta verilerinde içerir ve yalnızca, bir dosyanın derleme olup. Derlemeler ve meta veriler hakkında daha fazla bilgi için Ek Yardım konusuna [derleme bildirimi](https://msdn.microsoft.com/library/1w45z383).  
  
### <a name="how-to-manually-determine-if-a-file-is-an-assembly"></a>El ile bir dosyanın derleme olup olmadığını belirleme  
  
1.  Başlat [Ildasm.exe (IL ayrıştırıcı)](https://msdn.microsoft.com/library/f7dy01k1).  
  
2.  Test etmek istediğiniz dosya yükleyin.  
  
3.  Varsa **ILDASM** dosya taşınabilir yürütülebilir (PE) dosyası değil ve ardından bir derleme değil raporlar. Daha fazla bilgi için Ek Yardım konusuna [nasıl yapılır: derleme içeriği görüntüle](../../../../framework/app-domains/how-to-view-assembly-contents.md).  
  
### <a name="how-to-programmatically-determine-if-a-file-is-an-assembly"></a>Program aracılığıyla bir dosyanın derleme olup olmadığını belirleme  
  
1.  Çağrı <xref:System.Reflection.AssemblyName.GetAssemblyName%2A> yöntemi, test dosyasının adını ve tam dosya yolunu geçirme.  
  
2.  Varsa bir <xref:System.BadImageFormatException> özel durum, dosya bir derleme değil.  
  
## <a name="example"></a>Örnek  
 Bu örnek bir DLL derleme olup olmadığını görmek için sınar.  
  
```  
class TestAssembly  
{  
    static void Main()  
    {  
  
        try  
        {  
            System.Reflection.AssemblyName testAssembly =  
                System.Reflection.AssemblyName.GetAssemblyName(@"C:\Windows\Microsoft.NET\Framework\v3.5\System.Net.dll");  
  
            System.Console.WriteLine("Yes, the file is an assembly.");  
        }  
  
        catch (System.IO.FileNotFoundException)  
        {  
            System.Console.WriteLine("The file cannot be found.");  
        }  
  
        catch (System.BadImageFormatException)  
        {  
            System.Console.WriteLine("The file is not an assembly.");  
        }  
  
        catch (System.IO.FileLoadException)  
        {  
            System.Console.WriteLine("The assembly has already been loaded.");  
        }  
    }  
}  
/* Output (with .NET Framework 3.5 installed):  
    Yes, the file is an assembly.  
*/  
```  
  
 <xref:System.Reflection.AssemblyName.GetAssemblyName%2A> Yöntemi test dosyasını yükler ve bilgileri okuyun sonra yayımlar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Reflection.AssemblyName>  
 [C# programlama kılavuzu](../../../../csharp/programming-guide/index.md)  
 [Derlemeler ve Genel Derleme Önbelleği (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/index.md)
