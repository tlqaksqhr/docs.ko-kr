---
title: Key(Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.AnonymousKey
helpviewer_keywords:
- anonymous types [Visual Basic], key
- Key [Visual Basic]
- Key keyword [Visual Basic]
ms.assetid: 7697a928-7d14-4430-a72a-c9e96e8d6c11
caps.latest.revision: 22
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 20dbe4e67fb3e415ba0202555ace7fd5afed68d2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="key-visual-basic"></a><span data-ttu-id="cd85f-102">Key(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cd85f-102">Key (Visual Basic)</span></span>
<span data-ttu-id="cd85f-103">`Key` 키워드를 사용 하면 익명 형식의 속성에 대 한 동작을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd85f-103">The `Key` keyword enables you to specify behavior for properties of anonymous types.</span></span> <span data-ttu-id="cd85f-104">전용 속성으로 지정 하는 키 속성이 익명 형식 인스턴스, 또는 계산의 해시 코드 값 사이의 같음 테스트에 참여 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd85f-104">Only properties you designate as key properties participate in tests of equality between anonymous type instances, or calculation of hash code values.</span></span> <span data-ttu-id="cd85f-105">키 속성의 값을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cd85f-105">The values of key properties cannot be changed.</span></span>  
  
 <span data-ttu-id="cd85f-106">키워드를 배치 하 여 키 속성으로 익명 형식의 속성을 지정 `Key` 초기화 목록에서 해당 선언 앞에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd85f-106">You designate a property of an anonymous type as a key property by placing the keyword `Key` in front of its declaration in the initialization list.</span></span> <span data-ttu-id="cd85f-107">다음 예에서 `Airline` 및 `FlightNo` 은 키 속성이 있지만 `Gate` 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cd85f-107">In the following example, `Airline` and `FlightNo` are key properties, but `Gate` is not.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#26](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/key_1.vb)]  
  
 <span data-ttu-id="cd85f-108">직접 상속 하는 새로운 무명 형식 만들어지면 <xref:System.Object>합니다.</span><span class="sxs-lookup"><span data-stu-id="cd85f-108">When a new anonymous type is created, it inherits directly from <xref:System.Object>.</span></span> <span data-ttu-id="cd85f-109">컴파일러는 세 가지 상속 된 멤버를 재정의: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A>, 및 <xref:System.Object.ToString%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="cd85f-109">The compiler overrides three inherited members: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A>, and <xref:System.Object.ToString%2A>.</span></span> <span data-ttu-id="cd85f-110">에 대 한 생성 되는 재정의 코드 <xref:System.Object.Equals%2A> 및 <xref:System.Object.GetHashCode%2A> 키 속성에 기반 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd85f-110">The override code that is produced for <xref:System.Object.Equals%2A> and <xref:System.Object.GetHashCode%2A> is based on key properties.</span></span> <span data-ttu-id="cd85f-111">형식에 키 속성이 없는 경우 <xref:System.Object.GetHashCode%2A> 및 <xref:System.Object.Equals%2A> 재정의 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cd85f-111">If there are no key properties in the type, <xref:System.Object.GetHashCode%2A> and <xref:System.Object.Equals%2A> are not overridden.</span></span>  
  
## <a name="equality"></a><span data-ttu-id="cd85f-112">같음</span><span class="sxs-lookup"><span data-stu-id="cd85f-112">Equality</span></span>  
 <span data-ttu-id="cd85f-113">동일한 유형의 인스턴스인 경우 및 해당 키 속성의 값이 같으면 두 익명 형식의 인스턴스가 동일한 지 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd85f-113">Two anonymous type instances are equal if they are instances of the same type and if the values of their key properties are equal.</span></span> <span data-ttu-id="cd85f-114">다음 예에서 `flight2` 같으면 `flight1` 이전 예제에서 익명 같은 인스턴스 되기 때문에 형식을 가집니다 일치 하는 키 속성의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="cd85f-114">In the following examples, `flight2` is equal to `flight1` from the previous example because they are instances of the same anonymous type and they have matching values for their key properties.</span></span> <span data-ttu-id="cd85f-115">그러나 `flight3` 과 같지 않은 `flight1` 키 속성에 대해 다른 값을 있기 때문에 `FlightNo`합니다.</span><span class="sxs-lookup"><span data-stu-id="cd85f-115">However, `flight3` is not equal to `flight1` because it has a different value for a key property, `FlightNo`.</span></span> <span data-ttu-id="cd85f-116">인스턴스 `flight4` 가 동일한 형식이 아닌 `flight1` 있으므로 키 속성으로 다른 속성을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd85f-116">Instance `flight4` is not the same type as `flight1` because they designate different properties as key properties.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#27](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/key_2.vb)]  
  
 <span data-ttu-id="cd85f-117">키가 아닌 속성만, 이름, 형식, 순서 및 값에 동일한 두 인스턴스가 선언 된 두 인스턴스가 같지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cd85f-117">If two instances are declared with only non-key properties, identical in name, type, order, and value, the two instances are not equal.</span></span> <span data-ttu-id="cd85f-118">키 속성이 없는 인스턴스 자체에 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cd85f-118">An instance without key properties is equal only to itself.</span></span>  
  
 <span data-ttu-id="cd85f-119">동일한 익명 형식의 인스턴스는 두 익명 형식 인스턴스는 조건에 대 한 자세한 내용은 참조 [익명 형식](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="cd85f-119">For more information about the conditions under which two anonymous type instances are instances of the same anonymous type, see [Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>  
  
## <a name="hash-code-calculation"></a><span data-ttu-id="cd85f-120">해시 코드 계산</span><span class="sxs-lookup"><span data-stu-id="cd85f-120">Hash Code Calculation</span></span>  
 <span data-ttu-id="cd85f-121">마찬가지로 <xref:System.Object.Equals%2A>, 해시 함수에 정의 된 <xref:System.Object.GetHashCode%2A> 익명 형식을 기반으로 형식의 키 속성에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd85f-121">Like <xref:System.Object.Equals%2A>, the hash function that is defined in <xref:System.Object.GetHashCode%2A> for an anonymous type is based on the key properties of the type.</span></span> <span data-ttu-id="cd85f-122">다음 예제에서는 키 속성 및 해시 간의 상호 작용 코드 값을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cd85f-122">The following examples show the interaction between key properties and hash code values.</span></span>  
  
 <span data-ttu-id="cd85f-123">모든 키 속성에 대 한 동일한 값이 있는 익명 형식의 인스턴스는 키가 아닌 속성과 일치 하는 값을 포함 하지 않는 동일한 해시 코드 값을 가집니다.</span><span class="sxs-lookup"><span data-stu-id="cd85f-123">Instances of an anonymous type that have the same values for all key properties have the same hash code value, even if non-key properties do not have matching values.</span></span> <span data-ttu-id="cd85f-124">다음 문은 반환 `True`합니다.</span><span class="sxs-lookup"><span data-stu-id="cd85f-124">The following statement returns `True`.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#37](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/key_3.vb)]  
  
 <span data-ttu-id="cd85f-125">하나 이상의 키 속성에 대 한 다른 값이 있는 익명 형식의 인스턴스는 다른 해시 코드 값을 가집니다.</span><span class="sxs-lookup"><span data-stu-id="cd85f-125">Instances of an anonymous type that have different values for one or more key properties have different hash code values.</span></span> <span data-ttu-id="cd85f-126">다음 문은 반환 `False`합니다.</span><span class="sxs-lookup"><span data-stu-id="cd85f-126">The following statement returns `False`.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#38](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/key_4.vb)]  
  
 <span data-ttu-id="cd85f-127">키 속성으로 다른 속성을 지정 하는 익명 형식 인스턴스는 동일한 형식의 인스턴스 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cd85f-127">Instances of anonymous types that designate different properties as key properties are not instances of the same type.</span></span> <span data-ttu-id="cd85f-128">이름 및 모든 속성의 값이 동일한 경우에 다른 해시 코드 값을 가진 것입니다.</span><span class="sxs-lookup"><span data-stu-id="cd85f-128">They have different hash code values even when the names and values of all properties are the same.</span></span> <span data-ttu-id="cd85f-129">다음 문은 반환 `False`합니다.</span><span class="sxs-lookup"><span data-stu-id="cd85f-129">The following statement returns `False`.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#39](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/key_5.vb)]  
  
## <a name="read-only-values"></a><span data-ttu-id="cd85f-130">읽기 전용 값</span><span class="sxs-lookup"><span data-stu-id="cd85f-130">Read-Only Values</span></span>  
 <span data-ttu-id="cd85f-131">키 속성의 값을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cd85f-131">The values of key properties cannot be changed.</span></span> <span data-ttu-id="cd85f-132">예를 들어 `flight1` 앞의 예제에는 `Airline` 및 `FlightNo` 필드는 읽기 전용 하지만 `Gate` 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd85f-132">For example, in `flight1` in the earlier examples, the `Airline` and `FlightNo` fields are read-only, but `Gate` can be changed.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#28](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/key_6.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="cd85f-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cd85f-133">See Also</span></span>  
 [<span data-ttu-id="cd85f-134">익명 형식 정의</span><span class="sxs-lookup"><span data-stu-id="cd85f-134">Anonymous Type Definition</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-type-definition.md)  
 [<span data-ttu-id="cd85f-135">방법: 익명 형식 선언에서 속성 이름 및 형식 유추</span><span class="sxs-lookup"><span data-stu-id="cd85f-135">How to: Infer Property Names and Types in Anonymous Type Declarations</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)  
 [<span data-ttu-id="cd85f-136">익명 형식</span><span class="sxs-lookup"><span data-stu-id="cd85f-136">Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
