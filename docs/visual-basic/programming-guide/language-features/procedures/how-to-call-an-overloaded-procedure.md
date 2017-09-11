---
title: "방법: 오버 로드 된 프로시저 (Visual Basic)를 호출 합니다. | Microsoft 문서"
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
- procedures, overloading
- procedures, calling
- procedures, multiple versions
- procedure calls, overloaded
ms.assetid: 3bb331fb-f6bc-406f-9ca0-9609b497014c
caps.latest.revision: 12
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
ms.openlocfilehash: 777df0cc81a4e0518773a0e8cc98d590d1c0cf0d
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-call-an-overloaded-procedure-visual-basic"></a><span data-ttu-id="1b6d5-102">방법: 오버로드된 프로시저 호출(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1b6d5-102">How to: Call an Overloaded Procedure (Visual Basic)</span></span>
<span data-ttu-id="1b6d5-103">프로시저 오버 로드의 장점은 호출의 유연성에서입니다.</span><span class="sxs-lookup"><span data-stu-id="1b6d5-103">The advantage of overloading a procedure is in the flexibility of the call.</span></span> <span data-ttu-id="1b6d5-104">호출 코드에서 프로시저에 전달 하는 하나의 프로시저 이름을 전달 하는 인수에 관계 없이 다음 호출 하는 데 필요한 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b6d5-104">The calling code can obtain the information it needs to pass to the procedure and then call a single procedure name, no matter what arguments it is passing.</span></span>  
  
### <a name="to-call-a-procedure-that-has-more-than-one-version-defined"></a><span data-ttu-id="1b6d5-105">둘 이상의 버전이 정의 된 프로시저를 호출 하려면</span><span class="sxs-lookup"><span data-stu-id="1b6d5-105">To call a procedure that has more than one version defined</span></span>  
  
1.  <span data-ttu-id="1b6d5-106">호출 코드에서 프로시저에 전달할 데이터를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b6d5-106">In the calling code, determine which data to pass to the procedure.</span></span>  
  
2.  <span data-ttu-id="1b6d5-107">인수 목록에서 데이터를 표시 합니다. 일반적인 방법으로 프로시저 호출을 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b6d5-107">Write the procedure call in the normal way, presenting the data in the argument list.</span></span> <span data-ttu-id="1b6d5-108">인수에는 프로시저에 대해 정의 된 버전 중 하나에 매개 변수 목록과 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b6d5-108">Be sure the arguments match the parameter list in one of the versions defined for the procedure.</span></span>  
  
3.  <span data-ttu-id="1b6d5-109">호출할 프로시저의 버전을 확인 하 고 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1b6d5-109">You do not have to determine which version of the procedure to call.</span></span> [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="1b6d5-110">인수 목록과 일치 하는 버전으로 제어가 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b6d5-110"> passes control to the version matching your argument list.</span></span>  
  
     <span data-ttu-id="1b6d5-111">다음 예제에서는 `post` 프로시저에서 선언 [하는 방법: 여러 버전의 프로시저 정의](./how-to-define-multiple-versions-of-a-procedure.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1b6d5-111">The following example calls the `post` procedure declared in [How to: Define Multiple Versions of a Procedure](./how-to-define-multiple-versions-of-a-procedure.md).</span></span> <span data-ttu-id="1b6d5-112">고객 id를 받아 인지 확인 한 `String` 또는 `Integer`, 다음 두 경우 모두 같은 프로시저를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b6d5-112">It obtains the customer identification, determines whether it is a `String` or an `Integer`, and then in either case calls the same procedure.</span></span>  
  
     <span data-ttu-id="1b6d5-113">[!code-vb[VbVbcnProcedures #&56;](./codesnippet/VisualBasic/how-to-call-an-overloaded-procedure_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="1b6d5-113">[!code-vb[VbVbcnProcedures#56](./codesnippet/VisualBasic/how-to-call-an-overloaded-procedure_1.vb)]</span></span>  
  
     <span data-ttu-id="1b6d5-114">[!code-vb[VbVbcnProcedures #&57;](./codesnippet/VisualBasic/how-to-call-an-overloaded-procedure_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="1b6d5-114">[!code-vb[VbVbcnProcedures#57](./codesnippet/VisualBasic/how-to-call-an-overloaded-procedure_2.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b6d5-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1b6d5-115">See Also</span></span>  
 <span data-ttu-id="1b6d5-116">[프로시저](./index.md) </span><span class="sxs-lookup"><span data-stu-id="1b6d5-116">[Procedures](./index.md) </span></span>  
<span data-ttu-id="1b6d5-117"> [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="1b6d5-117"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="1b6d5-118"> [프로시저 오버 로드](./procedure-overloading.md) </span><span class="sxs-lookup"><span data-stu-id="1b6d5-118"> [Procedure Overloading](./procedure-overloading.md) </span></span>  
<span data-ttu-id="1b6d5-119"> [문제 해결 절차](./troubleshooting-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="1b6d5-119"> [Troubleshooting Procedures](./troubleshooting-procedures.md) </span></span>  
<span data-ttu-id="1b6d5-120"> [방법: 여러 버전의 프로시저 정의](./how-to-define-multiple-versions-of-a-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="1b6d5-120"> [How to: Define Multiple Versions of a Procedure](./how-to-define-multiple-versions-of-a-procedure.md) </span></span>  
<span data-ttu-id="1b6d5-121"> [방법: 선택적 매개 변수를 사용 하는 프로시저 오버 로드](./how-to-overload-a-procedure-that-takes-optional-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="1b6d5-121"> [How to: Overload a Procedure that Takes Optional Parameters](./how-to-overload-a-procedure-that-takes-optional-parameters.md) </span></span>  
<span data-ttu-id="1b6d5-122"> [방법: 불특정 개수의 매개 변수를 사용 하는 프로시저 오버 로드](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="1b6d5-122"> [How to: Overload a Procedure that Takes an Indefinite Number of Parameters](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md) </span></span>  
<span data-ttu-id="1b6d5-123"> [프로시저 오버 로드에 대 한 고려 사항](./considerations-in-overloading-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="1b6d5-123"> [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md) </span></span>  
<span data-ttu-id="1b6d5-124"> [오버 로드 확인](./overload-resolution.md) </span><span class="sxs-lookup"><span data-stu-id="1b6d5-124"> [Overload Resolution](./overload-resolution.md) </span></span>  
<span data-ttu-id="1b6d5-125"> [오버로드](../../../../visual-basic/language-reference/modifiers/overloads.md)</span><span class="sxs-lookup"><span data-stu-id="1b6d5-125"> [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md)</span></span>
