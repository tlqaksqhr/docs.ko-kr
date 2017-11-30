---
title: "방법: 오버로드된 프로시저 호출(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], overloading
- procedures [Visual Basic], calling
- procedures [Visual Basic], multiple versions
- procedure calls [Visual Basic], overloaded
ms.assetid: 3bb331fb-f6bc-406f-9ca0-9609b497014c
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ff5967c1b09ad59f249297b1cf0a4ed900faf4a1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-call-an-overloaded-procedure-visual-basic"></a><span data-ttu-id="95221-102">방법: 오버로드된 프로시저 호출(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="95221-102">How to: Call an Overloaded Procedure (Visual Basic)</span></span>
<span data-ttu-id="95221-103">프로시저 오버 로드의 장점은 호출의 유연성에서입니다.</span><span class="sxs-lookup"><span data-stu-id="95221-103">The advantage of overloading a procedure is in the flexibility of the call.</span></span> <span data-ttu-id="95221-104">호출 코드 프로시저에 전달 하 고 전달 하는 인수에 관계 없이 하나의 프로시저 이름을 호출 하는 데 필요한 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95221-104">The calling code can obtain the information it needs to pass to the procedure and then call a single procedure name, no matter what arguments it is passing.</span></span>  
  
### <a name="to-call-a-procedure-that-has-more-than-one-version-defined"></a><span data-ttu-id="95221-105">정의 된 버전이 둘 이상 있는 프로시저를 호출 하려면</span><span class="sxs-lookup"><span data-stu-id="95221-105">To call a procedure that has more than one version defined</span></span>  
  
1.  <span data-ttu-id="95221-106">호출 코드에서 프로시저에 전달할 데이터를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="95221-106">In the calling code, determine which data to pass to the procedure.</span></span>  
  
2.  <span data-ttu-id="95221-107">인수 목록에 데이터를 제공 하 여 정상적인 방식에서 프로시저 호출을 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="95221-107">Write the procedure call in the normal way, presenting the data in the argument list.</span></span> <span data-ttu-id="95221-108">인수는 프로시저에 정의 된 버전 중 하나에 매개 변수 목록과 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="95221-108">Be sure the arguments match the parameter list in one of the versions defined for the procedure.</span></span>  
  
3.  <span data-ttu-id="95221-109">호출할 프로시저의 버전을 결정 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="95221-109">You do not have to determine which version of the procedure to call.</span></span> [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="95221-110">인수 목록과 일치 하는 버전으로 제어가 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="95221-110"> passes control to the version matching your argument list.</span></span>  
  
     <span data-ttu-id="95221-111">다음 예제에서는 `post` 에 선언 된 프로시저 [하는 방법: 여러 버전의 프로시저 정의](./how-to-define-multiple-versions-of-a-procedure.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="95221-111">The following example calls the `post` procedure declared in [How to: Define Multiple Versions of a Procedure](./how-to-define-multiple-versions-of-a-procedure.md).</span></span> <span data-ttu-id="95221-112">고객 id를 받아 인지 확인 한 `String` 또는 `Integer`, 한 다음 두 경우 모두 같은 프로시저를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="95221-112">It obtains the customer identification, determines whether it is a `String` or an `Integer`, and then in either case calls the same procedure.</span></span>  
  
     [!code-vb[VbVbcnProcedures#56](./codesnippet/VisualBasic/how-to-call-an-overloaded-procedure_1.vb)]  
  
     [!code-vb[VbVbcnProcedures#57](./codesnippet/VisualBasic/how-to-call-an-overloaded-procedure_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="95221-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="95221-113">See Also</span></span>  
 [<span data-ttu-id="95221-114">절차</span><span class="sxs-lookup"><span data-stu-id="95221-114">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="95221-115">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="95221-115">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="95221-116">프로시저 오버로딩</span><span class="sxs-lookup"><span data-stu-id="95221-116">Procedure Overloading</span></span>](./procedure-overloading.md)  
 [<span data-ttu-id="95221-117">프로시저 문제 해결</span><span class="sxs-lookup"><span data-stu-id="95221-117">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)  
 [<span data-ttu-id="95221-118">방법: 여러 버전의 프로시저 정의</span><span class="sxs-lookup"><span data-stu-id="95221-118">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)  
 [<span data-ttu-id="95221-119">방법: 선택적 매개 변수를 사용하는 프로시저 오버로드</span><span class="sxs-lookup"><span data-stu-id="95221-119">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)  
 [<span data-ttu-id="95221-120">방법: 매개 변수를 무제한으로 사용하는 프로시저 오버로드</span><span class="sxs-lookup"><span data-stu-id="95221-120">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)  
 [<span data-ttu-id="95221-121">프로시저를 오버로드할 때 고려해야 할 사항</span><span class="sxs-lookup"><span data-stu-id="95221-121">Considerations in Overloading Procedures</span></span>](./considerations-in-overloading-procedures.md)  
 [<span data-ttu-id="95221-122">오버로드 확인</span><span class="sxs-lookup"><span data-stu-id="95221-122">Overload Resolution</span></span>](./overload-resolution.md)  
 [<span data-ttu-id="95221-123">오버로드</span><span class="sxs-lookup"><span data-stu-id="95221-123">Overloads</span></span>](../../../../visual-basic/language-reference/modifiers/overloads.md)
