---
title: "Mid 문 | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.MidB
- vb.Mid
dev_langs:
- VB
helpviewer_keywords:
- substrings, Mid statement
- strings [Visual Basic], substrings
- Mid statement
- strings [Visual Basic], replacing
ms.assetid: 2b82d7a8-9646-4cb0-bec5-80abc98297bf
caps.latest.revision: 20
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: e94500c8bd7f2c6351c91ba028c1ad6d8d3dd4c3
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="mid-statement"></a><span data-ttu-id="55ac1-102">Mid 문</span><span class="sxs-lookup"><span data-stu-id="55ac1-102">Mid Statement</span></span>
<span data-ttu-id="55ac1-103">문자를 지정 된 개수의 `String` 를 다른 문자열 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="55ac1-103">Replaces a specified number of characters in a `String` variable with characters from another string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55ac1-104">구문</span><span class="sxs-lookup"><span data-stu-id="55ac1-104">Syntax</span></span>  
  
```  
Mid( _  
   ByRef Target As String, _  
   ByVal Start As Integer, _  
   Optional ByVal Length As Integer _  
) = StringExpression  
```  
  
## <a name="parts"></a><span data-ttu-id="55ac1-105">요소</span><span class="sxs-lookup"><span data-stu-id="55ac1-105">Parts</span></span>  
 `Target`  
 <span data-ttu-id="55ac1-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="55ac1-106">Required.</span></span> <span data-ttu-id="55ac1-107">이름에서 `String` 변수를 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="55ac1-107">Name of the `String` variable to modify.</span></span>  
  
 `Start`  
 <span data-ttu-id="55ac1-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="55ac1-108">Required.</span></span> <span data-ttu-id="55ac1-109">`Integer`식입니다.</span><span class="sxs-lookup"><span data-stu-id="55ac1-109">`Integer` expression.</span></span> <span data-ttu-id="55ac1-110">문자 위치 `Target` 텍스트 교체를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="55ac1-110">Character position in `Target` where the replacement of text begins.</span></span> <span data-ttu-id="55ac1-111">`Start`1부터 시작 하는 인덱스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="55ac1-111">`Start` uses a one-based index.</span></span>  
  
 `Length`  
 <span data-ttu-id="55ac1-112">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="55ac1-112">Optional.</span></span> <span data-ttu-id="55ac1-113">`Integer`식입니다.</span><span class="sxs-lookup"><span data-stu-id="55ac1-113">`Integer` expression.</span></span> <span data-ttu-id="55ac1-114">바꿀 문자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="55ac1-114">Number of characters to replace.</span></span> <span data-ttu-id="55ac1-115">생략 하면 모든 `String` 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55ac1-115">If omitted, all of `String` is used.</span></span>  
  
 `StringExpression`  
 <span data-ttu-id="55ac1-116">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="55ac1-116">Required.</span></span> <span data-ttu-id="55ac1-117">`String`식의 일부를 대체 하는 `Target`합니다.</span><span class="sxs-lookup"><span data-stu-id="55ac1-117">`String` expression that replaces part of `Target`.</span></span>  
  
## <a name="exceptions"></a><span data-ttu-id="55ac1-118">예외</span><span class="sxs-lookup"><span data-stu-id="55ac1-118">Exceptions</span></span>  
  
