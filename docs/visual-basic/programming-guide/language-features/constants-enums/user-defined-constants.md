---
title: 사용자 정의 상수(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- constants [Visual Basic], circular references
- Const statement [Visual Basic], user-defined constants
- user-defined constants [Visual Basic]
- scope [Visual Basic], constants
- constants [Visual Basic], user-defined
- circular references between constants [Visual Basic]
ms.assetid: a1206d5c-c45e-4ac2-970a-4a0be6a05fdd
ms.openlocfilehash: b4a7e2b63b930b98ee082c0104c24f6857b5b35b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33648777"
---
# <a name="user-defined-constants-visual-basic"></a><span data-ttu-id="4fc86-102">사용자 정의 상수(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4fc86-102">User-Defined Constants (Visual Basic)</span></span>
<span data-ttu-id="4fc86-103">상수는 숫자 또는 변경 되지 않는 문자열의 일어나는 의미 있는 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4fc86-103">A constant is a meaningful name that takes the place of a number or string that does not change.</span></span> <span data-ttu-id="4fc86-104">상수는 응용 프로그램 실행 중 변함없이 유지되는 값을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="4fc86-104">Constants store values that, as the name implies, remain constant throughout the execution of an application.</span></span> <span data-ttu-id="4fc86-105">컨트롤이 나 함께 작업 하는 구성 요소에 정의 된 상수를 사용할 수 하거나 직접 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fc86-105">You can use constants that are defined by the controls or components you work with, or you can create your own.</span></span> <span data-ttu-id="4fc86-106">직접 만든 상수를 상수 라고 *사용자 정의*합니다.</span><span class="sxs-lookup"><span data-stu-id="4fc86-106">Constants you create yourself are described as *user-defined*.</span></span>  
  
 <span data-ttu-id="4fc86-107">상수를 선언에서 `Const` 문을, 변수 이름을 만들 때와 동일한 방법 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fc86-107">You declare a constant with the `Const` statement, using the same guidelines you would for creating a variable name.</span></span> <span data-ttu-id="4fc86-108">경우 `Option Strict` 은 `On`, 상수 형식을 명시적으로 선언 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fc86-108">If `Option Strict` is `On`, you must explicitly declare the constant type.</span></span>  
  
## <a name="const-statement-usage"></a><span data-ttu-id="4fc86-109">Const 문 사용</span><span class="sxs-lookup"><span data-stu-id="4fc86-109">Const Statement Usage</span></span>  
 <span data-ttu-id="4fc86-110">A `Const` 문 수 수치 나타낼 또는 날짜/시간 값:</span><span class="sxs-lookup"><span data-stu-id="4fc86-110">A `Const` statement can represent a mathematical or date/time quantity:</span></span>  
  
 [!code-vb[VbEnumsTask#10](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_1.vb)]  
  
 <span data-ttu-id="4fc86-111">정의할 수도 있습니다 `String` 상수:</span><span class="sxs-lookup"><span data-stu-id="4fc86-111">It also can define `String` constants:</span></span>  
  
 [!code-vb[VbEnumsTask#13](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_2.vb)]  
  
 <span data-ttu-id="4fc86-112">등호 기호의 오른쪽에 있는 식 ( `=` )는 숫자 또는 문자열 리터럴, 주로 발생 하지만 (하지만 식에 함수 호출이 포함 될 수 없습니다) 숫자 또는 문자열에 테이블이 되는 식이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fc86-112">The expression on the right side of the equal sign ( `=` ) is often a number or literal string, but it also can be an expression that results in a number or string (although that expression cannot contain calls to functions).</span></span> <span data-ttu-id="4fc86-113">이전에 정의 된 상수를 기준으로 상수를 정의할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fc86-113">You can even define constants in terms of previously defined constants:</span></span>  
  
 [!code-vb[VbEnumsTask#15](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_3.vb)]  
  
## <a name="scope-of-user-defined-constants"></a><span data-ttu-id="4fc86-114">사용자 정의 상수의 범위</span><span class="sxs-lookup"><span data-stu-id="4fc86-114">Scope of User-Defined Constants</span></span>  
 <span data-ttu-id="4fc86-115">A `Const` 문의 범위는 같은 위치에 선언 된 변수에 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fc86-115">A `Const` statement's scope is the same as that of a variable declared in the same location.</span></span> <span data-ttu-id="4fc86-116">다음과 같은 방법으로 범위를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fc86-116">You can specify scope in any of the following ways:</span></span>  
  
-   <span data-ttu-id="4fc86-117">프로시저 내에 존재 하는 상수를 만들려면 해당 절차 내에서 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fc86-117">To create a constant that exists only within a procedure, declare it within that procedure.</span></span>  
  
-   <span data-ttu-id="4fc86-118">클래스 내의 모든 프로시저에 속하지만 해당 모듈 외부 코드에 사용할 수 있는 상수를 만들려면 클래스의 선언 섹션에서 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fc86-118">To create a constant available to all procedures within a class, but not to any code outside that module, declare it in the declarations section of the class.</span></span>  
  
-   <span data-ttu-id="4fc86-119">어셈블리의 클라이언트 외부 아니라 어셈블리의 모든 구성원에 사용할 수 있는 상수를 만들려면 사용 하 여 선언는 `Friend` 클래스의 선언 섹션에는 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="4fc86-119">To create a constant that is available to all members of an assembly, but not to outside clients of the assembly, declare it using the `Friend` keyword in the declarations section of the class.</span></span>  
  
-   <span data-ttu-id="4fc86-120">응용 프로그램에 걸쳐 사용할 수 있는 상수를 만들려면 사용 하 여 선언 된 `Public` 선언에서 키워드 섹션 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="4fc86-120">To create a constant available throughout the application, declare it using the `Public` keyword in the declarations section the class.</span></span>  
  
 <span data-ttu-id="4fc86-121">자세한 내용은 참조 [하는 방법: A 상수 선언](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4fc86-121">For more information, see [How to: Declare A Constant](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md).</span></span>  
  
### <a name="avoiding-circular-references"></a><span data-ttu-id="4fc86-122">순환 참조를 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="4fc86-122">Avoiding Circular References</span></span>  
 <span data-ttu-id="4fc86-123">다른 상수 상수 정의 될 수 있습니다, 이므로에 실수로 만들 수는 *주기*, 또는 두 개 이상의 상수 간의 순환 참조.</span><span class="sxs-lookup"><span data-stu-id="4fc86-123">Because constants can be defined in terms of other constants, it is possible to inadvertently create a *cycle*, or circular reference, between two or more constants.</span></span> <span data-ttu-id="4fc86-124">다음 예제와 같이 서로 의해 정의 되는 각각 두 개 이상의 공용 상수 경우 순환이 발생:</span><span class="sxs-lookup"><span data-stu-id="4fc86-124">A cycle occurs when you have two or more public constants, each of which is defined in terms of the other, as in the following example:</span></span>  
  
 [!code-vb[VbEnumsTask#16](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_4.vb)]  
[!code-vb[VbEnumsTask#17](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_5.vb)]  
  
 <span data-ttu-id="4fc86-125">주기가 발생 하는 경우 Visual Basic 컴파일러 오류를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fc86-125">If a cycle occurs, Visual Basic generates a compiler error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fc86-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4fc86-126">See Also</span></span>  
 [<span data-ttu-id="4fc86-127">Const 문</span><span class="sxs-lookup"><span data-stu-id="4fc86-127">Const Statement</span></span>](../../../../visual-basic/language-reference/statements/const-statement.md)  
 [<span data-ttu-id="4fc86-128">상수 및 리터럴 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="4fc86-128">Constant and Literal Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)  
 [<span data-ttu-id="4fc86-129">상수 및 열거형</span><span class="sxs-lookup"><span data-stu-id="4fc86-129">Constants and Enumerations</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/index.md)  
 [<span data-ttu-id="4fc86-130">상수 및 열거형</span><span class="sxs-lookup"><span data-stu-id="4fc86-130">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)  
 [<span data-ttu-id="4fc86-131">열거형 개요</span><span class="sxs-lookup"><span data-stu-id="4fc86-131">Enumerations Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)  
 [<span data-ttu-id="4fc86-132">상수 개요</span><span class="sxs-lookup"><span data-stu-id="4fc86-132">Constants Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)  
 [<span data-ttu-id="4fc86-133">방법: 열거형 선언</span><span class="sxs-lookup"><span data-stu-id="4fc86-133">How to: Declare an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)  
 [<span data-ttu-id="4fc86-134">열거형 및 이름 한정</span><span class="sxs-lookup"><span data-stu-id="4fc86-134">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)  
 [<span data-ttu-id="4fc86-135">Option Strict 문</span><span class="sxs-lookup"><span data-stu-id="4fc86-135">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
