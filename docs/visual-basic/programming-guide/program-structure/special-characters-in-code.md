---
title: "(Visual Basic) 코드의 특수 문자 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.)
- vb.(
- vb.colon
- vb.!
- vb..
- 'vb.:'
dev_langs:
- VB
helpviewer_keywords:
- special characters, in code
- parentheses, using in code
- colons (:)
- period character in code
- dot operator (.)
- dictionary access operator
- concatenation operators, special characters in code
- concatenation operators, vs. addition operator
- '! operator'
- separators, using in code
- operators [Visual Basic], dictionary access
- ': separator character'
- member access operator
- addition operator
- operators [Visual Basic], member access
- . operator
- exclamation points
- separators
- exclamation point operator (!)
- Visual Basic code, special characters
ms.assetid: 310dce0c-45b5-4e0d-83e9-32df258d2a3e
caps.latest.revision: 21
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
ms.openlocfilehash: cd7fbce5c382c3acd88a12277a3d7899b823d049
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="special-characters-in-code-visual-basic"></a><span data-ttu-id="f3a8d-102">코드의 특수 문자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f3a8d-102">Special Characters in Code (Visual Basic)</span></span>
<span data-ttu-id="f3a8d-103">숫자 하지 않은 문자를, 사용자 코드에서 특수 문자를 사용 해야 하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3a8d-103">Sometimes you have to use special characters in your code, that is, characters that are not alphabetical or numeric.</span></span> <span data-ttu-id="f3a8d-104">문장 부호와 특수 문자는 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 문자 집합은 컴파일러 또는 컴파일된 프로그램이 수행 하는 작업 정의에 프로그램 텍스트의 구성에서 다양 한 용도로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3a8d-104">The punctuation and special characters in the [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] character set have various uses, from organizing program text to defining the tasks that the compiler or the compiled program performs.</span></span> <span data-ttu-id="f3a8d-105">이러한 특수 문자는 수행할 작업을 지정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f3a8d-105">They do not specify an operation to be performed.</span></span>  
  
## <a name="parentheses"></a><span data-ttu-id="f3a8d-106">괄호</span><span class="sxs-lookup"><span data-stu-id="f3a8d-106">Parentheses</span></span>  
 <span data-ttu-id="f3a8d-107">와 같은 프로시저를 정의 하는 경우 괄호를 사용 하 여 한 `Sub` 또는 `Function`합니다.</span><span class="sxs-lookup"><span data-stu-id="f3a8d-107">Use parentheses when you define a procedure, such as a `Sub` or `Function`.</span></span> <span data-ttu-id="f3a8d-108">모든 프로시저 인수 목록은 괄호로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3a8d-108">You must enclose all procedure argument lists in parentheses.</span></span> <span data-ttu-id="f3a8d-109">또한 괄호를 사용 하면 변수 또는 인수를 논리 그룹으로 배치 하는 데 특히 복잡 한 식에서 연산자 우선 순위의 기본 순서를 무시 하 게 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3a8d-109">You also use parentheses for putting variables or arguments into logical groups, especially to override the default order of operator precedence in a complex expression.</span></span> <span data-ttu-id="f3a8d-110">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="f3a8d-110">The following example illustrates this.</span></span>  
  
 <span data-ttu-id="f3a8d-111">[!code-vb[VbVbcnConventions #&11;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="f3a8d-111">[!code-vb[VbVbcnConventions#11](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_1.vb)]</span></span>  
  
 <span data-ttu-id="f3a8d-112">앞의 코드에서 값을 실행 하 고 `d` 은 8.225 값 `e` 은 3입니다.</span><span class="sxs-lookup"><span data-stu-id="f3a8d-112">Following execution of the previous code, the value of `d` is 8.225 and the value of `e` is 3.</span></span> <span data-ttu-id="f3a8d-113">에 대 한 계산 `d` 는 기본 우선 순위를 사용 하 여 `/` 통해 `+` 와 같습니다 `d = b + (c / a)`합니다.</span><span class="sxs-lookup"><span data-stu-id="f3a8d-113">The calculation for `d` uses the default precedence of `/` over `+` and is equivalent to `d = b + (c / a)`.</span></span> <span data-ttu-id="f3a8d-114">에 대 한 계산에 괄호 `e` 기본 우선 순위를 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3a8d-114">The parentheses in the calculation for `e` override the default precedence.</span></span>  
  
## <a name="separators"></a><span data-ttu-id="f3a8d-115">Separators</span><span class="sxs-lookup"><span data-stu-id="f3a8d-115">Separators</span></span>  
 <span data-ttu-id="f3a8d-116">구분 기호 그 이름이 의미 하는 기능을 수행 합니다: 여러 코드 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="f3a8d-116">Separators do what their name suggests: they separate sections of code.</span></span> <span data-ttu-id="f3a8d-117">[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], 구분 기호 문자는 콜론 (`:`).</span><span class="sxs-lookup"><span data-stu-id="f3a8d-117">In [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], the separator character is the colon (`:`).</span></span> <span data-ttu-id="f3a8d-118">별도 줄이 아니라 한 줄에 여러 개의 문을 포함 하려면 구분 기호를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3a8d-118">Use separators when you want to include multiple statements on a single line instead of separate lines.</span></span> <span data-ttu-id="f3a8d-119">이 공간을 절약 하 고 코드의 가독성을 향상 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="f3a8d-119">This saves space and improves the readability of your code.</span></span> <span data-ttu-id="f3a8d-120">다음 예제에는 콜론으로 구분 된 세 개의 문을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f3a8d-120">The following example shows three statements separated by colons.</span></span>  
  
 <span data-ttu-id="f3a8d-121">[!code-vb[VbVbcnConventions #&12;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="f3a8d-121">[!code-vb[VbVbcnConventions#12](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_2.vb)]</span></span>  
  
 <span data-ttu-id="f3a8d-122">자세한 내용은 참조 [하는 방법: 중단 되 고 코드에서 문 결합](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f3a8d-122">For more information, see [How to: Break and Combine Statements in Code](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).</span></span>  
  
 <span data-ttu-id="f3a8d-123">콜론 (`:`) 문자는 또한 문 레이블을 식별 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3a8d-123">The colon (`:`) character is also used to identify a statement label.</span></span> <span data-ttu-id="f3a8d-124">자세한 내용은 참조 [하는 방법: Label 문](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f3a8d-124">For more information, see [How to: Label Statements](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).</span></span>  
  
## <a name="concatenation"></a><span data-ttu-id="f3a8d-125">연결 연산</span><span class="sxs-lookup"><span data-stu-id="f3a8d-125">Concatenation</span></span>  
 <span data-ttu-id="f3a8d-126">사용 하는 `&` 에 대 한 연산자 *연결*, 또는 문자열을 함께 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3a8d-126">Use the `&` operator for *concatenation*, or linking strings together.</span></span> <span data-ttu-id="f3a8d-127">혼동 하지 마십시오는 `+` 함께 숫자 값을 추가 하는 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="f3a8d-127">Do not confuse it with the `+` operator, which adds together numeric values.</span></span> <span data-ttu-id="f3a8d-128">사용 하는 경우는 `+` 연산자를 숫자 값으로 작업할 때 잘못 된 결과 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3a8d-128">If you use the `+` operator to concatenate when you operate on numeric values, you can obtain incorrect results.</span></span> <span data-ttu-id="f3a8d-129">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="f3a8d-129">The following example demonstrates this.</span></span>  
  
 <span data-ttu-id="f3a8d-130">[!code-vb[VbVbcnConventions #&13;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="f3a8d-130">[!code-vb[VbVbcnConventions#13](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_3.vb)]</span></span>  
  
 <span data-ttu-id="f3a8d-131">앞의 코드에서 값을 실행 하 고 `resultA` 21.01의 값은 `resultB` "10.0111로 실행" 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3a8d-131">Following execution of the previous code, the value of `resultA` is 21.01 and the value of `resultB` is "10.0111".</span></span>  
  
## <a name="member-access-operators"></a><span data-ttu-id="f3a8d-132">멤버 액세스 연산자</span><span class="sxs-lookup"><span data-stu-id="f3a8d-132">Member Access Operators</span></span>  
 <span data-ttu-id="f3a8d-133">점 연산자를 사용 하면 형식 멤버에 액세스 하려면 (`.`) 또는 느낌표 (`!`) 형식 이름과 멤버 이름 사이 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="f3a8d-133">To access a member of a type, you use the dot (`.`) or exclamation point (`!`) operator between the type name and the member name.</span></span>  
  
### <a name="dot--operator"></a><span data-ttu-id="f3a8d-134">점 (입니다.) 연산자</span><span class="sxs-lookup"><span data-stu-id="f3a8d-134">Dot (.) Operator</span></span>  
 <span data-ttu-id="f3a8d-135">사용 된 `.` 클래스, 구조체, 인터페이스 또는 열거형의 멤버 액세스 연산자와 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="f3a8d-135">Use the `.` operator on a class, structure, interface, or enumeration as a member access operator.</span></span> <span data-ttu-id="f3a8d-136">필드, 속성, 이벤트 또는 메서드 멤버 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3a8d-136">The member can be a field, property, event, or method.</span></span> <span data-ttu-id="f3a8d-137">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="f3a8d-137">The following example illustrates this.</span></span>  
  
 <span data-ttu-id="f3a8d-138">[!code-vb[VbVbcnConventions #&14;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="f3a8d-138">[!code-vb[VbVbcnConventions#14](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_4.vb)]</span></span>  
  
### <a name="exclamation-point--operator"></a><span data-ttu-id="f3a8d-139">느낌표 (!) 연산자</span><span class="sxs-lookup"><span data-stu-id="f3a8d-139">Exclamation Point (!) Operator</span></span>  
 <span data-ttu-id="f3a8d-140">사용 된 `!` 사전 액세스 연산자와 클래스 또는 인터페이스에 대해서만 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="f3a8d-140">Use the `!` operator only on a class or interface as a dictionary access operator.</span></span> <span data-ttu-id="f3a8d-141">클래스 또는 인터페이스에는 단일 허용 하는 기본 속성 있어야 `String` 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="f3a8d-141">The class or interface must have a default property that accepts a single `String` argument.</span></span> <span data-ttu-id="f3a8d-142">바로 다음에 오는 식별자는 `!` 연산자를 문자열로 기본 속성에 전달 된 인수 값이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3a8d-142">The identifier immediately following the `!` operator becomes the argument value passed to the default property as a string.</span></span> <span data-ttu-id="f3a8d-143">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="f3a8d-143">The following example demonstrates this.</span></span>  
  
 <span data-ttu-id="f3a8d-144">[!code-vb[VbVbcnConventions #&15;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="f3a8d-144">[!code-vb[VbVbcnConventions#15](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_5.vb)]</span></span>  
  
 <span data-ttu-id="f3a8d-145">3 개의 출력 줄의 `MsgBox` 모두 표시 값 `32856`합니다.</span><span class="sxs-lookup"><span data-stu-id="f3a8d-145">The three output lines of `MsgBox` all display the value `32856`.</span></span> <span data-ttu-id="f3a8d-146">속성에 대 한 일반적인 액세스를 사용 하는 첫 번째 줄 `index`, 두 번째 사실을 활용 하는 `index` 클래스의 기본 속성은 `hasDefault`, 세 번째 클래스에 대 한 사전 액세스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3a8d-146">The first line uses the traditional access to property `index`, the second makes use of the fact that `index` is the default property of class `hasDefault`, and the third uses dictionary access to the class.</span></span>  
  
 <span data-ttu-id="f3a8d-147">두 번째 피연산자는 `!` 연산자는 큰따옴표로 묶지는 유효한 Visual Basic 식별자 여야 합니다 (`" "`).</span><span class="sxs-lookup"><span data-stu-id="f3a8d-147">Note that the second operand of the `!` operator must be a valid Visual Basic identifier not enclosed in double quotation marks (`" "`).</span></span> <span data-ttu-id="f3a8d-148">즉, 문자열 리터럴 또는 문자열 변수를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f3a8d-148">In other words, you cannot use a string literal or string variable.</span></span> <span data-ttu-id="f3a8d-149">다음과 같이 변경 하면 마지막 줄은 `MsgBox` 호출 하면 오류가 발생 하기 때문에 `"X"` 은 괄호로 묶인된 문자열 리터럴.</span><span class="sxs-lookup"><span data-stu-id="f3a8d-149">The following change to the last line of the `MsgBox` call generates an error because `"X"` is an enclosed string literal.</span></span>  
  
 `"Dictionary access returns " & hD!"X")`  
  
> [!NOTE]
>  <span data-ttu-id="f3a8d-150">기본 컬렉션에 대 한 참조를 명시적 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3a8d-150">References to default collections must be explicit.</span></span> <span data-ttu-id="f3a8d-151">특히, 사용할 수 없습니다는 `!` 연산자의 런타임에 바인딩된 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="f3a8d-151">In particular, you cannot use the `!` operator on a late-bound variable.</span></span>  
  
 <span data-ttu-id="f3a8d-152">`!` 문자는로 사용은 `Single` 문자를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3a8d-152">The `!` character is also used as the `Single` type character.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3a8d-153">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f3a8d-153">See Also</span></span>  
 <span data-ttu-id="f3a8d-154">[프로그램 구조 및 코드 규칙](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md) </span><span class="sxs-lookup"><span data-stu-id="f3a8d-154">[Program Structure and Code Conventions](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md) </span></span>  
<span data-ttu-id="f3a8d-155"> [형식 문자](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)</span><span class="sxs-lookup"><span data-stu-id="f3a8d-155"> [Type Characters](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)</span></span>
