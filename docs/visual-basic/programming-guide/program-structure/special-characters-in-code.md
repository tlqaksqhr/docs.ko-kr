---
title: 코드의 특수 문자(Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
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
helpviewer_keywords:
- special characters [Visual Basic], in code
- parentheses [Visual Basic], using in code
- colons (:)
- period character in code
- dot operator (.)
- dictionary access operator [Visual Basic]
- concatenation operators [Visual Basic], special characters in code
- concatenation operators [Visual Basic], vs. addition operator
- '! operator'
- separators [Visual Basic], using in code
- operators [Visual Basic], dictionary access
- ': separator character'
- member access operator [Visual Basic]
- addition operator [Visual Basic]
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
ms.openlocfilehash: b724c48320f74045d7192be6d6e269c00511ffc9
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="special-characters-in-code-visual-basic"></a><span data-ttu-id="7c4f9-102">코드의 특수 문자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7c4f9-102">Special Characters in Code (Visual Basic)</span></span>
<span data-ttu-id="7c4f9-103">경우에 따라 영문자 또는 숫자 하지 않은 문자가 즉, 사용자 코드에 특수 문자를 사용 해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c4f9-103">Sometimes you have to use special characters in your code, that is, characters that are not alphabetical or numeric.</span></span> <span data-ttu-id="7c4f9-104">문장 부호 및 Visual Basic 문자 집합의 특수 문자는 프로그램 텍스트에서 컴파일러 또는 컴파일된 프로그램이 수행 하는 작업 정의에 이르기까지 다양 한 용도로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c4f9-104">The punctuation and special characters in the Visual Basic character set have various uses, from organizing program text to defining the tasks that the compiler or the compiled program performs.</span></span> <span data-ttu-id="7c4f9-105">이러한 특수 문자는 수행할 작업을 지정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7c4f9-105">They do not specify an operation to be performed.</span></span>  
  
## <a name="parentheses"></a><span data-ttu-id="7c4f9-106">괄호</span><span class="sxs-lookup"><span data-stu-id="7c4f9-106">Parentheses</span></span>  
 <span data-ttu-id="7c4f9-107">와 같은 프로시저를 정의 하는 경우 괄호를 사용 하 여 한 `Sub` 또는 `Function`합니다.</span><span class="sxs-lookup"><span data-stu-id="7c4f9-107">Use parentheses when you define a procedure, such as a `Sub` or `Function`.</span></span> <span data-ttu-id="7c4f9-108">모든 프로시저 인수 목록을 괄호로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c4f9-108">You must enclose all procedure argument lists in parentheses.</span></span> <span data-ttu-id="7c4f9-109">또한 사용 하면 괄호를 논리 그룹으로 변수나 인수에 대 한 특히 다시 정의할 복잡 한 식에서 연산자 우선 순위의 기본 순서입니다.</span><span class="sxs-lookup"><span data-stu-id="7c4f9-109">You also use parentheses for putting variables or arguments into logical groups, especially to override the default order of operator precedence in a complex expression.</span></span> <span data-ttu-id="7c4f9-110">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="7c4f9-110">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbcnConventions#11](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_1.vb)]  
  
 <span data-ttu-id="7c4f9-111">값을 이전 코드의 실행 `d` 8.225의 값은 `e` 3입니다.</span><span class="sxs-lookup"><span data-stu-id="7c4f9-111">Following execution of the previous code, the value of `d` is 8.225 and the value of `e` is 3.</span></span> <span data-ttu-id="7c4f9-112">에 대 한 계산 `d` 는 기본 우선 순위를 사용 하 여 `/` 통해 `+` 와 같습니다 `d = b + (c / a)`합니다.</span><span class="sxs-lookup"><span data-stu-id="7c4f9-112">The calculation for `d` uses the default precedence of `/` over `+` and is equivalent to `d = b + (c / a)`.</span></span> <span data-ttu-id="7c4f9-113">에 대 한 계산에 괄호 `e` 기본 우선 순위를 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c4f9-113">The parentheses in the calculation for `e` override the default precedence.</span></span>  
  
## <a name="separators"></a><span data-ttu-id="7c4f9-114">Separators</span><span class="sxs-lookup"><span data-stu-id="7c4f9-114">Separators</span></span>  
 <span data-ttu-id="7c4f9-115">구분 기호는 이름 기준의 제안지 않습니다: 여러 코드 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="7c4f9-115">Separators do what their name suggests: they separate sections of code.</span></span> <span data-ttu-id="7c4f9-116">Visual Basic의 경우 구분 기호 문자는 콜론 (`:`).</span><span class="sxs-lookup"><span data-stu-id="7c4f9-116">In Visual Basic, the separator character is the colon (`:`).</span></span> <span data-ttu-id="7c4f9-117">별도 줄이 아니라 한 줄에 여러 개의 문을 포함할 구분 기호를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c4f9-117">Use separators when you want to include multiple statements on a single line instead of separate lines.</span></span> <span data-ttu-id="7c4f9-118">이 공간을 절약 하 고 코드의 가독성을 향상 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c4f9-118">This saves space and improves the readability of your code.</span></span> <span data-ttu-id="7c4f9-119">다음 예제에는 콜론으로 구분 된 세 가지 문을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7c4f9-119">The following example shows three statements separated by colons.</span></span>  
  
 [!code-vb[VbVbcnConventions#12](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_2.vb)]  
  
 <span data-ttu-id="7c4f9-120">자세한 내용은 참조 [하는 방법: 해제 및 코드에서 문 결합](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7c4f9-120">For more information, see [How to: Break and Combine Statements in Code](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).</span></span>  
  
 <span data-ttu-id="7c4f9-121">콜론 (`:`) 문자는 또한 문 레이블을 식별 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c4f9-121">The colon (`:`) character is also used to identify a statement label.</span></span> <span data-ttu-id="7c4f9-122">자세한 내용은 참조 [하는 방법: Label 문](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7c4f9-122">For more information, see [How to: Label Statements](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).</span></span>  
  
## <a name="concatenation"></a><span data-ttu-id="7c4f9-123">연결 연산</span><span class="sxs-lookup"><span data-stu-id="7c4f9-123">Concatenation</span></span>  
 <span data-ttu-id="7c4f9-124">사용 하 여는 `&` 에 대 한 연산자 *연결*, 또는 문자열을 함께 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c4f9-124">Use the `&` operator for *concatenation*, or linking strings together.</span></span> <span data-ttu-id="7c4f9-125">혼동 하지 마십시오는 `+` 숫자 값을 함께 추가 하는 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="7c4f9-125">Do not confuse it with the `+` operator, which adds together numeric values.</span></span> <span data-ttu-id="7c4f9-126">사용 하는 경우는 `+` 연산자를 숫자 값으로 작업할 때 잘못 된 결과 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c4f9-126">If you use the `+` operator to concatenate when you operate on numeric values, you can obtain incorrect results.</span></span> <span data-ttu-id="7c4f9-127">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="7c4f9-127">The following example demonstrates this.</span></span>  
  
 [!code-vb[VbVbcnConventions#13](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_3.vb)]  
  
 <span data-ttu-id="7c4f9-128">값을 이전 코드의 실행 `resultA` 21.01의 값은 `resultB` "10.0111로 실행" 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c4f9-128">Following execution of the previous code, the value of `resultA` is 21.01 and the value of `resultB` is "10.0111".</span></span>  
  
## <a name="member-access-operators"></a><span data-ttu-id="7c4f9-129">멤버 액세스 연산자</span><span class="sxs-lookup"><span data-stu-id="7c4f9-129">Member Access Operators</span></span>  
 <span data-ttu-id="7c4f9-130">점 형식의 멤버에 액세스 하려면 사용 (`.`) 또는 느낌표 (`!`) 연산자 형식 이름과 멤버 이름 사이입니다.</span><span class="sxs-lookup"><span data-stu-id="7c4f9-130">To access a member of a type, you use the dot (`.`) or exclamation point (`!`) operator between the type name and the member name.</span></span>  
  
### <a name="dot--operator"></a><span data-ttu-id="7c4f9-131">점 (입니다.) 연산자</span><span class="sxs-lookup"><span data-stu-id="7c4f9-131">Dot (.) Operator</span></span>  
 <span data-ttu-id="7c4f9-132">사용 하 여는 `.` 연산자를 클래스, 구조체, 인터페이스 또는 열거형의 멤버 액세스 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="7c4f9-132">Use the `.` operator on a class, structure, interface, or enumeration as a member access operator.</span></span> <span data-ttu-id="7c4f9-133">필드, 속성, 이벤트 또는 메서드 멤버 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c4f9-133">The member can be a field, property, event, or method.</span></span> <span data-ttu-id="7c4f9-134">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="7c4f9-134">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbcnConventions#14](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_4.vb)]  
  
### <a name="exclamation-point--operator"></a><span data-ttu-id="7c4f9-135">느낌표 (!) 연산자</span><span class="sxs-lookup"><span data-stu-id="7c4f9-135">Exclamation Point (!) Operator</span></span>  
 <span data-ttu-id="7c4f9-136">사용 된 `!` 사전 액세스 연산자와 클래스 또는 인터페이스에 대해서만 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="7c4f9-136">Use the `!` operator only on a class or interface as a dictionary access operator.</span></span> <span data-ttu-id="7c4f9-137">클래스 또는 인터페이스에는 단일 허용 하는 기본 속성이 있어야 `String` 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="7c4f9-137">The class or interface must have a default property that accepts a single `String` argument.</span></span> <span data-ttu-id="7c4f9-138">바로 뒤에 식별자는 `!` 연산자에 기본 속성을 문자열로 전달 된 인수 값이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c4f9-138">The identifier immediately following the `!` operator becomes the argument value passed to the default property as a string.</span></span> <span data-ttu-id="7c4f9-139">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="7c4f9-139">The following example demonstrates this.</span></span>  
  
 [!code-vb[VbVbcnConventions#15](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_5.vb)]  
  
 <span data-ttu-id="7c4f9-140">3 개의 출력의 줄 `MsgBox` 모든 값을 표시할 `32856`합니다.</span><span class="sxs-lookup"><span data-stu-id="7c4f9-140">The three output lines of `MsgBox` all display the value `32856`.</span></span> <span data-ttu-id="7c4f9-141">첫 번째 줄은 속성에 대 한 일반적인 액세스를 사용 하 여 `index`, 두 번째에서는 팩트를 활용 하는 `index` 클래스의 기본 속성은 `hasDefault`, 세 번째 사전 클래스에 대 한 액세스를 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c4f9-141">The first line uses the traditional access to property `index`, the second makes use of the fact that `index` is the default property of class `hasDefault`, and the third uses dictionary access to the class.</span></span>  
  
 <span data-ttu-id="7c4f9-142">두 번째 피연산자는 `!` 연산자 큰따옴표로 묶지 유효한 Visual Basic 식별자 여야 합니다 (`" "`).</span><span class="sxs-lookup"><span data-stu-id="7c4f9-142">Note that the second operand of the `!` operator must be a valid Visual Basic identifier not enclosed in double quotation marks (`" "`).</span></span> <span data-ttu-id="7c4f9-143">즉, 문자열 리터럴 또는 문자열 변수를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7c4f9-143">In other words, you cannot use a string literal or string variable.</span></span> <span data-ttu-id="7c4f9-144">다음과 같이 변경 하면 마지막 줄에서 `MsgBox` 호출 하면 오류가 발생 하기 때문에 `"X"` 은 괄호로 묶은 문자열 리터럴.</span><span class="sxs-lookup"><span data-stu-id="7c4f9-144">The following change to the last line of the `MsgBox` call generates an error because `"X"` is an enclosed string literal.</span></span>  
  
 `"Dictionary access returns " & hD!"X")`  
  
> [!NOTE]
>  <span data-ttu-id="7c4f9-145">기본 컬렉션에 대 한 참조를 명시적 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c4f9-145">References to default collections must be explicit.</span></span> <span data-ttu-id="7c4f9-146">특히, 사용할 수 없습니다는 `!` 런타임에 바인딩된 변수에 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="7c4f9-146">In particular, you cannot use the `!` operator on a late-bound variable.</span></span>  
  
 <span data-ttu-id="7c4f9-147">`!` 문자는로 사용은 `Single` 문자를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c4f9-147">The `!` character is also used as the `Single` type character.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c4f9-148">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7c4f9-148">See Also</span></span>  
 [<span data-ttu-id="7c4f9-149">프로그램 구조 및 코드 규칙</span><span class="sxs-lookup"><span data-stu-id="7c4f9-149">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)  
 [<span data-ttu-id="7c4f9-150">형식 문자</span><span class="sxs-lookup"><span data-stu-id="7c4f9-150">Type Characters</span></span>](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
