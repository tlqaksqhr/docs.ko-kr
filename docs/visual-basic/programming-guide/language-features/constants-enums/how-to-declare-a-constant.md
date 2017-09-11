---
title: "방법: 상수 선언 (Visual Basic) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.constant
dev_langs:
- VB
helpviewer_keywords:
- Integer data type, declaring constants
- Single data type, declaring constants
- Const statement [Visual Basic], declaring constants
- procedures, declaration
- data types [Visual Basic], constants
- Long data type, declaring constants
- Visual Basic code, declaring variables and constants
- Double data type, declaring constants
- Boolean data type, declaring constants
- modules, declaring constants
- Byte data type, declaring constants
- constants, declaring
- Date data type, declaring constants
- String data type, declaring constants
- declaring constants, const keyword
- Currency data type, declaring constants and variants
- module-level constants and variables
- Object data type, declaring constants
ms.assetid: f901b4fa-481f-4621-822e-427060577ad1
caps.latest.revision: 20
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
ms.sourcegitcommit: 31905a37f09db5f5192123f0118252fbe8b02eff
ms.openlocfilehash: b7fc499336c2b5db3b4d2fe9c0cd11799ea0ad77
ms.contentlocale: ko-kr
ms.lasthandoff: 05/26/2017

---
# <a name="how-to-declare-a-constant-visual-basic"></a><span data-ttu-id="72fc5-102">방법: 상수 선언(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="72fc5-102">How to: Declare A Constant (Visual Basic)</span></span>
<span data-ttu-id="72fc5-103">사용 된 `Const` 상수를 선언 하 고 해당 값을 설정 하는 문입니다.</span><span class="sxs-lookup"><span data-stu-id="72fc5-103">You use the `Const` statement to declare a constant and set its value.</span></span> <span data-ttu-id="72fc5-104">상수를 선언 하 여 값으로 의미 있는 이름을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="72fc5-104">By declaring a constant, you assign a meaningful name to a value.</span></span> <span data-ttu-id="72fc5-105">상수 선언 되 면 수정 하거나 새 값을 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="72fc5-105">Once a constant is declared, it cannot be modified or assigned a new value.</span></span>  
  
 <span data-ttu-id="72fc5-106">프로시저 내에서 또는 모듈, 클래스 또는 구조체의 선언 섹션에는 상수를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="72fc5-106">You declare a constant within a procedure or in the declarations section of a module, class, or structure.</span></span> <span data-ttu-id="72fc5-107">클래스 또는 구조체 수준의 상수는 `Private` 기본적으로,도로 선언할 수 있지만 `Public`, `Friend`, `Protected`, 또는 `Protected Friend` 적절 한 수준의 코드 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="72fc5-107">Class or structure-level constants are `Private` by default, but may also be declared as `Public`, `Friend`, `Protected`, or `Protected Friend` for the appropriate level of code access.</span></span>  
  
 <span data-ttu-id="72fc5-108">상수 (규칙은 변수 이름 만들기와 동일) 하는 기호화 된 올바른 이름 및 숫자 또는 문자열 상수 및 연산자 (없습니다 함수 호출)의 구성 된 식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="72fc5-108">The constant must have a valid symbolic name (the rules are the same as those for creating variable names) and an expression composed of numeric or string constants and operators (but no function calls).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-declare-a-constant"></a><span data-ttu-id="72fc5-109">상수 선언 하려면</span><span class="sxs-lookup"><span data-stu-id="72fc5-109">To declare a constant</span></span>  
  
