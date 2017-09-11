---
title: "방법: 여러 버전의 프로시저 (Visual Basic)를 정의 합니다. | Microsoft 문서"
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
- procedures, defining
- Visual Basic code, procedures
- procedures, overloading
- procedures, multiple versions
- procedure overloading, multiple versions
ms.assetid: 71ccdd66-1b00-4b66-bee4-6926c0d696f4
caps.latest.revision: 14
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
ms.openlocfilehash: f4296ba3a78316b70011bcca18f7071716f3c90d
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-define-multiple-versions-of-a-procedure-visual-basic"></a><span data-ttu-id="11a28-102">방법: 여러 버전의 프로시저 정의(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="11a28-102">How to: Define Multiple Versions of a Procedure (Visual Basic)</span></span>
<span data-ttu-id="11a28-103">여러 버전으로 프로시저를 정의할 수 *오버 로드* 이름은 동일 하지만 다른 매개 변수 목록을 사용 하 여 각 버전에 대 한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="11a28-103">You can define a procedure in multiple versions by *overloading* it, using the same name but a different parameter list for each version.</span></span> <span data-ttu-id="11a28-104">오버 로드의 목적은 이름을 다르게 하지 않고 프로시저의 밀접 한 관련이 있는 여러 버전을 정의 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="11a28-104">The purpose of overloading is to define several closely related versions of a procedure without having to differentiate them by name.</span></span>  
  
 <span data-ttu-id="11a28-105">자세한 내용은 참조 [프로시저 오버 로딩](./procedure-overloading.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="11a28-105">For more information, see [Procedure Overloading](./procedure-overloading.md).</span></span>  
  
### <a name="to-define-multiple-versions-of-a-procedure"></a><span data-ttu-id="11a28-106">여러 버전의 프로시저를 정의 하려면</span><span class="sxs-lookup"><span data-stu-id="11a28-106">To define multiple versions of a procedure</span></span>  
  
1.  <span data-ttu-id="11a28-107">쓰기는 `Sub` 또는 `Function` 정의 하려는 프로시저의 각 버전에 대 한 선언문입니다.</span><span class="sxs-lookup"><span data-stu-id="11a28-107">Write a `Sub` or `Function` declaration statement for each version of the procedure you want to define.</span></span> <span data-ttu-id="11a28-108">모든 선언에서 동일한 프로시저 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="11a28-108">Use the same procedure name in every declaration.</span></span>  
  
2.  <span data-ttu-id="11a28-109">앞에 `Sub` 또는 `Function` 각 선언에서 키워드는 [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="11a28-109">Precede the `Sub` or `Function` keyword in each declaration with the [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) keyword.</span></span> <span data-ttu-id="11a28-110">생략 해도 `Overloads` 선언 중 하나에 포함 하는 경우를 제외한 선언에 포함 해야 모든 선언에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11a28-110">You can optionally omit `Overloads` in the declarations, but if you include it in any of the declarations, you must include it in every declaration.</span></span>  
  
3.  <span data-ttu-id="11a28-111">각 선언문 뒤 호출 코드에서 해당 버전의 매개 변수 목록과 일치 하는 인수를 제공 하는 여기서 특정 경우를 처리 하도록 프로시저 코드를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="11a28-111">Following each declaration statement, write procedure code to handle the specific case where the calling code supplies arguments matching that version's parameter list.</span></span> <span data-ttu-id="11a28-112">필요가 없습니다 테스트 하는 매개 변수에 대 한 호출 코드에 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="11a28-112">You do not have to test for which parameters the calling code has supplied.</span></span> [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="11a28-113">에서는 프로시저의 일치 하는 버전으로 제어가 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="11a28-113"> passes control to the matching version of your procedure.</span></span>  
  
4.  <span data-ttu-id="11a28-114">각 버전을 사용 하 여 프로시저의 종료는 `End Sub` 또는 `End Function` 문을 적절 하 게 합니다.</span><span class="sxs-lookup"><span data-stu-id="11a28-114">Terminate each version of the procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
## <a name="example"></a><span data-ttu-id="11a28-115">예제</span><span class="sxs-lookup"><span data-stu-id="11a28-115">Example</span></span>  
 <span data-ttu-id="11a28-116">다음 예제에서는 정의 `Sub` 고객의 잔고에 대 한 트랜잭션을 게시 하는 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="11a28-116">The following example defines a `Sub` procedure to post a transaction against a customer's balance.</span></span> <span data-ttu-id="11a28-117">사용 하 여는 `Overloads` 이름 및 다른 고객 계정 번호를 허용 하는 프로시저의 두 버전을 정의 하는 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="11a28-117">It uses the `Overloads` keyword to define two versions of the procedure, one that accepts the customer by name and the other by account number.</span></span>  
  
 <span data-ttu-id="11a28-118">[!code-vb[VbVbcnProcedures #&72;](./codesnippet/VisualBasic/how-to-define-multiple-versions-of-a-procedure_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="11a28-118">[!code-vb[VbVbcnProcedures#72](./codesnippet/VisualBasic/how-to-define-multiple-versions-of-a-procedure_1.vb)]</span></span>  
  
 <span data-ttu-id="11a28-119">호출 코드로 고객 id를 가져올 수는 `String` 또는 `Integer`, 다음 두 경우 모두 동일한 호출 문을 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="11a28-119">The calling code can obtain the customer identification as either a `String` or an `Integer`, and then use the same calling statement in either case.</span></span>  
  
 <span data-ttu-id="11a28-120">이러한 버전을 호출 하는 방법에 대 한 내용은 `post` 프로시저 참조 [하는 방법: 오버 로드 된 프로시저 호출](./how-to-call-an-overloaded-procedure.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="11a28-120">For information on how to call these versions of the `post` procedure, see [How to: Call an Overloaded Procedure](./how-to-call-an-overloaded-procedure.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="11a28-121">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="11a28-121">Compiling the Code</span></span>  
 <span data-ttu-id="11a28-122">각 오버 로드 된 버전이 프로시저 이름은 동일 하지만 다른 매개 변수 목록에 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="11a28-122">Make sure each of your overloaded versions has the same procedure name but a different parameter list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11a28-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="11a28-123">See Also</span></span>  
 <span data-ttu-id="11a28-124">[프로시저](./index.md) </span><span class="sxs-lookup"><span data-stu-id="11a28-124">[Procedures](./index.md) </span></span>  
<span data-ttu-id="11a28-125"> [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="11a28-125"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="11a28-126"> [문제 해결 절차](./troubleshooting-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="11a28-126"> [Troubleshooting Procedures](./troubleshooting-procedures.md) </span></span>  
<span data-ttu-id="11a28-127"> [방법: 선택적 매개 변수를 사용 하는 프로시저 오버 로드](./how-to-overload-a-procedure-that-takes-optional-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="11a28-127"> [How to: Overload a Procedure that Takes Optional Parameters](./how-to-overload-a-procedure-that-takes-optional-parameters.md) </span></span>  
<span data-ttu-id="11a28-128"> [방법: 불특정 개수의 매개 변수를 사용 하는 프로시저 오버 로드](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="11a28-128"> [How to: Overload a Procedure that Takes an Indefinite Number of Parameters](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md) </span></span>  
<span data-ttu-id="11a28-129"> [프로시저 오버 로드에 대 한 고려 사항](./considerations-in-overloading-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="11a28-129"> [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md) </span></span>  
<span data-ttu-id="11a28-130"> [오버로드 확인](./overload-resolution.md)</span><span class="sxs-lookup"><span data-stu-id="11a28-130"> [Overload Resolution](./overload-resolution.md)</span></span>
