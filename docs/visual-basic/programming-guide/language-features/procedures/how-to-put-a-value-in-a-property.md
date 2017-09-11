---
title: "방법: 속성 (Visual Basic) 값을 입력 | Microsoft 문서"
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
ms.assetid: c39401e5-b5fc-4439-8f31-ed640f7ce6ed
caps.latest.revision: 13
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
ms.openlocfilehash: c838141a27c30b11765d30ae8b0c19bccc929f4b
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-put-a-value-in-a-property-visual-basic"></a><span data-ttu-id="e57f7-102">방법: 속성 값 입력(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e57f7-102">How to: Put a Value in a Property (Visual Basic)</span></span>
<span data-ttu-id="e57f7-103">대입문의 왼쪽에 속성 이름을 입력 하 여 속성에 값을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="e57f7-103">You store a value in a property by putting the property name on the left side of an assignment statement.</span></span>  
  
 <span data-ttu-id="e57f7-104">속성의 `Set` 프로시저는 값을 저장 하지만 호출 하지 않으면 명시적으로 그 이름으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="e57f7-104">The property's `Set` procedure stores a value, but you do not explicitly call it by name.</span></span> <span data-ttu-id="e57f7-105">변수를 사용할 때와 마찬가지로 속성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e57f7-105">You use the property just as you would use a variable.</span></span> [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="e57f7-106">에서는 속성의 프로시저를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="e57f7-106"> makes the calls to the property's procedures.</span></span>  
  
### <a name="to-store-a-value-in-a-property"></a><span data-ttu-id="e57f7-107">속성의 값을 저장 하는</span><span class="sxs-lookup"><span data-stu-id="e57f7-107">To store a value in a property</span></span>  
  
1.  <span data-ttu-id="e57f7-108">대입문의 왼쪽에 속성 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e57f7-108">Use the property name on the left side of an assignment statement.</span></span>  
  
     <span data-ttu-id="e57f7-109">값을 설정 하는 다음 예제는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] `TimeOfDay` 속성 정오에을 암시적으로 호출 해당 `Set` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="e57f7-109">The following example sets the value of the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] `TimeOfDay` property to noon, implicitly calling its `Set` procedure.</span></span>  
  
     <span data-ttu-id="e57f7-110">[!code-vb[VbVbcnProcedures #&11;](./codesnippet/VisualBasic/how-to-put-a-value-in-a-property_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="e57f7-110">[!code-vb[VbVbcnProcedures#11](./codesnippet/VisualBasic/how-to-put-a-value-in-a-property_1.vb)]</span></span>  
  
2.  <span data-ttu-id="e57f7-111">인수를 사용 하는 속성을 괄호로 묶어 인수 목록 속성 이름 뒤에.</span><span class="sxs-lookup"><span data-stu-id="e57f7-111">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="e57f7-112">필요에 따라 인수가 있을 경우 괄호를 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e57f7-112">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3.  <span data-ttu-id="e57f7-113">인수를 괄호로 묶고 쉼표로 구분 된 인수 목록에 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="e57f7-113">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="e57f7-114">속성은 해당 매개 변수를 정의 하는 동일한 순서 대로 인수를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e57f7-114">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
4.  <span data-ttu-id="e57f7-115">대입문의 오른쪽에 생성 된 값은 속성에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e57f7-115">The value generated on the right side of the assignment statement is stored in the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e57f7-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e57f7-116">See Also</span></span>  
 <span data-ttu-id="e57f7-117"><xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A></xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A></span><span class="sxs-lookup"><span data-stu-id="e57f7-117"><xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A></span></span>   
<span data-ttu-id="e57f7-118"> [속성 프로시저](./property-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="e57f7-118"> [Property Procedures](./property-procedures.md) </span></span>  
<span data-ttu-id="e57f7-119"> [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="e57f7-119"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="e57f7-120"> [Property 문](../../../../visual-basic/language-reference/statements/property-statement.md) </span><span class="sxs-lookup"><span data-stu-id="e57f7-120"> [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md) </span></span>  
<span data-ttu-id="e57f7-121"> [Visual Basic에서 속성과 변수의 차이점](./differences-between-properties-and-variables.md) </span><span class="sxs-lookup"><span data-stu-id="e57f7-121"> [Differences Between Properties and Variables in Visual Basic](./differences-between-properties-and-variables.md) </span></span>  
<span data-ttu-id="e57f7-122"> [방법: 속성 만들기](./how-to-create-a-property.md) </span><span class="sxs-lookup"><span data-stu-id="e57f7-122"> [How to: Create a Property](./how-to-create-a-property.md) </span></span>  
<span data-ttu-id="e57f7-123"> [방법: 액세스 수준이 혼합된 된 속성 선언](./how-to-declare-a-property-with-mixed-access-levels.md) </span><span class="sxs-lookup"><span data-stu-id="e57f7-123"> [How to: Declare a Property with Mixed Access Levels](./how-to-declare-a-property-with-mixed-access-levels.md) </span></span>  
<span data-ttu-id="e57f7-124"> [방법: 속성 프로시저 호출](./how-to-call-a-property-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="e57f7-124"> [How to: Call a Property Procedure](./how-to-call-a-property-procedure.md) </span></span>  
<span data-ttu-id="e57f7-125"> [방법: 선언 하 고 Visual Basic의 기본 속성 호출](./how-to-declare-and-call-a-default-property.md) </span><span class="sxs-lookup"><span data-stu-id="e57f7-125"> [How to: Declare and Call a Default Property in Visual Basic](./how-to-declare-and-call-a-default-property.md) </span></span>  
<span data-ttu-id="e57f7-126"> [방법: 속성에서 값 가져오기](./how-to-get-a-value-from-a-property.md)</span><span class="sxs-lookup"><span data-stu-id="e57f7-126"> [How to: Get a Value from a Property](./how-to-get-a-value-from-a-property.md)</span></span>
