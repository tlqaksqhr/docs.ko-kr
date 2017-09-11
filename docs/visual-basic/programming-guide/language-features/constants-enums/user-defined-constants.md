---
title: "사용자 정의 상수 (Visual Basic) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- constants, circular references
- Const statement [Visual Basic], user-defined constants
- user-defined constants
- scope, constants
- constants, user-defined
- circular references between constants
ms.assetid: a1206d5c-c45e-4ac2-970a-4a0be6a05fdd
caps.latest.revision: 19
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
ms.openlocfilehash: b1ab1501309823b1565d5198fff25edf2927a2ce
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="user-defined-constants-visual-basic"></a><span data-ttu-id="02e27-102">사용자 정의 상수(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="02e27-102">User-Defined Constants (Visual Basic)</span></span>
<span data-ttu-id="02e27-103">상수는 숫자 또는 변경 되지 않는 문자열의 발생 하는 의미 있는 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="02e27-103">A constant is a meaningful name that takes the place of a number or string that does not change.</span></span> <span data-ttu-id="02e27-104">상수 이름에서 알 수 있듯이 응용 프로그램의 실행 하는 동안 일정 하 게 유지 하는 값을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="02e27-104">Constants store values that, as the name implies, remain constant throughout the execution of an application.</span></span> <span data-ttu-id="02e27-105">컨트롤이 나 함께 작업 하는 구성 요소에 의해 정의 된 상수를 사용할 수 또는 직접 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02e27-105">You can use constants that are defined by the controls or components you work with, or you can create your own.</span></span> <span data-ttu-id="02e27-106">사용자가 직접 만든 상수 상수 라고 *사용자 정의*합니다.</span><span class="sxs-lookup"><span data-stu-id="02e27-106">Constants you create yourself are described as *user-defined*.</span></span>  
  
 <span data-ttu-id="02e27-107">상수를 선언에서 `Const` 문을, 변수 이름을 만들 때와 동일한 방법 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="02e27-107">You declare a constant with the `Const` statement, using the same guidelines you would for creating a variable name.</span></span> <span data-ttu-id="02e27-108">경우 `Option Strict` 는 `On`, 상수 형식을 명시적으로 선언 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="02e27-108">If `Option Strict` is `On`, you must explicitly declare the constant type.</span></span>  
  
## <a name="const-statement-usage"></a><span data-ttu-id="02e27-109">Const 문 사용</span><span class="sxs-lookup"><span data-stu-id="02e27-109">Const Statement Usage</span></span>  
 <span data-ttu-id="02e27-110">A `Const` 문 수 수치 나타낼 또는 날짜/시간 값:</span><span class="sxs-lookup"><span data-stu-id="02e27-110">A `Const` statement can represent a mathematical or date/time quantity:</span></span>  
  
 <span data-ttu-id="02e27-111">[!code-vb[VbEnumsTask #&10;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="02e27-111">[!code-vb[VbEnumsTask#10](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_1.vb)]</span></span>  
  
 <span data-ttu-id="02e27-112">정의할 수도 있습니다 `String` 상수:</span><span class="sxs-lookup"><span data-stu-id="02e27-112">It also can define `String` constants:</span></span>  
  
 <span data-ttu-id="02e27-113">[!code-vb[VbEnumsTask #&13;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="02e27-113">[!code-vb[VbEnumsTask#13](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_2.vb)]</span></span>  
  
 <span data-ttu-id="02e27-114">등호 오른쪽에 있는 식 ( `=` )는 대개 숫자 또는 리터럴 문자열 하지만 결과 숫자 또는 문자열 (식에 함수 호출이 포함 될 수 없습니다) 식일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02e27-114">The expression on the right side of the equal sign ( `=` ) is often a number or literal string, but it also can be an expression that results in a number or string (although that expression cannot contain calls to functions).</span></span> <span data-ttu-id="02e27-115">이전에 정의 된 상수를 기준으로 상수를 정의할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02e27-115">You can even define constants in terms of previously defined constants:</span></span>  
  
 <span data-ttu-id="02e27-116">[!code-vb[VbEnumsTask #&15;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="02e27-116">[!code-vb[VbEnumsTask#15](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_3.vb)]</span></span>  
  
## <a name="scope-of-user-defined-constants"></a><span data-ttu-id="02e27-117">사용자 정의 상수의 범위</span><span class="sxs-lookup"><span data-stu-id="02e27-117">Scope of User-Defined Constants</span></span>  
 <span data-ttu-id="02e27-118">A `Const` 문의 범위는 같은 위치에 선언 된 변수에 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="02e27-118">A `Const` statement's scope is the same as that of a variable declared in the same location.</span></span> <span data-ttu-id="02e27-119">다음 방법 중 하나에서 범위를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02e27-119">You can specify scope in any of the following ways:</span></span>  
  
-   <span data-ttu-id="02e27-120">프로시저 내에 존재 하는 상수를 만들려면 해당 프로시저 내에서 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="02e27-120">To create a constant that exists only within a procedure, declare it within that procedure.</span></span>  
  
-   <span data-ttu-id="02e27-121">클래스 내의 모든 프로시저에 있지만 해당 모듈 외부 코드에 사용할 수 있는 상수를 만들려면 클래스의 선언 섹션에서 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="02e27-121">To create a constant available to all procedures within a class, but not to any code outside that module, declare it in the declarations section of the class.</span></span>  
  
-   <span data-ttu-id="02e27-122">사용 하 여 선언 된 어셈블리의 클라이언트 외부 아니라 어셈블리의 모든 구성원에 사용할 수 있는 상수를 만들려면는 `Friend` 키워드는 클래스의 선언 섹션에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02e27-122">To create a constant that is available to all members of an assembly, but not to outside clients of the assembly, declare it using the `Friend` keyword in the declarations section of the class.</span></span>  
  
-   <span data-ttu-id="02e27-123">응용 프로그램에 걸쳐 사용할 수 있는 상수를 만들려면 사용 하 여 선언 된 `Public` 키워드는 선언에는 클래스를 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="02e27-123">To create a constant available throughout the application, declare it using the `Public` keyword in the declarations section the class.</span></span>  
  
 <span data-ttu-id="02e27-124">자세한 내용은 참조 [하는 방법: A 상수 선언](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="02e27-124">For more information, see [How to: Declare A Constant](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md).</span></span>  
  
### <a name="avoiding-circular-references"></a><span data-ttu-id="02e27-125">순환 참조를 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="02e27-125">Avoiding Circular References</span></span>  
 <span data-ttu-id="02e27-126">실수로 만들 수는 다른 상수를 기준으로 상수를 정의할 수는 *주기*, 또는 두 개 이상의 상수 간의 순환 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="02e27-126">Because constants can be defined in terms of other constants, it is possible to inadvertently create a *cycle*, or circular reference, between two or more constants.</span></span> <span data-ttu-id="02e27-127">주기는 다음 예제와 같이 다른 측면에서 정의 된 각 두 개 이상의 공용 상수 있을 때 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="02e27-127">A cycle occurs when you have two or more public constants, each of which is defined in terms of the other, as in the following example:</span></span>  
  
 <span data-ttu-id="02e27-128">[!code-vb[VbEnumsTask #&16;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="02e27-128">[!code-vb[VbEnumsTask#16](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_4.vb)]</span></span>  
<span data-ttu-id="02e27-129">[!code-vb[VbEnumsTask #&17;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="02e27-129">[!code-vb[VbEnumsTask#17](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_5.vb)]</span></span>  
  
 <span data-ttu-id="02e27-130">주기가 발생 하는 경우 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 컴파일러 오류를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="02e27-130">If a cycle occurs, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] generates a compiler error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02e27-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="02e27-131">See Also</span></span>  
 <span data-ttu-id="02e27-132">[Const 문](../../../../visual-basic/language-reference/statements/const-statement.md) </span><span class="sxs-lookup"><span data-stu-id="02e27-132">[Const Statement](../../../../visual-basic/language-reference/statements/const-statement.md) </span></span>  
<span data-ttu-id="02e27-133"> [상수 및 리터럴 데이터 형식](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="02e27-133"> [Constant and Literal Data Types](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md) </span></span>  
<span data-ttu-id="02e27-134"> [상수 및 열거형](../../../../visual-basic/programming-guide/language-features/constants-enums/index.md) </span><span class="sxs-lookup"><span data-stu-id="02e27-134"> [Constants and Enumerations](../../../../visual-basic/programming-guide/language-features/constants-enums/index.md) </span></span>  
<span data-ttu-id="02e27-135"> [상수 및 열거형](../../../../visual-basic/language-reference/constants-and-enumerations.md) </span><span class="sxs-lookup"><span data-stu-id="02e27-135"> [Constants and Enumerations](../../../../visual-basic/language-reference/constants-and-enumerations.md) </span></span>  
<span data-ttu-id="02e27-136"> [열거형 개요](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md) </span><span class="sxs-lookup"><span data-stu-id="02e27-136"> [Enumerations Overview](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md) </span></span>  
<span data-ttu-id="02e27-137"> [상수 개요](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md) </span><span class="sxs-lookup"><span data-stu-id="02e27-137"> [Constants Overview](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md) </span></span>  
<span data-ttu-id="02e27-138"> [방법: 열거형 선언](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md) </span><span class="sxs-lookup"><span data-stu-id="02e27-138"> [How to: Declare an Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md) </span></span>  
<span data-ttu-id="02e27-139"> [열거형 및 이름 한정](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md) </span><span class="sxs-lookup"><span data-stu-id="02e27-139"> [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md) </span></span>  
<span data-ttu-id="02e27-140"> [Option Strict 문](../../../../visual-basic/language-reference/statements/option-strict-statement.md)</span><span class="sxs-lookup"><span data-stu-id="02e27-140"> [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)</span></span>
