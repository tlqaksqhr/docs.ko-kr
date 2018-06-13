---
title: '방법: 열거형 선언(Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], enumerations
- enumerations [Visual Basic], declaring
- declaring enumerations [Visual Basic]
ms.assetid: db4ca1c3-f429-4c81-ae81-29e0157b29fd
ms.openlocfilehash: e2dbdbbf6bf7fe3e4b71cbe7edc7a19b18f96ef2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650805"
---
# <a name="how-to-declare-enumerations-visual-basic"></a><span data-ttu-id="ca367-102">방법: 열거형 선언(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ca367-102">How to: Declare Enumerations (Visual Basic)</span></span>
<span data-ttu-id="ca367-103">구성 된 열거형을 만들면는 `Enum` 클래스 또는 모듈 선언 섹션에서 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca367-103">You create an enumeration with the `Enum` statement in the declarations section of a class or module.</span></span> <span data-ttu-id="ca367-104">메서드 내에서 열거형을 선언할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ca367-104">You cannot declare an enumeration within a method.</span></span> <span data-ttu-id="ca367-105">적절 한 액세스 수준을 지정 하려면 `Private`, `Protected`, `Friend`, 또는 `Public`합니다.</span><span class="sxs-lookup"><span data-stu-id="ca367-105">To specify the appropriate level of access, use `Private`, `Protected`, `Friend`, or `Public`.</span></span>  
  
 <span data-ttu-id="ca367-106">`Enum` 형식에는 이름, 내부 형식 및 필드의 집합을 각각 나타내는 상수입니다.</span><span class="sxs-lookup"><span data-stu-id="ca367-106">An `Enum` type has a name, an underlying type, and a set of fields, each representing a constant.</span></span> <span data-ttu-id="ca367-107">이름은 올바른 Visual Basic.NET 한정자 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca367-107">The name must be a valid Visual Basic .NET qualifier.</span></span> <span data-ttu-id="ca367-108">내부 형식은 정수 형식 중 하나 여야 합니다-`Byte`, `Short`, `Long` 또는 `Integer`합니다.</span><span class="sxs-lookup"><span data-stu-id="ca367-108">The underlying type must be one of the integer types—`Byte`, `Short`, `Long` or `Integer`.</span></span> <span data-ttu-id="ca367-109">기본값은 `Integer`입니다.</span><span class="sxs-lookup"><span data-stu-id="ca367-109">`Integer` is the default.</span></span> <span data-ttu-id="ca367-110">열거형에는 항상 강력한 형식 및 정수 숫자 형식 메서드와 호환 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ca367-110">Enumerations are always strongly typed and are not interchangeable with integer number types.</span></span>  
  
 <span data-ttu-id="ca367-111">열거형 부동 소수점 값을 가질 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ca367-111">Enumerations cannot have floating-point values.</span></span> <span data-ttu-id="ca367-112">열거형에는 부동 소수점 값을 지정 되 면 `Option Strict On`, 컴파일러 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca367-112">If an enumeration is assigned a floating-point value with `Option Strict On`, a compiler error results.</span></span> <span data-ttu-id="ca367-113">경우 `Option Strict` 은 `Off`에 자동으로 변환 된 값은 `Enum` 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="ca367-113">If `Option Strict` is `Off`, the value is automatically converted to the `Enum` type.</span></span>  
  
 <span data-ttu-id="ca367-114">이름에 대 한 사용 하는 방법에 대 한는 `Imports` 문을 이름 한정, 불필요 한 참조 [열거형 및 이름 한정](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ca367-114">For information on names, and how to use the `Imports` statement to make name qualification unnecessary, see [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md).</span></span>  
  
### <a name="to-declare-an-enumeration"></a><span data-ttu-id="ca367-115">열거형 선언</span><span class="sxs-lookup"><span data-stu-id="ca367-115">To declare an enumeration</span></span>  
  
1.  <span data-ttu-id="ca367-116">코드 액세스 수준을 포함 하는 선언을 작성 된 `Enum` 키워드 및 한 올바른 이름으로 다음 예제와 같이 각각 서로 다른 선언 `Enum`합니다.</span><span class="sxs-lookup"><span data-stu-id="ca367-116">Write a declaration that includes a code access level, the `Enum` keyword, and a valid name, as in the following examples, each of which declares a different `Enum`.</span></span>  
  
     [!code-vb[VbEnumsTask#3](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_1.vb)]  
  
2.  <span data-ttu-id="ca367-117">열거형에서 상수를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca367-117">Define the constants in the enumeration.</span></span> <span data-ttu-id="ca367-118">기본적으로 열거형의 첫 번째 상수에 초기화 `0`, 고 후속 상수 이전 상수 보다 하나 더 큰 값으로 초기화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca367-118">By default, the first constant in an enumeration is initialized to `0`, and subsequent constants are initialized to a value of one more than the previous constant.</span></span> <span data-ttu-id="ca367-119">예를 들어 다음 열거형 `Days`, 명명 된 상수를 포함 `Sunday` 값과 `0`, 명명 된 상수 `Monday` 값과 `1`, 명명 된 상수 `Tuesday` 값을가진`2`등입니다.</span><span class="sxs-lookup"><span data-stu-id="ca367-119">For example, the following enumeration, `Days`, contains a constant named `Sunday` with the value `0`, a constant named `Monday` with the value `1`, a constant named `Tuesday` with the value of `2`, and so on.</span></span>  
  
     [!code-vb[VbEnumsTask#4](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_2.vb)]  
  
3.  <span data-ttu-id="ca367-120">명시적으로 할당 문을 사용 하 여 열거형에서 상수에 값을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca367-120">You can explicitly assign values to constants in an enumeration by using an assignment statement.</span></span> <span data-ttu-id="ca367-121">음수를 포함 하는 정수 값을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca367-121">You can assign any integer value, including negative numbers.</span></span> <span data-ttu-id="ca367-122">예를 들어 상수를 오류 상태를 나타내는 0 보다 작은 값으로 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ca367-122">For example, you may want constants with values less than zero to represent error conditions.</span></span> <span data-ttu-id="ca367-123">다음 열거형 상수 `Invalid` 값이 명시적으로 할당 `–1`, 상수 및 `Sunday` 값이 할당 됩니다 `0`합니다.</span><span class="sxs-lookup"><span data-stu-id="ca367-123">In the following enumeration, the constant `Invalid` is explicitly assigned the value `–1`, and the constant `Sunday` is assigned the value `0`.</span></span> <span data-ttu-id="ca367-124">열거형에서 첫 번째 상수 이므로 `Saturday` 또한 값으로 초기화 됩니다 `0`합니다.</span><span class="sxs-lookup"><span data-stu-id="ca367-124">Because it is the first constant in the enumeration, `Saturday` is also initialized to the value `0`.</span></span> <span data-ttu-id="ca367-125">값 `Monday` 은 `1` (의 값 보다 하나 더 큰 `Sunday`);의 값 `Tuesday` 은 `2`등입니다.</span><span class="sxs-lookup"><span data-stu-id="ca367-125">The value of `Monday` is `1` (one more than the value of `Sunday`); the value of `Tuesday` is `2`, and so on.</span></span>  
  
     [!code-vb[VbEnumsTask#5](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_3.vb)]  
  
### <a name="to-declare-an-enumeration-as-an-explicit-type"></a><span data-ttu-id="ca367-126">명시적 형식으로 열거형 선언</span><span class="sxs-lookup"><span data-stu-id="ca367-126">To declare an enumeration as an explicit type</span></span>  
  
-   <span data-ttu-id="ca367-127">열거형 형식을 사용 하 여 지정 된 `As` 절, 다음 예제와 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca367-127">Specify the type of the enum by using the `As` clause, as shown in the following example.</span></span>  
  
     [!code-vb[VbEnumsTask#6](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-enumerations_4.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="ca367-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ca367-128">See Also</span></span>  
 [<span data-ttu-id="ca367-129">열거형 및 이름 한정</span><span class="sxs-lookup"><span data-stu-id="ca367-129">Enumerations and Name Qualification</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)  
 [<span data-ttu-id="ca367-130">방법: 열거형 멤버 참조</span><span class="sxs-lookup"><span data-stu-id="ca367-130">How to: Refer to an Enumeration Member</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-refer-to-an-enumeration-member.md)  
 [<span data-ttu-id="ca367-131">방법: Visual Basic에서 열거형 반복</span><span class="sxs-lookup"><span data-stu-id="ca367-131">How to: Iterate Through An Enumeration in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)  
 [<span data-ttu-id="ca367-132">방법: 열거형 값과 연결된 문자열 확인</span><span class="sxs-lookup"><span data-stu-id="ca367-132">How to: Determine the String Associated with an Enumeration Value</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)  
 [<span data-ttu-id="ca367-133">열거형을 사용하는 경우</span><span class="sxs-lookup"><span data-stu-id="ca367-133">When to Use an Enumeration</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)  
 [<span data-ttu-id="ca367-134">상수 개요</span><span class="sxs-lookup"><span data-stu-id="ca367-134">Constants Overview</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)  
 [<span data-ttu-id="ca367-135">상수 및 리터럴 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="ca367-135">Constant and Literal Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)  
 [<span data-ttu-id="ca367-136">상수 및 열거형</span><span class="sxs-lookup"><span data-stu-id="ca367-136">Constants and Enumerations</span></span>](../../../../visual-basic/language-reference/constants-and-enumerations.md)
