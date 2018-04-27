---
title: 인수를 값으로 전달할 때와 참조로 전달할 때의 차이점(Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- ByRef keyword [Visual Basic], passing arguments by reference
- Visual Basic code, procedures
- procedures [Visual Basic], passing arguments
- ByVal keyword [Visual Basic], passing arguments by value
- arguments [Visual Basic], passing by value or by reference
ms.assetid: 5f5c38fe-3e2d-494c-8fff-f4025b55ec93
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8f733b4fd50612292c0c4ac7195304d99ae2dbea
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="differences-between-passing-an-argument-by-value-and-by-reference-visual-basic"></a><span data-ttu-id="07077-102">인수를 값으로 전달할 때와 참조로 전달할 때의 차이점(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="07077-102">Differences Between Passing an Argument By Value and By Reference (Visual Basic)</span></span>
<span data-ttu-id="07077-103">프로시저에 하나 이상의 인수를 전달 하는 경우 각 인수에서 호출 코드의 기본 프로그래밍 요소에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="07077-103">When you pass one or more arguments to a procedure, each argument corresponds to an underlying programming element in the calling code.</span></span> <span data-ttu-id="07077-104">이 내부 요소 값 또는 그에 대 한 참조를 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07077-104">You can pass either the value of this underlying element, or a reference to it.</span></span> <span data-ttu-id="07077-105">이것은 *전달 메커니즘*합니다.</span><span class="sxs-lookup"><span data-stu-id="07077-105">This is known as the *passing mechanism*.</span></span>  
  
## <a name="passing-by-value"></a><span data-ttu-id="07077-106">값으로 전달</span><span class="sxs-lookup"><span data-stu-id="07077-106">Passing by Value</span></span>  
 <span data-ttu-id="07077-107">인수를 전달 하면 *값별로* 지정 하 여는 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) 프로시저 정의에서 해당 매개 변수에 대 한 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="07077-107">You pass an argument *by value* by specifying the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) keyword for the corresponding parameter in the procedure definition.</span></span> <span data-ttu-id="07077-108">이 전달 메커니즘을 사용 하는 경우 Visual Basic 프로시저의 지역 변수에는 기본 프로그래밍 요소의 값을 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="07077-108">When you use this passing mechanism, Visual Basic copies the value of the underlying programming element into a local variable in the procedure.</span></span> <span data-ttu-id="07077-109">호출 코드의 프로시저 코드 내부 요소에 대 한 액세스를 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="07077-109">The procedure code does not have any access to the underlying element in the calling code.</span></span>  
  
## <a name="passing-by-reference"></a><span data-ttu-id="07077-110">참조로 전달</span><span class="sxs-lookup"><span data-stu-id="07077-110">Passing by Reference</span></span>  
 <span data-ttu-id="07077-111">인수를 전달 하면 *참조로* 지정 하 여는 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) 프로시저 정의에서 해당 매개 변수에 대 한 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="07077-111">You pass an argument *by reference* by specifying the [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) keyword for the corresponding parameter in the procedure definition.</span></span> <span data-ttu-id="07077-112">이 전달 메커니즘을 사용 하는 경우 Visual Basic에서는 호출 코드에서 기본 프로그래밍 요소에 대 한 직접 참조를 프로시저에 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="07077-112">When you use this passing mechanism, Visual Basic gives the procedure a direct reference to the underlying programming element in the calling code.</span></span>  
  
## <a name="passing-mechanism-and-element-type"></a><span data-ttu-id="07077-113">전달 메커니즘 및 요소 형식</span><span class="sxs-lookup"><span data-stu-id="07077-113">Passing Mechanism and Element Type</span></span>  
 <span data-ttu-id="07077-114">전달 메커니즘의 선택은 요소 형식의 분류와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="07077-114">The choice of passing mechanism is not the same as the classification of the underlying element type.</span></span> <span data-ttu-id="07077-115">값 이나 참조로 전달 프로시저 코드에 제공 될 Visual Basic 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="07077-115">Passing by value or by reference refers to what Visual Basic supplies to the procedure code.</span></span> <span data-ttu-id="07077-116">값 형식 또는 참조 형식에는 프로그래밍 요소는 메모리에 저장 하는 방법을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="07077-116">A value type or reference type refers to how a programming element is stored in memory.</span></span>  
  
 <span data-ttu-id="07077-117">그러나 전달 메커니즘 및 요소 형식이 서로 관련 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07077-117">However, the passing mechanism and element type are interrelated.</span></span> <span data-ttu-id="07077-118">참조 형식의 값은 메모리의 다른 위치에서 데이터에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="07077-118">The value of a reference type is a pointer to the data elsewhere in memory.</span></span> <span data-ttu-id="07077-119">즉, 참조 형식 값으로 전달 하면 프로시저 코드에는 기본 요소 데이터에 대 한 포인터 요소 자체에 액세스할 수 없는 경우에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07077-119">This means that when you pass a reference type by value, the procedure code has a pointer to the underlying element's data, even though it cannot access the underlying element itself.</span></span> <span data-ttu-id="07077-120">예를 들어 요소는 배열 변수, 프로시저 코드에는 변수 자체에 액세스할 수 없는 있지만 배열 멤버에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07077-120">For example, if the element is an array variable, the procedure code does not have access to the variable itself, but it can access the array members.</span></span>  
  
