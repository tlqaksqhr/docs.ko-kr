---
title: "ByRef&quot; 매개 변수 값을 복사 &quot;&lt;parametername&gt;&quot;일치 하는 인수에 다시 좁힐 형식에서 &quot;&lt;typename1&gt;&quot;를 입력 하 고&quot;&lt;typename2&gt;&quot; | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc32053
- vbc32053
dev_langs:
- VB
helpviewer_keywords:
- BC32053
ms.assetid: 281564b7-99f7-451f-b10d-f985e831bb25
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 10ad4af689c11f3e4defe43c4fed9ed579ba5305
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="copying-the-value-of-39byref39-parameter-39ltparameternamegt39-back-to-the-matching-argument-narrows-from-type-39lttypename1gt39-to-type-39lttypename2gt39"></a><span data-ttu-id="a04b7-102">ByRef' 매개 변수 값을 복사 '&lt;parametername&gt;'일치 하는 인수에 다시 좁힐 형식에서 '&lt;typename1&gt;'를 입력 하 고'&lt;typename2&gt;'</span><span class="sxs-lookup"><span data-stu-id="a04b7-102">Copying the value of &#39;ByRef&#39; parameter &#39;&lt;parametername&gt;&#39; back to the matching argument narrows from type &#39;&lt;typename1&gt;&#39; to type &#39;&lt;typename2&gt;&#39;</span></span>
<span data-ttu-id="a04b7-103">해당 매개 변수 형식으로 확장 되는 인수와 함께 프로시저를 호출 하 고 축소 하는 인수에 매개 변수에서 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a04b7-103">A procedure is called with an argument that widens to the corresponding parameter type, and the conversion from the parameter to the argument is narrowing.</span></span>  
  
 <span data-ttu-id="a04b7-104">클래스 또는 구조체를 정의하는 경우 해당 클래스 또는 구조체 형식을 다른 형식으로 변환하는 변환 연산자를 하나 이상 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a04b7-104">When you define a class or structure, you can define one or more conversion operators to convert that class or structure type to other types.</span></span> <span data-ttu-id="a04b7-105">다른 형식을 클래스 또는 구조체 형식으로 다시 변환하는 역방향 변환 연산자를 정의할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a04b7-105">You can also define reverse conversion operators to convert those other types back to your class or structure type.</span></span> <span data-ttu-id="a04b7-106">프로시저 호출에서 클래스 또는 구조체 형식을 사용할 때 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 이러한 변환 연산자를 사용 하 여 인수 형식을 해당 매개 변수의 형식으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a04b7-106">When you use your class or structure type in a procedure call, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] can use these conversion operators to convert the type of an argument to the type of its corresponding parameter.</span></span>  
  
 <span data-ttu-id="a04b7-107">인수를 전달 하는 경우 [ByRef](../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 로컬 변수에 대 한 참조를 전달 하는 대신 프로시저에 인수 값을 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="a04b7-107">If you pass the argument [ByRef](../../../visual-basic/language-reference/modifiers/byref.md), [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] sometimes copies the argument value into a local variable in the procedure instead of passing a reference.</span></span> <span data-ttu-id="a04b7-108">이 경우, 프로시저에서 반환 하는 경우 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 지역 변수 값은 호출 코드에서 인수에 다시 복사 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a04b7-108">In such a case, when the procedure returns, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] must then copy the local variable value back into the argument in the calling code.</span></span>  
  
 <span data-ttu-id="a04b7-109">`ByRef` 인수 값이 프로시저에 복사되고 인수 및 매개 변수가 동일한 형식인 경우에는 변환이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a04b7-109">If a `ByRef` argument value is copied into the procedure and the argument and parameter are of the same type, no conversion is necessary.</span></span> <span data-ttu-id="a04b7-110">그러나 형식이 서로 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 양방향으로 변환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a04b7-110">But if the types are different, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] must convert in both directions.</span></span> <span data-ttu-id="a04b7-111">클래스 또는 구조체 형식, 형식 중 하나 이면 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 하 고 다른 형식에서 변환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a04b7-111">If one of the types is your class or structure type, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] must convert it both to and from the other type.</span></span> <span data-ttu-id="a04b7-112">이러한 변환 중 하나은 확대 하는 경우 역방향 변환 축소 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a04b7-112">If one of these conversions is widening, the reverse conversion might be narrowing.</span></span>  
  
 <span data-ttu-id="a04b7-113">**오류 ID:** BC32053</span><span class="sxs-lookup"><span data-stu-id="a04b7-113">**Error ID:** BC32053</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a04b7-114">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="a04b7-114">To correct this error</span></span>  
  
