---
title: 암시적으로 변환 &#39; &lt;typename1&gt;&#39;를 &#39;&lt; typename2&gt;&#39; 값으로 &#39; 복사 ByRef &#39; &#39; 매개 변수 &lt;parametername&gt;&#39; 해당 인수에 저장 합니다.
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc41999
- bc41999
helpviewer_keywords:
- BC41999
ms.assetid: ae48c738-dff8-4c0f-8931-bbb70b2c8b03
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9e858b475a816a35d18822643de5a273abe28562
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="implicit-conversion-from-39lttypename1gt39-to-39lttypename2gt39-in-copying-the-value-of-39byref39-parameter-39ltparameternamegt39-back-to-the-matching-argument"></a><span data-ttu-id="d9764-102">암시적으로 변환 &#39; &lt;typename1&gt;&#39;를 &#39;&lt; typename2&gt;&#39; 값으로 &#39; 복사 ByRef &#39; &#39; 매개 변수 &lt;parametername&gt;&#39; 해당 인수에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9764-102">Implicit conversion from &#39;&lt;typename1&gt;&#39; to &#39;&lt;typename2&gt;&#39; in copying the value of &#39;ByRef&#39; parameter &#39;&lt;parametername&gt;&#39; back to the matching argument.</span></span>
<span data-ttu-id="d9764-103">프로시저를 호출는 [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) 해당 매개 변수의 형식과 다른 형식의 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="d9764-103">A procedure is called with a [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) argument of a different type than that of its corresponding parameter.</span></span>  
  
 <span data-ttu-id="d9764-104">인수를 전달 하는 경우 `ByRef`, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 에서 참조를 전달 하는 대신 프로시저의 지역 변수에 인수 값을 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9764-104">If you pass an argument `ByRef`, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] sometimes copies the argument value into a local variable in the procedure instead of passing a reference.</span></span> <span data-ttu-id="d9764-105">이 경우 프로시저가 반환되면 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 에서 지역 변수 값을 호출 코드의 인수에 다시 복사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9764-105">In such a case, when the procedure returns, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] must then copy the local variable value back into the argument in the calling code.</span></span>  
  
 <span data-ttu-id="d9764-106">`ByRef` 인수 값이 프로시저에 복사되고 인수 및 매개 변수가 동일한 형식인 경우에는 변환이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d9764-106">If a `ByRef` argument value is copied into the procedure and the argument and parameter are of the same type, no conversion is necessary.</span></span> <span data-ttu-id="d9764-107">그러나 형식이 서로 다르면 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 에서 양방향으로 변환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9764-107">But if the types are different, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] must convert in both directions.</span></span> <span data-ttu-id="d9764-108">사용할 수 없으므로 `CType` 암시적 프로시저 인수 또는 매개 변수, 이러한 변환에서 다른 변환 키워드 중 하나는 항상 또는 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9764-108">Because you cannot use `CType` or any of the other conversion keywords on a procedure argument or parameter, such a conversion is always implicit.</span></span>  
  
 <span data-ttu-id="d9764-109">이 메시지는 기본적으로 경고입니다.</span><span class="sxs-lookup"><span data-stu-id="d9764-109">By default, this message is a warning.</span></span> <span data-ttu-id="d9764-110">경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d9764-110">For information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="d9764-111">**오류 ID:** BC41999</span><span class="sxs-lookup"><span data-stu-id="d9764-111">**Error ID:** BC41999</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d9764-112">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="d9764-112">To correct this error</span></span>  
  
-   <span data-ttu-id="d9764-113">가능한 경우 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 에서 변환할 필요가 없도록 프로시저 매개 변수와 동일한 형식의 호출 인수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d9764-113">If possible, use a calling argument of the same type as the procedure parameter, so [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] does not need to do any conversion.</span></span>  
  
-   <span data-ttu-id="d9764-114">인수로 사용 하 여 프로시저를 호출 하는 경우 입력 매개 변수 형식과 다른 하지만 호출 인수에 값을 반환 하려면 매개 변수를 정의 합니다. 필요 하지 않은 [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) 대신 `ByRef`합니다.</span><span class="sxs-lookup"><span data-stu-id="d9764-114">If you need to call the procedure with an argument type different from the parameter type but do not need to return a value into the calling argument, define the parameter to be [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) instead of `ByRef`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9764-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d9764-115">See Also</span></span>  
 [<span data-ttu-id="d9764-116">절차</span><span class="sxs-lookup"><span data-stu-id="d9764-116">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [<span data-ttu-id="d9764-117">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="d9764-117">Procedure Parameters and Arguments</span></span>](../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="d9764-118">값 또는 참조로 인수 전달</span><span class="sxs-lookup"><span data-stu-id="d9764-118">Passing Arguments by Value and by Reference</span></span>](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)  
 [<span data-ttu-id="d9764-119">암시적 변환과 명시적 변환</span><span class="sxs-lookup"><span data-stu-id="d9764-119">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
