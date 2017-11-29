---
title: "방법: 속성 만들기(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- Visual Basic code, properties
- properties [Visual Basic]
ms.assetid: 4d229712-6be8-4c5c-bac5-06995ce9185a
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d140e6a10061f7fabe3d12c6cce5d0c201e103d6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-property-visual-basic"></a><span data-ttu-id="786d6-102">방법: 속성 만들기(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="786d6-102">How to: Create a Property (Visual Basic)</span></span>
<span data-ttu-id="786d6-103">속성 정의 간에 묶습니다는 `Property` 문 및 `End Property` 문.</span><span class="sxs-lookup"><span data-stu-id="786d6-103">You enclose a property definition between a `Property` statement and an `End Property` statement.</span></span> <span data-ttu-id="786d6-104">정의 하 고이 정의 `Get` 프로시저는 `Set` 프로시저 중 하나 또는 둘 다 합니다.</span><span class="sxs-lookup"><span data-stu-id="786d6-104">Within this definition you define a `Get` procedure, a `Set` procedure, or both.</span></span> <span data-ttu-id="786d6-105">이러한 프로시저 내에서 모든 속성의 코드에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="786d6-105">All the property's code lies within these procedures.</span></span>  
  
 <span data-ttu-id="786d6-106">`Get` 프로시저 속성의 값을 검색 및 `Set` 프로시저는 값을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="786d6-106">The `Get` procedure retrieves the property's value, and the `Set` procedure stores a value.</span></span> <span data-ttu-id="786d6-107">속성 읽기/쓰기 액세스할 수 있도록 추가 하려는 경우에 두 절차 모두를 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="786d6-107">If you want the property to have read/write access, you must define both procedures.</span></span> <span data-ttu-id="786d6-108">읽기 전용 속성에 대 한 정의 `Get`, 쓰기 전용 속성에 대 한 정의 `Set`합니다.</span><span class="sxs-lookup"><span data-stu-id="786d6-108">For a read-only property, you define only `Get`, and for a write-only property, you define only `Set`.</span></span>  
  
### <a name="to-create-a-property"></a><span data-ttu-id="786d6-109">속성을 만들려면</span><span class="sxs-lookup"><span data-stu-id="786d6-109">To create a property</span></span>  
  
1.  <span data-ttu-id="786d6-110">사용 하 여 모든 속성 또는 프로시저 외부는 [Property 문](../../../../visual-basic/language-reference/statements/property-statement.md)옵니다는 `End Property` 문.</span><span class="sxs-lookup"><span data-stu-id="786d6-110">Outside any property or procedure, use a [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md), followed by an `End Property` statement.</span></span>  
  
2.  <span data-ttu-id="786d6-111">속성 매개 변수를 사용 하는 경우에 따라는 `Property` 키워드와 프로시저를 지정한 다음 매개 변수 목록을 괄호로 이름 합니다.</span><span class="sxs-lookup"><span data-stu-id="786d6-111">If the property takes parameters, follow the `Property` keyword with the name of the procedure, then the parameter list in parentheses.</span></span>  
  
3.  <span data-ttu-id="786d6-112">괄호 다음에 `As` 절 속성의 값의 데이터 형식을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="786d6-112">Follow the parentheses with an `As` clause to specify the data type of the property's value.</span></span> <span data-ttu-id="786d6-113">쓰기 전용 속성에도 데이터 형식을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="786d6-113">You must specify the data type even for a write-only property.</span></span>  
  
4.  <span data-ttu-id="786d6-114">추가 `Get` 및 `Set` 프로시저 적절 하 게 합니다.</span><span class="sxs-lookup"><span data-stu-id="786d6-114">Add `Get` and `Set` procedures, as appropriate.</span></span> <span data-ttu-id="786d6-115">다음 지침을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="786d6-115">See the following directions.</span></span>  
  
### <a name="to-create-a-get-procedure-that-retrieves-a-property-value"></a><span data-ttu-id="786d6-116">속성 값을 검색 하는 Get 프로시저를 만들려면</span><span class="sxs-lookup"><span data-stu-id="786d6-116">To create a Get procedure that retrieves a property value</span></span>  
  
