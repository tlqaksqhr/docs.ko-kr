---
title: "Visual Basic 프로그램의 구조 | Microsoft 문서"
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
- conditional compilation, Visual Basic
- program structure, Visual Basic
- procedures, structure
- Visual Basic code, program structure
ms.assetid: ad0c6531-d762-4c77-a700-de16b07b6119
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
ms.openlocfilehash: 3e16ea51d0f766fcb5866cde89e5384a153ac050
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="structure-of-a-visual-basic-program"></a><span data-ttu-id="7b394-102">Visual Basic 프로그램의 구조</span><span class="sxs-lookup"><span data-stu-id="7b394-102">Structure of a Visual Basic Program</span></span>
<span data-ttu-id="7b394-103">A [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 프로그램은 표준 구성 요소에서 빌드됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b394-103">A [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] program is built up from standard building blocks.</span></span> <span data-ttu-id="7b394-104">A *솔루션* 하나 이상의 프로젝트를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b394-104">A *solution* comprises one or more projects.</span></span> <span data-ttu-id="7b394-105">A *프로젝트* 어셈블리 하나 이상 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b394-105">A *project* in turn can contain one or more assemblies.</span></span> <span data-ttu-id="7b394-106">각 *어셈블리* 는 하나 이상의 소스 파일에서 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b394-106">Each *assembly* is compiled from one or more source files.</span></span> <span data-ttu-id="7b394-107">A *소스 파일* 정 및 클래스, 구조체, 모듈 및 궁극적으로 모든 코드를 포함 하는 인터페이스의 구현을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b394-107">A *source file* provides the definition and implementation of classes, structures, modules, and interfaces, which ultimately contain all your code.</span></span>  
  
 <span data-ttu-id="7b394-108">이러한 구성 요소에 대 한 자세한 내용은 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 프로그램의 경우 참조 [솔루션 및 프로젝트](https://docs.microsoft.com/visualstudio/ide/solutions-and-projects-in-visual-studio) 및 [어셈블리 및 전역 어셈블리 캐시](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7b394-108">For more information about these building blocks of a [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] program, see [Solutions and Projects](https://docs.microsoft.com/visualstudio/ide/solutions-and-projects-in-visual-studio) and [Assemblies and the Global Assembly Cache](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md).</span></span>  
  
## <a name="file-level-programming-elements"></a><span data-ttu-id="7b394-109">파일 수준 프로그래밍 요소</span><span class="sxs-lookup"><span data-stu-id="7b394-109">File-Level Programming Elements</span></span>  
 <span data-ttu-id="7b394-110">프로젝트 또는 파일을 시작 하 고 코드 편집기를 열고 일부 코드가 이미 있는 및 올바른 순서로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b394-110">When you start a project or file and open the code editor, you see some code already in place and in the correct order.</span></span> <span data-ttu-id="7b394-111">모든 코드를 작성할 때는 다음 순서를 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b394-111">Any code that you write should follow the following sequence:</span></span>  
  
1.  <span data-ttu-id="7b394-112">`Option`문</span><span class="sxs-lookup"><span data-stu-id="7b394-112">`Option` statements</span></span>  
  
2.  <span data-ttu-id="7b394-113">`Imports`문</span><span class="sxs-lookup"><span data-stu-id="7b394-113">`Imports` statements</span></span>  
  
3.  <span data-ttu-id="7b394-114">`Namespace`문 및 네임 스페이스 수준 요소</span><span class="sxs-lookup"><span data-stu-id="7b394-114">`Namespace` statements and namespace-level elements</span></span>  
  
 <span data-ttu-id="7b394-115">다른 순서로 명령문을 입력 하는 경우 컴파일 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b394-115">If you enter statements in a different order, compilation errors can result.</span></span>  
  
 <span data-ttu-id="7b394-116">프로그램에는 조건부 컴파일 문에 포함할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b394-116">A program can also contain conditional compilation statements.</span></span> <span data-ttu-id="7b394-117">앞에 나온 일련의 문 함께 소스 파일에서 이러한 중간에 삽입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b394-117">You can intersperse these in the source file among the statements of the preceding sequence.</span></span>  
  
### <a name="option-statements"></a><span data-ttu-id="7b394-118">Option 문</span><span class="sxs-lookup"><span data-stu-id="7b394-118">Option Statements</span></span>  
 <span data-ttu-id="7b394-119">`Option`문 구문 및 논리 오류를 방지 하기 위해 노력 하는 후속 코드에 대 한 기본 규칙을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b394-119">`Option` statements establish ground rules for subsequent code, helping prevent syntax and logic errors.</span></span> <span data-ttu-id="7b394-120">[Option Explicit 문](../../../visual-basic/language-reference/statements/option-explicit-statement.md) 는 모든 변수 선언 되 고 철자가 디버깅 시간을 줄여주는 보장 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b394-120">The [Option Explicit Statement](../../../visual-basic/language-reference/statements/option-explicit-statement.md) ensures that all variables are declared and spelled correctly, which reduces debugging time.</span></span> <span data-ttu-id="7b394-121">[Option Strict 문](../../../visual-basic/language-reference/statements/option-strict-statement.md) 서로 다른 데이터 형식의 변수 사이 작업할 때 발생할 수 있는 논리 오류 및 데이터 손실을 최소화 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b394-121">The [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md) helps to minimize logic errors and data loss that can occur when you work between variables of different data types.</span></span> <span data-ttu-id="7b394-122">[옵션 비교 문](../../../visual-basic/language-reference/statements/option-compare-statement.md) 서로 기반 방식으로 문자열 비교 지정 자신의 `Binary` 또는 `Text` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="7b394-122">The [Option Compare Statement](../../../visual-basic/language-reference/statements/option-compare-statement.md) specifies the way strings are compared to each other, based on either their `Binary` or `Text` values.</span></span>  
  
### <a name="imports-statements"></a><span data-ttu-id="7b394-123">Imports 문</span><span class="sxs-lookup"><span data-stu-id="7b394-123">Imports Statements</span></span>  
 <span data-ttu-id="7b394-124">포함할 수는 [Imports 문 (.NET Namespace 및 형식)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) 프로젝트 외부에 정의 된 이름을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b394-124">You can include an [Imports Statement (.NET Namespace and Type)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) to import names defined outside your project.</span></span> <span data-ttu-id="7b394-125">`Imports` 문은 코드를 클래스와 기타 형식을 한정 하지 않고는 가져온된 네임 스페이스 내에 정의 된 참조를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b394-125">An `Imports` statement allows your code to refer to classes and other types defined within the imported namespace, without having to qualify them.</span></span> <span data-ttu-id="7b394-126">만큼 사용할 수 `Imports` 문을 적절 하 게 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b394-126">You can use as many `Imports` statements as appropriate.</span></span> <span data-ttu-id="7b394-127">자세한 내용은 참조 [참조 및 Imports 문](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7b394-127">For more information, see [References and the Imports Statement](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md).</span></span>  
  
### <a name="namespace-statements"></a><span data-ttu-id="7b394-128">Namespace 문</span><span class="sxs-lookup"><span data-stu-id="7b394-128">Namespace Statements</span></span>  
 <span data-ttu-id="7b394-129">네임 스페이스 도움말 구성 하 고 그룹화 하 고 액세스 하는 편의 위해 프로그래밍 요소를 분류 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b394-129">Namespaces help you organize and classify your programming elements for ease of grouping and accessing.</span></span> <span data-ttu-id="7b394-130">사용의 [Namespace 문을](../../../visual-basic/language-reference/statements/namespace-statement.md) 특정 네임 스페이스 내에서 다음 문을 분류할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b394-130">You use the [Namespace Statement](../../../visual-basic/language-reference/statements/namespace-statement.md) to classify the following statements within a particular namespace.</span></span> <span data-ttu-id="7b394-131">자세한 내용은 참조 [Visual Basic의 네임 스페이스](../../../visual-basic/programming-guide/program-structure/namespaces.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7b394-131">For more information, see [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md).</span></span>  
  
### <a name="conditional-compilation-statements"></a><span data-ttu-id="7b394-132">조건부 컴파일 문은</span><span class="sxs-lookup"><span data-stu-id="7b394-132">Conditional Compilation Statements</span></span>  
 <span data-ttu-id="7b394-133">조건부 컴파일 문은 원본 파일에서 거의 모든 곳에 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b394-133">Conditional compilation statements can appear almost anywhere in your source file.</span></span> <span data-ttu-id="7b394-134">일부 코드를 포함 하거나 제외할 특정 조건에 따라 컴파일 타임에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b394-134">They cause parts of your code to be included or excluded at compile time depending on certain conditions.</span></span> <span data-ttu-id="7b394-135">사용할 수도 있습니다 이러한 응용 프로그램을 디버깅 하는 것에 대 한 조건부 코드 디버깅 모드 에서만 실행 되므로 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b394-135">You can also use them for debugging your application, because conditional code runs in debugging mode only.</span></span> <span data-ttu-id="7b394-136">자세한 내용은 참조 [조건부 컴파일](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7b394-136">For more information, see [Conditional Compilation](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md).</span></span>  
  
## <a name="namespace-level-programming-elements"></a><span data-ttu-id="7b394-137">Namespace 수준 프로그래밍 요소</span><span class="sxs-lookup"><span data-stu-id="7b394-137">Namespace-Level Programming Elements</span></span>  
 <span data-ttu-id="7b394-138">클래스, 구조체 및 모듈에는 원본 파일의 모든 코드를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b394-138">Classes, structures, and modules contain all the code in your source file.</span></span> <span data-ttu-id="7b394-139">이들은 *네임 스페이스 수준* 요소 네임 스페이스 내에서 또는 소스 파일 수준에서 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b394-139">They are *namespace-level* elements, which can appear within a namespace or at the source file level.</span></span> <span data-ttu-id="7b394-140">다른 모든 프로그래밍 요소 선언이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b394-140">They hold the declarations of all other programming elements.</span></span> <span data-ttu-id="7b394-141">인터페이스 요소 서명을 정의 되지만 구현이 제공 하는 모듈 수준에도 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="7b394-141">Interfaces, which define element signatures but provide no implementation, also appear at module level.</span></span> <span data-ttu-id="7b394-142">모듈 수준 요소에 대 한 자세한 내용은 다음을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b394-142">For more information on the module-level elements, see the following:</span></span>  
  
-   [<span data-ttu-id="7b394-143">Class 문</span><span class="sxs-lookup"><span data-stu-id="7b394-143">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
-   [<span data-ttu-id="7b394-144">Structure 문</span><span class="sxs-lookup"><span data-stu-id="7b394-144">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
-   [<span data-ttu-id="7b394-145">Module 문</span><span class="sxs-lookup"><span data-stu-id="7b394-145">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)  
  
-   [<span data-ttu-id="7b394-146">Interface 문</span><span class="sxs-lookup"><span data-stu-id="7b394-146">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 <span data-ttu-id="7b394-147">네임 스페이스 수준에서 데이터 요소는 열거형 및 대리자입니다.</span><span class="sxs-lookup"><span data-stu-id="7b394-147">Data elements at namespace level are enumerations and delegates.</span></span>  
  
## <a name="module-level-programming-elements"></a><span data-ttu-id="7b394-148">모듈 수준 프로그래밍 요소</span><span class="sxs-lookup"><span data-stu-id="7b394-148">Module-Level Programming Elements</span></span>  
 <span data-ttu-id="7b394-149">프로시저, 연산자, 속성 및 이벤트는 실행 코드 (실행 시 작업을 수행 하는 문)을 보유할 수 있는 유일한 프로그래밍 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="7b394-149">Procedures, operators, properties, and events are the only programming elements that can hold executable code (statements that perform actions at run time).</span></span> <span data-ttu-id="7b394-150">이들은 *모듈 수준* 프로그램의 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="7b394-150">They are the *module-level* elements of your program.</span></span> <span data-ttu-id="7b394-151">프로시저 수준 요소에 대 한 자세한 내용은 다음을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b394-151">For more information on the procedure-level elements, see the following:</span></span>  
  
-   [<span data-ttu-id="7b394-152">Function 문</span><span class="sxs-lookup"><span data-stu-id="7b394-152">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
-   [<span data-ttu-id="7b394-153">Sub 문</span><span class="sxs-lookup"><span data-stu-id="7b394-153">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
-   [<span data-ttu-id="7b394-154">Declare 문</span><span class="sxs-lookup"><span data-stu-id="7b394-154">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
-   [<span data-ttu-id="7b394-155">Operator 문</span><span class="sxs-lookup"><span data-stu-id="7b394-155">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
-   [<span data-ttu-id="7b394-156">Property 문</span><span class="sxs-lookup"><span data-stu-id="7b394-156">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
-   [<span data-ttu-id="7b394-157">Event 문</span><span class="sxs-lookup"><span data-stu-id="7b394-157">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 <span data-ttu-id="7b394-158">모듈 수준에서 데이터 요소에는 변수, 상수, 열거형 및 대리자는입니다.</span><span class="sxs-lookup"><span data-stu-id="7b394-158">Data elements at module level are variables, constants, enumerations, and delegates.</span></span>  
  
## <a name="procedure-level-programming-elements"></a><span data-ttu-id="7b394-159">프로시저 수준 프로그래밍 요소</span><span class="sxs-lookup"><span data-stu-id="7b394-159">Procedure-Level Programming Elements</span></span>  
 <span data-ttu-id="7b394-160">내용 대부분 *프로시저 수준* 요소는 구성 하는 프로그램의 런타임 코드를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b394-160">Most of the contents of *procedure-level* elements are executable statements, which constitute the run-time code of your program.</span></span> <span data-ttu-id="7b394-161">일부 절차의 모든 실행 코드 여야 합니다 (`Function`, `Sub`, `Operator`, `Get`, `Set`, `AddHandler`, `RemoveHandler`, `RaiseEvent`).</span><span class="sxs-lookup"><span data-stu-id="7b394-161">All executable code must be in some procedure (`Function`, `Sub`, `Operator`, `Get`, `Set`, `AddHandler`, `RemoveHandler`, `RaiseEvent`).</span></span> <span data-ttu-id="7b394-162">자세한 내용은 참조 [문을](../../../visual-basic/programming-guide/language-features/statements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7b394-162">For more information, see [Statements](../../../visual-basic/programming-guide/language-features/statements.md).</span></span>  
  
 <span data-ttu-id="7b394-163">프로시저 수준에서 데이터 요소는 로컬 변수 및 상수 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b394-163">Data elements at procedure level are limited to local variables and constants.</span></span>  
  
## <a name="the-main-procedure"></a><span data-ttu-id="7b394-164">Main 프로시저</span><span class="sxs-lookup"><span data-stu-id="7b394-164">The Main Procedure</span></span>  
 <span data-ttu-id="7b394-165">`Main` 절차는 응용 프로그램 로드 되었을 때 실행 하는 첫 번째 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="7b394-165">The `Main` procedure is the first code to run when your application has been loaded.</span></span> <span data-ttu-id="7b394-166">`Main`시작 지점 및 응용 프로그램에 대 한 전체 제어 하는 데 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b394-166">`Main` serves as the starting point and overall control for your application.</span></span> <span data-ttu-id="7b394-167">네 가지가 `Main`:</span><span class="sxs-lookup"><span data-stu-id="7b394-167">There are four varieties of `Main`:</span></span>  
  
-   `Sub Main()`  
  
-   `Sub Main(ByVal cmdArgs() As String)`  
  
-   `Function Main() As Integer`  
  
-   `Function Main(ByVal cmdArgs() As String) As Integer`  
  
 <span data-ttu-id="7b394-168">이 절차의 가장 일반적인 것은 `Sub Main()`합니다.</span><span class="sxs-lookup"><span data-stu-id="7b394-168">The most common variety of this procedure is `Sub Main()`.</span></span> <span data-ttu-id="7b394-169">자세한 내용은 참조 [Visual Basic의 Main 프로시저](../../../visual-basic/programming-guide/program-structure/main-procedure.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7b394-169">For more information, see [Main Procedure in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b394-170">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7b394-170">See Also</span></span>  
 <span data-ttu-id="7b394-171">[Visual Basic의 main 프로시저](../../../visual-basic/programming-guide/program-structure/main-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="7b394-171">[Main Procedure in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md) </span></span>  
<span data-ttu-id="7b394-172"> [Visual Basic 명명 규칙](../../../visual-basic/programming-guide/program-structure/naming-conventions.md) </span><span class="sxs-lookup"><span data-stu-id="7b394-172"> [Visual Basic Naming Conventions](../../../visual-basic/programming-guide/program-structure/naming-conventions.md) </span></span>  
<span data-ttu-id="7b394-173"> [Visual Basic 제한 사항](../../../visual-basic/programming-guide/program-structure/limitations.md)</span><span class="sxs-lookup"><span data-stu-id="7b394-173"> [Visual Basic Limitations](../../../visual-basic/programming-guide/program-structure/limitations.md)</span></span>