|<span data-ttu-id="55ac1-119">예외 형식</span><span class="sxs-lookup"><span data-stu-id="55ac1-119">Exception type</span></span>|<span data-ttu-id="55ac1-120">조건</span><span class="sxs-lookup"><span data-stu-id="55ac1-120">Condition</span></span>|  
|--------------------|---------------|  
|<span data-ttu-id="55ac1-121"><xref:System.ArgumentException></xref:System.ArgumentException></span><span class="sxs-lookup"><span data-stu-id="55ac1-121"><xref:System.ArgumentException></span></span>|<span data-ttu-id="55ac1-122">`Start`<= 0="" or=""></=>`Length`< 0.></ 0.></span><span class="sxs-lookup"><span data-stu-id="55ac1-122">`Start` <= 0 or `Length` < 0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="55ac1-123">설명</span><span class="sxs-lookup"><span data-stu-id="55ac1-123">Remarks</span></span>  
 <span data-ttu-id="55ac1-124">대체 문자 수는 항상의 문자 수가 보다 작거나 `Target`합니다.</span><span class="sxs-lookup"><span data-stu-id="55ac1-124">The number of characters replaced is always less than or equal to the number of characters in `Target`.</span></span>  
  
 <span data-ttu-id="55ac1-125">Visual Basic에는 <xref:Microsoft.VisualBasic.Strings.Mid%2A>함수 및 `Mid` 문.</xref:Microsoft.VisualBasic.Strings.Mid%2A></span><span class="sxs-lookup"><span data-stu-id="55ac1-125">Visual Basic has a <xref:Microsoft.VisualBasic.Strings.Mid%2A> function and a `Mid` statement.</span></span> <span data-ttu-id="55ac1-126">이러한 요소는 지정된 된 수는 문자열의 문자에 모두 작동 하지만 `Mid` 해당 문자를 반환 하는 함수는 `Mid` 문은 문자를 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="55ac1-126">These elements both operate on a specified number of characters in a string, but the `Mid` function returns the characters while the `Mid` statement replaces the characters.</span></span> <span data-ttu-id="55ac1-127">자세한 내용은 <xref:Microsoft.VisualBasic.Strings.Mid%2A>.</xref:Microsoft.VisualBasic.Strings.Mid%2A> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="55ac1-127">For more information, see <xref:Microsoft.VisualBasic.Strings.Mid%2A>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="55ac1-128">`MidB` 이전 버전의 Visual Basic의 문 문자가 아닌 바이트의 하위 문자열을 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="55ac1-128">The `MidB` statement of earlier versions of Visual Basic replaces a substring in bytes, rather than characters.</span></span> <span data-ttu-id="55ac1-129">더블 바이트 문자 집합 (DBCS) 응용 프로그램에서 문자열을 변환 하는 데 주로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55ac1-129">It is used primarily for converting strings in double-byte character set (DBCS) applications.</span></span> <span data-ttu-id="55ac1-130">모든 Visual Basic 문자열은 유니코드에서 및 `MidB` 은 더 이상 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="55ac1-130">All Visual Basic strings are in Unicode, and `MidB` is no longer supported.</span></span>  
  
## <a name="example"></a><span data-ttu-id="55ac1-131">예제</span><span class="sxs-lookup"><span data-stu-id="55ac1-131">Example</span></span>  
 <span data-ttu-id="55ac1-132">사용 하 여이 예제는 `Mid` 문을 다른 문자열에서 지정한 개수의 문자열 변수에 문자를 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="55ac1-132">This example uses the `Mid` statement to replace a specified number of characters in a string variable with characters from another string.</span></span>  
  
 <span data-ttu-id="55ac1-133">[!code-vb[VbVbalrStrings #&5;](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/mid-statement_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="55ac1-133">[!code-vb[VbVbalrStrings#5](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/mid-statement_1.vb)]</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55ac1-134">요구 사항</span><span class="sxs-lookup"><span data-stu-id="55ac1-134">Requirements</span></span>  
 <span data-ttu-id="55ac1-135">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="55ac1-135">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="55ac1-136">**모듈:**`Strings`</span><span class="sxs-lookup"><span data-stu-id="55ac1-136">**Module:** `Strings`</span></span>  
  
 <span data-ttu-id="55ac1-137">**어셈블리:**[!INCLUDE[vbprvbruntime](../../../visual-basic/language-reference/objects/includes/vbprvbruntime_md.md)]</span><span class="sxs-lookup"><span data-stu-id="55ac1-137">**Assembly:** [!INCLUDE[vbprvbruntime](../../../visual-basic/language-reference/objects/includes/vbprvbruntime_md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55ac1-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="55ac1-138">See Also</span></span>  
 <span data-ttu-id="55ac1-139"><xref:Microsoft.VisualBasic.Strings.Mid%2A></xref:Microsoft.VisualBasic.Strings.Mid%2A></span><span class="sxs-lookup"><span data-stu-id="55ac1-139"><xref:Microsoft.VisualBasic.Strings.Mid%2A></span></span>   
<span data-ttu-id="55ac1-140"> [문자열](../../../visual-basic/programming-guide/language-features/strings/index.md) </span><span class="sxs-lookup"><span data-stu-id="55ac1-140"> [Strings](../../../visual-basic/programming-guide/language-features/strings/index.md) </span></span>  
<span data-ttu-id="55ac1-141"> [Visual Basic의 문자열 소개](../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)</span><span class="sxs-lookup"><span data-stu-id="55ac1-141"> [Introduction to Strings in Visual Basic](../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)</span></span>