1.  <span data-ttu-id="786d6-117">사이 `Property` 및 `End Property` 문을 작성 한 [Get 문을](../../../../visual-basic/language-reference/statements/get-statement.md)옵니다는 `End Get` 문을 합니다.</span><span class="sxs-lookup"><span data-stu-id="786d6-117">Between the `Property` and `End Property` statements, write a [Get Statement](../../../../visual-basic/language-reference/statements/get-statement.md), followed by an `End Get` statement.</span></span> <span data-ttu-id="786d6-118">에 대 한 모든 매개 변수를 정의할 필요가 없습니다는 `Get` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="786d6-118">You do not need to define any parameters for the `Get` procedure.</span></span>  
  
2.  <span data-ttu-id="786d6-119">사이의 속성의 값을 검색 하는 코드 문을 배치는 `Get` 및 `End Get` 문.</span><span class="sxs-lookup"><span data-stu-id="786d6-119">Place the code statements to retrieve the property's value between the `Get` and `End Get` statements.</span></span> <span data-ttu-id="786d6-120">이 코드는 다른 계산 및 데이터 조작을 생성 하 고 속성의 값을 반환 하는 것 외에도 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="786d6-120">This code can include other calculations and data manipulations in addition to generating and returning the property's value.</span></span>  
  
3.  <span data-ttu-id="786d6-121">사용 하 여 한 `Return` 호출 코드에 속성의 값을 반환 하는 문입니다.</span><span class="sxs-lookup"><span data-stu-id="786d6-121">Use a `Return` statement to return the property's value to the calling code.</span></span>  
  
 <span data-ttu-id="786d6-122">작성 해야 합니다는 `Get` 프로시저 읽기 / 쓰기 속성에 대 한 읽기 전용 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="786d6-122">You must write a `Get` procedure for a read-write property and for a read-only property.</span></span> <span data-ttu-id="786d6-123">정의할 수 없습니다는 `Get` 쓰기 전용 속성에 대 한 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="786d6-123">You must not define a `Get` procedure for a write-only property.</span></span>  
  
### <a name="to-create-a-set-procedure-that-writes-a-propertys-value"></a><span data-ttu-id="786d6-124">속성의 값을 작성 하는 집합 프로시저를 만들려면</span><span class="sxs-lookup"><span data-stu-id="786d6-124">To create a Set procedure that writes a property's value</span></span>  
  
1.  <span data-ttu-id="786d6-125">사이 `Property` 및 `End Property` 문을 작성 한 [Set 문을](../../../../visual-basic/language-reference/statements/set-statement.md)옵니다는 `End Set` 문을 합니다.</span><span class="sxs-lookup"><span data-stu-id="786d6-125">Between the `Property` and `End Property` statements, write a [Set Statement](../../../../visual-basic/language-reference/statements/set-statement.md), followed by an `End Set` statement.</span></span>  
  
2.  <span data-ttu-id="786d6-126">에 `Set` 문을 수행는 `Set` 매개 변수 목록 괄호로 묶어 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="786d6-126">In the `Set` statement, follow the `Set` keyword with a parameter list in parentheses.</span></span> <span data-ttu-id="786d6-127">이 매개 변수 목록 호출 코드에 의해 전달 된 값에 대 한 하나 이상의 값 매개 변수를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="786d6-127">This parameter list must include at least a value parameter for the value passed by the calling code.</span></span> <span data-ttu-id="786d6-128">이 값 매개 변수의 기본 이름은 `Value`, 하지만 해당 하는 경우 다른 이름을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="786d6-128">The default name for this value parameter is `Value`, but you can use a different name if appropriate.</span></span> <span data-ttu-id="786d6-129">Value 매개 변수는 동일한 데이터 형식이 속성 자체으로 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="786d6-129">The value parameter must have the same data type as the property itself.</span></span>  
  
3.  <span data-ttu-id="786d6-130">값은 속성에 저장 하는 코드 문을 배치는 `Set` 및 `End Set` 문.</span><span class="sxs-lookup"><span data-stu-id="786d6-130">Place the code statements to store a value in the property between the `Set` and `End Set` statements.</span></span> <span data-ttu-id="786d6-131">이 코드는 다른 계산 및 데이터 조작을 유효성을 검사 하 고 속성의 값을 저장 하는 것 외에도 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="786d6-131">This code can include other calculations and data manipulations in addition to validating and storing the property's value.</span></span>  
  
