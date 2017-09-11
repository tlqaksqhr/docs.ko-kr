---
title: "방법: 선언 하 고 Visual Basic의 기본 속성을 호출 | Microsoft 문서"
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
- defaults, properties
- properties [Visual Basic], default
- procedures, defining
- default properties, in Visual Basic
- Visual Basic code, procedures
- Visual Basic code, properties
- default properties
ms.assetid: 68b4026e-09ef-4613-808e-f6287494ff63
caps.latest.revision: 23
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
ms.openlocfilehash: 7cfd476def67ccf46e524da7943680f9e34b6a26
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-declare-and-call-a-default-property-in-visual-basic"></a><span data-ttu-id="bf9fd-102">방법: Visual Basic에서 기본 속성 선언 및 호출</span><span class="sxs-lookup"><span data-stu-id="bf9fd-102">How to: Declare and Call a Default Property in Visual Basic</span></span>
<span data-ttu-id="bf9fd-103">A *기본 속성* 지정 하지 않고 코드에 액세스할 수 있는 클래스 또는 구조체 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="bf9fd-103">A *default property* is a class or structure property that your code can access without specifying it.</span></span> <span data-ttu-id="bf9fd-104">클래스 또는 구조 있지만 속성이 아닌 이름을 지정 코드를 호출 하 고는 컨텍스트 속성에 대 한 액세스를 통해 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 있을 경우 해당 클래스 또는 구조체의 기본 속성에 대 한 액세스를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf9fd-104">When calling code names a class or structure but not a property, and the context allows access to a property, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] resolves the access to that class or structure's default property if one exists.</span></span>  
  
 <span data-ttu-id="bf9fd-105">클래스 또는 구조체 개뿐입니다 최대 하나의 기본 속성.</span><span class="sxs-lookup"><span data-stu-id="bf9fd-105">A class or structure can have at most one default property.</span></span> <span data-ttu-id="bf9fd-106">그러나 기본 속성을 오버 로드할 수 있으며의 버전이 여러 개 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf9fd-106">However, you can overload a default property and have more than one version of it.</span></span>  
  
 <span data-ttu-id="bf9fd-107">자세한 내용은 참조 [기본](../../../../visual-basic/language-reference/modifiers/default.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bf9fd-107">For more information, see [Default](../../../../visual-basic/language-reference/modifiers/default.md).</span></span>  
  
### <a name="to-declare-a-default-property"></a><span data-ttu-id="bf9fd-108">기본 속성을 선언 하려면</span><span class="sxs-lookup"><span data-stu-id="bf9fd-108">To declare a default property</span></span>  
  
1.  <span data-ttu-id="bf9fd-109">일반적인 방법으로 속성을 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf9fd-109">Declare the property in the normal way.</span></span> <span data-ttu-id="bf9fd-110">지정 하지 않으면는 `Shared` 또는 `Private` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="bf9fd-110">Do not specify the `Shared` or `Private` keyword.</span></span>  
  
2.  <span data-ttu-id="bf9fd-111">포함 된 `Default` 속성 선언에는 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="bf9fd-111">Include the `Default` keyword in the property declaration.</span></span>  
  
3.  <span data-ttu-id="bf9fd-112">속성에 대 한 하나 이상의 매개 변수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf9fd-112">Specify at least one parameter for the property.</span></span> <span data-ttu-id="bf9fd-113">하나 이상의 인수를 사용 하지 않는 기본 속성을 정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bf9fd-113">You cannot define a default property that does not take at least one argument.</span></span>  
  
     <span data-ttu-id="bf9fd-114">[!code-vb[VbVbcnProcedures #&17;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="bf9fd-114">[!code-vb[VbVbcnProcedures#17](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_1.vb)]</span></span>  
  
### <a name="to-call-a-default-property"></a><span data-ttu-id="bf9fd-115">기본 속성을 호출 하려면</span><span class="sxs-lookup"><span data-stu-id="bf9fd-115">To call a default property</span></span>  
  
1.  <span data-ttu-id="bf9fd-116">포함 하는 클래스 또는 구조체 형식의 변수를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf9fd-116">Declare a variable of the containing class or structure type.</span></span>  
  
     <span data-ttu-id="bf9fd-117">[!code-vb[VbVbcnProcedures #&16;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="bf9fd-117">[!code-vb[VbVbcnProcedures#16](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_2.vb)]</span></span>  
  
2.  <span data-ttu-id="bf9fd-118">속성 이름은 일반적으로 포함 위치는 식에 변수 이름만을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf9fd-118">Use the variable name alone in an expression where you would normally include the property name.</span></span>  
  
     <span data-ttu-id="bf9fd-119">[!code-vb[VbVbcnProcedures #&21;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="bf9fd-119">[!code-vb[VbVbcnProcedures#21](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_3.vb)]</span></span>  
  
3.  <span data-ttu-id="bf9fd-120">괄호 안에 인수 목록과 함께 변수 이름을 뒤에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf9fd-120">Follow the variable name with an argument list in parentheses.</span></span> <span data-ttu-id="bf9fd-121">기본 속성을 하나 이상의 인수를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf9fd-121">A default property must take at least one argument.</span></span>  
  
     <span data-ttu-id="bf9fd-122">[!code-vb[VbVbcnProcedures #&20;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="bf9fd-122">[!code-vb[VbVbcnProcedures#20](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_4.vb)]</span></span>  
  
4.  <span data-ttu-id="bf9fd-123">기본 속성 값을 검색 하려면 변수 이름으로 인수 목록과 식에서 또는 등호 다음 함께 사용 하 여 (`=`) 대입문에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf9fd-123">To retrieve the default property value, use the variable name, with an argument list, in an expression or following the equal (`=`) sign in an assignment statement.</span></span>  
  
     <span data-ttu-id="bf9fd-124">[!code-vb[VbVbcnProcedures #&15;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="bf9fd-124">[!code-vb[VbVbcnProcedures#15](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_5.vb)]</span></span>  
  
5.  <span data-ttu-id="bf9fd-125">기본 속성 값을 설정 하려면 대입문의 왼쪽에는 인수 목록을 가진 변수 이름으로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf9fd-125">To set the default property value, use the variable name, with an argument list, on the left side of an assignment statement.</span></span>  
  
     <span data-ttu-id="bf9fd-126">[!code-vb[VbVbcnProcedures #&14;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="bf9fd-126">[!code-vb[VbVbcnProcedures#14](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_6.vb)]</span></span>  
  
6.  <span data-ttu-id="bf9fd-127">방금와 같은 다른 속성에 액세스 하려면 항상 기본 속성 이름은 변수 이름과 함께 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf9fd-127">You can always specify the default property name together with the variable name, just as you would do to access any other property.</span></span>  
  
     <span data-ttu-id="bf9fd-128">[!code-vb[VbVbcnProcedures #&19;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="bf9fd-128">[!code-vb[VbVbcnProcedures#19](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_7.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="bf9fd-129">예제</span><span class="sxs-lookup"><span data-stu-id="bf9fd-129">Example</span></span>  
 <span data-ttu-id="bf9fd-130">다음 예제에서는 클래스에는 기본 속성을 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="bf9fd-130">The following example declares a default property on a class.</span></span>  
  
 <span data-ttu-id="bf9fd-131">[!code-vb[VbVbcnProcedures #&12;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_8.vb)]</span><span class="sxs-lookup"><span data-stu-id="bf9fd-131">[!code-vb[VbVbcnProcedures#12](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_8.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="bf9fd-132">예제</span><span class="sxs-lookup"><span data-stu-id="bf9fd-132">Example</span></span>  
 <span data-ttu-id="bf9fd-133">다음 예제에서는 기본 속성을 호출 하는 방법을 `myProperty` 클래스에 `class1`합니다.</span><span class="sxs-lookup"><span data-stu-id="bf9fd-133">The following example demonstrates how to call the default property `myProperty` on class `class1`.</span></span> <span data-ttu-id="bf9fd-134">값을 저장 하는 세 개의 대입문 `myProperty`, 및 <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>통화 값을 읽습니다.</xref:Microsoft.VisualBasic.Interaction.MsgBox%2A></span><span class="sxs-lookup"><span data-stu-id="bf9fd-134">The three assignment statements store values in `myProperty`, and the <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> call reads the values.</span></span>  
  
 <span data-ttu-id="bf9fd-135">[!code-vb[VbVbcnProcedures #&13;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_9.vb)]</span><span class="sxs-lookup"><span data-stu-id="bf9fd-135">[!code-vb[VbVbcnProcedures#13](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_9.vb)]</span></span>  
  
 <span data-ttu-id="bf9fd-136">기본 속성의 가장 일반적인 사용은는 <xref:Microsoft.VisualBasic.Collection.Item%2A>다양 한 컬렉션 클래스에는 속성입니다.</xref:Microsoft.VisualBasic.Collection.Item%2A></span><span class="sxs-lookup"><span data-stu-id="bf9fd-136">The most common use of a default property is the <xref:Microsoft.VisualBasic.Collection.Item%2A> property on various collection classes.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="bf9fd-137">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="bf9fd-137">Robust Programming</span></span>  
 <span data-ttu-id="bf9fd-138">기본 속성 소스 코드의 문자를 약간 저하 될 수 있지만 코드를 읽을 수 더 어렵게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf9fd-138">Default properties can result in a small reduction in source code-characters, but they can make your code more difficult to read.</span></span> <span data-ttu-id="bf9fd-139">클래스 또는 구조체 이름에 대 한 참조를 수행할 때 호출 코드에서 클래스 또는 구조체에 익숙하지 않은 경우 수 없습니다 특정 참조 하는 클래스 또는 구조체 자체를 기본 속성에 액세스 하는지 여부.</span><span class="sxs-lookup"><span data-stu-id="bf9fd-139">If the calling code is not familiar with your class or structure, when it makes a reference to the class or structure name it cannot be certain whether that reference accesses the class or structure itself, or a default property.</span></span> <span data-ttu-id="bf9fd-140">이 경우 컴파일러 오류 또는 미묘한 런타임 논리 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf9fd-140">This can lead to compiler errors or subtle run-time logic errors.</span></span>  
  
 <span data-ttu-id="bf9fd-141">항상 사용 하 여 기본 속성 오류 가능성을을 다소 줄일 수는 [Option Strict 문](../../../../visual-basic/language-reference/statements/option-strict-statement.md) 컴파일러 형식 검사를 설정 하려면 `On`합니다.</span><span class="sxs-lookup"><span data-stu-id="bf9fd-141">You can somewhat reduce the chance of default property errors by always using the [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) to set compiler type checking to `On`.</span></span>  
  
 <span data-ttu-id="bf9fd-142">에서 사용 하는 미리 정의 된 클래스 또는 구조체에서 코드를 결정 해야 기본 속성이 있는지 여부 그리고 있다면 하고자 한다면 어떤 이름은입니다.</span><span class="sxs-lookup"><span data-stu-id="bf9fd-142">If you are planning to use a predefined class or structure in your code, you must determine whether it has a default property, and if so, what its name is.</span></span>  
  
 <span data-ttu-id="bf9fd-143">이러한 단점 때문에 기본 속성을 정의 하지 않는 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf9fd-143">Because of these disadvantages, you should consider not defining default properties.</span></span> <span data-ttu-id="bf9fd-144">또한 항상 모든 속성에 명시적으로 참조를 고려해 해야 코드 가독성을 기본 속성까지 하세요.</span><span class="sxs-lookup"><span data-stu-id="bf9fd-144">For code readability, you should also consider always referring to all properties explicitly, even default properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf9fd-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bf9fd-145">See Also</span></span>  
 <span data-ttu-id="bf9fd-146">[속성 프로시저](./property-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="bf9fd-146">[Property Procedures](./property-procedures.md) </span></span>  
<span data-ttu-id="bf9fd-147"> [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="bf9fd-147"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="bf9fd-148"> [Property 문](../../../../visual-basic/language-reference/statements/property-statement.md) </span><span class="sxs-lookup"><span data-stu-id="bf9fd-148"> [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md) </span></span>  
<span data-ttu-id="bf9fd-149"> [기본값](../../../../visual-basic/language-reference/modifiers/default.md) </span><span class="sxs-lookup"><span data-stu-id="bf9fd-149"> [Default](../../../../visual-basic/language-reference/modifiers/default.md) </span></span>  
<span data-ttu-id="bf9fd-150"> [Visual Basic에서 속성과 변수의 차이점](./differences-between-properties-and-variables.md) </span><span class="sxs-lookup"><span data-stu-id="bf9fd-150"> [Differences Between Properties and Variables in Visual Basic](./differences-between-properties-and-variables.md) </span></span>  
<span data-ttu-id="bf9fd-151"> [방법: 속성 만들기](./how-to-create-a-property.md) </span><span class="sxs-lookup"><span data-stu-id="bf9fd-151"> [How to: Create a Property](./how-to-create-a-property.md) </span></span>  
<span data-ttu-id="bf9fd-152"> [방법: 액세스 수준이 혼합된 된 속성 선언](./how-to-declare-a-property-with-mixed-access-levels.md) </span><span class="sxs-lookup"><span data-stu-id="bf9fd-152"> [How to: Declare a Property with Mixed Access Levels](./how-to-declare-a-property-with-mixed-access-levels.md) </span></span>  
<span data-ttu-id="bf9fd-153"> [방법: 속성 프로시저 호출](./how-to-call-a-property-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="bf9fd-153"> [How to: Call a Property Procedure](./how-to-call-a-property-procedure.md) </span></span>  
<span data-ttu-id="bf9fd-154"> [방법: 속성 값 입력](./how-to-put-a-value-in-a-property.md) </span><span class="sxs-lookup"><span data-stu-id="bf9fd-154"> [How to: Put a Value in a Property](./how-to-put-a-value-in-a-property.md) </span></span>  
<span data-ttu-id="bf9fd-155"> [방법: 속성에서 값 가져오기](./how-to-get-a-value-from-a-property.md)</span><span class="sxs-lookup"><span data-stu-id="bf9fd-155"> [How to: Get a Value from a Property](./how-to-get-a-value-from-a-property.md)</span></span>
