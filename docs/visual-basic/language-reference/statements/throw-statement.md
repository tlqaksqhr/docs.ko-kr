---
title: Throw 문(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Throw
helpviewer_keywords:
- structured exception handling, throw statements
- try-catch exception handling, throw statements
- throw statement [Visual Basic], about throw statements
- throwing exceptions, throw statement
- exception handling, throw statement
- On Error statement [Visual Basic], throwing exceptions
- throwing exceptions
- exception handling, unstructured
- throw statement [Visual Basic]
ms.assetid: a6e07406-5c8a-4498-87a2-8339f3651d62
ms.openlocfilehash: cfa53b3585846da25711739fb7af4bde21746b29
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33602855"
---
# <a name="throw-statement-visual-basic"></a><span data-ttu-id="0c3ac-102">Throw 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0c3ac-102">Throw Statement (Visual Basic)</span></span>
<span data-ttu-id="0c3ac-103">프로시저 내에서 예외가 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c3ac-103">Throws an exception within a procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c3ac-104">구문</span><span class="sxs-lookup"><span data-stu-id="0c3ac-104">Syntax</span></span>  
  
```  
Throw [ expression ]  
```  
  
## <a name="part"></a><span data-ttu-id="0c3ac-105">파트</span><span class="sxs-lookup"><span data-stu-id="0c3ac-105">Part</span></span>  
 `expression`  
 <span data-ttu-id="0c3ac-106">예외를 throw 하는 방법에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c3ac-106">Provides information about the exception to be thrown.</span></span> <span data-ttu-id="0c3ac-107">에 있는 경우 선택 사항:는 `Catch` 문, 그렇지 않으면 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c3ac-107">Optional when residing in a `Catch` statement, otherwise required.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0c3ac-108">설명</span><span class="sxs-lookup"><span data-stu-id="0c3ac-108">Remarks</span></span>  
 <span data-ttu-id="0c3ac-109">`Throw` 구조적 예외 처리 코드로 처리할 수 있는 예외를 throw 하는 문 (`Try`... `Catch`... `Finally`) 또는 비구조적된 예외 처리 코드 (`On Error GoTo`).</span><span class="sxs-lookup"><span data-stu-id="0c3ac-109">The `Throw` statement throws an exception that you can handle with structured exception-handling code (`Try`...`Catch`...`Finally`) or unstructured exception-handling code (`On Error GoTo`).</span></span> <span data-ttu-id="0c3ac-110">사용할 수는 `Throw` 문을 Visual Basic에서는 적절 한 예외 처리 코드를 찾을 때까지 호출 스택 위로 이동 하기 때문에 코드 내에서 오류를 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c3ac-110">You can use the `Throw` statement to trap errors within your code because Visual Basic moves up the call stack until it finds the appropriate exception-handling code.</span></span>  
  
 <span data-ttu-id="0c3ac-111">A `Throw` 문 식 에서만 사용할 수는 `Catch` 경우 문이에서 현재 처리 되 고 예외가 다시 throw 문을 `Catch` 문.</span><span class="sxs-lookup"><span data-stu-id="0c3ac-111">A `Throw` statement with no expression can only be used in a `Catch` statement, in which case the statement rethrows the exception currently being handled by the `Catch` statement.</span></span>  
  
 <span data-ttu-id="0c3ac-112">`Throw` 문은 대 한 호출 스택을 다시 설정 된 `expression` 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="0c3ac-112">The `Throw` statement resets the call stack for the `expression` exception.</span></span> <span data-ttu-id="0c3ac-113">경우 `expression` 호출 스택을 제공 하지 않으면 그대로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c3ac-113">If `expression` is not provided, the call stack is left unchanged.</span></span> <span data-ttu-id="0c3ac-114">통해 예외에 대 한 호출 스택을 액세스할 수 있습니다는 <xref:System.Exception.StackTrace%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="0c3ac-114">You can access the call stack for the exception through the <xref:System.Exception.StackTrace%2A> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0c3ac-115">예제</span><span class="sxs-lookup"><span data-stu-id="0c3ac-115">Example</span></span>  
 <span data-ttu-id="0c3ac-116">다음 코드에서는 `Throw` 문이 예외를 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c3ac-116">The following code uses the `Throw` statement to throw an exception:</span></span>  
  
 [!code-vb[VbVbalrStatements#84](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/throw-statement_1.vb)]  
  
## <a name="requirements"></a><span data-ttu-id="0c3ac-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0c3ac-117">Requirements</span></span>  
 <span data-ttu-id="0c3ac-118">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="0c3ac-118">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="0c3ac-119">**모듈:** `Interaction`</span><span class="sxs-lookup"><span data-stu-id="0c3ac-119">**Module:** `Interaction`</span></span>  
  
 <span data-ttu-id="0c3ac-120">**어셈블리:** Visual Basic 런타임 라이브러리 (Microsoft.VisualBasic.dll)</span><span class="sxs-lookup"><span data-stu-id="0c3ac-120">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c3ac-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0c3ac-121">See Also</span></span>  
 [<span data-ttu-id="0c3ac-122">Try...Catch...Finally 문</span><span class="sxs-lookup"><span data-stu-id="0c3ac-122">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [<span data-ttu-id="0c3ac-123">On Error 문</span><span class="sxs-lookup"><span data-stu-id="0c3ac-123">On Error Statement</span></span>](../../../visual-basic/language-reference/statements/on-error-statement.md)
