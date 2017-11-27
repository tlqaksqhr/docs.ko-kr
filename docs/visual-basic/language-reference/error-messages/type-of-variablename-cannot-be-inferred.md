---
title: "유형의 &#39; &lt;variablename&gt;&#39; 루프 범위와 단계 변수가 같은 형식으로 확대 되지 않으므로 유추할 수 없습니다."
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30982
- vbc30982
helpviewer_keywords: BC30982
ms.assetid: 741e85d9-a747-42ad-a1e1-a3f1928aaff5
caps.latest.revision: "30"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 022e29e38a93d2880bbfa250e65a8b95b39ff140
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="type-of-39ltvariablenamegt39-cannot-be-inferred-because-the-loop-bounds-and-the-step-variable-do-not-widen-to-the-same-type"></a><span data-ttu-id="c1738-102">유형의 &#39; &lt;variablename&gt;&#39; 루프 범위와 단계 변수가 같은 형식으로 확대 되지 않으므로 유추할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c1738-102">Type of &#39;&lt;variablename&gt;&#39; cannot be inferred because the loop bounds and the step variable do not widen to the same type</span></span>
<span data-ttu-id="c1738-103">사용자가 작성 한 `For...Next` 루프는 다음 조건에 해당 하기 때문에 컴파일러가 루프 제어 변수의 데이터 형식을 유추할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c1738-103">You have written a `For...Next` loop in which the compiler cannot infer a data type for the loop control variable because the following conditions are true:</span></span>  
  
-   <span data-ttu-id="c1738-104">`As` 절을 사용하여 루프 제어 변수의 데이터 형식을 지정하지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="c1738-104">The data type of the loop control variable is not specified with an `As` clause.</span></span>  
  
-   <span data-ttu-id="c1738-105">루프 범위와 단계 변수에 두 개 이상의 데이터 형식이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1738-105">The loop bounds and step variable contain at least two data types.</span></span>  
  
-   <span data-ttu-id="c1738-106">데이터 형식 간의 표준 변환이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c1738-106">No standard conversions exist between the data types.</span></span>  
  
 <span data-ttu-id="c1738-107">따라서 컴파일러는 루프 제어 변수의 데이터 형식을 유추할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c1738-107">Therefore, the compiler cannot infer the data type of a loop's control variable.</span></span>  
  
 <span data-ttu-id="c1738-108">다음 예에서 단계 변수는 문자가 고 루프 범위는 모두 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="c1738-108">In the following example, the step variable is a character and the loop bounds are both integers.</span></span> <span data-ttu-id="c1738-109">문자와 정수 간에 변환 작업 없이 표준 이기 때문에이 오류가 보고 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1738-109">Because there is no standard conversion between characters and integers, this error is reported.</span></span>  
  
```vb  
Dim stepVar = "1"c  
Dim m = 0  
Dim n = 20  
  
' Not valid.  
' For i = 1 To 10 Step stepVar  
    ' Loop processing  
' Next  
```  
  
 <span data-ttu-id="c1738-110">**오류 ID:** BC30982</span><span class="sxs-lookup"><span data-stu-id="c1738-110">**Error ID:** BC30982</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c1738-111">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="c1738-111">To correct this error</span></span>  
  
-   <span data-ttu-id="c1738-112">다른 항목으로 확장 된 형식이 하나 이상 있도록 루프 범위와 단계 변수가 필요에 따라의 종류를 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1738-112">Change the types of the loop bounds and step variable as necessary so that at least one of them is a type that the others widen to.</span></span> <span data-ttu-id="c1738-113">앞의 예제에서 변경 유형을 `stepVar` 를 `Integer`합니다.</span><span class="sxs-lookup"><span data-stu-id="c1738-113">In the preceding example, change the type of `stepVar` to `Integer`.</span></span>  
  
    ```  
    Dim stepVar = 1  
    ```  
  
     <span data-ttu-id="c1738-114">또는</span><span class="sxs-lookup"><span data-stu-id="c1738-114">—or—</span></span>  
  
    ```  
    Dim stepVar As Integer = 1  
    ```  
  
-   <span data-ttu-id="c1738-115">루프 범위와 단계 변수에 적합 한 형식으로 변환 하려면 명시적 변환 함수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c1738-115">Use explicit conversion functions to convert the loop bounds and step variable to the appropriate types.</span></span> <span data-ttu-id="c1738-116">앞의 예제에서 적용 된 `Val` 함수를 `stepVar`합니다.</span><span class="sxs-lookup"><span data-stu-id="c1738-116">In the preceding example, apply the `Val` function to `stepVar`.</span></span>  
  
    ```  
    For i = 1 To 10 Step Val(stepVar)  
        ' Loop processing  
    Next  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="c1738-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c1738-117">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Conversion.Val%2A>  
 [<span data-ttu-id="c1738-118">For...Next 문</span><span class="sxs-lookup"><span data-stu-id="c1738-118">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [<span data-ttu-id="c1738-119">암시적 변환과 명시적 변환</span><span class="sxs-lookup"><span data-stu-id="c1738-119">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [<span data-ttu-id="c1738-120">지역 형식 유추</span><span class="sxs-lookup"><span data-stu-id="c1738-120">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [<span data-ttu-id="c1738-121">Option Infer 문</span><span class="sxs-lookup"><span data-stu-id="c1738-121">Option Infer Statement</span></span>](../../../visual-basic/language-reference/statements/option-infer-statement.md)  
 [<span data-ttu-id="c1738-122">형식 변환 함수</span><span class="sxs-lookup"><span data-stu-id="c1738-122">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="c1738-123">확대 변환과 축소 변환</span><span class="sxs-lookup"><span data-stu-id="c1738-123">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
