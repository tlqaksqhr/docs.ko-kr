---
title: 범위 변수 이름은 인수가 없는 단순한 이름 또는 정규화된 이름에서만 유추할 수 있습니다.
ms.date: 07/20/2015
f1_keywords:
- vbc36599
- bc36599
helpviewer_keywords:
- BC36599
ms.assetid: 17763dbe-f74f-4ccb-8086-cb7e45ec4d12
ms.openlocfilehash: d6d082511d501b961b537317f0cb17bcd1c9370b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33594623"
---
# <a name="range-variable-name-can-be-inferred-only-from-a-simple-or-qualified-name-with-no-arguments"></a><span data-ttu-id="856db-102">범위 변수 이름은 인수가 없는 단순한 이름 또는 정규화된 이름에서만 유추할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="856db-102">Range variable name can be inferred only from a simple or qualified name with no arguments</span></span>
<span data-ttu-id="856db-103">하나 이상의 인수를 사용 하는 프로그래밍 요소는 LINQ 쿼리에서 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="856db-103">A programming element that takes one or more arguments is included in a LINQ query.</span></span> <span data-ttu-id="856db-104">컴파일러에서 해당 프로그래밍 요소에서 범위 변수를 유추할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="856db-104">The compiler is unable to infer a range variable from that programming element.</span></span>  
  
 <span data-ttu-id="856db-105">**오류 ID:** BC36599</span><span class="sxs-lookup"><span data-stu-id="856db-105">**Error ID:** BC36599</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="856db-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="856db-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="856db-107">다음 코드에 나와 있는 것 처럼 프로그래밍 요소에 대 한 명시적 변수 이름을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="856db-107">Supply an explicit variable name for the programming element, as shown in the following code:</span></span>  
  
```  
Dim query = From var1 In collection1   
            Select VariableAlias= SampleFunction(var1), var1  
```  
  
## <a name="see-also"></a><span data-ttu-id="856db-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="856db-108">See Also</span></span>  
 [<span data-ttu-id="856db-109">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="856db-109">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="856db-110">Select 절</span><span class="sxs-lookup"><span data-stu-id="856db-110">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
