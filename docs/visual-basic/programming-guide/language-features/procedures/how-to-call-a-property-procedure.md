---
title: "방법: 속성 프로시저 (Visual Basic)를 호출 합니다. | Microsoft 문서"
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
- Visual Basic code, procedures
- Visual Basic code, properties
- procedures, calling
- properties [Visual Basic], property procedures
- procedure calls, property procedures
ms.assetid: 96bc4d74-d9c3-4b7a-954d-58ac8553cd94
caps.latest.revision: 16
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
ms.openlocfilehash: d0d37fc2b7ae1d563a7e9d0a8e75343dd690089b
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-call-a-property-procedure-visual-basic"></a><span data-ttu-id="7b1ac-102">방법: 속성 프로시저 호출(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7b1ac-102">How to: Call a Property Procedure (Visual Basic)</span></span>
<span data-ttu-id="7b1ac-103">속성에 값을 저장 하거나 값을 검색 하는 속성 프로시저를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b1ac-103">You call a property procedure by storing a value in the property or retrieving its value.</span></span> <span data-ttu-id="7b1ac-104">변수에 액세스 같은 방법으로 속성에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b1ac-104">You access a property the same way you access a variable.</span></span>  
  
 <span data-ttu-id="7b1ac-105">속성의 `Set` 프로시저는 값을 저장 하며 `Get` 프로시저는 값을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b1ac-105">The property's `Set` procedure stores a value, and its `Get` procedure retrieves the value.</span></span> <span data-ttu-id="7b1ac-106">그러나 호출 하지 않으면 명시적으로 이러한 프로시저 이름으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b1ac-106">However, you do not explicitly call these procedures by name.</span></span> <span data-ttu-id="7b1ac-107">저장 하거나 변수 값을 검색할 것 처럼 대입문 이나 식에서 속성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b1ac-107">You use the property in an assignment statement or an expression, just as you would store or retrieve the value of a variable.</span></span> [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="7b1ac-108">에서는 속성의 프로시저를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b1ac-108"> makes the calls to the property's procedures.</span></span>  
  
### <a name="to-call-a-propertys-get-procedure"></a><span data-ttu-id="7b1ac-109">속성의 Get 프로시저를 호출 하려면</span><span class="sxs-lookup"><span data-stu-id="7b1ac-109">To call a property's Get procedure</span></span>  
  