## <a name="ability-to-modify"></a><span data-ttu-id="07077-121">수정할 수 있는 기능</span><span class="sxs-lookup"><span data-stu-id="07077-121">Ability to Modify</span></span>  
 <span data-ttu-id="07077-122">수정할 수 없는 요소를 인수로 전달 하면 프로시저 수정할 수 것 호출 코드에서 전달 되는 여부 `ByVal` 또는 `ByRef`합니다.</span><span class="sxs-lookup"><span data-stu-id="07077-122">When you pass a nonmodifiable element as an argument, the procedure can never modify it in the calling code, whether it is passed `ByVal` or `ByRef`.</span></span>  
  
 <span data-ttu-id="07077-123">다음 표에서 수정할 수 있는 요소에 대 한 요소 형식 및 전달 메커니즘 간의 상호 작용 요약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07077-123">For a modifiable element, the following table summarizes the interaction between the element type and the passing mechanism.</span></span>  
  
|<span data-ttu-id="07077-124">요소 형식</span><span class="sxs-lookup"><span data-stu-id="07077-124">Element type</span></span>|<span data-ttu-id="07077-125">전달 `ByVal`</span><span class="sxs-lookup"><span data-stu-id="07077-125">Passed `ByVal`</span></span>|<span data-ttu-id="07077-126">전달 `ByRef`</span><span class="sxs-lookup"><span data-stu-id="07077-126">Passed `ByRef`</span></span>|  
|------------------|--------------------|--------------------|  
|<span data-ttu-id="07077-127">값 형식 (값만 포함)</span><span class="sxs-lookup"><span data-stu-id="07077-127">Value type (contains only a value)</span></span>|<span data-ttu-id="07077-128">프로시저 변수 또는 해당 멤버 중 하나를 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="07077-128">The procedure cannot change the variable or any of its members.</span></span>|<span data-ttu-id="07077-129">프로시저가 변수 및 해당 멤버를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07077-129">The procedure can change the variable and its members.</span></span>|  
|<span data-ttu-id="07077-130">참조 형식 (클래스 또는 구조체 인스턴스에 대 한 포인터 포함)</span><span class="sxs-lookup"><span data-stu-id="07077-130">Reference type (contains a pointer to a class or structure instance)</span></span>|<span data-ttu-id="07077-131">프로시저 변수 변경할 수 없지만 가리키는 인스턴스의 멤버를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07077-131">The procedure cannot change the variable but can change members of the instance to which it points.</span></span>|<span data-ttu-id="07077-132">프로시저 변수와 가리키는 인스턴스의 멤버 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07077-132">The procedure can change the variable and members of the instance to which it points.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="07077-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="07077-133">See Also</span></span>  
 [<span data-ttu-id="07077-134">절차</span><span class="sxs-lookup"><span data-stu-id="07077-134">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="07077-135">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="07077-135">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="07077-136">방법: 프로시저에 인수 전달</span><span class="sxs-lookup"><span data-stu-id="07077-136">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)  
 [<span data-ttu-id="07077-137">값 또는 참조로 인수 전달</span><span class="sxs-lookup"><span data-stu-id="07077-137">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)  
 [<span data-ttu-id="07077-138">수정할 수 있는 인수와 수정할 수 없는 인수 사이의 차이점</span><span class="sxs-lookup"><span data-stu-id="07077-138">Differences Between Modifiable and Nonmodifiable Arguments</span></span>](./differences-between-modifiable-and-nonmodifiable-arguments.md)  
 [<span data-ttu-id="07077-139">방법: 프로시저 인수의 값 변경</span><span class="sxs-lookup"><span data-stu-id="07077-139">How to: Change the Value of a Procedure Argument</span></span>](./how-to-change-the-value-of-a-procedure-argument.md)  
 [<span data-ttu-id="07077-140">방법: 값 변경에 대해 프로시저 인수 보호</span><span class="sxs-lookup"><span data-stu-id="07077-140">How to: Protect a Procedure Argument Against Value Changes</span></span>](./how-to-protect-a-procedure-argument-against-value-changes.md)  
 [<span data-ttu-id="07077-141">방법: 인수가 값으로 전달되도록 설정</span><span class="sxs-lookup"><span data-stu-id="07077-141">How to: Force an Argument to Be Passed by Value</span></span>](./how-to-force-an-argument-to-be-passed-by-value.md)  
 [<span data-ttu-id="07077-142">위치 및 이름으로 인수 전달</span><span class="sxs-lookup"><span data-stu-id="07077-142">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)  
 [<span data-ttu-id="07077-143">값 형식과 참조 형식</span><span class="sxs-lookup"><span data-stu-id="07077-143">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
