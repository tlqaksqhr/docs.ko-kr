---
title: "For 루프 제어 변수를 통해 선언되는 배열은 초기 크기를 지정하여 선언할 수 없습니다."
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc32039
- bc32039
helpviewer_keywords: BC32039
ms.assetid: 1d8b6560-c9eb-4b71-a038-24c6f5a5ce46
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ef36f14d5323a4592afe59573e249d8cfb218df9
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="array-declared-as-for-loop-control-variable-cannot-be-declared-with-an-initial-size"></a><span data-ttu-id="f53d5-102">For 루프 제어 변수를 통해 선언되는 배열은 초기 크기를 지정하여 선언할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f53d5-102">Array declared as for loop control variable cannot be declared with an initial size</span></span>
<span data-ttu-id="f53d5-103">A `For Each` 루프는 배열을 사용 하 여 해당 *요소* 반복 변수는 있지만 해당 배열을 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="f53d5-103">A `For Each` loop uses an array as its *element* iteration variable but initializes that array.</span></span>  
  
 <span data-ttu-id="f53d5-104">다음 문에서이 오류를 생성 될 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f53d5-104">The following statements show how this error can be generated.</span></span>  
  
```  
Dim arrayList As New List(Of Integer())  
For Each listElement() As Integer In arrayList  
For Each listElement(1) As Integer In arrayList  
```  
  
 <span data-ttu-id="f53d5-105">첫 번째 `For Each` 문에 요소에 액세스 하는 올바른 방법은 `arrayList`합니다.</span><span class="sxs-lookup"><span data-stu-id="f53d5-105">The first `For Each` statement is the correct way to access elements of `arrayList`.</span></span> <span data-ttu-id="f53d5-106">두 번째 `For Each` 문은이 오류를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="f53d5-106">The second `For Each` statement generates this error.</span></span>  
  
 <span data-ttu-id="f53d5-107">**오류 ID:** BC32039</span><span class="sxs-lookup"><span data-stu-id="f53d5-107">**Error ID:** BC32039</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f53d5-108">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="f53d5-108">To correct this error</span></span>  
  
-   <span data-ttu-id="f53d5-109">선언에서 초기화를 제거는 *요소* 반복 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="f53d5-109">Remove the initialization from the declaration of the *element* iteration variable.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f53d5-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f53d5-110">See Also</span></span>  
 [<span data-ttu-id="f53d5-111">For...Next 문</span><span class="sxs-lookup"><span data-stu-id="f53d5-111">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [<span data-ttu-id="f53d5-112">배열</span><span class="sxs-lookup"><span data-stu-id="f53d5-112">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [<span data-ttu-id="f53d5-113">컬렉션</span><span class="sxs-lookup"><span data-stu-id="f53d5-113">Collections</span></span>](../../../standard/collections/index.md)