1.  <span data-ttu-id="7b1ac-110">변수 이름을 사용할 것 같은 방법으로 식에서 속성 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b1ac-110">Use the property name in an expression the same way you would use a variable name.</span></span> <span data-ttu-id="7b1ac-111">속성을 사용 하 여 어디서 나 변수 또는 상수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b1ac-111">You can use a property anywhere you can use a variable or a constant.</span></span>  
  
     <span data-ttu-id="7b1ac-112">또는</span><span class="sxs-lookup"><span data-stu-id="7b1ac-112">-or-</span></span>  
  
     <span data-ttu-id="7b1ac-113">다음에 오는 속성 이름을 사용 하 여 (`=`) 대입문에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b1ac-113">Use the property name following the equal (`=`) sign in an assignment statement.</span></span>  
  
     <span data-ttu-id="7b1ac-114">다음 예제에서는 값을 읽었습니다는 <xref:Microsoft.VisualBasic.DateAndTime.Now%2A>암시적으로 호출 하는 속성을 해당 `Get` 절차.</xref:Microsoft.VisualBasic.DateAndTime.Now%2A></span><span class="sxs-lookup"><span data-stu-id="7b1ac-114">The following example reads the value of the <xref:Microsoft.VisualBasic.DateAndTime.Now%2A> property, implicitly calling its `Get` procedure.</span></span>  
  
     <span data-ttu-id="7b1ac-115">[!code-vb[VbVbalrDateProperties #&4;](./codesnippet/VisualBasic/how-to-call-a-property-procedure_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="7b1ac-115">[!code-vb[VbVbalrDateProperties#4](./codesnippet/VisualBasic/how-to-call-a-property-procedure_1.vb)]</span></span>  
  
2.  <span data-ttu-id="7b1ac-116">인수를 사용 하는 속성을 괄호로 묶어 인수 목록 속성 이름 뒤에.</span><span class="sxs-lookup"><span data-stu-id="7b1ac-116">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="7b1ac-117">필요에 따라 인수가 있을 경우 괄호를 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b1ac-117">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3.  <span data-ttu-id="7b1ac-118">인수를 괄호로 묶고 쉼표로 구분 된 인수 목록에 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b1ac-118">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="7b1ac-119">속성은 해당 매개 변수를 정의 하는 동일한 순서 대로 인수를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b1ac-119">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
 <span data-ttu-id="7b1ac-120">변수 처럼 식에 참여 하는 속성의 값 또는 상수 또는 변수 또는 대입문의 왼쪽에는 속성에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b1ac-120">The value of the property participates in the expression just as a variable or constant would, or it is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
### <a name="to-call-a-propertys-set-procedure"></a><span data-ttu-id="7b1ac-121">호출 하는 속성의 Set 프로시저</span><span class="sxs-lookup"><span data-stu-id="7b1ac-121">To call a property's Set procedure</span></span>  
  
1.  <span data-ttu-id="7b1ac-122">대입문의 왼쪽에 속성 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b1ac-122">Use the property name on the left side of an assignment statement.</span></span>  
  
     <span data-ttu-id="7b1ac-123">값을 설정 하는 다음 예제는 <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A>속성을 암시적으로 호출 된 `Set` 절차.</xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A></span><span class="sxs-lookup"><span data-stu-id="7b1ac-123">The following example sets the value of the <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A> property, implicitly calling the `Set` procedure.</span></span>  
  
     <span data-ttu-id="7b1ac-124">[!code-vb[VbVbcnProcedures #&11;](./codesnippet/VisualBasic/how-to-call-a-property-procedure_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="7b1ac-124">[!code-vb[VbVbcnProcedures#11](./codesnippet/VisualBasic/how-to-call-a-property-procedure_2.vb)]</span></span>  
  
2.  <span data-ttu-id="7b1ac-125">인수를 사용 하는 속성을 괄호로 묶어 인수 목록 속성 이름 뒤에.</span><span class="sxs-lookup"><span data-stu-id="7b1ac-125">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="7b1ac-126">필요에 따라 인수가 있을 경우 괄호를 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b1ac-126">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3.  <span data-ttu-id="7b1ac-127">인수를 괄호로 묶고 쉼표로 구분 된 인수 목록에 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b1ac-127">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="7b1ac-128">속성은 해당 매개 변수를 정의 하는 동일한 순서 대로 인수를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b1ac-128">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
 <span data-ttu-id="7b1ac-129">대입문의 오른쪽에 생성 된 값은 속성에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b1ac-129">The value generated on the right side of the assignment statement is stored in the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b1ac-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7b1ac-130">See Also</span></span>  
 <span data-ttu-id="7b1ac-131">[속성 프로시저](./property-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="7b1ac-131">[Property Procedures](./property-procedures.md) </span></span>  
<span data-ttu-id="7b1ac-132"> [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="7b1ac-132"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="7b1ac-133"> [Property 문](../../../../visual-basic/language-reference/statements/property-statement.md) </span><span class="sxs-lookup"><span data-stu-id="7b1ac-133"> [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md) </span></span>  
<span data-ttu-id="7b1ac-134"> [Visual Basic에서 속성과 변수의 차이점](./differences-between-properties-and-variables.md) </span><span class="sxs-lookup"><span data-stu-id="7b1ac-134"> [Differences Between Properties and Variables in Visual Basic](./differences-between-properties-and-variables.md) </span></span>  
<span data-ttu-id="7b1ac-135"> [방법: 속성 만들기](./how-to-create-a-property.md) </span><span class="sxs-lookup"><span data-stu-id="7b1ac-135"> [How to: Create a Property](./how-to-create-a-property.md) </span></span>  
<span data-ttu-id="7b1ac-136"> [방법: 액세스 수준이 혼합된 된 속성 선언](./how-to-declare-a-property-with-mixed-access-levels.md) </span><span class="sxs-lookup"><span data-stu-id="7b1ac-136"> [How to: Declare a Property with Mixed Access Levels](./how-to-declare-a-property-with-mixed-access-levels.md) </span></span>  
<span data-ttu-id="7b1ac-137"> [방법: 선언 하 고 Visual Basic의 기본 속성 호출](./how-to-declare-and-call-a-default-property.md) </span><span class="sxs-lookup"><span data-stu-id="7b1ac-137"> [How to: Declare and Call a Default Property in Visual Basic](./how-to-declare-and-call-a-default-property.md) </span></span>  
<span data-ttu-id="7b1ac-138"> [방법: 속성 값 입력](./how-to-put-a-value-in-a-property.md) </span><span class="sxs-lookup"><span data-stu-id="7b1ac-138"> [How to: Put a Value in a Property](./how-to-put-a-value-in-a-property.md) </span></span>  
<span data-ttu-id="7b1ac-139"> [방법: 속성에서 값 가져오기](./how-to-get-a-value-from-a-property.md) </span><span class="sxs-lookup"><span data-stu-id="7b1ac-139"> [How to: Get a Value from a Property](./how-to-get-a-value-from-a-property.md) </span></span>  
<span data-ttu-id="7b1ac-140"> [Get 문](../../../../visual-basic/language-reference/statements/get-statement.md) </span><span class="sxs-lookup"><span data-stu-id="7b1ac-140"> [Get Statement](../../../../visual-basic/language-reference/statements/get-statement.md) </span></span>  
<span data-ttu-id="7b1ac-141"> [Set 문](../../../../visual-basic/language-reference/statements/set-statement.md)</span><span class="sxs-lookup"><span data-stu-id="7b1ac-141"> [Set Statement](../../../../visual-basic/language-reference/statements/set-statement.md)</span></span>
