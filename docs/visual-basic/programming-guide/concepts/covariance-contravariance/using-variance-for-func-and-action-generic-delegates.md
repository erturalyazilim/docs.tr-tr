---
title: "İşlev ve eylem genel temsilciler (Visual Basic) için varyans kullanma"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 36c3012f-b39c-493b-b90f-079b5912ac1b
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b8f9b2ebf758bc0d67b2b623038a4beeb7149261
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="using-variance-for-func-and-action-generic-delegates-visual-basic"></a>İşlev ve eylem genel temsilciler (Visual Basic) için varyans kullanma
Bu örnekler Kovaryans ve kontravaryans nasıl kullanılacağını göstermektedir `Func` ve `Action` yöntemleri kullanılmasını etkinleştirmek ve kodunuzu daha fazla esneklik sağlamak için genel temsilciler.  
  
 Kovaryans ve kontravaryans hakkında daha fazla bilgi için bkz: [Temsilcilerde varyans (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md).  
  
## <a name="using-delegates-with-covariant-type-parameters"></a>Eşdeğişken tür parametreleri ile kullanma  
 Aşağıdaki örnek genel türlerde Kovaryans desteği yararları gösterilmektedir `Func` temsilciler. `FindByTitle` Yöntemi alır, bir parametre `String` yazın ve bir nesne döndürür `Employee` türü. Ancak, bu yönteme atayabilirsiniz `Func(Of String, Person)` çünkü temsilci `Employee` devralır `Person`.  
  
```vb  
' Simple hierarchy of classes.  
Public Class Person  
End Class  
  
Public Class Employee  
    Inherits Person  
End Class  
  
Class Finder  
    Public Shared Function FindByTitle(  
        ByVal title As String) As Employee  
        ' This is a stub for a method that returns  
        ' an employee that has the specified title.  
        Return New Employee  
    End Function  
  
    Sub Test()  
        ' Create an instance of the delegate without using variance.  
        Dim findEmployee As Func(Of String, Employee) =  
            AddressOf FindByTitle  
  
        ' The delegate expects a method to return Person,  
        ' but you can assign it a method that returns Employee.  
        Dim findPerson As Func(Of String, Person) =  
            AddressOf FindByTitle  
  
        ' You can also assign a delegate   
        ' that returns a more derived type to a delegate   
        ' that returns a less derived type.  
        findPerson = findEmployee  
    End Sub  
End Class  
```  
  
## <a name="using-delegates-with-contravariant-type-parameters"></a>Temsilcileri karşıtı tür parametreleri ile kullanma  
 Aşağıdaki örnek genel değişken karşıtı desteği yararları gösterilmektedir `Action` temsilciler. `AddToContacts` Yöntemi alır, bir parametre `Person` türü. Ancak, bu yönteme atayabilirsiniz `Action(Of Employee)` çünkü temsilci `Employee` devralır `Person`.  
  
```vb  
Public Class Person  
End Class  
  
Public Class Employee  
    Inherits Person  
End Class  
  
Class AddressBook  
    Shared Sub AddToContacts(ByVal person As Person)  
        ' This method adds a Person object  
        ' to a contact list.  
    End Sub  
  
    Sub Test()  
        ' Create an instance of the delegate without using variance.  
        Dim addPersonToContacts As Action(Of Person) =  
            AddressOf AddToContacts  
  
        ' The Action delegate expects   
        ' a method that has an Employee parameter,  
        ' but you can assign it a method that has a Person parameter  
        ' because Employee derives from Person.  
        Dim addEmployeeToContacts As Action(Of Employee) =  
            AddressOf AddToContacts  
  
        ' You can also assign a delegate   
        ' that accepts a less derived parameter   
        ' to a delegate that accepts a more derived parameter.  
        addEmployeeToContacts = addPersonToContacts  
    End Sub  
End Class  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kovaryans ve kontravaryans (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/index.md)  
 [Genel türler](~/docs/standard/generics/index.md)
