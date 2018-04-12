---
title: 범위 변수 이름은 인수가 없는 단순한 이름 또는 정규화된 이름에서만 유추할 수 있습니다.
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc36599
- bc36599
helpviewer_keywords:
- BC36599
ms.assetid: 17763dbe-f74f-4ccb-8086-cb7e45ec4d12
caps.latest.revision: 6
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5c986fcf188482c526c53ddf3019cec5163d0b62
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="range-variable-name-can-be-inferred-only-from-a-simple-or-qualified-name-with-no-arguments"></a><span data-ttu-id="f5f6d-102">범위 변수 이름은 인수가 없는 단순한 이름 또는 정규화된 이름에서만 유추할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5f6d-102">Range variable name can be inferred only from a simple or qualified name with no arguments</span></span>
<span data-ttu-id="f5f6d-103">하나 이상의 인수를 사용 하는 프로그래밍 요소는 LINQ 쿼리에서 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5f6d-103">A programming element that takes one or more arguments is included in a LINQ query.</span></span> <span data-ttu-id="f5f6d-104">컴파일러에서 해당 프로그래밍 요소에서 범위 변수를 유추할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f5f6d-104">The compiler is unable to infer a range variable from that programming element.</span></span>  
  
 <span data-ttu-id="f5f6d-105">**오류 ID:** BC36599</span><span class="sxs-lookup"><span data-stu-id="f5f6d-105">**Error ID:** BC36599</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f5f6d-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="f5f6d-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="f5f6d-107">다음 코드에 나와 있는 것 처럼 프로그래밍 요소에 대 한 명시적 변수 이름을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5f6d-107">Supply an explicit variable name for the programming element, as shown in the following code:</span></span>  
  
```  
Dim query = From var1 In collection1   
            Select VariableAlias= SampleFunction(var1), var1  
```  
  
## <a name="see-also"></a><span data-ttu-id="f5f6d-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f5f6d-108">See Also</span></span>  
 [<span data-ttu-id="f5f6d-109">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="f5f6d-109">Introduction to LINQ in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [<span data-ttu-id="f5f6d-110">Select 절</span><span class="sxs-lookup"><span data-stu-id="f5f6d-110">Select Clause</span></span>](../../../visual-basic/language-reference/queries/select-clause.md)
