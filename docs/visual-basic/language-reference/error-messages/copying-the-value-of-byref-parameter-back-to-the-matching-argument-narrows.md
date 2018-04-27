---
title: 값을 복사 &#39;ByRef&#39; 매개 변수 &#39; &lt;parametername&gt; &#39; 형식에서 일치 하는 인수에 다시 축소 됩니다 &#39; &lt;typename1&gt; &#39; &#39; &lt;typename2&gt;&#39;
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc32053
- vbc32053
helpviewer_keywords:
- BC32053
ms.assetid: 281564b7-99f7-451f-b10d-f985e831bb25
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 18c72e56e4b2cc9c2251de2417a9f12a6688323f
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="copying-the-value-of-39byref39-parameter-39ltparameternamegt39-back-to-the-matching-argument-narrows-from-type-39lttypename1gt39-to-type-39lttypename2gt39"></a><span data-ttu-id="63237-102">값을 복사 &#39;ByRef&#39; 매개 변수 &#39; &lt;parametername&gt; &#39; 형식에서 일치 하는 인수에 다시 축소 됩니다 &#39; &lt;typename1&gt; &#39; &#39; &lt;typename2&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="63237-102">Copying the value of &#39;ByRef&#39; parameter &#39;&lt;parametername&gt;&#39; back to the matching argument narrows from type &#39;&lt;typename1&gt;&#39; to type &#39;&lt;typename2&gt;&#39;</span></span>
<span data-ttu-id="63237-103">해당 매개 변수 형식으로 확대 되는 인수가 지정 된 프로시저를 호출 하 고 축소 인수에 매개 변수에서 변환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="63237-103">A procedure is called with an argument that widens to the corresponding parameter type, and the conversion from the parameter to the argument is narrowing.</span></span>  
  
 <span data-ttu-id="63237-104">클래스 또는 구조체를 정의하는 경우 해당 클래스 또는 구조체 형식을 다른 형식으로 변환하는 변환 연산자를 하나 이상 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63237-104">When you define a class or structure, you can define one or more conversion operators to convert that class or structure type to other types.</span></span> <span data-ttu-id="63237-105">다른 형식을 클래스 또는 구조체 형식으로 다시 변환하는 역방향 변환 연산자를 정의할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63237-105">You can also define reverse conversion operators to convert those other types back to your class or structure type.</span></span> <span data-ttu-id="63237-106">클래스 또는 구조체 형식을 사용 하 여 프로시저 호출에서 Visual Basic 인수 형식을 해당 매개 변수의 형식으로 변환 하 이러한 변환 연산자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63237-106">When you use your class or structure type in a procedure call, Visual Basic can use these conversion operators to convert the type of an argument to the type of its corresponding parameter.</span></span>  
  
 <span data-ttu-id="63237-107">인수를 전달 하는 경우 [ByRef](../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic에서 참조를 전달 하는 대신 프로시저의 지역 변수에 인수 값을 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="63237-107">If you pass the argument [ByRef](../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic sometimes copies the argument value into a local variable in the procedure instead of passing a reference.</span></span> <span data-ttu-id="63237-108">이 경우 프로시저가 반환 되 면 Visual Basic에서 지역 변수 값을 호출 코드의 인수에 다시 복사 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="63237-108">In such a case, when the procedure returns, Visual Basic must then copy the local variable value back into the argument in the calling code.</span></span>  
  
 <span data-ttu-id="63237-109">`ByRef` 인수 값이 프로시저에 복사되고 인수 및 매개 변수가 동일한 형식인 경우에는 변환이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="63237-109">If a `ByRef` argument value is copied into the procedure and the argument and parameter are of the same type, no conversion is necessary.</span></span> <span data-ttu-id="63237-110">그러나 형식이 서로 다르면, Visual Basic 양방향으로 변환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="63237-110">But if the types are different, Visual Basic must convert in both directions.</span></span> <span data-ttu-id="63237-111">형식 중 하나가 클래스 또는 구조체 형식의 이면 Visual Basic 변환 해야 하 고 다른 형식에서.</span><span class="sxs-lookup"><span data-stu-id="63237-111">If one of the types is your class or structure type, Visual Basic must convert it both to and from the other type.</span></span> <span data-ttu-id="63237-112">이러한 변환 중 하나은 확대 하는 경우 역방향 변환 축소 수입니다.</span><span class="sxs-lookup"><span data-stu-id="63237-112">If one of these conversions is widening, the reverse conversion might be narrowing.</span></span>  
  
 <span data-ttu-id="63237-113">**오류 ID:** BC32053</span><span class="sxs-lookup"><span data-stu-id="63237-113">**Error ID:** BC32053</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="63237-114">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="63237-114">To correct this error</span></span>  
  
-   <span data-ttu-id="63237-115">가능 하면 Visual Basic 모든 변환을 수행 하지 않아도 되므로 프로시저 매개 변수와 동일한 형식의 호출 인수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="63237-115">If possible, use a calling argument of the same type as the procedure parameter, so Visual Basic does not need to do any conversion.</span></span>  
  
-   <span data-ttu-id="63237-116">인수로 사용 하 여 프로시저를 호출 하는 경우 입력 매개 변수 형식과 다른 하지만 호출 인수에 값을 반환 하려면 매개 변수를 정의 합니다. 필요 하지 않은 [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) 대신 `ByRef`합니다.</span><span class="sxs-lookup"><span data-stu-id="63237-116">If you need to call the procedure with an argument type different from the parameter type but do not need to return a value into the calling argument, define the parameter to be [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) instead of `ByRef`.</span></span>  
  
-   <span data-ttu-id="63237-117">호출 인수에 값을 반환 해야 할 경우으로 역방향 변환 연산자 정의 [Widening](../../../visual-basic/language-reference/modifiers/widening.md), 가능한 경우.</span><span class="sxs-lookup"><span data-stu-id="63237-117">If you need to return a value into the calling argument, define the reverse conversion operator as [Widening](../../../visual-basic/language-reference/modifiers/widening.md), if possible.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63237-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="63237-118">See Also</span></span>  
 [<span data-ttu-id="63237-119">절차</span><span class="sxs-lookup"><span data-stu-id="63237-119">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [<span data-ttu-id="63237-120">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="63237-120">Procedure Parameters and Arguments</span></span>](../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="63237-121">값 또는 참조로 인수 전달</span><span class="sxs-lookup"><span data-stu-id="63237-121">Passing Arguments by Value and by Reference</span></span>](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)  
 [<span data-ttu-id="63237-122">연산자 프로시저</span><span class="sxs-lookup"><span data-stu-id="63237-122">Operator Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)  
 [<span data-ttu-id="63237-123">Operator 문</span><span class="sxs-lookup"><span data-stu-id="63237-123">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
 [<span data-ttu-id="63237-124">방법: 연산자 정의</span><span class="sxs-lookup"><span data-stu-id="63237-124">How to: Define an Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)  
 [<span data-ttu-id="63237-125">방법: 변환 연산자 정의</span><span class="sxs-lookup"><span data-stu-id="63237-125">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)  
 [<span data-ttu-id="63237-126">Visual Basic의 형식 변환</span><span class="sxs-lookup"><span data-stu-id="63237-126">Type Conversions in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [<span data-ttu-id="63237-127">확대 변환과 축소 변환</span><span class="sxs-lookup"><span data-stu-id="63237-127">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
