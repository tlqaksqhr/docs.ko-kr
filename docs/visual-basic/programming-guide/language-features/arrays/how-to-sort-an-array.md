---
title: "방법: Visual Basic에서 배열 정렬"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: Array.Sort
helpviewer_keywords:
- arrays [Visual Basic], sorting
- examples [Visual Basic], arrays
ms.assetid: 9289aeaa-9626-4698-94a7-1d1fd3702b87
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 310c2dacb384de49c80073840c6c58d37f3937d9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-sort-an-array-in-visual-basic"></a><span data-ttu-id="b2e54-102">방법: Visual Basic에서 배열 정렬</span><span class="sxs-lookup"><span data-stu-id="b2e54-102">How to: Sort An Array in Visual Basic</span></span>
<span data-ttu-id="b2e54-103">이 예제에서는 배열을 선언 `String` 개체의 명명 된 `zooAnimals`, 채운 다음 사전순으로 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2e54-103">This example declares an array of `String` objects named `zooAnimals`, populates it, and then sorts it alphabetically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b2e54-104">예제</span><span class="sxs-lookup"><span data-stu-id="b2e54-104">Example</span></span>  
  
```  
Private Sub sortAnimals()  
    Dim zooAnimals(2) As String  
    zooAnimals(0) = "lion"  
    zooAnimals(1) = "turtle"  
    zooAnimals(2) = "ostrich"  
    Array.Sort(zooAnimals)  
End Sub  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b2e54-105">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="b2e54-105">Compiling the Code</span></span>  
 <span data-ttu-id="b2e54-106">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b2e54-106">This example requires:</span></span>  
  
-   <span data-ttu-id="b2e54-107">Mscorlib.dll에 대 한 액세스 및 <xref:System> 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="b2e54-107">Access to Mscorlib.dll and the <xref:System> namespace.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="b2e54-108">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="b2e54-108">Robust Programming</span></span>  
 <span data-ttu-id="b2e54-109">다음 조건에서 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="b2e54-109">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="b2e54-110">배열이 비어 있는 (<xref:System.ArgumentNullException> 클래스)</span><span class="sxs-lookup"><span data-stu-id="b2e54-110">Array is empty (<xref:System.ArgumentNullException> class)</span></span>  
  
-   <span data-ttu-id="b2e54-111">배열이 다차원 (<xref:System.RankException> 클래스)</span><span class="sxs-lookup"><span data-stu-id="b2e54-111">Array is multidimensional (<xref:System.RankException> class)</span></span>  
  
-   <span data-ttu-id="b2e54-112">배열의 하나 이상의 요소를 구현 하지 않습니다는 <xref:System.IComparable> 인터페이스 (<xref:System.InvalidOperationException> 클래스)</span><span class="sxs-lookup"><span data-stu-id="b2e54-112">One or more elements of the array do not implement the <xref:System.IComparable> interface (<xref:System.InvalidOperationException> class)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2e54-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b2e54-113">See Also</span></span>  
 <xref:System.Array.Sort%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="b2e54-114">배열</span><span class="sxs-lookup"><span data-stu-id="b2e54-114">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [<span data-ttu-id="b2e54-115">배열 문제 해결</span><span class="sxs-lookup"><span data-stu-id="b2e54-115">Troubleshooting Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)  
 [<span data-ttu-id="b2e54-116">컬렉션</span><span class="sxs-lookup"><span data-stu-id="b2e54-116">Collections</span></span>](http://msdn.microsoft.com/library/e76533a9-5033-4a0b-b003-9c2be60d185b)  
 [<span data-ttu-id="b2e54-117">For Each...Next 문</span><span class="sxs-lookup"><span data-stu-id="b2e54-117">For Each...Next Statement</span></span>](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)
