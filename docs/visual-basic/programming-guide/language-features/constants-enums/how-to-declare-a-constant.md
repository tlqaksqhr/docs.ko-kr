---
title: '방법: 상수 선언(Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.constant
helpviewer_keywords:
- Integer data type [Visual Basic], declaring constants
- Single data type [Visual Basic], declaring constants
- Const statement [Visual Basic], declaring constants
- procedures [Visual Basic], declaration
- data types [Visual Basic], constants
- Long data type [Visual Basic], declaring constants
- Visual Basic code, declaring variables and constants
- Double data type [Visual Basic], declaring constants
- Boolean data type [Visual Basic], declaring constants
- modules, declaring constants
- Byte data type [Visual Basic], declaring constants
- constants [Visual Basic], declaring
- Date data type [Visual Basic], declaring constants
- String data type [Visual Basic], declaring constants
- declaring constants [Visual Basic], const keyword
- Currency data type [Visual Basic], declaring constants and variants
- module-level constants and variables
- Object data type [Visual Basic], declaring constants
ms.assetid: f901b4fa-481f-4621-822e-427060577ad1
ms.openlocfilehash: ce45e4df7f74cd68bde0fb2adba10197a11edb1b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649739"
---
# <a name="how-to-declare-a-constant-visual-basic"></a><span data-ttu-id="3f08c-102">방법: 상수 선언(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3f08c-102">How to: Declare A Constant (Visual Basic)</span></span>
<span data-ttu-id="3f08c-103">사용 하면는 `Const` 문을 상수를 선언 하 고 해당 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f08c-103">You use the `Const` statement to declare a constant and set its value.</span></span> <span data-ttu-id="3f08c-104">상수를 선언 하 여 값으로 의미 있는 이름을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f08c-104">By declaring a constant, you assign a meaningful name to a value.</span></span> <span data-ttu-id="3f08c-105">상수 선언 되 면 수정 또는 새 값을 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3f08c-105">Once a constant is declared, it cannot be modified or assigned a new value.</span></span>  
  
 <span data-ttu-id="3f08c-106">프로시저 내에서 또는 모듈, 클래스 또는 구조체의 선언 섹션에는 상수를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="3f08c-106">You declare a constant within a procedure or in the declarations section of a module, class, or structure.</span></span> <span data-ttu-id="3f08c-107">클래스 또는 구조 수준 상수는 `Private` 기본적으로도로 선언할 수 있지만 `Public`, `Friend`, `Protected`, 또는 `Protected Friend` 적절 한 수준의 코드 액세스에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f08c-107">Class or structure-level constants are `Private` by default, but may also be declared as `Public`, `Friend`, `Protected`, or `Protected Friend` for the appropriate level of code access.</span></span>  
  
 <span data-ttu-id="3f08c-108">올바른 심볼 이름을 (규칙은 변수 이름 만들기와 동일)와 숫자 또는 문자열 상수 및 연산자 (함수 호출 없음)의 구성 된 식의 상수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f08c-108">The constant must have a valid symbolic name (the rules are the same as those for creating variable names) and an expression composed of numeric or string constants and operators (but no function calls).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-declare-a-constant"></a><span data-ttu-id="3f08c-109">상수 선언 하려면</span><span class="sxs-lookup"><span data-stu-id="3f08c-109">To declare a constant</span></span>  
  
