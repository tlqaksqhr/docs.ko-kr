---
title: '방법: 여러 버전의 프로시저 정의(Visual Basic)'
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
- procedure overloading [Visual Basic], multiple versions
ms.assetid: 71ccdd66-1b00-4b66-bee4-6926c0d696f4
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e6db075e9b31355d4a0a593040b1fe7c96a0c730
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-define-multiple-versions-of-a-procedure-visual-basic"></a><span data-ttu-id="782ef-102">방법: 여러 버전의 프로시저 정의(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="782ef-102">How to: Define Multiple Versions of a Procedure (Visual Basic)</span></span>
<span data-ttu-id="782ef-103">여러 버전으로 프로시저를 정의할 수 *오버 로드* 이름은 동일 하지만 다른 매개 변수 목록을 사용 하 여 각 버전에 대 한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="782ef-103">You can define a procedure in multiple versions by *overloading* it, using the same name but a different parameter list for each version.</span></span> <span data-ttu-id="782ef-104">오버 로드의 목적은 이름을 다르게 필요 없이 프로시저의 밀접 한 관련이 있는 여러 버전을 정의 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="782ef-104">The purpose of overloading is to define several closely related versions of a procedure without having to differentiate them by name.</span></span>  
  
 <span data-ttu-id="782ef-105">자세한 내용은 참조 [프로시저 오버 로드](./procedure-overloading.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="782ef-105">For more information, see [Procedure Overloading](./procedure-overloading.md).</span></span>  
  
### <a name="to-define-multiple-versions-of-a-procedure"></a><span data-ttu-id="782ef-106">여러 버전의 프로시저를 정의 하려면</span><span class="sxs-lookup"><span data-stu-id="782ef-106">To define multiple versions of a procedure</span></span>  
  
1.  <span data-ttu-id="782ef-107">쓰기는 `Sub` 또는 `Function` 선언문 정의 하려면 프로시저의 각 버전에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="782ef-107">Write a `Sub` or `Function` declaration statement for each version of the procedure you want to define.</span></span> <span data-ttu-id="782ef-108">모든 선언에 이름이 같은 프로시저를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="782ef-108">Use the same procedure name in every declaration.</span></span>  
  
2.  <span data-ttu-id="782ef-109">앞의 `Sub` 또는 `Function` 각 선언에서 키워드는 [오버 로드](../../../../visual-basic/language-reference/modifiers/overloads.md) 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="782ef-109">Precede the `Sub` or `Function` keyword in each declaration with the [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) keyword.</span></span> <span data-ttu-id="782ef-110">선택적으로 생략할 수 `Overloads` 선언 중 하나에 포함 하는 경우를 제외한 선언에 포함 해야 모든 선언에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="782ef-110">You can optionally omit `Overloads` in the declarations, but if you include it in any of the declarations, you must include it in every declaration.</span></span>  
  
3.  <span data-ttu-id="782ef-111">각 선언문 뒤 호출 코드에서 해당 버전의 매개 변수 목록과 일치 하는 인수를 제공 하는 여기서 특정 경우를 처리 하는 프로시저 코드를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="782ef-111">Following each declaration statement, write procedure code to handle the specific case where the calling code supplies arguments matching that version's parameter list.</span></span> <span data-ttu-id="782ef-112">않아도 테스트 하려면 호출 코드에서 제공한 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="782ef-112">You do not have to test for which parameters the calling code has supplied.</span></span> <span data-ttu-id="782ef-113">Visual Basic에서는 프로시저의 짝이 되는 버전 제어를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="782ef-113">Visual Basic passes control to the matching version of your procedure.</span></span>  
  
4.  <span data-ttu-id="782ef-114">사용 하 여 프로시저의 각 버전을 종료는 `End Sub` 또는 `End Function` 문으로 적절 하 게 합니다.</span><span class="sxs-lookup"><span data-stu-id="782ef-114">Terminate each version of the procedure with the `End Sub` or `End Function` statement as appropriate.</span></span>  
  
## <a name="example"></a><span data-ttu-id="782ef-115">예제</span><span class="sxs-lookup"><span data-stu-id="782ef-115">Example</span></span>  
 <span data-ttu-id="782ef-116">다음 예제에서는 정의 `Sub` 고객의 균형에 대 한 트랜잭션을 게시 하는 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="782ef-116">The following example defines a `Sub` procedure to post a transaction against a customer's balance.</span></span> <span data-ttu-id="782ef-117">사용 하 여는 `Overloads` 하나 이름 및 다른 고객 계정 번호를 허용 하는 프로시저의 두 버전을 정의 하는 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="782ef-117">It uses the `Overloads` keyword to define two versions of the procedure, one that accepts the customer by name and the other by account number.</span></span>  
  
 [!code-vb[VbVbcnProcedures#72](./codesnippet/VisualBasic/how-to-define-multiple-versions-of-a-procedure_1.vb)]  
  
 <span data-ttu-id="782ef-118">호출 코드로 고객 id를 가져올 수는 `String` 또는 `Integer`, 다음 두 경우 모두 동일한 호출 문을 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="782ef-118">The calling code can obtain the customer identification as either a `String` or an `Integer`, and then use the same calling statement in either case.</span></span>  
  
 <span data-ttu-id="782ef-119">이러한 버전을 호출 하는 방법에 대 한 내용은 `post` 프로시저 참조 [하는 방법: 오버 로드 된 프로시저 호출](./how-to-call-an-overloaded-procedure.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="782ef-119">For information on how to call these versions of the `post` procedure, see [How to: Call an Overloaded Procedure](./how-to-call-an-overloaded-procedure.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="782ef-120">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="782ef-120">Compiling the Code</span></span>  
 <span data-ttu-id="782ef-121">프로시저 이름은 동일 하지만 다른 매개 변수 목록 각 오버 로드 된 버전에 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="782ef-121">Make sure each of your overloaded versions has the same procedure name but a different parameter list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="782ef-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="782ef-122">See Also</span></span>  
 [<span data-ttu-id="782ef-123">절차</span><span class="sxs-lookup"><span data-stu-id="782ef-123">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="782ef-124">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="782ef-124">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="782ef-125">프로시저 문제 해결</span><span class="sxs-lookup"><span data-stu-id="782ef-125">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)  
 [<span data-ttu-id="782ef-126">방법: 선택적 매개 변수를 사용하는 프로시저 오버로드</span><span class="sxs-lookup"><span data-stu-id="782ef-126">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)  
 [<span data-ttu-id="782ef-127">방법: 매개 변수를 무제한으로 사용하는 프로시저 오버로드</span><span class="sxs-lookup"><span data-stu-id="782ef-127">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)  
 [<span data-ttu-id="782ef-128">프로시저를 오버로드할 때 고려해야 할 사항</span><span class="sxs-lookup"><span data-stu-id="782ef-128">Considerations in Overloading Procedures</span></span>](./considerations-in-overloading-procedures.md)  
 [<span data-ttu-id="782ef-129">오버로드 확인</span><span class="sxs-lookup"><span data-stu-id="782ef-129">Overload Resolution</span></span>](./overload-resolution.md)
