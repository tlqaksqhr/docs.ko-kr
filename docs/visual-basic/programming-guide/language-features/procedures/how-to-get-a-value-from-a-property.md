---
title: "방법: 속성 (Visual Basic)에서 값 가져오기 | Microsoft 문서"
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
- property values
- Visual Basic code, procedures
- values, properties
- Visual Basic code, properties
- properties [Visual Basic], values
ms.assetid: 3954423e-6ab7-4a4c-b55c-a8d27be47891
caps.latest.revision: 11
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
ms.openlocfilehash: 719a4fc9ff163fb4437ea40c8265a5e36232347e
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-get-a-value-from-a-property-visual-basic"></a><span data-ttu-id="7f892-102">방법: 속성에서 값 가져오기(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7f892-102">How to: Get a Value from a Property (Visual Basic)</span></span>
<span data-ttu-id="7f892-103">식에서 속성 이름을 포함 하 여 속성의 값을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f892-103">You retrieve a property's value by including the property name in an expression.</span></span>  
  
 <span data-ttu-id="7f892-104">속성의 `Get` 프로시저는 값을 검색 하지만 호출 하지 않으면 명시적으로 그 이름으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f892-104">The property's `Get` procedure retrieves the value, but you do not explicitly call it by name.</span></span> <span data-ttu-id="7f892-105">변수를 사용할 때와 마찬가지로 속성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f892-105">You use the property just as you would use a variable.</span></span> [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="7f892-106">에서는 속성의 프로시저를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f892-106"> makes the calls to the property's procedures.</span></span>  
  
### <a name="to-retrieve-a-value-from-a-property"></a><span data-ttu-id="7f892-107">속성에서 값을 검색 하려면</span><span class="sxs-lookup"><span data-stu-id="7f892-107">To retrieve a value from a property</span></span>  
  
1.  <span data-ttu-id="7f892-108">변수 이름을 사용할 것 같은 방법으로 식에서 속성 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f892-108">Use the property name in an expression the same way you would use a variable name.</span></span> <span data-ttu-id="7f892-109">속성을 사용 하 여 어디서 나 변수 또는 상수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f892-109">You can use a property anywhere you can use a variable or a constant.</span></span>  
  
     <span data-ttu-id="7f892-110">또는</span><span class="sxs-lookup"><span data-stu-id="7f892-110">-or-</span></span>  
  
     <span data-ttu-id="7f892-111">다음에 오는 속성 이름을 사용 하 여 (`=`) 대입문에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f892-111">Use the property name following the equal (`=`) sign in an assignment statement.</span></span>  
  
     <span data-ttu-id="7f892-112">다음 예제에서는 값을 읽었습니다는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] `Now` 암시적으로 호출 하는 속성을 해당 `Get` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="7f892-112">The following example reads the value of the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] `Now` property, implicitly calling its `Get` procedure.</span></span>  
  
     <span data-ttu-id="7f892-113">[!code-vb[VbVbalrDateProperties #&4;](./codesnippet/VisualBasic/how-to-get-a-value-from-a-property_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="7f892-113">[!code-vb[VbVbalrDateProperties#4](./codesnippet/VisualBasic/how-to-get-a-value-from-a-property_1.vb)]</span></span>  
  
2.  <span data-ttu-id="7f892-114">인수를 사용 하는 속성을 괄호로 묶어 인수 목록 속성 이름 뒤에.</span><span class="sxs-lookup"><span data-stu-id="7f892-114">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="7f892-115">필요에 따라 인수가 있을 경우 괄호를 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f892-115">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3.  <span data-ttu-id="7f892-116">인수를 괄호로 묶고 쉼표로 구분 된 인수 목록에 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f892-116">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="7f892-117">속성은 해당 매개 변수를 정의 하는 동일한 순서 대로 인수를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f892-117">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
 <span data-ttu-id="7f892-118">변수 처럼 식에 참여 하는 속성의 값 또는 상수 또는 변수 또는 대입문의 왼쪽에는 속성에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f892-118">The value of the property participates in the expression just as a variable or constant would, or it is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f892-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7f892-119">See Also</span></span>  
 <span data-ttu-id="7f892-120">[프로시저](./index.md) </span><span class="sxs-lookup"><span data-stu-id="7f892-120">[Procedures](./index.md) </span></span>  
<span data-ttu-id="7f892-121"> [속성 프로시저](./property-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="7f892-121"> [Property Procedures](./property-procedures.md) </span></span>  
<span data-ttu-id="7f892-122"> [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="7f892-122"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="7f892-123"> [Property 문](../../../../visual-basic/language-reference/statements/property-statement.md) </span><span class="sxs-lookup"><span data-stu-id="7f892-123"> [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md) </span></span>  
<span data-ttu-id="7f892-124"> [Visual Basic에서 속성과 변수의 차이점](./differences-between-properties-and-variables.md) </span><span class="sxs-lookup"><span data-stu-id="7f892-124"> [Differences Between Properties and Variables in Visual Basic](./differences-between-properties-and-variables.md) </span></span>  
<span data-ttu-id="7f892-125"> [방법: 속성 만들기](./how-to-create-a-property.md) </span><span class="sxs-lookup"><span data-stu-id="7f892-125"> [How to: Create a Property](./how-to-create-a-property.md) </span></span>  
<span data-ttu-id="7f892-126"> [방법: 액세스 수준이 혼합된 된 속성 선언](./how-to-declare-a-property-with-mixed-access-levels.md) </span><span class="sxs-lookup"><span data-stu-id="7f892-126"> [How to: Declare a Property with Mixed Access Levels](./how-to-declare-a-property-with-mixed-access-levels.md) </span></span>  
<span data-ttu-id="7f892-127"> [방법: 속성 프로시저 호출](./how-to-call-a-property-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="7f892-127"> [How to: Call a Property Procedure](./how-to-call-a-property-procedure.md) </span></span>  
<span data-ttu-id="7f892-128"> [방법: 선언 하 고 Visual Basic의 기본 속성 호출](./how-to-declare-and-call-a-default-property.md) </span><span class="sxs-lookup"><span data-stu-id="7f892-128"> [How to: Declare and Call a Default Property in Visual Basic](./how-to-declare-and-call-a-default-property.md) </span></span>  
<span data-ttu-id="7f892-129"> [방법: 속성 값 입력](./how-to-put-a-value-in-a-property.md)</span><span class="sxs-lookup"><span data-stu-id="7f892-129"> [How to: Put a Value in a Property](./how-to-put-a-value-in-a-property.md)</span></span>
