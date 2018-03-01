---
title: "방법: 개체의 초기화 지연 수행"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lazy initialization in .NET, how to perform
ms.assetid: 8cd68620-dcc3-4f20-8835-c728a6820e71
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1728165dbed9a011afe6e621df86be7b372a684f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-perform-lazy-initialization-of-objects"></a><span data-ttu-id="2cd2d-102">방법: 개체의 초기화 지연 수행</span><span class="sxs-lookup"><span data-stu-id="2cd2d-102">How to: Perform Lazy Initialization of Objects</span></span>
<span data-ttu-id="2cd2d-103"><xref:System.Lazy%601?displayProperty=nameWithType> 클래스는 개체의 인스턴스화 및 초기화 지연을 수행하는 작업을 간소화합니다.</span><span class="sxs-lookup"><span data-stu-id="2cd2d-103">The <xref:System.Lazy%601?displayProperty=nameWithType> class simplifies the work of performing lazy initialization and instantiation of objects.</span></span> <span data-ttu-id="2cd2d-104">지연 방식으로 개체를 초기화하면 개체가 필요하지 않을 경우 개체를 전혀 만들지 않아도 되고, 필요한 경우에도 개체에 처음 액세스할 때까지 초기화를 연기할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cd2d-104">By initializing objects in a lazy manner, you can avoid having to create them at all if they are never needed, or you can postpone their initialization until they are first accessed.</span></span> <span data-ttu-id="2cd2d-105">자세한 내용은 [초기화 지연](../../../docs/framework/performance/lazy-initialization.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2cd2d-105">For more information, see [Lazy Initialization](../../../docs/framework/performance/lazy-initialization.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2cd2d-106">예</span><span class="sxs-lookup"><span data-stu-id="2cd2d-106">Example</span></span>  
 <span data-ttu-id="2cd2d-107">다음 예제에서는 <xref:System.Lazy%601>로 값을 초기화하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2cd2d-107">The following example shows how to initialize a value with <xref:System.Lazy%601>.</span></span> <span data-ttu-id="2cd2d-108">`someCondition` 변수를 true 또는 false로 설정하는 일부 기타 코드에 따라 지연 변수가 필요하지 않을 수 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="2cd2d-108">Assume that the lazy variable might not be needed, depending on some other code that sets the `someCondition` variable to true or false.</span></span>  
  
```vb  
Dim someCondition As Boolean = False  
  
Sub Main()  
    'Initializing a value with a big computation, computed in parallel  
    Dim _data As Lazy(Of Integer) = New Lazy(Of Integer)(Function()  
                                                             Dim result =  
                                                                 ParallelEnumerable.Range(0, 1000).  
                                                                 Aggregate(Function(x, y)  
                                                                               Return x + y  
                                                                           End Function)  
                                                             Return result  
                                                         End Function)  
  
    '  do work that may or may not set someCondition to True  
    ' ...  
    '  Initialize the data only if needed  
    If someCondition = True Then  
  
        If (_data.Value > 100) Then  
  
            Console.WriteLine("Good data")  
        End If  
    End If  
End Sub  
```  
  
```csharp  
  static bool someCondition = false;    
  //Initializing a value with a big computation, computed in parallel  
  Lazy<int> _data = new Lazy<int>(delegate  
  {  
      return ParallelEnumerable.Range(0, 1000).  
          Select(i => Compute(i)).Aggregate((x,y) => x + y);  
  }, LazyExecutionMode.EnsureSingleThreadSafeExecution);  
  
  // Do some work that may or may not set someCondition to true.  
  //  ...  
  // Initialize the data only if necessary  
  if (someCondition)  
{  
    if (_data.Value > 100)  
      {  
          Console.WriteLine("Good data");  
      }  
}  
```  
  
## <a name="example"></a><span data-ttu-id="2cd2d-109">예</span><span class="sxs-lookup"><span data-stu-id="2cd2d-109">Example</span></span>  
 <span data-ttu-id="2cd2d-110">다음 예제에서는 <xref:System.Threading.ThreadLocal%601?displayProperty=nameWithType> 클래스를 사용하여 현재 스레드의 현재 개체 인스턴스에만 표시되는 형식을 초기화하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2cd2d-110">The following example shows how to use the <xref:System.Threading.ThreadLocal%601?displayProperty=nameWithType> class to initialize a type that is visible only to the current object instance on the current thread.</span></span>  
  
 [!code-csharp[CDS#13](../../../samples/snippets/csharp/VS_Snippets_Misc/cds/cs/cds2.cs#13)]
 [!code-vb[CDS#13](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds/vb/lazyhowto.vb#13)]  
  
## <a name="see-also"></a><span data-ttu-id="2cd2d-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2cd2d-111">See Also</span></span>  
 <xref:System.Threading.LazyInitializer?displayProperty=nameWithType>  
 [<span data-ttu-id="2cd2d-112">초기화 지연</span><span class="sxs-lookup"><span data-stu-id="2cd2d-112">Lazy Initialization</span></span>](../../../docs/framework/performance/lazy-initialization.md)
