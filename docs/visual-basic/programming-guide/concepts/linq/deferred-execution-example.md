---
title: "지연된 실행 예제 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9a22bea1-c755-4aac-800a-fcd9e5107ace
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a4d2146901d9282b0df706b483afef79f714f660
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="deferred-execution-example-visual-basic"></a><span data-ttu-id="b23a1-102">지연된 실행 예제 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b23a1-102">Deferred Execution Example (Visual Basic)</span></span>
<span data-ttu-id="b23a1-103">이 항목에서는 지연된 실행과 지연 계산이 LINQ to XML 쿼리의 실행에 미치는 영향을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b23a1-103">This topic shows how deferred execution and lazy evaluation affect the execution of your LINQ to XML queries.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b23a1-104">예제</span><span class="sxs-lookup"><span data-stu-id="b23a1-104">Example</span></span>  
 <span data-ttu-id="b23a1-105">다음 예제에서는 지연된 실행을 사용하는 확장 메서드를 사용하는 경우의 실행 순서를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b23a1-105">The following example shows the order of execution when using an extension method that uses deferred execution.</span></span> <span data-ttu-id="b23a1-106">이 예제에서는 세 문자열의 배열을 선언한 다음</span><span class="sxs-lookup"><span data-stu-id="b23a1-106">The example declares an array of three strings.</span></span> <span data-ttu-id="b23a1-107">`ConvertCollectionToUpperCase`에서 반환하는 컬렉션을 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="b23a1-107">It then iterates through the collection returned by `ConvertCollectionToUpperCase`.</span></span>  
  
```vb  
Imports System.Runtime.CompilerServices  
  
Module Module1  
  
    <Extension()>  
    Private Iterator Function ConvertCollectionToUpperCase(  
    ByVal source As IEnumerable(Of String)) _  
    As IEnumerable(Of String)   
        For Each str As String In source  
            Console.WriteLine("ToUpper: source {0}", str)   
            Yield str.ToUpper()  
        Next  
    End Function  
  
    Sub Main()  
        Dim stringArray = New String() {"abc", "def", "ghi"}  
  
        Dim q = From str In stringArray.ConvertCollectionToUpperCase()  
                Select str  
  
        For Each Str As String In q  
            Console.WriteLine("Main: str {0}", Str)   
        Next  
    End Sub  
  
End Module  
```  
  
 <span data-ttu-id="b23a1-108">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="b23a1-108">This example produces the following output:</span></span>  
  
```  
ToUpper: source abc  
Main: str ABC  
ToUpper: source def  
Main: str DEF  
ToUpper: source ghi  
Main: str GHI  
```  
  
 <span data-ttu-id="b23a1-109">`ConvertCollectionToUpperCase`에서 반환하는 컬렉션을 반복할 때 각 항목이 소스 문자열 배열에서 검색되어 대문자로 변환된 후 다음 항목이 소스 문자열 배열에서 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="b23a1-109">Notice that when iterating through the collection returned by `ConvertCollectionToUpperCase`, each item is retrieved from the source string array and converted to uppercase before the next item is retrieved from the source string array.</span></span>  
  
 <span data-ttu-id="b23a1-110">반환된 컬렉션의 각 항목이 `foreach`의 `Main` 루프에서 처리되기 전에는 문자열의 전체 배열이 대문자로 변환되지 않는 것을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b23a1-110">You can see that the entire array of strings is not converted to uppercase before each item in the returned collection is processed in the `foreach` loop in `Main`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b23a1-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b23a1-111">See Also</span></span>  
 [<span data-ttu-id="b23a1-112">자습서: 지연 된 실행 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b23a1-112">Tutorial: Deferred Execution (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/tutorial-deferred-execution.md)
