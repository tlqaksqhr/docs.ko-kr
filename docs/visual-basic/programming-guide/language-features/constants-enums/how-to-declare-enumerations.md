---
title: "방법: 열거형 선언 (Visual Basic) | Microsoft 문서"
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
- declarations, enumerations
- enumerations [Visual Basic], declaring
- declaring enumerations
ms.assetid: db4ca1c3-f429-4c81-ae81-29e0157b29fd
caps.latest.revision: 24
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
ms.openlocfilehash: 7adaca7e7252ce7165a5fd27b5bc9c049388206c
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-declare-enumerations-visual-basic"></a><span data-ttu-id="bfc48-102">방법: 열거형 선언(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bfc48-102">How to: Declare Enumerations (Visual Basic)</span></span>
<span data-ttu-id="bfc48-103">구성 된 열거형을 만들면는 `Enum` 클래스 또는 모듈의 선언 섹션에서 문.</span><span class="sxs-lookup"><span data-stu-id="bfc48-103">You create an enumeration with the `Enum` statement in the declarations section of a class or module.</span></span> <span data-ttu-id="bfc48-104">메서드 내에서 열거형을 선언할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-104">You cannot declare an enumeration within a method.</span></span> <span data-ttu-id="bfc48-105">적절 한 수준의 액세스를 지정 하려면 `Private`, `Protected`, `Friend`, 또는 `Public`합니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-105">To specify the appropriate level of access, use `Private`, `Protected`, `Friend`, or `Public`.</span></span>  
  
 <span data-ttu-id="bfc48-106">`Enum` 형식에는 이름, 내부 형식 및 필드 집합을 각각 나타내는 상수입니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-106">An `Enum` type has a name, an underlying type, and a set of fields, each representing a constant.</span></span> <span data-ttu-id="bfc48-107">이 이름은 유효한 해야 [!INCLUDE[vbprvblong](../../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)] 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-107">The name must be a valid [!INCLUDE[vbprvblong](../../../../visual-basic/developing-apps/customizing-extending-my/includes/vbprvblong_md.md)] qualifier.</span></span> <span data-ttu-id="bfc48-108">기본 형식이 정수 형식 중 하나 여야 합니다-`Byte`, `Short`, `Long` 또는 `Integer`합니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-108">The underlying type must be one of the integer types—`Byte`, `Short`, `Long` or `Integer`.</span></span> <span data-ttu-id="bfc48-109">기본값은 `Integer`입니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-109">`Integer` is the default.</span></span> <span data-ttu-id="bfc48-110">열거형에는 항상 강력한 형식 및 정수 숫자 형식에는 서로 호환 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-110">Enumerations are always strongly typed and are not interchangeable with integer number types.</span></span>  
  
 <span data-ttu-id="bfc48-111">열거형에는 부동 소수점 값은 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-111">Enumerations cannot have floating-point values.</span></span> <span data-ttu-id="bfc48-112">열거형에는 부동 소수점 값을 할당 되 면 `Option Strict On`, 컴파일러 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-112">If an enumeration is assigned a floating-point value with `Option Strict On`, a compiler error results.</span></span> <span data-ttu-id="bfc48-113">경우 `Option Strict` 는 `Off`에 자동으로 변환 된 값은 `Enum` 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-113">If `Option Strict` is `Off`, the value is automatically converted to the `Enum` type.</span></span>  
  
 <span data-ttu-id="bfc48-114">이름에 대 한 정보 및 사용 하는 방법에 대 한는 `Imports` 이름 한정 불필요 하다 고 확인 하는 문을 참조 [열거형 및 이름 한정](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-114">For information on names, and how to use the `Imports` statement to make name qualification unnecessary, see [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).</span></span>  
  
### <a name="to-declare-an-enumeration"></a><span data-ttu-id="bfc48-115">열거형 선언</span><span class="sxs-lookup"><span data-stu-id="bfc48-115">To declare an enumeration</span></span>  
  
1.  <span data-ttu-id="bfc48-116">작성 한 코드 액세스 수준을 포함 하는 선언을 `Enum` 키워드 및 다른 선언는 각각 다음 예제에서와 같이 유효한 이름을 `Enum`합니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-116">Write a declaration that includes a code access level, the `Enum` keyword, and a valid name, as in the following examples, each of which declares a different `Enum`.</span></span>  
  
     <span data-ttu-id="bfc48-117">[!code-vb[VbEnumsTask #&3;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="bfc48-117">[!code-vb[VbEnumsTask#3](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_1.vb)]</span></span>  
  
2.  <span data-ttu-id="bfc48-118">열거형에서 상수를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-118">Define the constants in the enumeration.</span></span> <span data-ttu-id="bfc48-119">기본적으로 열거형의 첫 번째 상수에 초기화 `0`, 후속 상수 이전 상수 보다 하나 더 큰 값으로 초기화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-119">By default, the first constant in an enumeration is initialized to `0`, and subsequent constants are initialized to a value of one more than the previous constant.</span></span> <span data-ttu-id="bfc48-120">예를 들어, 다음 열거형 `Days`, 명명 된 상수를 포함 `Sunday` 값으로 `0`, 명명 된 상수 `Monday` 값으로 `1`, 명명 된 상수 `Tuesday` 값을 가진 `2`등.</span><span class="sxs-lookup"><span data-stu-id="bfc48-120">For example, the following enumeration, `Days`, contains a constant named `Sunday` with the value `0`, a constant named `Monday` with the value `1`, a constant named `Tuesday` with the value of `2`, and so on.</span></span>  
  
     <span data-ttu-id="bfc48-121">[!code-vb[VbEnumsTask #&4;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="bfc48-121">[!code-vb[VbEnumsTask#4](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_2.vb)]</span></span>  
  
3.  <span data-ttu-id="bfc48-122">명시적으로 할당 문을 사용 하 여 열거형에서 상수 값을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-122">You can explicitly assign values to constants in an enumeration by using an assignment statement.</span></span> <span data-ttu-id="bfc48-123">음수를 포함 하 여 모든 정수 값을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-123">You can assign any integer value, including negative numbers.</span></span> <span data-ttu-id="bfc48-124">예를 들어 오류 조건을 나타낼 수는&0; 보다 작은 값으로 상수 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-124">For example, you may want constants with values less than zero to represent error conditions.</span></span> <span data-ttu-id="bfc48-125">다음 열거 상수 `Invalid` 값이 명시적으로 할당 `–1`, 상수 및 `Sunday` 값이 할당 됩니다 `0`합니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-125">In the following enumeration, the constant `Invalid` is explicitly assigned the value `–1`, and the constant `Sunday` is assigned the value `0`.</span></span> <span data-ttu-id="bfc48-126">열거형에서 첫 번째 상수 이므로 `Saturday` 또한 값으로 초기화 됩니다 `0`합니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-126">Because it is the first constant in the enumeration, `Saturday` is also initialized to the value `0`.</span></span> <span data-ttu-id="bfc48-127">값 `Monday` 는 `1` (의 값 보다&1; `Sunday`);의 값 `Tuesday` 는 `2`등입니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-127">The value of `Monday` is `1` (one more than the value of `Sunday`); the value of `Tuesday` is `2`, and so on.</span></span>  
  
     <span data-ttu-id="bfc48-128">[!code-vb[VbEnumsTask #&5;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="bfc48-128">[!code-vb[VbEnumsTask#5](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_3.vb)]</span></span>  
  
### <a name="to-declare-an-enumeration-as-an-explicit-type"></a><span data-ttu-id="bfc48-129">명시적 형식으로 열거형 선언</span><span class="sxs-lookup"><span data-stu-id="bfc48-129">To declare an enumeration as an explicit type</span></span>  
  
-   <span data-ttu-id="bfc48-130">열거형 형식을 사용 하 여 지정 된 `As` 절을 다음 예와에서 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfc48-130">Specify the type of the enum by using the `As` clause, as shown in the following example.</span></span>  
  
     <span data-ttu-id="bfc48-131">[!code-vb[VbEnumsTask #&6;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="bfc48-131">[!code-vb[VbEnumsTask#6](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_4.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfc48-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bfc48-132">See Also</span></span>  
 <span data-ttu-id="bfc48-133">[열거형 및 이름 한정](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md) </span><span class="sxs-lookup"><span data-stu-id="bfc48-133">[Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md) </span></span>  
<span data-ttu-id="bfc48-134"> [방법: 열거형 멤버 참조](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md) </span><span class="sxs-lookup"><span data-stu-id="bfc48-134"> [How to: Refer to an Enumeration Member](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md) </span></span>  
<span data-ttu-id="bfc48-135"> [방법: Visual Basic에서 열거형 반복](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md) </span><span class="sxs-lookup"><span data-stu-id="bfc48-135"> [How to: Iterate Through An Enumeration in Visual Basic](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md) </span></span>  
<span data-ttu-id="bfc48-136"> [방법: 열거형 값과 연결 된 문자열 확인](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md) </span><span class="sxs-lookup"><span data-stu-id="bfc48-136"> [How to: Determine the String Associated with an Enumeration Value](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md) </span></span>  
<span data-ttu-id="bfc48-137"> [열거형을 사용 하는 경우](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md) </span><span class="sxs-lookup"><span data-stu-id="bfc48-137"> [When to Use an Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md) </span></span>  
<span data-ttu-id="bfc48-138"> [상수 개요](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md) </span><span class="sxs-lookup"><span data-stu-id="bfc48-138"> [Constants Overview](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md) </span></span>  
<span data-ttu-id="bfc48-139"> [상수 및 리터럴 데이터 형식](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="bfc48-139"> [Constant and Literal Data Types](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md) </span></span>  
<span data-ttu-id="bfc48-140"> [상수 및 열거형](../../../../visual-basic/language-reference/constants-and-enumerations.md)</span><span class="sxs-lookup"><span data-stu-id="bfc48-140"> [Constants and Enumerations](../../../../visual-basic/language-reference/constants-and-enumerations.md)</span></span>
