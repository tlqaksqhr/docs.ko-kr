---
title: Visual Basic 프로그램의 구조
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- conditional compilation [Visual Basic], Visual Basic
- program structure [Visual Basic], Visual Basic
- procedures [Visual Basic], structure
- Visual Basic code, program structure
ms.assetid: ad0c6531-d762-4c77-a700-de16b07b6119
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5def0de1e22af39eb16489a2d4d27bdbd1853f2b
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="structure-of-a-visual-basic-program"></a><span data-ttu-id="ca6af-102">Visual Basic 프로그램의 구조</span><span class="sxs-lookup"><span data-stu-id="ca6af-102">Structure of a Visual Basic Program</span></span>
<span data-ttu-id="ca6af-103">Visual Basic 프로그램은 표준 구성 요소에서 빌드됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca6af-103">A Visual Basic program is built up from standard building blocks.</span></span> <span data-ttu-id="ca6af-104">A *솔루션* 하나 이상의 프로젝트를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca6af-104">A *solution* comprises one or more projects.</span></span> <span data-ttu-id="ca6af-105">A *프로젝트* 어셈블리를 하나 이상 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca6af-105">A *project* in turn can contain one or more assemblies.</span></span> <span data-ttu-id="ca6af-106">각 *어셈블리* 는 하나 이상의 소스 파일에서 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca6af-106">Each *assembly* is compiled from one or more source files.</span></span> <span data-ttu-id="ca6af-107">A *소스 파일* 정 및 클래스, 구조체, 모듈 및 모든 코드를 포함 하는 인터페이스의 구현을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca6af-107">A *source file* provides the definition and implementation of classes, structures, modules, and interfaces, which ultimately contain all your code.</span></span>  
  
 <span data-ttu-id="ca6af-108">Visual Basic 프로그램의 이러한 빌딩 블록에 대 한 자세한 내용은 참조 [솔루션 및 프로젝트](/visualstudio/ide/solutions-and-projects-in-visual-studio) 및 [어셈블리 및 전역 어셈블리 캐시](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ca6af-108">For more information about these building blocks of a Visual Basic program, see [Solutions and Projects](/visualstudio/ide/solutions-and-projects-in-visual-studio) and [Assemblies and the Global Assembly Cache](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md).</span></span>  
  
## <a name="file-level-programming-elements"></a><span data-ttu-id="ca6af-109">파일-수준 프로그래밍 요소</span><span class="sxs-lookup"><span data-stu-id="ca6af-109">File-Level Programming Elements</span></span>  
 <span data-ttu-id="ca6af-110">프로젝트나 파일을 시작 하 고을 코드 편집기를 열려면 일부 코드가 이미 있는 및 올바른 순서로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca6af-110">When you start a project or file and open the code editor, you see some code already in place and in the correct order.</span></span> <span data-ttu-id="ca6af-111">작성 하는 모든 코드를 다음 순서 대로 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca6af-111">Any code that you write should follow the following sequence:</span></span>  
  
1.  <span data-ttu-id="ca6af-112">`Option` 문</span><span class="sxs-lookup"><span data-stu-id="ca6af-112">`Option` statements</span></span>  
  
2.  <span data-ttu-id="ca6af-113">`Imports` 문</span><span class="sxs-lookup"><span data-stu-id="ca6af-113">`Imports` statements</span></span>  
  
3.  <span data-ttu-id="ca6af-114">`Namespace` 문 및 네임 스페이스 수준 요소</span><span class="sxs-lookup"><span data-stu-id="ca6af-114">`Namespace` statements and namespace-level elements</span></span>  
  
 <span data-ttu-id="ca6af-115">다른 순서로 문을 입력 하면 컴파일 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca6af-115">If you enter statements in a different order, compilation errors can result.</span></span>  
  
 <span data-ttu-id="ca6af-116">프로그램에는 조건부 컴파일 문에 포함할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca6af-116">A program can also contain conditional compilation statements.</span></span> <span data-ttu-id="ca6af-117">앞에 나온 일련의 문 함께 소스 파일에서 이러한 중간에 삽입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca6af-117">You can intersperse these in the source file among the statements of the preceding sequence.</span></span>  
  
### <a name="option-statements"></a><span data-ttu-id="ca6af-118">옵션 문</span><span class="sxs-lookup"><span data-stu-id="ca6af-118">Option Statements</span></span>  
 <span data-ttu-id="ca6af-119">`Option` 문 구문 및 논리 오류를 방지 하는 후속 코드에 대 한 기본 규칙을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca6af-119">`Option` statements establish ground rules for subsequent code, helping prevent syntax and logic errors.</span></span> <span data-ttu-id="ca6af-120">[Option Explicit 문](../../../visual-basic/language-reference/statements/option-explicit-statement.md) 모든 변수 선언를 제대로 입력 했는지, 디버깅 시간을 줄여주는 보장 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca6af-120">The [Option Explicit Statement](../../../visual-basic/language-reference/statements/option-explicit-statement.md) ensures that all variables are declared and spelled correctly, which reduces debugging time.</span></span> <span data-ttu-id="ca6af-121">[Option Strict 문](../../../visual-basic/language-reference/statements/option-strict-statement.md) 서로 다른 데이터 형식의 변수 사이 작업할 때 발생할 수 있는 논리 오류 및 데이터 손실을 최소화 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca6af-121">The [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md) helps to minimize logic errors and data loss that can occur when you work between variables of different data types.</span></span> <span data-ttu-id="ca6af-122">[옵션 비교 문](../../../visual-basic/language-reference/statements/option-compare-statement.md) 서로 하나에 따라 방식으로 문자열 비교 지정 자신의 `Binary` 또는 `Text` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="ca6af-122">The [Option Compare Statement](../../../visual-basic/language-reference/statements/option-compare-statement.md) specifies the way strings are compared to each other, based on either their `Binary` or `Text` values.</span></span>  
  
### <a name="imports-statements"></a><span data-ttu-id="ca6af-123">Imports 문</span><span class="sxs-lookup"><span data-stu-id="ca6af-123">Imports Statements</span></span>  
 <span data-ttu-id="ca6af-124">포함할 수 있습니다는 [Imports 문 (.NET Namespace 및 형식)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) 프로젝트 외부에 정의 된 이름을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca6af-124">You can include an [Imports Statement (.NET Namespace and Type)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) to import names defined outside your project.</span></span> <span data-ttu-id="ca6af-125">`Imports` 문은 클래스와 한정 하지 않고는 가져온된 네임 스페이스 내에서 정의 된 다른 형식을 참조 하도록 코드를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca6af-125">An `Imports` statement allows your code to refer to classes and other types defined within the imported namespace, without having to qualify them.</span></span> <span data-ttu-id="ca6af-126">만큼 사용할 수 있습니다 `Imports` 문을 적절 하 게 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca6af-126">You can use as many `Imports` statements as appropriate.</span></span> <span data-ttu-id="ca6af-127">자세한 내용은 참조 [참조 및 Imports 문](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ca6af-127">For more information, see [References and the Imports Statement](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md).</span></span>  
  
### <a name="namespace-statements"></a><span data-ttu-id="ca6af-128">Namespace 문</span><span class="sxs-lookup"><span data-stu-id="ca6af-128">Namespace Statements</span></span>  
 <span data-ttu-id="ca6af-129">네임 스페이스 도움말 구성 하 고 그룹화 하 고 액세스 하는 쉽도록 프로그래밍 요소를 분류 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca6af-129">Namespaces help you organize and classify your programming elements for ease of grouping and accessing.</span></span> <span data-ttu-id="ca6af-130">사용 하면는 [Namespace 문](../../../visual-basic/language-reference/statements/namespace-statement.md) 특정 네임 스페이스 내에서 다음 문을 분류할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca6af-130">You use the [Namespace Statement](../../../visual-basic/language-reference/statements/namespace-statement.md) to classify the following statements within a particular namespace.</span></span> <span data-ttu-id="ca6af-131">자세한 내용은 [Visual Basic의 네임스페이스](../../../visual-basic/programming-guide/program-structure/namespaces.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ca6af-131">For more information, see [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md).</span></span>  
  
### <a name="conditional-compilation-statements"></a><span data-ttu-id="ca6af-132">조건부 컴파일 문에</span><span class="sxs-lookup"><span data-stu-id="ca6af-132">Conditional Compilation Statements</span></span>  
 <span data-ttu-id="ca6af-133">조건부 컴파일 문은 소스 파일에서 거의 모든 곳에 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca6af-133">Conditional compilation statements can appear almost anywhere in your source file.</span></span> <span data-ttu-id="ca6af-134">일부 코드를 포함 하거나 제외할 특정 조건에 따라 컴파일 타임에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca6af-134">They cause parts of your code to be included or excluded at compile time depending on certain conditions.</span></span> <span data-ttu-id="ca6af-135">있습니다 사용할 수도 응용 프로그램 디버깅에 대 한 조건부 코드 디버깅 모드 에서만 실행 되기 때문에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca6af-135">You can also use them for debugging your application, because conditional code runs in debugging mode only.</span></span> <span data-ttu-id="ca6af-136">자세한 내용은 참조 [조건부 컴파일](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ca6af-136">For more information, see [Conditional Compilation](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md).</span></span>  
  
## <a name="namespace-level-programming-elements"></a><span data-ttu-id="ca6af-137">Namespace 수준 프로그래밍 요소</span><span class="sxs-lookup"><span data-stu-id="ca6af-137">Namespace-Level Programming Elements</span></span>  
 <span data-ttu-id="ca6af-138">클래스, 구조체 및 모듈에는 원본 파일의 모든 코드를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca6af-138">Classes, structures, and modules contain all the code in your source file.</span></span> <span data-ttu-id="ca6af-139">이들은 *네임 스페이스 수준* 요소 네임 스페이스 내에서 또는 소스 파일 수준에서 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca6af-139">They are *namespace-level* elements, which can appear within a namespace or at the source file level.</span></span> <span data-ttu-id="ca6af-140">다른 모든 프로그래밍 요소의 선언 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca6af-140">They hold the declarations of all other programming elements.</span></span> <span data-ttu-id="ca6af-141">인터페이스 정의 요소 시그니처 표시 되지만 구현이 제공 하는 모듈 수준에도 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca6af-141">Interfaces, which define element signatures but provide no implementation, also appear at module level.</span></span> <span data-ttu-id="ca6af-142">모듈 수준 요소에 대 한 자세한 내용은 다음을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca6af-142">For more information on the module-level elements, see the following:</span></span>  
  
-   [<span data-ttu-id="ca6af-143">Class 문</span><span class="sxs-lookup"><span data-stu-id="ca6af-143">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)  
  
-   [<span data-ttu-id="ca6af-144">Structure 문</span><span class="sxs-lookup"><span data-stu-id="ca6af-144">Structure Statement</span></span>](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
-   [<span data-ttu-id="ca6af-145">Module 문</span><span class="sxs-lookup"><span data-stu-id="ca6af-145">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)  
  
-   [<span data-ttu-id="ca6af-146">Interface 문</span><span class="sxs-lookup"><span data-stu-id="ca6af-146">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 <span data-ttu-id="ca6af-147">네임 스페이스 수준에서 데이터 요소는 열거형 및 대리자입니다.</span><span class="sxs-lookup"><span data-stu-id="ca6af-147">Data elements at namespace level are enumerations and delegates.</span></span>  
  
## <a name="module-level-programming-elements"></a><span data-ttu-id="ca6af-148">모듈 수준 프로그래밍 요소</span><span class="sxs-lookup"><span data-stu-id="ca6af-148">Module-Level Programming Elements</span></span>  
 <span data-ttu-id="ca6af-149">프로시저, 연산자, 속성 및 이벤트는 실행 코드 (실행 시 작업을 수행 하는 문)을 저장할 수 있는 유일한 프로그래밍 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="ca6af-149">Procedures, operators, properties, and events are the only programming elements that can hold executable code (statements that perform actions at run time).</span></span> <span data-ttu-id="ca6af-150">이들은 *모듈 수준* 프로그램의 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="ca6af-150">They are the *module-level* elements of your program.</span></span> <span data-ttu-id="ca6af-151">프로시저 수준 요소에 대 한 자세한 내용은 다음을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca6af-151">For more information on the procedure-level elements, see the following:</span></span>  
  
-   [<span data-ttu-id="ca6af-152">Function 문</span><span class="sxs-lookup"><span data-stu-id="ca6af-152">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
  
-   [<span data-ttu-id="ca6af-153">Sub 문</span><span class="sxs-lookup"><span data-stu-id="ca6af-153">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
-   [<span data-ttu-id="ca6af-154">Declare 문</span><span class="sxs-lookup"><span data-stu-id="ca6af-154">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
-   [<span data-ttu-id="ca6af-155">Operator 문</span><span class="sxs-lookup"><span data-stu-id="ca6af-155">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
-   [<span data-ttu-id="ca6af-156">Property 문</span><span class="sxs-lookup"><span data-stu-id="ca6af-156">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
-   [<span data-ttu-id="ca6af-157">Event 문</span><span class="sxs-lookup"><span data-stu-id="ca6af-157">Event Statement</span></span>](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 <span data-ttu-id="ca6af-158">모듈 수준에서 데이터 요소에는 변수, 상수, 열거형 및 대리자는입니다.</span><span class="sxs-lookup"><span data-stu-id="ca6af-158">Data elements at module level are variables, constants, enumerations, and delegates.</span></span>  
  
## <a name="procedure-level-programming-elements"></a><span data-ttu-id="ca6af-159">프로시저 수준 프로그래밍 요소</span><span class="sxs-lookup"><span data-stu-id="ca6af-159">Procedure-Level Programming Elements</span></span>  
 <span data-ttu-id="ca6af-160">대부분의 내용을의 *프로시저 수준* 요소는 구성 하는 프로그램의 런타임 코드를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca6af-160">Most of the contents of *procedure-level* elements are executable statements, which constitute the run-time code of your program.</span></span> <span data-ttu-id="ca6af-161">모든 실행 코드 일부 프로시저에 있어야 합니다. (`Function`, `Sub`, `Operator`, `Get`, `Set`, `AddHandler`, `RemoveHandler`, `RaiseEvent`).</span><span class="sxs-lookup"><span data-stu-id="ca6af-161">All executable code must be in some procedure (`Function`, `Sub`, `Operator`, `Get`, `Set`, `AddHandler`, `RemoveHandler`, `RaiseEvent`).</span></span> <span data-ttu-id="ca6af-162">자세한 내용은 [문](../../../visual-basic/programming-guide/language-features/statements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ca6af-162">For more information, see [Statements](../../../visual-basic/programming-guide/language-features/statements.md).</span></span>  
  
 <span data-ttu-id="ca6af-163">프로시저 수준에서 데이터 요소는 로컬 변수 및 상수 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca6af-163">Data elements at procedure level are limited to local variables and constants.</span></span>  
  
## <a name="the-main-procedure"></a><span data-ttu-id="ca6af-164">Main 프로시저</span><span class="sxs-lookup"><span data-stu-id="ca6af-164">The Main Procedure</span></span>  
 <span data-ttu-id="ca6af-165">`Main` 프로시저는 첫 번째 코드를 응용 프로그램 로드 되었을 때를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca6af-165">The `Main` procedure is the first code to run when your application has been loaded.</span></span> <span data-ttu-id="ca6af-166">`Main` 시작 지점 및 응용 프로그램에 대 한 전체 제어 하는 데 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca6af-166">`Main` serves as the starting point and overall control for your application.</span></span> <span data-ttu-id="ca6af-167">네 가지 종류의 `Main`:</span><span class="sxs-lookup"><span data-stu-id="ca6af-167">There are four varieties of `Main`:</span></span>  
  
-   `Sub Main()`  
  
-   `Sub Main(ByVal cmdArgs() As String)`  
  
-   `Function Main() As Integer`  
  
-   `Function Main(ByVal cmdArgs() As String) As Integer`  
  
 <span data-ttu-id="ca6af-168">이 절차의 가장 일반적인 것은 `Sub Main()`합니다.</span><span class="sxs-lookup"><span data-stu-id="ca6af-168">The most common variety of this procedure is `Sub Main()`.</span></span> <span data-ttu-id="ca6af-169">자세한 내용은 참조 [Visual Basic의 Main 프로시저](../../../visual-basic/programming-guide/program-structure/main-procedure.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ca6af-169">For more information, see [Main Procedure in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca6af-170">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ca6af-170">See Also</span></span>  
 [<span data-ttu-id="ca6af-171">Visual Basic의 main 프로시저</span><span class="sxs-lookup"><span data-stu-id="ca6af-171">Main Procedure in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/main-procedure.md)  
 [<span data-ttu-id="ca6af-172">Visual Basic 명명 규칙</span><span class="sxs-lookup"><span data-stu-id="ca6af-172">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)  
 [<span data-ttu-id="ca6af-173">Visual Basic 제한 사항</span><span class="sxs-lookup"><span data-stu-id="ca6af-173">Visual Basic Limitations</span></span>](../../../visual-basic/programming-guide/program-structure/limitations.md)