-   <span data-ttu-id="a04b7-115">따라서 프로시저 매개 변수로 동일한 형식의 호출 인수를 가능 하면 사용 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 변수와 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a04b7-115">If possible, use a calling argument of the same type as the procedure parameter, so [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] does not need to do any conversion.</span></span>  
  
-   <span data-ttu-id="a04b7-116">인수로 사용 하 여 프로시저를 호출 하는 경우 형식 매개 변수 형식과 다를 수 있지만 매개 변수를 정의 호출 인수에 값을 반환할 필요가 없습니다 [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) 대신 `ByRef`합니다.</span><span class="sxs-lookup"><span data-stu-id="a04b7-116">If you need to call the procedure with an argument type different from the parameter type but do not need to return a value into the calling argument, define the parameter to be [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) instead of `ByRef`.</span></span>  
  
-   <span data-ttu-id="a04b7-117">호출 인수에 값을 반환 해야 하는 경우로 역방향 변환 연산자 정의 [Widening](../../../visual-basic/language-reference/modifiers/widening.md), 가능한 경우.</span><span class="sxs-lookup"><span data-stu-id="a04b7-117">If you need to return a value into the calling argument, define the reverse conversion operator as [Widening](../../../visual-basic/language-reference/modifiers/widening.md), if possible.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a04b7-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a04b7-118">See Also</span></span>  
 <span data-ttu-id="a04b7-119">[프로시저](../../../visual-basic/programming-guide/language-features/procedures/index.md) </span><span class="sxs-lookup"><span data-stu-id="a04b7-119">[Procedures](../../../visual-basic/programming-guide/language-features/procedures/index.md) </span></span>  
<span data-ttu-id="a04b7-120"> [프로시저 매개 변수 및 인수](../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="a04b7-120"> [Procedure Parameters and Arguments](../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="a04b7-121"> [값 및 참조로 인수 전달](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md) </span><span class="sxs-lookup"><span data-stu-id="a04b7-121"> [Passing Arguments by Value and by Reference](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md) </span></span>  
<span data-ttu-id="a04b7-122"> [연산자 프로시저](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="a04b7-122"> [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md) </span></span>  
<span data-ttu-id="a04b7-123"> [Operator 문](../../../visual-basic/language-reference/statements/operator-statement.md) </span><span class="sxs-lookup"><span data-stu-id="a04b7-123"> [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md) </span></span>  
<span data-ttu-id="a04b7-124"> [방법: 연산자 정의](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md) </span><span class="sxs-lookup"><span data-stu-id="a04b7-124"> [How to: Define an Operator](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md) </span></span>  
<span data-ttu-id="a04b7-125"> [방법: 변환 연산자 정의](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md) </span><span class="sxs-lookup"><span data-stu-id="a04b7-125"> [How to: Define a Conversion Operator](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md) </span></span>  
<span data-ttu-id="a04b7-126"> [Visual Basic의 형식 변환](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="a04b7-126"> [Type Conversions in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span></span>  
<span data-ttu-id="a04b7-127"> [확대 변환과 축소 변환](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)</span><span class="sxs-lookup"><span data-stu-id="a04b7-127"> [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)</span></span>