4.  <span data-ttu-id="786d6-132">Value 매개 변수를 사용 하 여 호출 코드에서 제공 된 값을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="786d6-132">Use the value parameter to accept the value supplied by the calling code.</span></span> <span data-ttu-id="786d6-133">대입문에서 직접이 값을 저장 하거나 내부 값을 저장할 수를 계산 하는 식에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="786d6-133">You can either store this value directly in an assignment statement, or use it in an expression to calculate the internal value to be stored.</span></span>  
  
 <span data-ttu-id="786d6-134">작성 해야 합니다는 `Set` 쓰기 전용 속성에 대 한 읽기 / 쓰기 속성에 대 한 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="786d6-134">You must write a `Set` procedure for a read-write property and for a write-only property.</span></span> <span data-ttu-id="786d6-135">정의할 수 없습니다는 `Set` 프로시저에 대 한 읽기 전용 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="786d6-135">You must not define a `Set` procedure for a read-only property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="786d6-136">예제</span><span class="sxs-lookup"><span data-stu-id="786d6-136">Example</span></span>  
 <span data-ttu-id="786d6-137">다음 예제에서는 두 개의 구성 요소 이름, 성 및 last name로 전체 이름을 저장 하는 읽기/쓰기 속성을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="786d6-137">The following example creates a read/write property that stores a full name as two constituent names, the first name and the last name.</span></span> <span data-ttu-id="786d6-138">호출 코드를 읽을 때 `fullName`, `Get` 프로시저가 두 구성 요소 이름을 결합 하 고 전체 이름을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="786d6-138">When the calling code reads `fullName`, the `Get` procedure combines the two constituent names and returns the full name.</span></span> <span data-ttu-id="786d6-139">새 전체 이름을 할당 하는 호출 하는 코드는 `Set` 프로시저가 두 구성 요소 이름으로 나누는 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="786d6-139">When the calling code assigns a new full name, the `Set` procedure attempts to break it into two constituent names.</span></span> <span data-ttu-id="786d6-140">공백을 찾지 못하면 하는 경우 모든 이름으로 저장 것입니다.</span><span class="sxs-lookup"><span data-stu-id="786d6-140">If it does not find a space, it stores it all as the first name.</span></span>  
  
 [!code-vb[VbVbcnProcedures#8](./codesnippet/VisualBasic/how-to-create-a-property_1.vb)]  
  
 <span data-ttu-id="786d6-141">다음 예제에서는의 속성 프로시저를 호출 하는 일반적인 `fullName`합니다.</span><span class="sxs-lookup"><span data-stu-id="786d6-141">The following example shows typical calls to the property procedures of `fullName`.</span></span> <span data-ttu-id="786d6-142">속성 값을 설정 하는 첫 번째 호출 하 고 두 번째 호출에서 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="786d6-142">The first call sets the property value and the second call retrieves it.</span></span>  
  
 [!code-vb[VbVbcnProcedures#9](./codesnippet/VisualBasic/how-to-create-a-property_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="786d6-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="786d6-143">See Also</span></span>  
 [<span data-ttu-id="786d6-144">절차</span><span class="sxs-lookup"><span data-stu-id="786d6-144">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="786d6-145">속성 프로시저</span><span class="sxs-lookup"><span data-stu-id="786d6-145">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="786d6-146">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="786d6-146">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="786d6-147">Visual Basic에서 속성과 변수의 차이점</span><span class="sxs-lookup"><span data-stu-id="786d6-147">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)  
 [<span data-ttu-id="786d6-148">방법: 액세스 수준이 혼합된 속성 선언</span><span class="sxs-lookup"><span data-stu-id="786d6-148">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)  
 [<span data-ttu-id="786d6-149">방법: 속성 프로시저 호출</span><span class="sxs-lookup"><span data-stu-id="786d6-149">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)  
 [<span data-ttu-id="786d6-150">방법: 선언 하 고 Visual Basic의 기본 속성 호출</span><span class="sxs-lookup"><span data-stu-id="786d6-150">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)  
 [<span data-ttu-id="786d6-151">방법: 속성 값 입력</span><span class="sxs-lookup"><span data-stu-id="786d6-151">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)  
 [<span data-ttu-id="786d6-152">방법: 속성에서 값 가져오기</span><span class="sxs-lookup"><span data-stu-id="786d6-152">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
