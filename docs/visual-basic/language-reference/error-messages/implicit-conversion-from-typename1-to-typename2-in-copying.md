---
title: 암시적으로 변환 &#39; &lt;typename1&gt; &#39; 를 &#39; &lt;typename2&gt; &#39; 의 값을 복사 &#39;ByRef&#39; 매개 변수 &#39; &lt; parametername&gt; &#39; 일치 하는 인수에 다시 합니다.
ms.date: 07/20/2015
f1_keywords:
- vbc41999
- bc41999
helpviewer_keywords:
- BC41999
ms.assetid: ae48c738-dff8-4c0f-8931-bbb70b2c8b03
ms.openlocfilehash: b1f772598b18f8edfe0198f62d78854d30f993ab
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33590002"
---
# <a name="implicit-conversion-from-39lttypename1gt39-to-39lttypename2gt39-in-copying-the-value-of-39byref39-parameter-39ltparameternamegt39-back-to-the-matching-argument"></a><span data-ttu-id="f33cf-102">암시적으로 변환 &#39; &lt;typename1&gt; &#39; 를 &#39; &lt;typename2&gt; &#39; 의 값을 복사 &#39;ByRef&#39; 매개 변수 &#39; &lt; parametername&gt; &#39; 일치 하는 인수에 다시 합니다.</span><span class="sxs-lookup"><span data-stu-id="f33cf-102">Implicit conversion from &#39;&lt;typename1&gt;&#39; to &#39;&lt;typename2&gt;&#39; in copying the value of &#39;ByRef&#39; parameter &#39;&lt;parametername&gt;&#39; back to the matching argument.</span></span>
<span data-ttu-id="f33cf-103">프로시저를 호출는 [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) 해당 매개 변수의 형식과 다른 형식의 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="f33cf-103">A procedure is called with a [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) argument of a different type than that of its corresponding parameter.</span></span>  
  
 <span data-ttu-id="f33cf-104">인수를 전달 하는 경우 `ByRef`, Visual Basic에서 참조를 전달 하는 대신 프로시저의 지역 변수에 인수 값을 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="f33cf-104">If you pass an argument `ByRef`, Visual Basic sometimes copies the argument value into a local variable in the procedure instead of passing a reference.</span></span> <span data-ttu-id="f33cf-105">이 경우 프로시저가 반환 되 면 Visual Basic에서 지역 변수 값을 호출 코드의 인수에 다시 복사 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f33cf-105">In such a case, when the procedure returns, Visual Basic must then copy the local variable value back into the argument in the calling code.</span></span>  
  
 <span data-ttu-id="f33cf-106">`ByRef` 인수 값이 프로시저에 복사되고 인수 및 매개 변수가 동일한 형식인 경우에는 변환이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f33cf-106">If a `ByRef` argument value is copied into the procedure and the argument and parameter are of the same type, no conversion is necessary.</span></span> <span data-ttu-id="f33cf-107">그러나 형식이 서로 다르면, Visual Basic 양방향으로 변환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f33cf-107">But if the types are different, Visual Basic must convert in both directions.</span></span> <span data-ttu-id="f33cf-108">사용할 수 없으므로 `CType` 암시적 프로시저 인수 또는 매개 변수, 이러한 변환에서 다른 변환 키워드 중 하나는 항상 또는 합니다.</span><span class="sxs-lookup"><span data-stu-id="f33cf-108">Because you cannot use `CType` or any of the other conversion keywords on a procedure argument or parameter, such a conversion is always implicit.</span></span>  
  
 <span data-ttu-id="f33cf-109">이 메시지는 기본적으로 경고입니다.</span><span class="sxs-lookup"><span data-stu-id="f33cf-109">By default, this message is a warning.</span></span> <span data-ttu-id="f33cf-110">경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f33cf-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="f33cf-111">**오류 ID:** BC41999</span><span class="sxs-lookup"><span data-stu-id="f33cf-111">**Error ID:** BC41999</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f33cf-112">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="f33cf-112">To correct this error</span></span>  
  
-   <span data-ttu-id="f33cf-113">가능 하면 Visual Basic 모든 변환을 수행 하지 않아도 되므로 프로시저 매개 변수와 동일한 형식의 호출 인수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f33cf-113">If possible, use a calling argument of the same type as the procedure parameter, so Visual Basic does not need to do any conversion.</span></span>  
  
-   <span data-ttu-id="f33cf-114">인수로 사용 하 여 프로시저를 호출 하는 경우 입력 매개 변수 형식과 다른 하지만 호출 인수에 값을 반환 하려면 매개 변수를 정의 합니다. 필요 하지 않은 [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) 대신 `ByRef`합니다.</span><span class="sxs-lookup"><span data-stu-id="f33cf-114">If you need to call the procedure with an argument type different from the parameter type but do not need to return a value into the calling argument, define the parameter to be [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) instead of `ByRef`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f33cf-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f33cf-115">See Also</span></span>  
 [<span data-ttu-id="f33cf-116">절차</span><span class="sxs-lookup"><span data-stu-id="f33cf-116">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [<span data-ttu-id="f33cf-117">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="f33cf-117">Procedure Parameters and Arguments</span></span>](../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="f33cf-118">값 또는 참조로 인수 전달</span><span class="sxs-lookup"><span data-stu-id="f33cf-118">Passing Arguments by Value and by Reference</span></span>](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)  
 [<span data-ttu-id="f33cf-119">암시적 변환과 명시적 변환</span><span class="sxs-lookup"><span data-stu-id="f33cf-119">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
