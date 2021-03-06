---
title: "using Deyimi (C# Başvurusu)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: using statement [C#]
ms.assetid: afc355e6-f0b9-4240-94dd-0d93f17d9fc3
caps.latest.revision: "31"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 1fdf37e1bfc57bf850b332f167e57d3e05d23e78
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2017
---
# <a name="using-statement-c-reference"></a>using Deyimi (C# Başvurusu)
Doğru kullanımı sağlar kullanışlı bir sözdizimi sağlar <xref:System.IDisposable> nesneleri.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kullanarak kullanmayı gösterir deyimi.  
  
 [!code-csharp[csrefKeywordsNamespace#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_1.cs)]  
  
## <a name="remarks"></a>Açıklamalar  
 <xref:System.IO.File>ve <xref:System.Drawing.Font> yönetilmeyen kaynaklara (Bu örnek dosya tanıtıcıları ve cihaz bağlamları) erişim yönetilen türlerine örnek olarak verilebilir. Yönetilmeyen kaynakları ve bunları saklayan sınıf kitaplığı türleri pek çok değişik vardır. Tüm türleri uygulamalıdır <xref:System.IDisposable> arabirimi.  
  
Zaman ömrü bir `IDisposable` nesnesidir tek bir yöntem sınırlı, bildirme ve içinde örneği bir `using` deyimi. `using` Deyimi çağrıları <xref:System.IDisposable.Dispose%2A> doğru bir şekilde ve (daha önce gösterildiği gibi kullandığınız zaman) nesnesi üzerinde yöntemi de neden nesnenin kendisini kapsamının dışına gitmek için hemen <xref:System.IDisposable.Dispose%2A> olarak adlandırılır. İçinde `using` bloğu, nesneyi salt okunur ve yeniden atandığında veya değiştirilemez.  
  
 `using` Deyimi sağlar <xref:System.IDisposable.Dispose%2A> dahi nesnede yöntemleri çağırma bir özel durum oluşursa çağrılır. Try bloğunun bir nesne koyma ve ardından çağırma aynı sonucu elde edebilirsiniz <xref:System.IDisposable.Dispose%2A> içinde bir finally bloğunda; aslında, bu nasıl `using` deyimi derleyici tarafından çevrilir. Kod örneği, aşağıdaki kodu önceden derleme zamanında genişletir. (nesne için sınırlı kapsamı oluşturmak için ek süslü ayraçlar unutmayın):  
  
 [!code-csharp[csrefKeywordsNamespace#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_2.cs)]  
  
 Bir türde birden çok örneği içinde bildirilen bir `using` aşağıdaki örnekte gösterildiği gibi deyimi.  
  
 [!code-csharp[csrefKeywordsNamespace#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_3.cs)]  
  
 Kaynak nesne örneği ve daha sonra değişkeni geçirin `using` deyimi değildir, ancak bu en iyi yöntem. Bu durumda, nesne denetimi terk sonra kapsam içinde kalır `using` rağmen büyük olasılıkla artık yönetilmeyen kaynaklarına erişebilir engelleyin. Diğer bir deyişle, onu artık tam olarak başlatılır. Nesne dışında kullanmayı denerseniz `using` engellemek, bir özel durum oluşturulmasına neden risk. Bu nedenle, nesne örneğini oluşturmak genellikle daha iyi `using` deyimi ve bunun kapsamına sınırlamak `using` bloğu.  
  
 [!code-csharp[csrefKeywordsNamespace#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-statement_4.cs)]  
  
Atma hakkında daha fazla bilgi için `IDisposable` nesneleri bkz [IDisposable uygulayan nesneler kullanma](../../../standard/garbage-collection/using-objects.md).

## <a name="c-language-specification"></a>C# Dil Belirtimi  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C# başvurusu](../../../csharp/language-reference/index.md)  
 [C# programlama kılavuzu](../../../csharp/programming-guide/index.md)  
 [C# anahtar sözcükleri](../../../csharp/language-reference/keywords/index.md)  
 [using yönergesi](../../../csharp/language-reference/keywords/using-directive.md)  
 [Çöp toplama](../../../standard/garbage-collection/index.md)  
 [IDisposable uygulayan nesneler kullanma](../../../standard/garbage-collection/using-objects.md)  
 [IDisposable arabirimi](xref:System.IDisposable)
