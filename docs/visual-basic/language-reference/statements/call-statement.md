---
title: "Call 문(Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Call
helpviewer_keywords:
- procedures [Visual Basic], Call statement
- Call statement [Visual Basic]
- procedures [Visual Basic], calling
ms.assetid: e5b31571-6867-406f-b8e7-a3f9aae4723a
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c72450fd6f931f36f640d3e384a6fd38d57a7a23
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="call-statement-visual-basic"></a><span data-ttu-id="bdf9d-102">Call 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bdf9d-102">Call Statement (Visual Basic)</span></span>
<span data-ttu-id="bdf9d-103">컨트롤을 전송 하는 `Function`, `Sub`, 또는 동적 연결 라이브러리 (DLL) 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="bdf9d-103">Transfers control to a `Function`, `Sub`, or dynamic-link library (DLL) procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bdf9d-104">구문</span><span class="sxs-lookup"><span data-stu-id="bdf9d-104">Syntax</span></span>  
  
```  
[ Call ] procedureName [ (argumentList) ]  
```  
  
## <a name="parts"></a><span data-ttu-id="bdf9d-105">요소</span><span class="sxs-lookup"><span data-stu-id="bdf9d-105">Parts</span></span>  
 `procedureName`  
 <span data-ttu-id="bdf9d-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="bdf9d-106">Required.</span></span> <span data-ttu-id="bdf9d-107">호출할 프로시저의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="bdf9d-107">Name of the procedure to call.</span></span>  
  
 `argumentList`  
 <span data-ttu-id="bdf9d-108">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="bdf9d-108">Optional.</span></span> <span data-ttu-id="bdf9d-109">변수 또는 호출 될 때 프로시저에 전달 되는 인수를 나타내는 식의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="bdf9d-109">List of variables or expressions representing arguments that are passed to the procedure when it is called.</span></span> <span data-ttu-id="bdf9d-110">인수가 여러 개이면 쉼표로 구분 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bdf9d-110">Multiple arguments are separated by commas.</span></span> <span data-ttu-id="bdf9d-111">포함 하는 경우 `argumentList`를 괄호로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdf9d-111">If you include `argumentList`, you must enclose it in parentheses.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bdf9d-112">설명</span><span class="sxs-lookup"><span data-stu-id="bdf9d-112">Remarks</span></span>  
 <span data-ttu-id="bdf9d-113">사용할 수는 `Call` 키워드 프로시저를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdf9d-113">You can use the `Call` keyword when you call a procedure.</span></span> <span data-ttu-id="bdf9d-114">대부분의 프로시저 호출에 대 한이 키워드를 사용 하도록 요구 하지 않음.</span><span class="sxs-lookup"><span data-stu-id="bdf9d-114">For most procedure calls, you aren’t required to use this  keyword.</span></span>  
  
 <span data-ttu-id="bdf9d-115">일반적으로 사용 된 `Call` 키워드를 식별자로 호출된 식을 시작 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bdf9d-115">You typically use the `Call` keyword when the called expression doesn’t start with an identifier.</span></span> <span data-ttu-id="bdf9d-116">사용은 `Call` 키워드를 다른 곳에 권장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bdf9d-116">Use of the `Call` keyword for other uses isn’t recommended.</span></span>  
  
 <span data-ttu-id="bdf9d-117">프로시저는 값을 반환 하는 경우는 `Call` 문을 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdf9d-117">If the procedure returns a value, the `Call` statement discards it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bdf9d-118">예제</span><span class="sxs-lookup"><span data-stu-id="bdf9d-118">Example</span></span>  
 <span data-ttu-id="bdf9d-119">다음 코드는 두 가지 예를 보여 줍니다. 여기서는 `Call` 키워드는 프로시저를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdf9d-119">The following code shows two examples where the `Call` keyword is necessary to call a procedure.</span></span> <span data-ttu-id="bdf9d-120">두 예제에서는 호출된 식을 식별자 문자로 시작 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bdf9d-120">In both examples, the called expression doesn't start with an identifier.</span></span>  
  
 [!code-vb[VbVbalrStatements#97](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/call-statement_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="bdf9d-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bdf9d-121">See Also</span></span>  
 [<span data-ttu-id="bdf9d-122">Function 문</span><span class="sxs-lookup"><span data-stu-id="bdf9d-122">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
 [<span data-ttu-id="bdf9d-123">Sub 문</span><span class="sxs-lookup"><span data-stu-id="bdf9d-123">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="bdf9d-124">Declare 문</span><span class="sxs-lookup"><span data-stu-id="bdf9d-124">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
 [<span data-ttu-id="bdf9d-125">람다 식</span><span class="sxs-lookup"><span data-stu-id="bdf9d-125">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
