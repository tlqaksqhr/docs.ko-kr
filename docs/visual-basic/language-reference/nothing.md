---
title: Nothing(Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- Nothing
- vb.Nothing
helpviewer_keywords:
- Nothing keyword [Visual Basic]
- Nothing keyword [Visual Basic], syntax
ms.assetid: 06176e2d-bbf7-4a37-afaa-a86ad21ee99f
caps.latest.revision: "31"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6932fee01ec6f39f67fb1a26a9a5b5cbd47d9767
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="nothing-visual-basic"></a><span data-ttu-id="d6e22-102">Nothing(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d6e22-102">Nothing (Visual Basic)</span></span>
<span data-ttu-id="d6e22-103">모든 데이터 형식의 기본 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d6e22-103">Represents the default value of any data type.</span></span> <span data-ttu-id="d6e22-104">기본값은 참조 형식에 대해는 `null` 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e22-104">For reference types, the default value is the `null` reference.</span></span> <span data-ttu-id="d6e22-105">값 형식에 대 한 기본값 값 형식이 nullable 인지에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="d6e22-105">For value types, the default value depends on whether the value type is nullable.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d6e22-106">Nullable이 아닌 값 형식에 대 한 `Nothing` Visual Basic에서 다릅니다 `null` C#입니다.</span><span class="sxs-lookup"><span data-stu-id="d6e22-106">For non-nullable value types, `Nothing` in Visual Basic differs from `null` in C#.</span></span> <span data-ttu-id="d6e22-107">Visual basic에서는 null이 아닌 값 형식으로의 변수를 설정 하면 `Nothing`, 변수 선언된 된 형식에 대 한 기본 값으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6e22-107">In Visual Basic, if you set a variable of a non-nullable value type to `Nothing`, the variable is set to the default value for its declared type.</span></span> <span data-ttu-id="d6e22-108">C#에서 nullable이 아닌 값 형식으로의 변수를 할당 하는 경우 `null`, 컴파일 타임 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e22-108">In C#, if you assign a variable of a non-nullable value type to `null`, a compile-time error occurs.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d6e22-109">설명</span><span class="sxs-lookup"><span data-stu-id="d6e22-109">Remarks</span></span>  
 <span data-ttu-id="d6e22-110">`Nothing`데이터 형식의 기본 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d6e22-110">`Nothing` represents the default value of a data type.</span></span> <span data-ttu-id="d6e22-111">기본값의 값 형식 또는 참조 형식의 변수 인지에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="d6e22-111">The default value depends on whether the variable is of a value type or of a reference type.</span></span>  
  
 <span data-ttu-id="d6e22-112">변수는 *값 형식* 직접 해당 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e22-112">A variable of a *value type* directly contains its value.</span></span> <span data-ttu-id="d6e22-113">값 형식에는 숫자 데이터 형식을 모두 포함 `Boolean`, `Char`, `Date`, 모든 구조 및 모든 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e22-113">Value types include all numeric data types, `Boolean`, `Char`, `Date`, all structures, and all enumerations.</span></span> <span data-ttu-id="d6e22-114">변수는 *유형을 참조* 메모리에 개체의 인스턴스에 대 한 참조를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e22-114">A variable of a *reference type* stores a reference to an instance of the object in memory.</span></span> <span data-ttu-id="d6e22-115">참조 형식 클래스, 배열, 대리자 및 문자열을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e22-115">Reference types include classes, arrays, delegates, and strings.</span></span> <span data-ttu-id="d6e22-116">자세한 내용은 [Value Types and Reference Types](../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d6e22-116">For more information, see [Value Types and Reference Types](../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md).</span></span>  
  
 <span data-ttu-id="d6e22-117">변수 값의 경우 입력의 동작 `Nothing` null 허용 데이터 형식의 변수 인지에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="d6e22-117">If a variable is of a value type, the behavior of `Nothing` depends on whether the variable is of a nullable data type.</span></span> <span data-ttu-id="d6e22-118">Nullable 값 형식을 나타내는, 추가 된 `?` 형식 이름에는 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="d6e22-118">To represent a nullable value type, add a `?` modifier to the type name.</span></span> <span data-ttu-id="d6e22-119">할당 `Nothing` nullable 변수를 값으로 설정 `null`합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e22-119">Assigning `Nothing` to a nullable variable sets the value to `null`.</span></span> <span data-ttu-id="d6e22-120">자세한 내용 및 예제에 대 한 참조 [Nullable 값 형식](../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e22-120">For more information and examples, see [Nullable Value Types](../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md).</span></span>  
  
 <span data-ttu-id="d6e22-121">변수가 null을 허용 하는 값 형식에 있으면 할당 `Nothing` 를 설정 하기 기본 값으로 선언된 된 형식에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e22-121">If a variable is of a value type that is not nullable, assigning `Nothing` to it sets it to the default value for its declared type.</span></span> <span data-ttu-id="d6e22-122">해당 형식 가변 멤버에 포함 된 경우 해당 기본값을 모두 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6e22-122">If that type contains variable members, they are all set to their default values.</span></span> <span data-ttu-id="d6e22-123">다음 예에서는 스칼라 형식에 대 한 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d6e22-123">The following example illustrates this for scalar types.</span></span>  
  
 [!code-vb[VbVbalrKeywords#7](../../visual-basic/language-reference/codesnippet/VisualBasic/nothing_1.vb)]  
  
 <span data-ttu-id="d6e22-124">할당 된 변수는 참조 형식의 경우 `Nothing` 변수를 설정는 `null` 변수의 형식의 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e22-124">If a variable is of a reference type, assigning `Nothing` to the variable sets it to a `null` reference of the variable's type.</span></span> <span data-ttu-id="d6e22-125">로 설정 된 변수는 `null` 참조 개체와 연결 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e22-125">A variable that is set to a `null` reference is not associated with any object.</span></span> <span data-ttu-id="d6e22-126">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="d6e22-126">The following example demonstrates this.</span></span>  
  
 [!code-vb[VbVbalrKeywords#8](../../visual-basic/language-reference/codesnippet/VisualBasic/nothing_2.vb)]  
  
 <span data-ttu-id="d6e22-127">변수는 참조 (또는 nullable 값 형식을) 여부를 확인할 때 `null`, 사용 하지 않는 `= Nothing` 또는 `<> Nothing`합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e22-127">When checking whether a reference (or nullable value type) variable is `null`, do not use `= Nothing` or `<> Nothing`.</span></span> <span data-ttu-id="d6e22-128">항상 사용 하 여 `Is Nothing` 또는 `IsNot Nothing`합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e22-128">Always use `Is Nothing` or `IsNot Nothing`.</span></span>  
  
 <span data-ttu-id="d6e22-129">Visual Basic의 문자열에 대해 빈 문자열은 `Nothing`합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e22-129">For strings in Visual Basic, the empty string equals `Nothing`.</span></span> <span data-ttu-id="d6e22-130">따라서 `"" = Nothing` 그렇습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e22-130">Therefore, `"" = Nothing` is true.</span></span>  
  
 <span data-ttu-id="d6e22-131">다음 예제에서는 사용 하는 비교는 `Is` 및 `IsNot` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="d6e22-131">The following example shows comparisons that use the `Is` and `IsNot` operators.</span></span>  
  
 [!code-vb[VbVbalrKeywords#9](../../visual-basic/language-reference/codesnippet/VisualBasic/nothing_3.vb)]  
  
 <span data-ttu-id="d6e22-132">사용 하지 않고 변수를 선언 하는 경우는 `As` 절이 속성을 설정 하 고 `Nothing`, 변수 형식이 `Object`합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e22-132">If you declare a variable without using an `As` clause and set it to `Nothing`, the variable has a type of `Object`.</span></span> <span data-ttu-id="d6e22-133">이 예제는 `Dim something = Nothing`합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e22-133">An example of this is `Dim something = Nothing`.</span></span> <span data-ttu-id="d6e22-134">컴파일 타임 오류가 발생 하는 예에서 때 `Option Strict` 에 및 `Option Infer` 꺼져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e22-134">A compile-time error occurs in this case when `Option Strict` is on and `Option Infer` is off.</span></span>  
  
 <span data-ttu-id="d6e22-135">할당 하면 `Nothing` 하는 개체 변수를 더 이상 참조 개체 인스턴스를 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e22-135">When you assign `Nothing` to an object variable, it no longer refers to any object instance.</span></span> <span data-ttu-id="d6e22-136">이전 인스턴스로 참조 변수를 한 경우로 설정 `Nothing` 인스턴스 자체는 종료 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e22-136">If the variable had previously referred to an instance, setting it to `Nothing` does not terminate the instance itself.</span></span> <span data-ttu-id="d6e22-137">종료 되 고 인스턴스와 및 남은 활성 참조가 없는 가비지 수집기 (GC) 검색 한 후에 연결 된 메모리와 시스템 리소스가 해제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6e22-137">The instance is terminated, and the memory and system resources associated with it are released, only after the garbage collector (GC) detects that there are no active references remaining.</span></span>  
  
 <span data-ttu-id="d6e22-138">`Nothing`와 다른는 <xref:System.DBNull> 초기화 되지 않은 변형 또는 존재 하지 않는 데이터베이스 열을 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="d6e22-138">`Nothing` differs from the <xref:System.DBNull> object, which represents an uninitialized variant or a nonexistent database column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6e22-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d6e22-139">See Also</span></span>  
 [<span data-ttu-id="d6e22-140">Dim 문</span><span class="sxs-lookup"><span data-stu-id="d6e22-140">Dim Statement</span></span>](../../visual-basic/language-reference/statements/dim-statement.md)  
 [<span data-ttu-id="d6e22-141">개체 수명: 개체가 만들어지고 제거되는 방법</span><span class="sxs-lookup"><span data-stu-id="d6e22-141">Object Lifetime: How Objects Are Created and Destroyed</span></span>](../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)  
 [<span data-ttu-id="d6e22-142">Visual Basic의 수명</span><span class="sxs-lookup"><span data-stu-id="d6e22-142">Lifetime in Visual Basic</span></span>](../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)  
 [<span data-ttu-id="d6e22-143">Is 연산자</span><span class="sxs-lookup"><span data-stu-id="d6e22-143">Is Operator</span></span>](../../visual-basic/language-reference/operators/is-operator.md)  
 [<span data-ttu-id="d6e22-144">IsNot 연산자</span><span class="sxs-lookup"><span data-stu-id="d6e22-144">IsNot Operator</span></span>](../../visual-basic/language-reference/operators/isnot-operator.md)  
 [<span data-ttu-id="d6e22-145">Nullable 값 형식</span><span class="sxs-lookup"><span data-stu-id="d6e22-145">Nullable Value Types</span></span>](../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
