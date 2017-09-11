---
title: "방법: 값 (Visual Basic)를 반환 하지 않는 프로시저 호출 | Microsoft 문서"
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
- procedure calls, returning values
- Visual Basic code, procedures
- procedures, calling
ms.assetid: 259b49a3-a3c1-4254-ba8c-73cdc4127703
caps.latest.revision: 17
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
ms.openlocfilehash: 26120b763d2ecedb3aa43adb08e4c87c2b1e0be1
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-call-a-procedure-that-does-not-return-a-value-visual-basic"></a><span data-ttu-id="1302a-102">방법: 값을 반환하지 않는 프로시저 호출(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1302a-102">How to: Call a Procedure that Does Not Return a Value (Visual Basic)</span></span>
<span data-ttu-id="1302a-103">A `Sub` 프로시저 호출 코드에 값을 반환 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1302a-103">A `Sub` procedure does not return a value to the calling code.</span></span> <span data-ttu-id="1302a-104">이 명시적으로 호출 독립 실행형 호출 문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1302a-104">You call it explicitly with a stand-alone calling statement.</span></span> <span data-ttu-id="1302a-105">식 내에서 프로시저 이름을 사용 하 여 호출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1302a-105">You cannot call it by simply using its name within an expression.</span></span>  
  
### <a name="to-call-a-sub-procedure"></a><span data-ttu-id="1302a-106">Sub 프로시저를 호출 하려면</span><span class="sxs-lookup"><span data-stu-id="1302a-106">To call a Sub procedure</span></span>  
  
1.  <span data-ttu-id="1302a-107">이름을 지정는 `Sub` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="1302a-107">Specify the name of the `Sub` procedure.</span></span>  
  
2.  <span data-ttu-id="1302a-108">괄호로 묶어 인수 목록 프로시저 이름 뒤에.</span><span class="sxs-lookup"><span data-stu-id="1302a-108">Follow the procedure name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="1302a-109">필요에 따라 인수가 있을 경우 괄호를 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1302a-109">If there are no arguments, you can optionally omit the parentheses.</span></span> <span data-ttu-id="1302a-110">그러나 괄호를 사용 하는 코드를 읽기 쉽게.</span><span class="sxs-lookup"><span data-stu-id="1302a-110">However, using the parentheses makes your code easier to read.</span></span>  
  
3.  <span data-ttu-id="1302a-111">인수를 괄호로 묶고 쉼표로 구분 된 인수 목록에 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="1302a-111">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="1302a-112">같은 순서로 인수를 지정 해야 하는 `Sub` 프로시저는 해당 매개 변수를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="1302a-112">Be sure you supply the arguments in the same order that the `Sub` procedure defines the corresponding parameters.</span></span>  
  
     <span data-ttu-id="1302a-113">다음 예제에서는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A>응용 프로그램 창을 활성화 하는 함수입니다.</xref:Microsoft.VisualBasic.Interaction.AppActivate%2A></span><span class="sxs-lookup"><span data-stu-id="1302a-113">The following example calls the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> function to activate an application window.</span></span> <span data-ttu-id="1302a-114"><xref:Microsoft.VisualBasic.Interaction.AppActivate%2A>창 제목 유일한 인수로 사용합니다.</xref:Microsoft.VisualBasic.Interaction.AppActivate%2A></span><span class="sxs-lookup"><span data-stu-id="1302a-114"><xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> takes the window title as its sole argument.</span></span> <span data-ttu-id="1302a-115">호출 코드에는 값을 반환 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1302a-115">It does not return a value to the calling code.</span></span> <span data-ttu-id="1302a-116">예제에서는 throw <xref:System.ArgumentException>.</xref:System.ArgumentException> 메모장 프로세스를 실행 하지 않는 경우</span><span class="sxs-lookup"><span data-stu-id="1302a-116">If a Notepad process is not running, the example throws an <xref:System.ArgumentException>.</span></span> <span data-ttu-id="1302a-117">`Shell` 절차에서는 응용 프로그램을 지정 된 경로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1302a-117">The `Shell` procedure assumes the applications are in the paths specified.</span></span>  
  
     <span data-ttu-id="1302a-118">[!code-vb[VbVbalrCatRef #&11;](./codesnippet/VisualBasic/how-to-call-a-procedure-that-does-not-return-a-value_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="1302a-118">[!code-vb[VbVbalrCatRef#11](./codesnippet/VisualBasic/how-to-call-a-procedure-that-does-not-return-a-value_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1302a-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1302a-119">See Also</span></span>  
 <span data-ttu-id="1302a-120"><xref:Microsoft.VisualBasic.Interaction.Shell%2A></xref:Microsoft.VisualBasic.Interaction.Shell%2A></span><span class="sxs-lookup"><span data-stu-id="1302a-120"><xref:Microsoft.VisualBasic.Interaction.Shell%2A></span></span>   
 <span data-ttu-id="1302a-121"><xref:System.ArgumentException></xref:System.ArgumentException></span><span class="sxs-lookup"><span data-stu-id="1302a-121"><xref:System.ArgumentException></span></span>   
<span data-ttu-id="1302a-122"> [프로시저](./index.md) </span><span class="sxs-lookup"><span data-stu-id="1302a-122"> [Procedures](./index.md) </span></span>  
<span data-ttu-id="1302a-123"> [Sub 프로시저](./sub-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="1302a-123"> [Sub Procedures](./sub-procedures.md) </span></span>  
<span data-ttu-id="1302a-124"> [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="1302a-124"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="1302a-125"> [Sub 문](../../../../visual-basic/language-reference/statements/sub-statement.md) </span><span class="sxs-lookup"><span data-stu-id="1302a-125"> [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md) </span></span>  
<span data-ttu-id="1302a-126"> [방법: 프로시저 만들기](./how-to-create-a-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="1302a-126"> [How to: Create a Procedure](./how-to-create-a-procedure.md) </span></span>  
<span data-ttu-id="1302a-127"> [방법: 값을 반환 하는 프로시저 호출](./how-to-call-a-procedure-that-returns-a-value.md) </span><span class="sxs-lookup"><span data-stu-id="1302a-127"> [How to: Call a Procedure That Returns a Value](./how-to-call-a-procedure-that-returns-a-value.md) </span></span>  
<span data-ttu-id="1302a-128"> [방법: Visual Basic에서 이벤트 처리기 호출](./how-to-call-an-event-handler.md)</span><span class="sxs-lookup"><span data-stu-id="1302a-128"> [How to: Call an Event Handler in Visual Basic](./how-to-call-an-event-handler.md)</span></span>