-   <span data-ttu-id="3f08c-110">액세스 지정자를 포함 하는 선언을 작성 된 `Const` 키워드 및 다음 예와 같이 식:</span><span class="sxs-lookup"><span data-stu-id="3f08c-110">Write a declaration that includes an access specifier, the `Const` keyword, and an expression, as in the following examples:</span></span>  
  
     [!code-vb[VbEnumsTask#8](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-a-constant_1.vb)]  
  
     <span data-ttu-id="3f08c-111">때 [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) 은 `Off` 및 [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) 은 `On`, 데이터 형식을 지정 하 여 명시적으로 상수를 선언 해야 합니다 (`Boolean`, `Byte`, `Char`, `DateTime`, `Decimal`, `Double`, `Integer`, `Long`, `Short`, `Single`, 또는 `String`).</span><span class="sxs-lookup"><span data-stu-id="3f08c-111">When [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) is `Off` and [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) is `On`, you must declare a constant explicitly by specifying a data type (`Boolean`, `Byte`, `Char`, `DateTime`, `Decimal`, `Double`, `Integer`, `Long`, `Short`, `Single`, or `String`).</span></span>  
  
     <span data-ttu-id="3f08c-112">때 `Option Infer` 은 `On` 또는 `Option Strict` 은 `Off`, 데이터 형식으로 지정 하지 않고 상수를 선언할 수 있습니다는 `As` 절.</span><span class="sxs-lookup"><span data-stu-id="3f08c-112">When `Option Infer` is `On` or `Option Strict` is `Off`, you can declare a constant without specifying a data type with an `As` clause.</span></span> <span data-ttu-id="3f08c-113">컴파일러에는 상수 식의 형식에서의 유형을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="3f08c-113">The compiler determines the type of the constant from the type of the expression.</span></span> <span data-ttu-id="3f08c-114">자세한 내용은 참조 [상수 및 리터럴 데이터 형식](constant-and-literal-data-types.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3f08c-114">For more information, see [Constant and Literal Data Types](constant-and-literal-data-types.md).</span></span>  
  
### <a name="to-declare-a-constant-that-has-an-explicitly-stated-data-type"></a><span data-ttu-id="3f08c-115">으로 명시적으로 지정된 하는 데이터 형식이 지정 된 상수를 선언 하려면</span><span class="sxs-lookup"><span data-stu-id="3f08c-115">To declare a constant that has an explicitly stated data type</span></span>  
  
-   <span data-ttu-id="3f08c-116">포함 하는 선언을 작성는 `As` 키워드 및 명시적 데이터 형식, 다음 예제와 같이:</span><span class="sxs-lookup"><span data-stu-id="3f08c-116">Write a declaration that includes the `As` keyword and an explicit data type, as in the following examples:</span></span>  
  
     [!code-vb[VbEnumsTask#9](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-a-constant_2.vb)]  
  
     <span data-ttu-id="3f08c-117">코드 줄에 하나씩 단일 상수만 선언 하는 경우 더 쉽게 읽을 수는 있지만 한 줄에 여러 개의 상수를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f08c-117">You can declare multiple constants on a single line, although your code is more readable if you declare only a single constant per line.</span></span> <span data-ttu-id="3f08c-118">한 줄에 여러 개의 상수를 선언 하는 경우 이들은 모두 가져야 동일한 액세스 레벨 (`Public`, `Private`, `Friend`, `Protected`, 또는 `Protected Friend`).</span><span class="sxs-lookup"><span data-stu-id="3f08c-118">If you declare multiple constants on a single line, they must all have the same access level (`Public`, `Private`, `Friend`, `Protected`, or `Protected Friend`).</span></span>  
  
### <a name="to-declare-multiple-constants-on-a-single-line"></a><span data-ttu-id="3f08c-119">한 줄에 여러 개의 상수를 선언 하려면</span><span class="sxs-lookup"><span data-stu-id="3f08c-119">To declare multiple constants on a single line</span></span>  
  
-   <span data-ttu-id="3f08c-120">다음 예제와 같이 공백, 쉼표와 선언을 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f08c-120">Separate the declarations with a comma and a space, as in the following example:</span></span>  
  
    ```  
    Public Const Four As Integer = 4, Five As Integer = 5, Six As Integer = 44  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="3f08c-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3f08c-121">See Also</span></span>  
 [<span data-ttu-id="3f08c-122">Const 문</span><span class="sxs-lookup"><span data-stu-id="3f08c-122">Const Statement</span></span>](../../../../visual-basic/language-reference/statements/const-statement.md)  
 [<span data-ttu-id="3f08c-123">상수 및 리터럴 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="3f08c-123">Constant and Literal Data Types</span></span>](constant-and-literal-data-types.md)  
 <span data-ttu-id="3f08c-124">[상수 개요](constants-overview.md) [하는 방법: 상수 선언](how-to-declare-a-constant.md) [사용자 정의 상수](user-defined-constants.md) [상수 및 리터럴 데이터 형식](constant-and-literal-data-types.md) [하는 방법: 그룹 관련 상수 값 그룹화](how-to-group-related-constant-values-together.md) [열거형 개요](enumerations-overview.md) [하는 방법: 열거형 선언](how-to-declare-enumerations.md) [하는 방법: 열거형 멤버 참조](how-to-refer-to-an-enumeration-member.md) [열거형 및 이름 한정](enumerations-and-name-qualification.md) [하는 방법: 열거형 반복](how-to-iterate-through-an-enumeration.md) [하는 방법: 열거형 값과 연결 된 문자열을 결정](how-to-determine-the-string-associated-with-an-enumeration-value.md) [열거형을 사용 하는 경우](when-to-use-an-enumeration.md)</span><span class="sxs-lookup"><span data-stu-id="3f08c-124">[Constants Overview](constants-overview.md) [How to: Declare A Constant](how-to-declare-a-constant.md) [User-Defined Constants](user-defined-constants.md) [Constant and Literal Data Types](constant-and-literal-data-types.md) [How to: Group Related Constant Values Together](how-to-group-related-constant-values-together.md) [Enumerations Overview](enumerations-overview.md) [How to: Declare Enumerations](how-to-declare-enumerations.md) [How to: Refer to an Enumeration Member](how-to-refer-to-an-enumeration-member.md) [Enumerations and Name Qualification](enumerations-and-name-qualification.md) [How to: Iterate Through An Enumeration](how-to-iterate-through-an-enumeration.md) [How to: Determine the String Associated with an Enumeration Value](how-to-determine-the-string-associated-with-an-enumeration-value.md) [When to Use an Enumeration](when-to-use-an-enumeration.md)</span></span>

 [<span data-ttu-id="3f08c-125">열거형 개요</span><span class="sxs-lookup"><span data-stu-id="3f08c-125">Enumerations Overview</span></span>](enumerations-overview.md)  
 [<span data-ttu-id="3f08c-126">상수 개요</span><span class="sxs-lookup"><span data-stu-id="3f08c-126">Constants Overview</span></span>](constants-overview.md)  
 [<span data-ttu-id="3f08c-127">방법: 열거형 선언</span><span class="sxs-lookup"><span data-stu-id="3f08c-127">How to: Declare an Enumeration</span></span>](how-to-declare-enumerations.md)  
 [<span data-ttu-id="3f08c-128">열거형 및 이름 한정</span><span class="sxs-lookup"><span data-stu-id="3f08c-128">Enumerations and Name Qualification</span></span>](enumerations-and-name-qualification.md)  
 [<span data-ttu-id="3f08c-129">Option Strict 문</span><span class="sxs-lookup"><span data-stu-id="3f08c-129">Option Strict Statement</span></span>](../../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [<span data-ttu-id="3f08c-130">상수 및 열거형</span><span class="sxs-lookup"><span data-stu-id="3f08c-130">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
