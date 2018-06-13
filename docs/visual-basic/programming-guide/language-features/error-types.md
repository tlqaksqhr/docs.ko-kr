---
title: 오류 형식(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- exceptions, types
- errors [Visual Basic], types
- errors [Visual Basic], logic
- errors [Visual Basic], syntax
- logic errors [Visual Basic], Visual Basic
- run-time errors [Visual Basic], types of errors
- syntax errors [Visual Basic], Visual Basic
ms.assetid: 3048aabf-8c97-4e13-9150-853769cb5f6f
ms.openlocfilehash: c11b7f41dee57fc52ca1dff75734ad0b27b6a43a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33647113"
---
# <a name="error-types-visual-basic"></a><span data-ttu-id="56a72-102">오류 형식(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="56a72-102">Error Types (Visual Basic)</span></span>
<span data-ttu-id="56a72-103">Visual basic에서 오류 (호출 또한 *예외*) 세 가지 범주 중 하나에 해당: 구문 오류, 런타임 오류 및 논리 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="56a72-103">In Visual Basic, errors (also called *exceptions*) fall into one of three categories: syntax errors, run-time errors, and logic errors.</span></span>  
  
## <a name="syntax-errors"></a><span data-ttu-id="56a72-104">구문 오류</span><span class="sxs-lookup"><span data-stu-id="56a72-104">Syntax Errors</span></span>  
 <span data-ttu-id="56a72-105">*구문 오류* 는 코드를 작성 하는 동안 발생 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="56a72-105">*Syntax errors* are those that appear while you write code.</span></span> <span data-ttu-id="56a72-106">Visual Basic에서는 코드에서 입력할 때는 **코드 편집기** 창 철자 또는 부적절 하 게 언어 요소를 사용 하 여 등의 실수 한 경우 경고 합니다.</span><span class="sxs-lookup"><span data-stu-id="56a72-106">Visual Basic checks your code as you type it in the **Code Editor** window and alerts you if you make a mistake, such as misspelling a word or using a language element improperly.</span></span> <span data-ttu-id="56a72-107">구문 오류는 오류의 가장 일반적인 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="56a72-107">Syntax errors are the most common type of errors.</span></span> <span data-ttu-id="56a72-108">하면 쉽게 수정할 수 코딩 환경에서 발생 하는 즉시 합니다.</span><span class="sxs-lookup"><span data-stu-id="56a72-108">You can fix them easily in the coding environment as soon as they occur.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="56a72-109">`Option Explicit` 문의 구문 오류를 방지 하는 한 가지 방법은 됩니다.</span><span class="sxs-lookup"><span data-stu-id="56a72-109">The `Option Explicit` statement is one means of avoiding syntax errors.</span></span> <span data-ttu-id="56a72-110">강제로 응용 프로그램에 사용할 모든 변수 사전에 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56a72-110">It forces you to declare, in advance, all the variables to be used in the application.</span></span> <span data-ttu-id="56a72-111">따라서 이러한 변수는 코드에 사용 되는 경우 철자 오류가 발생할 즉시 발생 하며 수정 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56a72-111">Therefore, when those variables are used in the code, any typographic errors are caught immediately and can be fixed.</span></span>  
  
## <a name="run-time-errors"></a><span data-ttu-id="56a72-112">런타임 오류</span><span class="sxs-lookup"><span data-stu-id="56a72-112">Run-Time Errors</span></span>  
 <span data-ttu-id="56a72-113">*런타임 오류* 는 컴파일 및 코드를 실행 한 후에 발생 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="56a72-113">*Run-time errors* are those that appear only after you compile and run your code.</span></span> <span data-ttu-id="56a72-114">이러한 문제가 되는 것에 구문 오류가 없으면 실행 되지 것입니다 한다는 점에서 올바른 것으로 표시 될 수 있는 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="56a72-114">These involve code that may appear to be correct in that it has no syntax errors, but that will not execute.</span></span> <span data-ttu-id="56a72-115">예를 들어 파일을 여는 코드 줄을 올바르게 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56a72-115">For example, you might correctly write a line of code to open a file.</span></span> <span data-ttu-id="56a72-116">하지만 파일이 손상 된 경우 응용 프로그램을 수행할 수 없습니다는 `Open` 기능을 실행을 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="56a72-116">But if the file is corrupted, the application cannot carry out the `Open` function, and it stops running.</span></span> <span data-ttu-id="56a72-117">잘못 된 코드를 다시 작성 한 후 다시 컴파일하지 마우스를 다시 실행 하 여 대부분의 런타임 오류를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56a72-117">You can fix most run-time errors by rewriting the faulty code, and then recompiling and rerunning it.</span></span>  
  
## <a name="logic-errors"></a><span data-ttu-id="56a72-118">논리 오류</span><span class="sxs-lookup"><span data-stu-id="56a72-118">Logic Errors</span></span>  
 <span data-ttu-id="56a72-119">*논리 오류* 는 나타나는 응용 프로그램을 사용에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="56a72-119">*Logic errors* are those that appear once the application is in use.</span></span> <span data-ttu-id="56a72-120">이들은 대부분 종종 예기치 않은 결과가 사용자의 작업에 대 한 응답 으로입니다.</span><span class="sxs-lookup"><span data-stu-id="56a72-120">They are most often unwanted or unexpected results in response to user actions.</span></span> <span data-ttu-id="56a72-121">예를 들어 잘못 입력 된 키 또는 등의 외부 요인 않을 응용 프로그램의 실행이 필요한 매개 변수 내에서 작업을 중지 또는 완전히 합니다.</span><span class="sxs-lookup"><span data-stu-id="56a72-121">For example, a mistyped key or other outside influence might cause your application to stop working within expected parameters, or altogether.</span></span> <span data-ttu-id="56a72-122">논리 오류는 일반적으로 되지 않으므로 항상 지우기 시작 위치를 해결 하려면 가장 어려운 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="56a72-122">Logic errors are generally the hardest type to fix, since it is not always clear where they originate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56a72-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="56a72-123">See Also</span></span>  
 [<span data-ttu-id="56a72-124">Try...Catch...Finally 문</span><span class="sxs-lookup"><span data-stu-id="56a72-124">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [<span data-ttu-id="56a72-125">디버거 기본 사항</span><span class="sxs-lookup"><span data-stu-id="56a72-125">Debugger Basics</span></span>](/visualstudio/debugger/debugger-basics)
