---
title: Mid 문
ms.date: 07/20/2015
f1_keywords:
- vb.MidB
- vb.Mid
helpviewer_keywords:
- substrings [Visual Basic], Mid statement
- strings [Visual Basic], substrings
- Mid statement [Visual Basic]
- strings [Visual Basic], replacing
ms.assetid: 2b82d7a8-9646-4cb0-bec5-80abc98297bf
ms.openlocfilehash: 90b805df902dcdfebe85421583dd54e9af04bec9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33602267"
---
# <a name="mid-statement"></a><span data-ttu-id="cc862-102">Mid 문</span><span class="sxs-lookup"><span data-stu-id="cc862-102">Mid Statement</span></span>
<span data-ttu-id="cc862-103">지정 된 개수의 문자를 바꿉니다는 `String` 를 다른 문자열 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="cc862-103">Replaces a specified number of characters in a `String` variable with characters from another string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc862-104">구문</span><span class="sxs-lookup"><span data-stu-id="cc862-104">Syntax</span></span>  
  
```  
Mid( _  
   ByRef Target As String, _  
   ByVal Start As Integer, _  
   Optional ByVal Length As Integer _  
) = StringExpression  
```  
  
## <a name="parts"></a><span data-ttu-id="cc862-105">요소</span><span class="sxs-lookup"><span data-stu-id="cc862-105">Parts</span></span>  
 `Target`  
 <span data-ttu-id="cc862-106">필수.</span><span class="sxs-lookup"><span data-stu-id="cc862-106">Required.</span></span> <span data-ttu-id="cc862-107">이름에서 `String` 변수를 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc862-107">Name of the `String` variable to modify.</span></span>  
  
 `Start`  
 <span data-ttu-id="cc862-108">필수.</span><span class="sxs-lookup"><span data-stu-id="cc862-108">Required.</span></span> <span data-ttu-id="cc862-109">`Integer` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="cc862-109">`Integer` expression.</span></span> <span data-ttu-id="cc862-110">문자 위치 `Target` 바꿀 텍스트가 시작 하는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="cc862-110">Character position in `Target` where the replacement of text begins.</span></span> <span data-ttu-id="cc862-111">`Start` 한 인덱스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cc862-111">`Start` uses a one-based index.</span></span>  
  
 `Length`  
 <span data-ttu-id="cc862-112">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="cc862-112">Optional.</span></span> <span data-ttu-id="cc862-113">`Integer` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="cc862-113">`Integer` expression.</span></span> <span data-ttu-id="cc862-114">바꿀 문자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="cc862-114">Number of characters to replace.</span></span> <span data-ttu-id="cc862-115">생략 하면 모든 `String` 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc862-115">If omitted, all of `String` is used.</span></span>  
  
 `StringExpression`  
 <span data-ttu-id="cc862-116">필수.</span><span class="sxs-lookup"><span data-stu-id="cc862-116">Required.</span></span> <span data-ttu-id="cc862-117">`String` 식의 일부를 대체 하는 `Target`합니다.</span><span class="sxs-lookup"><span data-stu-id="cc862-117">`String` expression that replaces part of `Target`.</span></span>  
  
## <a name="exceptions"></a><span data-ttu-id="cc862-118">예외</span><span class="sxs-lookup"><span data-stu-id="cc862-118">Exceptions</span></span>  
  
|<span data-ttu-id="cc862-119">예외 형식</span><span class="sxs-lookup"><span data-stu-id="cc862-119">Exception type</span></span>|<span data-ttu-id="cc862-120">조건</span><span class="sxs-lookup"><span data-stu-id="cc862-120">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|<span data-ttu-id="cc862-121">`Start` < = 0 또는 `Length` < 0입니다.</span><span class="sxs-lookup"><span data-stu-id="cc862-121">`Start` <= 0 or `Length` < 0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cc862-122">설명</span><span class="sxs-lookup"><span data-stu-id="cc862-122">Remarks</span></span>  
 <span data-ttu-id="cc862-123">바꿀 문자 수는 항상에 있는 문자의 수와 같거나 작음 `Target`합니다.</span><span class="sxs-lookup"><span data-stu-id="cc862-123">The number of characters replaced is always less than or equal to the number of characters in `Target`.</span></span>  
  
 <span data-ttu-id="cc862-124">Visual Basic에는 <xref:Microsoft.VisualBasic.Strings.Mid%2A> 함수 및 `Mid` 문.</span><span class="sxs-lookup"><span data-stu-id="cc862-124">Visual Basic has a <xref:Microsoft.VisualBasic.Strings.Mid%2A> function and a `Mid` statement.</span></span> <span data-ttu-id="cc862-125">이러한 요소는 지정된 된 수는 문자열에 있는 문자에 모두 작동 하지만 `Mid` 해당 문자를 반환 하는 함수는 `Mid` 문은 문자를 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc862-125">These elements both operate on a specified number of characters in a string, but the `Mid` function returns the characters while the `Mid` statement replaces the characters.</span></span> <span data-ttu-id="cc862-126">자세한 내용은 <xref:Microsoft.VisualBasic.Strings.Mid%2A>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cc862-126">For more information, see <xref:Microsoft.VisualBasic.Strings.Mid%2A>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cc862-127">`MidB` 이전 버전의 Visual Basic의 문은 문자가 아닌 바이트의 하위 문자열을 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc862-127">The `MidB` statement of earlier versions of Visual Basic replaces a substring in bytes, rather than characters.</span></span> <span data-ttu-id="cc862-128">더블 바이트 문자 집합 (DBCS) 응용 프로그램의 문자열을 변환에 주로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc862-128">It is used primarily for converting strings in double-byte character set (DBCS) applications.</span></span> <span data-ttu-id="cc862-129">모든 Visual Basic 문자열은 유니코드에서 및 `MidB` 더 이상 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc862-129">All Visual Basic strings are in Unicode, and `MidB` is no longer supported.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cc862-130">예제</span><span class="sxs-lookup"><span data-stu-id="cc862-130">Example</span></span>  
 <span data-ttu-id="cc862-131">사용 하 여이 예제는 `Mid` 문을 다른 문자열을 문자로 지정된 된 수의 문자열 변수에 문자를 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc862-131">This example uses the `Mid` statement to replace a specified number of characters in a string variable with characters from another string.</span></span>  
  
 [!code-vb[VbVbalrStrings#5](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/mid-statement_1.vb)]  
  
## <a name="requirements"></a><span data-ttu-id="cc862-132">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cc862-132">Requirements</span></span>  
 <span data-ttu-id="cc862-133">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="cc862-133">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="cc862-134">**모듈:** `Strings`</span><span class="sxs-lookup"><span data-stu-id="cc862-134">**Module:** `Strings`</span></span>  
  
 <span data-ttu-id="cc862-135">**어셈블리:** [!INCLUDE[vbprvbruntime](~/includes/vbprvbruntime-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc862-135">**Assembly:** [!INCLUDE[vbprvbruntime](~/includes/vbprvbruntime-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc862-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cc862-136">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Strings.Mid%2A>  
 [<span data-ttu-id="cc862-137">문자열</span><span class="sxs-lookup"><span data-stu-id="cc862-137">Strings</span></span>](../../../visual-basic/programming-guide/language-features/strings/index.md)  
 [<span data-ttu-id="cc862-138">Visual Basic의 문자열 소개</span><span class="sxs-lookup"><span data-stu-id="cc862-138">Introduction to Strings in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
