---
title: ParamArray(Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.ParamArray
- ParamArray
helpviewer_keywords:
- ParamArray keyword [Visual Basic]
- ParamArray keyword [Visual Basic], syntax
ms.assetid: a5f18789-92bd-488f-9c7e-cf3719963635
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 06770f05aabedcf13cc9af1970a2c511a30c73b4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="paramarray-visual-basic"></a><span data-ttu-id="ee15c-102">ParamArray(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ee15c-102">ParamArray (Visual Basic)</span></span>
<span data-ttu-id="ee15c-103">프로시저 매개 변수가 지정 된 형식의 요소 선택적 배열 임을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee15c-103">Specifies that a procedure parameter takes an optional array of elements of the specified type.</span></span> <span data-ttu-id="ee15c-104">`ParamArray`매개 변수 목록의 마지막 매개 변수 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee15c-104">`ParamArray` can be used only on the last parameter of a parameter list.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ee15c-105">설명</span><span class="sxs-lookup"><span data-stu-id="ee15c-105">Remarks</span></span>  
 <span data-ttu-id="ee15c-106">`ParamArray`프로시저에 임의 개수의 인수를 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee15c-106">`ParamArray` allows you to pass an arbitrary number of arguments to the procedure.</span></span> <span data-ttu-id="ee15c-107">A `ParamArray` 매개 변수는 항상 사용 하 여 선언 [ByVal](../../../visual-basic/language-reference/modifiers/byval.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ee15c-107">A `ParamArray` parameter is always declared using [ByVal](../../../visual-basic/language-reference/modifiers/byval.md).</span></span>  
  
 <span data-ttu-id="ee15c-108">하나 이상의 인수를 제공할 수 있습니다는 `ParamArray` 적절 한 데이터의 배열을 전달 하 여 매개 변수를 쉼표로 구분 된 목록을 입력 값 또는 아무 것도 전혀 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee15c-108">You can supply one or more arguments to a `ParamArray` parameter by passing an array of the appropriate data type, a comma-separated list of values, or nothing at all.</span></span> <span data-ttu-id="ee15c-109">자세한 내용은 "ParamArray 호출"의 참조 [매개 변수 배열](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ee15c-109">For details, see "Calling a ParamArray" in [Parameter Arrays](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ee15c-110">무한정 커질 수 있는 배열을 처리할 때마다 응용 프로그램의 일부 내부 용량 오버런이 위험이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee15c-110">Whenever you deal with an array which can be indefinitely large, there is a risk of overrunning some internal capacity of your application.</span></span> <span data-ttu-id="ee15c-111">호출 코드에서 매개 변수 배열에 동의 하면 해당 길이 테스트 하 고 응용 프로그램에 대해 너무 큰 경우 적절 한 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee15c-111">If you accept a parameter array from the calling code, you should test its length and take appropriate steps if it is too large for your application.</span></span>  
  
 <span data-ttu-id="ee15c-112">`ParamArray` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee15c-112">The `ParamArray` modifier can be used in these contexts:</span></span>  
  
 [<span data-ttu-id="ee15c-113">Declare 문</span><span class="sxs-lookup"><span data-stu-id="ee15c-113">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [<span data-ttu-id="ee15c-114">Function 문</span><span class="sxs-lookup"><span data-stu-id="ee15c-114">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [<span data-ttu-id="ee15c-115">Property 문</span><span class="sxs-lookup"><span data-stu-id="ee15c-115">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [<span data-ttu-id="ee15c-116">Sub 문</span><span class="sxs-lookup"><span data-stu-id="ee15c-116">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="ee15c-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ee15c-117">See Also</span></span>  
 [<span data-ttu-id="ee15c-118">키워드</span><span class="sxs-lookup"><span data-stu-id="ee15c-118">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)  
 [<span data-ttu-id="ee15c-119">매개 변수 배열</span><span class="sxs-lookup"><span data-stu-id="ee15c-119">Parameter Arrays</span></span>](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)
