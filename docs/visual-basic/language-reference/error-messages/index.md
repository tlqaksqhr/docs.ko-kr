---
title: "오류 메시지(Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- errors [Visual Basic]
- error messages
- trappable errors
- errors [Visual Basic], trappable
ms.assetid: f2dda05b-baef-41f5-8bb1-598bd7cf239f
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f7f5138d430e6737a4a8a47d4a800905dedff660
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="error-messages-visual-basic"></a><span data-ttu-id="d3121-102">오류 메시지(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d3121-102">Error Messages (Visual Basic)</span></span>
<span data-ttu-id="d3121-103">Visual Basic 응용 프로그램을 작성, 컴파일 또는 실행할 때 다음과 같은 유형의 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3121-103">When you write, compile, or run a Visual Basic application, the following types of errors can occur:</span></span>  
  
1.  <span data-ttu-id="d3121-104">디자인 타임 오류: Visual Studio에서 응용 프로그램을 작성할 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="d3121-104">Design-time errors, which occur when you write an application in Visual Studio.</span></span>  
  
2.  <span data-ttu-id="d3121-105">컴파일 타임 오류: Visual Studio 또는 명령 프롬프트에서 응용 프로그램을 컴파일할 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="d3121-105">Compile-time errors, which occur when you compile an application in Visual Studio or at a command prompt.</span></span>  
  
3.  <span data-ttu-id="d3121-106">런타임 오류: Visual Studio에서 응용 프로그램을 실행하거나 독립 실행형 실행 파일을 실행할 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="d3121-106">Run-time errors, which occur when you run an application in Visual Studio or as a stand-alone executable file.</span></span>  
  
 <span data-ttu-id="d3121-107">특정 오류를 해결하는 방법에 대한 자세한 내용은 [Visual Basic 프로그래머를 위한 추가 리소스](../../../visual-basic/getting-started/additional-resources.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d3121-107">For information about how to troubleshoot a specific error, see [Additional Resources for Visual Basic Programmers](../../../visual-basic/getting-started/additional-resources.md).</span></span>  
  
## <a name="run-time-errors"></a><span data-ttu-id="d3121-108">런타임 오류</span><span class="sxs-lookup"><span data-stu-id="d3121-108">Run Time Errors</span></span>  
 <span data-ttu-id="d3121-109">Visual Basic 응용 프로그램이 시스템에서 실행할 수 없는 작업을 수행하려고 하는 경우 런타임 오류가 발생하고 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]에서 `Exception` 개체를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="d3121-109">If a Visual Basic application tries to perform an action that the system can't execute, a run-time error occurs, and [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] throws an `Exception` object.</span></span> [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<span data-ttu-id="d3121-110">에서는 `Throw` 문을 사용하여 `Exception` 개체를 포함하는 모든 데이터 형식의 사용자 지정 오류를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3121-110"> can generate custom errors of any data type, including `Exception` objects, by using the `Throw` statement.</span></span> <span data-ttu-id="d3121-111">응용 프로그램은 catch한 예외의 오류 번호 및 메시지를 표시하여 오류를 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3121-111">An application can identify the error by displaying the error number and message of a caught exception.</span></span> <span data-ttu-id="d3121-112">오류가 catch되지 않으면 응용 프로그램이 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3121-112">If an error isn't caught, the application ends.</span></span>  
  
 <span data-ttu-id="d3121-113">코드는 런타임 오류를 트래핑하고 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3121-113">The code can trap and examine run-time errors.</span></span> <span data-ttu-id="d3121-114">오류를 생성하는 코드를 `Try` 블록에 포함할 경우 일치 하는 `Catch` 블록 내에서 throw된 오류를 catch할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3121-114">If you enclose the code that produces the error in a `Try` block, you can catch any thrown error within a matching `Catch` block.</span></span> <span data-ttu-id="d3121-115">런타임 시 오류를 트래핑하고 코드에 응답하는 방법에 대한 자세한 내용은 [Try...Catch...Finally 문](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d3121-115">For information about how to trap errors at run time and respond to them in your code, see [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
## <a name="compile-time-errors"></a><span data-ttu-id="d3121-116">컴파일 타임 오류</span><span class="sxs-lookup"><span data-stu-id="d3121-116">Compile Time Errors</span></span>  
 <span data-ttu-id="d3121-117">Visual Basic 컴파일러를 사용하는 동안 코드에서 문제가 발생하는 경우 컴파일 타임 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="d3121-117">If the Visual Basic compiler encounters a problem in the code, a compile-time error occurs.</span></span> <span data-ttu-id="d3121-118">코드 편집기에서 해당 코드 줄 아래에 물결 무늬가 표시되므로 오류를 유발한 코드 줄을 쉽게 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3121-118">In the Code Editor, you can easily identify which line of code caused the error because a wavy line appears under that line of code.</span></span> <span data-ttu-id="d3121-119">물결 무늬 밑줄을 가리키거나 **오류 목록**을 열어도 오류 메시지가 표시됩니다. 오류 목록을 열면 다른 메시지도 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3121-119">The error message appears if you either point to the wavy underline or open the **Error List**, which also shows other messages.</span></span>  
  
 <span data-ttu-id="d3121-120">식별자에 물결 무늬 밑줄이 있고 맨 오른쪽 문자 아래에 짧은 밑줄이 표시되면 클래스, 생성자, 메서드, 속성, 필드 또는 열거형에 대한 스텁을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3121-120">If an identifier has a wavy underline and a short underline appears under the rightmost character, you can generate a stub for the class, constructor, method, property, field or enum.</span></span> <span data-ttu-id="d3121-121">자세한 내용은 [관례에서 생성](/visualstudio/ide/visual-csharp-intellisense#generate-from-usage)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d3121-121">For more information, see [Generate From Usage](/visualstudio/ide/visual-csharp-intellisense#generate-from-usage).</span></span>
  
 <span data-ttu-id="d3121-122">Visual Basic 컴파일러에서 경고를 확인하면 버그 수를 줄이고 코드를 더 빠르게 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d3121-122">By resolving warnings from the Visual Basic compiler, you might be able to write code that runs faster and has fewer bugs.</span></span> <span data-ttu-id="d3121-123">이러한 경고는 응용 프로그램이 실행될 때 오류를 유발할 수 있는 코드를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="d3121-123">These warnings identify code that may cause errors when the application is run.</span></span> <span data-ttu-id="d3121-124">예를 들어 컴파일러에서는 사용자가 할당되지 않은 개체 변수의 멤버를 호출하거나, 반환 값을 설정하지 않고 함수에서 반환되거나, 예외를 catch하기 위한 논리에서 오류가 있는 `Try` 블록을 실행하려고 시도할 경우 경고합니다.</span><span class="sxs-lookup"><span data-stu-id="d3121-124">For example, the compiler warns you if you try to invoke a member of an unassigned object variable, return from a function without setting the return value, or execute a `Try` block with errors in the logic to catch exceptions.</span></span> <span data-ttu-id="d3121-125">경고를 켜고 끄는 방법을 비롯하여 경고에 대한 자세한 내용은 [Visual Basic에서 경고 구성](/visualstudio/ide/configuring-warnings-in-visual-basic)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d3121-125">For more information about warnings, including how to turn them on and off, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>
