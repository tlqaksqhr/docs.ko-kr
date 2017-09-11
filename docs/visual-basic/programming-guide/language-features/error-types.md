---
title: "오류 유형 (Visual Basic) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- exceptions, types
- errors [Visual Basic], types
- errors [Visual Basic], logic
- errors [Visual Basic], syntax
- logic errors, Visual Basic
- run-time errors, types of errors
- syntax errors, Visual Basic
ms.assetid: 3048aabf-8c97-4e13-9150-853769cb5f6f
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
ms.openlocfilehash: 51cf5820e79ff9467357619d4f5b067bc4168bfb
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="error-types-visual-basic"></a><span data-ttu-id="d641b-102">오류 형식(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d641b-102">Error Types (Visual Basic)</span></span>
<span data-ttu-id="d641b-103">[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], 오류 (라고도 *예외*) 세 가지 범주 중 하나에 속합니다: 구문 오류, 런타임 오류 및 논리 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="d641b-103">In [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], errors (also called *exceptions*) fall into one of three categories: syntax errors, run-time errors, and logic errors.</span></span>  
  
## <a name="syntax-errors"></a><span data-ttu-id="d641b-104">구문 오류</span><span class="sxs-lookup"><span data-stu-id="d641b-104">Syntax Errors</span></span>  
 <span data-ttu-id="d641b-105">*구문 오류* 코드를 작성 하는 동안 나타나는 것 들입니다.</span><span class="sxs-lookup"><span data-stu-id="d641b-105">*Syntax errors* are those that appear while you write code.</span></span> [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="d641b-106">입력할 때 코드를 검사 하는 **코드 편집기** 창 철자 부적절 하 게 언어 요소를 사용 하 여 등의 실수 한 경우 사용자에 게 알려 합니다.</span><span class="sxs-lookup"><span data-stu-id="d641b-106"> checks your code as you type it in the **Code Editor** window and alerts you if you make a mistake, such as misspelling a word or using a language element improperly.</span></span> <span data-ttu-id="d641b-107">구문 오류는 오류의 가장 일반적인 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="d641b-107">Syntax errors are the most common type of errors.</span></span> <span data-ttu-id="d641b-108">하면 쉽게 수정할 수 코딩 환경에서 발생 하는 즉시 합니다.</span><span class="sxs-lookup"><span data-stu-id="d641b-108">You can fix them easily in the coding environment as soon as they occur.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d641b-109">`Option Explicit` 문은 구문 오류를 방지 하는 한 가지 방법은입니다.</span><span class="sxs-lookup"><span data-stu-id="d641b-109">The `Option Explicit` statement is one means of avoiding syntax errors.</span></span> <span data-ttu-id="d641b-110">강제로 사전에 응용 프로그램에서 사용할 모든 변수를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d641b-110">It forces you to declare, in advance, all the variables to be used in the application.</span></span> <span data-ttu-id="d641b-111">따라서 이러한 변수는 코드에 사용 되는 경우 철자 오류가 발생할 즉시 발생 하며 수정 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d641b-111">Therefore, when those variables are used in the code, any typographic errors are caught immediately and can be fixed.</span></span>  
  
## <a name="run-time-errors"></a><span data-ttu-id="d641b-112">런타임 오류</span><span class="sxs-lookup"><span data-stu-id="d641b-112">Run-Time Errors</span></span>  
 <span data-ttu-id="d641b-113">*런타임 오류* 컴파일 및 코드를 실행 한 후에 나타나는 것 들입니다.</span><span class="sxs-lookup"><span data-stu-id="d641b-113">*Run-time errors* are those that appear only after you compile and run your code.</span></span> <span data-ttu-id="d641b-114">이러한 구문 오류가 없을 실행 되지 않는 한다는 점에서 올바른 것으로 나타날 수 있는 코드 작업이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d641b-114">These involve code that may appear to be correct in that it has no syntax errors, but that will not execute.</span></span> <span data-ttu-id="d641b-115">예를 들어 파일을 여는 코드 줄을 올바르게 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d641b-115">For example, you might correctly write a line of code to open a file.</span></span> <span data-ttu-id="d641b-116">파일이 손상 된 경우 응용 프로그램을 수행할 수 없습니다 하지만 `Open` 기능을 실행을 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="d641b-116">But if the file is corrupted, the application cannot carry out the `Open` function, and it stops running.</span></span> <span data-ttu-id="d641b-117">결함이 있는 코드를 다시 작성 한 다음 다시 컴파일하고 다시 실행 하 여 대부분의 런타임 오류를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d641b-117">You can fix most run-time errors by rewriting the faulty code, and then recompiling and rerunning it.</span></span>  
  
## <a name="logic-errors"></a><span data-ttu-id="d641b-118">논리 오류</span><span class="sxs-lookup"><span data-stu-id="d641b-118">Logic Errors</span></span>  
 <span data-ttu-id="d641b-119">*논리 오류* 는 나타나는 응용 프로그램을 사용에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="d641b-119">*Logic errors* are those that appear once the application is in use.</span></span> <span data-ttu-id="d641b-120">이들은 대부분 자주 예기치 않은 결과가 사용자 작업에 대 한 응답에서입니다.</span><span class="sxs-lookup"><span data-stu-id="d641b-120">They are most often unwanted or unexpected results in response to user actions.</span></span> <span data-ttu-id="d641b-121">예를 들어 키를 잘못 입력된 또는 다른 외부 영향을 주지 않이 예상된 매개 변수 내에서 작동을 중지 하는 응용 프로그램 또는 완전히 합니다.</span><span class="sxs-lookup"><span data-stu-id="d641b-121">For example, a mistyped key or other outside influence might cause your application to stop working within expected parameters, or altogether.</span></span> <span data-ttu-id="d641b-122">논리 오류는 일반적으로 되지 않으므로 항상 지우기 시작 위치를 수정 하기 어려운 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="d641b-122">Logic errors are generally the hardest type to fix, since it is not always clear where they originate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d641b-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d641b-123">See Also</span></span>  
 <span data-ttu-id="d641b-124">[Try...Catch...Finally 문](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) </span><span class="sxs-lookup"><span data-stu-id="d641b-124">[Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) </span></span>  
<span data-ttu-id="d641b-125"> [디버거 기본 사항](https://docs.microsoft.com/visualstudio/debugger/debugger-basics)</span><span class="sxs-lookup"><span data-stu-id="d641b-125"> [Debugger Basics](https://docs.microsoft.com/visualstudio/debugger/debugger-basics)</span></span>