-   <span data-ttu-id="72fc5-110">액세스 지정자를 포함 하는 선언을 작성 된 `Const` 키워드 및 다음 예와 같이 식:</span><span class="sxs-lookup"><span data-stu-id="72fc5-110">Write a declaration that includes an access specifier, the `Const` keyword, and an expression, as in the following examples:</span></span>  
  
     <span data-ttu-id="72fc5-111">[!code-vb[VbEnumsTask #&8;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-a-constant_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="72fc5-111">[!code-vb[VbEnumsTask#8](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-a-constant_1.vb)]</span></span>  
  
     <span data-ttu-id="72fc5-112">때 [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) 는 `Off` 및 [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) 는 `On`, 데이터 형식을 지정 하 여 상수를 명시적으로 선언 해야 합니다 (`Boolean`, `Byte`, `Char`, `DateTime`, `Decimal`, `Double`, `Integer`, `Long`, `Short`, `Single`, 또는 `String`).</span><span class="sxs-lookup"><span data-stu-id="72fc5-112">When [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) is `Off` and [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) is `On`, you must declare a constant explicitly by specifying a data type (`Boolean`, `Byte`, `Char`, `DateTime`, `Decimal`, `Double`, `Integer`, `Long`, `Short`, `Single`, or `String`).</span></span>  
  
     <span data-ttu-id="72fc5-113">때 `Option Infer` 는 `On` 또는 `Option Strict` 는 `Off`, 데이터 형식으로 지정 하지 않고 상수를 선언할 수는 `As` 절.</span><span class="sxs-lookup"><span data-stu-id="72fc5-113">When `Option Infer` is `On` or `Option Strict` is `Off`, you can declare a constant without specifying a data type with an `As` clause.</span></span> <span data-ttu-id="72fc5-114">컴파일러에는 상수 식의 형식에서 형식을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="72fc5-114">The compiler determines the type of the constant from the type of the expression.</span></span> <span data-ttu-id="72fc5-115">자세한 내용은 참조 [상수 및 리터럴 데이터 형식](constant-and-literal-data-types.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="72fc5-115">For more information, see [Constant and Literal Data Types](constant-and-literal-data-types.md).</span></span>  
  
### <a name="to-declare-a-constant-that-has-an-explicitly-stated-data-type"></a><span data-ttu-id="72fc5-116">으로 명시적으로 지정된 하는 데이터 형식이 지정 된 상수를 선언 하려면</span><span class="sxs-lookup"><span data-stu-id="72fc5-116">To declare a constant that has an explicitly stated data type</span></span>  
  
-   <span data-ttu-id="72fc5-117">포함 하는 선언을 쓰기는 `As` 키워드 및는 명시적 데이터 형식, 다음 예제와 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="72fc5-117">Write a declaration that includes the `As` keyword and an explicit data type, as in the following examples:</span></span>  
  
     <span data-ttu-id="72fc5-118">[!code-vb[VbEnumsTask #&9;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-a-constant_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="72fc5-118">[!code-vb[VbEnumsTask#9](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-a-constant_2.vb)]</span></span>  
  
     <span data-ttu-id="72fc5-119">코드 줄에 하나씩만 하는 단일 상수를 선언 하는 경우 보다 읽기 쉬운 되어도 한 줄에 여러 개의 상수를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72fc5-119">You can declare multiple constants on a single line, although your code is more readable if you declare only a single constant per line.</span></span> <span data-ttu-id="72fc5-120">한 줄에 여러 개의 상수를 선언 하는 경우 이들은 모두 가져야 동일한 액세스 레벨 (`Public`, `Private`, `Friend`, `Protected`, 또는 `Protected Friend`).</span><span class="sxs-lookup"><span data-stu-id="72fc5-120">If you declare multiple constants on a single line, they must all have the same access level (`Public`, `Private`, `Friend`, `Protected`, or `Protected Friend`).</span></span>  
  
### <a name="to-declare-multiple-constants-on-a-single-line"></a><span data-ttu-id="72fc5-121">한 줄에 여러 상수를 선언 하려면</span><span class="sxs-lookup"><span data-stu-id="72fc5-121">To declare multiple constants on a single line</span></span>  
  
-   <span data-ttu-id="72fc5-122">다음 예제와 같이 공백, 쉼표와 선언을 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="72fc5-122">Separate the declarations with a comma and a space, as in the following example:</span></span>  
  
    ```  
    Public Const Four As Integer = 4, Five As Integer = 5, Six As Integer = 44  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="72fc5-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="72fc5-123">See Also</span></span>  
 <span data-ttu-id="72fc5-124">[Const 문](../../../../visual-basic/language-reference/statements/const-statement.md) </span><span class="sxs-lookup"><span data-stu-id="72fc5-124">[Const Statement](../../../../visual-basic/language-reference/statements/const-statement.md) </span></span>  
<span data-ttu-id="72fc5-125"> [상수 및 리터럴 데이터 형식](constant-and-literal-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="72fc5-125"> [Constant and Literal Data Types](constant-and-literal-data-types.md) </span></span>  
<span data-ttu-id="72fc5-126"> [상수 개요](constants-overview.md)
 [하는 방법: 상수 선언](how-to-declare-a-constant.md)
 [사용자 정의 상수](user-defined-constants.md)
 [상수 및 리터럴 데이터 형식](constant-and-literal-data-types.md)
 [하는 방법: 관련 상수 값 그룹화](how-to-group-related-constant-values-together.md)
 [열거형 개요](enumerations-overview.md)
 [하는 방법: 열거형 선언](how-to-declare-enumerations.md)
 [하는 방법: 열거형 멤버 참조](how-to-refer-to-an-enumeration-member.md)
 [열거형 및 이름 한정](enumerations-and-name-qualification.md)
 [하는 방법: 열거형 반복](how-to-iterate-through-an-enumeration.md)
 [하는 방법: 문자열 확인 열거형 값과 연결 된](how-to-determine-the-string-associated-with-an-enumeration-value.md)
 [열거형을 사용 하는 경우](when-to-use-an-enumeration.md)</span><span class="sxs-lookup"><span data-stu-id="72fc5-126"> [Constants Overview](constants-overview.md)
 [How to: Declare A Constant](how-to-declare-a-constant.md)
 [User-Defined Constants](user-defined-constants.md)
 [Constant and Literal Data Types](constant-and-literal-data-types.md)
 [How to: Group Related Constant Values Together](how-to-group-related-constant-values-together.md)
 [Enumerations Overview](enumerations-overview.md)
 [How to: Declare Enumerations](how-to-declare-enumerations.md)
 [How to: Refer to an Enumeration Member](how-to-refer-to-an-enumeration-member.md)
 [Enumerations and Name Qualification](enumerations-and-name-qualification.md)
 [How to: Iterate Through An Enumeration](how-to-iterate-through-an-enumeration.md)
 [How to: Determine the String Associated with an Enumeration Value](how-to-determine-the-string-associated-with-an-enumeration-value.md)
 [When to Use an Enumeration](when-to-use-an-enumeration.md)</span></span>

 <span data-ttu-id="72fc5-127">[열거형 개요](enumerations-overview.md) </span><span class="sxs-lookup"><span data-stu-id="72fc5-127">[Enumerations Overview](enumerations-overview.md) </span></span>  
<span data-ttu-id="72fc5-128"> [상수 개요](constants-overview.md) </span><span class="sxs-lookup"><span data-stu-id="72fc5-128"> [Constants Overview](constants-overview.md) </span></span>  
<span data-ttu-id="72fc5-129"> [방법: 열거형 선언](how-to-declare-enumerations.md) </span><span class="sxs-lookup"><span data-stu-id="72fc5-129"> [How to: Declare an Enumeration](how-to-declare-enumerations.md) </span></span>  
<span data-ttu-id="72fc5-130"> [열거형 및 이름 한정](enumerations-and-name-qualification.md) </span><span class="sxs-lookup"><span data-stu-id="72fc5-130"> [Enumerations and Name Qualification](enumerations-and-name-qualification.md) </span></span>  
<span data-ttu-id="72fc5-131"> [Option Strict 문](../../../../visual-basic/language-reference/statements/option-strict-statement.md) </span><span class="sxs-lookup"><span data-stu-id="72fc5-131"> [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) </span></span>  
<span data-ttu-id="72fc5-132"> [상수 및 열거형](../../../../visual-basic/language-reference/constants-and-enumerations.md)</span><span class="sxs-lookup"><span data-stu-id="72fc5-132"> [Constants and Enumerations](../../../../visual-basic/language-reference/constants-and-enumerations.md)</span></span>

