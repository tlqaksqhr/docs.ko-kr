---
title: '방법: Visual Basic에서 기본 속성 선언 및 호출'
ms.date: 07/20/2015
helpviewer_keywords:
- defaults [Visual Basic], properties
- properties [Visual Basic], default
- procedures [Visual Basic], defining
- default properties [Visual Basic], in Visual Basic
- Visual Basic code, procedures
- Visual Basic code, properties
- default properties
ms.assetid: 68b4026e-09ef-4613-808e-f6287494ff63
ms.openlocfilehash: 7805ee4dcd4bad0d0624c97ccc25232e9bc31ba4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650997"
---
# <a name="how-to-declare-and-call-a-default-property-in-visual-basic"></a><span data-ttu-id="cb2e7-102">방법: Visual Basic에서 기본 속성 선언 및 호출</span><span class="sxs-lookup"><span data-stu-id="cb2e7-102">How to: Declare and Call a Default Property in Visual Basic</span></span>
<span data-ttu-id="cb2e7-103">A *기본 속성* 지정 하지 않고 코드에 액세스할 수 있는 클래스 또는 구조체 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="cb2e7-103">A *default property* is a class or structure property that your code can access without specifying it.</span></span> <span data-ttu-id="cb2e7-104">코드 이름을 호출 하는 경우 클래스 또는 구조 하지만 하지는 속성 및 컨텍스트 속성에 대 한 액세스를 허용, Visual Basic 있을 경우 해당 클래스 또는 구조체의 기본 속성에 대 한 액세스를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb2e7-104">When calling code names a class or structure but not a property, and the context allows access to a property, Visual Basic resolves the access to that class or structure's default property if one exists.</span></span>  
  
 <span data-ttu-id="cb2e7-105">클래스 또는 구조체 수 최대 하나의 기본 속성이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb2e7-105">A class or structure can have at most one default property.</span></span> <span data-ttu-id="cb2e7-106">그러나 기본 속성을 오버 로드 수 있으며 버전을 여러 개 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb2e7-106">However, you can overload a default property and have more than one version of it.</span></span>  
  
 <span data-ttu-id="cb2e7-107">자세한 내용은 참조 [기본](../../../../visual-basic/language-reference/modifiers/default.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="cb2e7-107">For more information, see [Default](../../../../visual-basic/language-reference/modifiers/default.md).</span></span>  
  
### <a name="to-declare-a-default-property"></a><span data-ttu-id="cb2e7-108">기본 속성을 선언 하려면</span><span class="sxs-lookup"><span data-stu-id="cb2e7-108">To declare a default property</span></span>  
  
1.  <span data-ttu-id="cb2e7-109">일반적인 방법으로 속성을 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb2e7-109">Declare the property in the normal way.</span></span> <span data-ttu-id="cb2e7-110">지정 하지 않으면는 `Shared` 또는 `Private` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="cb2e7-110">Do not specify the `Shared` or `Private` keyword.</span></span>  
  
2.  <span data-ttu-id="cb2e7-111">포함 된 `Default` 속성 선언에서 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="cb2e7-111">Include the `Default` keyword in the property declaration.</span></span>  
  
3.  <span data-ttu-id="cb2e7-112">속성에 대 한 하나 이상의 매개 변수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb2e7-112">Specify at least one parameter for the property.</span></span> <span data-ttu-id="cb2e7-113">하나 이상의 인수를 사용 하지 않는 기본 속성을 정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cb2e7-113">You cannot define a default property that does not take at least one argument.</span></span>  
  
     [!code-vb[VbVbcnProcedures#17](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_1.vb)]  
  
### <a name="to-call-a-default-property"></a><span data-ttu-id="cb2e7-114">기본 속성을 호출 하려면</span><span class="sxs-lookup"><span data-stu-id="cb2e7-114">To call a default property</span></span>  
  
1.  <span data-ttu-id="cb2e7-115">포함 하는 클래스 또는 구조체 형식의 변수를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb2e7-115">Declare a variable of the containing class or structure type.</span></span>  
  
     [!code-vb[VbVbcnProcedures#16](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_2.vb)]  
  
2.  <span data-ttu-id="cb2e7-116">속성 이름은 일반적으로 포함 위치 식에서 변수 이름만을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb2e7-116">Use the variable name alone in an expression where you would normally include the property name.</span></span>  
  
     [!code-vb[VbVbcnProcedures#21](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_3.vb)]  
  
3.  <span data-ttu-id="cb2e7-117">에 인수 목록 괄호로 묶어 변수 이름을 뒤에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb2e7-117">Follow the variable name with an argument list in parentheses.</span></span> <span data-ttu-id="cb2e7-118">기본 속성은 하나 이상의 인수를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb2e7-118">A default property must take at least one argument.</span></span>  
  
     [!code-vb[VbVbcnProcedures#20](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_4.vb)]  
  
4.  <span data-ttu-id="cb2e7-119">기본 속성 값을 검색 하려면 변수 이름 또는 등호 따라 식에서 인수 목록과 함께 사용 하 여 (`=`) 대입문에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb2e7-119">To retrieve the default property value, use the variable name, with an argument list, in an expression or following the equal (`=`) sign in an assignment statement.</span></span>  
  
     [!code-vb[VbVbcnProcedures#15](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_5.vb)]  
  
5.  <span data-ttu-id="cb2e7-120">기본 속성 값을 설정 하려면 대입문의 왼쪽에는 인수 목록을 사용 하 여 변수 이름으로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb2e7-120">To set the default property value, use the variable name, with an argument list, on the left side of an assignment statement.</span></span>  
  
     [!code-vb[VbVbcnProcedures#14](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_6.vb)]  
  
6.  <span data-ttu-id="cb2e7-121">다른 속성에 액세스 하려면 수행한 것 처럼 항상 기본 속성 이름은 변수 이름과 함께 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb2e7-121">You can always specify the default property name together with the variable name, just as you would do to access any other property.</span></span>  
  
     [!code-vb[VbVbcnProcedures#19](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_7.vb)]  
  
## <a name="example"></a><span data-ttu-id="cb2e7-122">예제</span><span class="sxs-lookup"><span data-stu-id="cb2e7-122">Example</span></span>  
 <span data-ttu-id="cb2e7-123">다음 예제에서는 클래스에 기본 속성을 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb2e7-123">The following example declares a default property on a class.</span></span>  
  
 [!code-vb[VbVbcnProcedures#12](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_8.vb)]  
  
## <a name="example"></a><span data-ttu-id="cb2e7-124">예제</span><span class="sxs-lookup"><span data-stu-id="cb2e7-124">Example</span></span>  
 <span data-ttu-id="cb2e7-125">다음 예제에서는 기본 속성을 호출 하는 방법을 `myProperty` 클래스에 `class1`합니다.</span><span class="sxs-lookup"><span data-stu-id="cb2e7-125">The following example demonstrates how to call the default property `myProperty` on class `class1`.</span></span> <span data-ttu-id="cb2e7-126">에 값을 저장 하는 세 개의 대입문 `myProperty`, 및 <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> 통화 값을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="cb2e7-126">The three assignment statements store values in `myProperty`, and the <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> call reads the values.</span></span>  
  
 [!code-vb[VbVbcnProcedures#13](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_9.vb)]  
  
 <span data-ttu-id="cb2e7-127">기본 속성의 가장 일반적으로 사용 되는 <xref:Microsoft.VisualBasic.Collection.Item%2A> 다양 한 컬렉션 클래스는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="cb2e7-127">The most common use of a default property is the <xref:Microsoft.VisualBasic.Collection.Item%2A> property on various collection classes.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="cb2e7-128">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="cb2e7-128">Robust Programming</span></span>  
 <span data-ttu-id="cb2e7-129">기본 속성 소스 코드 문자가 약간 저하 될 수 있지만 코드를 읽기 더 어렵게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb2e7-129">Default properties can result in a small reduction in source code-characters, but they can make your code more difficult to read.</span></span> <span data-ttu-id="cb2e7-130">클래스 또는 구조체 이름에 대 한 참조는 시 호출 코드에서 클래스 또는 구조체에 익숙하지 않은 경우 않아야 특정 참조 하는 클래스 또는 구조체를 자체 또는 기본 속성에 액세스 하는지 여부입니다.</span><span class="sxs-lookup"><span data-stu-id="cb2e7-130">If the calling code is not familiar with your class or structure, when it makes a reference to the class or structure name it cannot be certain whether that reference accesses the class or structure itself, or a default property.</span></span> <span data-ttu-id="cb2e7-131">컴파일러 오류 또는 미묘한 런타임에 논리 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb2e7-131">This can lead to compiler errors or subtle run-time logic errors.</span></span>  
  
 <span data-ttu-id="cb2e7-132">항상 사용 하 여 기본 속성 오류의 가능성을 어느 정도 줄일 수 있습니다는 [Option Strict 문](../../../../visual-basic/language-reference/statements/option-strict-statement.md) 컴파일러 형식 검사를 설정 하려면 `On`합니다.</span><span class="sxs-lookup"><span data-stu-id="cb2e7-132">You can somewhat reduce the chance of default property errors by always using the [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) to set compiler type checking to `On`.</span></span>  
  
 <span data-ttu-id="cb2e7-133">에서 사용 하는 미리 정의 된 클래스 또는 구조체 코드를 결정 해야 기본 속성이 여부와 그럴 경우 계획 이라면 해당 이름이 무엇 인지 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb2e7-133">If you are planning to use a predefined class or structure in your code, you must determine whether it has a default property, and if so, what its name is.</span></span>  
  
 <span data-ttu-id="cb2e7-134">이러한 단점으로 인해 기본 속성을 정의 하지 않는 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb2e7-134">Because of these disadvantages, you should consider not defining default properties.</span></span> <span data-ttu-id="cb2e7-135">코드의 가독성을 높이기 위해 또한 항상 모든 속성에 명시적으로 참조를 고려 해야, 심지어 기본 속성 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="cb2e7-135">For code readability, you should also consider always referring to all properties explicitly, even default properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb2e7-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cb2e7-136">See Also</span></span>  
 [<span data-ttu-id="cb2e7-137">속성 프로시저</span><span class="sxs-lookup"><span data-stu-id="cb2e7-137">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="cb2e7-138">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="cb2e7-138">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="cb2e7-139">Property 문</span><span class="sxs-lookup"><span data-stu-id="cb2e7-139">Property Statement</span></span>](../../../../visual-basic/language-reference/statements/property-statement.md)  
 [<span data-ttu-id="cb2e7-140">기본</span><span class="sxs-lookup"><span data-stu-id="cb2e7-140">Default</span></span>](../../../../visual-basic/language-reference/modifiers/default.md)  
 [<span data-ttu-id="cb2e7-141">Visual Basic에서 속성과 변수의 차이점</span><span class="sxs-lookup"><span data-stu-id="cb2e7-141">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)  
 [<span data-ttu-id="cb2e7-142">방법: 속성 만들기</span><span class="sxs-lookup"><span data-stu-id="cb2e7-142">How to: Create a Property</span></span>](./how-to-create-a-property.md)  
 [<span data-ttu-id="cb2e7-143">방법: 액세스 수준이 혼합된 속성 선언</span><span class="sxs-lookup"><span data-stu-id="cb2e7-143">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)  
 [<span data-ttu-id="cb2e7-144">방법: 속성 프로시저 호출</span><span class="sxs-lookup"><span data-stu-id="cb2e7-144">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)  
 [<span data-ttu-id="cb2e7-145">방법: 속성 값 입력</span><span class="sxs-lookup"><span data-stu-id="cb2e7-145">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)  
 [<span data-ttu-id="cb2e7-146">방법: 속성에서 값 가져오기</span><span class="sxs-lookup"><span data-stu-id="cb2e7-146">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
