---
title: Visual Basic의 조건부 컴파일
ms.date: 07/20/2015
helpviewer_keywords:
- conditional compilation [Visual Basic], about conditional compilation
- compilation [Visual Basic], conditional
ms.assetid: 9c35e55e-7eee-44fb-a586-dad1f1884848
ms.openlocfilehash: 496df36242c6b43e7e3ec94ce675d11177e8b466
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33653019"
---
# <a name="conditional-compilation-in-visual-basic"></a><span data-ttu-id="e5a5b-102">Visual Basic의 조건부 컴파일</span><span class="sxs-lookup"><span data-stu-id="e5a5b-102">Conditional Compilation in Visual Basic</span></span>
<span data-ttu-id="e5a5b-103">*조건부 컴파일*, 특정 코드 블록을 프로그램에서 선택적으로 컴파일되고 다른 특성을 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5a5b-103">In *conditional compilation*, particular blocks of code in a program are compiled selectively while others are ignored.</span></span>  
  
 <span data-ttu-id="e5a5b-104">작성 하려는 하는 예를 들어 여러 언어에 대 한 응용 프로그램을 지역화 하는 경우가 동일한 프로그래밍 작업에 다양 한 접근 방법의 속도 비교 하는 문을 디버깅 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5a5b-104">For example, you may want to write debugging statements that compare the speed of different approaches to the same programming task, or you may want to localize an application for multiple languages.</span></span> <span data-ttu-id="e5a5b-105">조건부 컴파일 문은 실행된 시간 아닌 컴파일 타임 중에 실행 하도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e5a5b-105">Conditional compilation statements are designed to run during compile time, not at run time.</span></span>  
  
 <span data-ttu-id="e5a5b-106">조건에 따라 사용 하 여 컴파일할 코드 블록을 나타내는 `#If...Then...#Else` 지시문입니다.</span><span class="sxs-lookup"><span data-stu-id="e5a5b-106">You denote blocks of code to be conditionally compiled with the `#If...Then...#Else` directive.</span></span> <span data-ttu-id="e5a5b-107">예를 들어 프랑스어, 독일어 언어를 만들려는 버전 같은 동일한 응용 프로그램의 소스 코드를 플랫폼 특정 코드 세그먼트를 포함 하면 `#If...Then` 미리 정의 된 상수를 사용 하 여 문을 `FrenchVersion` 및 `GermanVersion`합니다.</span><span class="sxs-lookup"><span data-stu-id="e5a5b-107">For example, to create French- and German-language versions of the same application from the same source code, you embed platform-specific code segments in `#If...Then` statements using the predefined constants `FrenchVersion` and `GermanVersion`.</span></span> <span data-ttu-id="e5a5b-108">다음 예제에서는 방법을:</span><span class="sxs-lookup"><span data-stu-id="e5a5b-108">The following example demonstrates how:</span></span>  
  
 [!code-vb[VbVbalrConditionalComp#5](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/conditional-compilation_1.vb)]  
  
 <span data-ttu-id="e5a5b-109">값을 설정 하는 경우는 `FrenchVersion` 조건부 컴파일 상수를 `True` 프랑스어 버전에 대 한 조건부 코드 컴파일 타임에 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5a5b-109">If you set the value of the `FrenchVersion` conditional compilation constant to `True` at compile time, the conditional code for the French version is compiled.</span></span> <span data-ttu-id="e5a5b-110">값을 설정 하는 경우는 `GermanVersion` 를 상수 `True`, 컴파일러는 독일어 버전을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5a5b-110">If you set the value of the `GermanVersion` constant to `True`, the compiler uses the German version.</span></span> <span data-ttu-id="e5a5b-111">설정 하지 않으면 `True`, 지난에서 코드 `Else` 블록이 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5a5b-111">If neither is set to `True`, the code in the last `Else` block runs.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e5a5b-112">자동 완성 코드를 편집 하는 경우 not 함수 및 코드의 현재 분기의 일부가 아닌 경우 조건부 컴파일 지시문을 사용 하 여 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5a5b-112">Autocompletion will not function when editing code and using conditional compilation directives if the code is not part of the current branch.</span></span>  
  
## <a name="declaring-conditional-compilation-constants"></a><span data-ttu-id="e5a5b-113">조건부 컴파일 상수 선언</span><span class="sxs-lookup"><span data-stu-id="e5a5b-113">Declaring Conditional Compilation Constants</span></span>  
 <span data-ttu-id="e5a5b-114">다음 세 가지 방법 중 하나에서 조건부 컴파일 상수를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5a5b-114">You can set conditional compilation constants in one of three ways:</span></span>  
  
-   <span data-ttu-id="e5a5b-115">에 **프로젝트 디자이너**</span><span class="sxs-lookup"><span data-stu-id="e5a5b-115">In the **Project Designer**</span></span>  
  
-   <span data-ttu-id="e5a5b-116">명령줄 컴파일러를 사용 하는 경우 명령줄에서</span><span class="sxs-lookup"><span data-stu-id="e5a5b-116">At the command line when using the command-line compiler</span></span>  
  
-   <span data-ttu-id="e5a5b-117">코드에서</span><span class="sxs-lookup"><span data-stu-id="e5a5b-117">In your code</span></span>  
  
 <span data-ttu-id="e5a5b-118">조건부 컴파일 상수는 특별 한 범위가 있으며 표준 코드에서 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e5a5b-118">Conditional compilation constants have a special scope and cannot be accessed from standard code.</span></span> <span data-ttu-id="e5a5b-119">조건부 컴파일 상수 범위 설정 방법에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="e5a5b-119">The scope of a conditional compilation constant is dependent on the way it is set.</span></span> <span data-ttu-id="e5a5b-120">다음 표에서 각 위에서 언급 한 세 가지 방법으로 사용 하 여 선언 된 상수 변수의 범위를 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5a5b-120">The following table lists the scope of constants declared using each of the three ways mentioned above.</span></span>  
  
|<span data-ttu-id="e5a5b-121">상수 설정 방법</span><span class="sxs-lookup"><span data-stu-id="e5a5b-121">How constant is set</span></span>|<span data-ttu-id="e5a5b-122">상수의 범위</span><span class="sxs-lookup"><span data-stu-id="e5a5b-122">Scope of constant</span></span>|  
|---|---|  
|<span data-ttu-id="e5a5b-123">**프로젝트 디자이너**</span><span class="sxs-lookup"><span data-stu-id="e5a5b-123">**Project Designer**</span></span>|<span data-ttu-id="e5a5b-124">프로젝트의 모든 파일</span><span class="sxs-lookup"><span data-stu-id="e5a5b-124">Public to all files in the project</span></span>|  
|<span data-ttu-id="e5a5b-125">명령줄</span><span class="sxs-lookup"><span data-stu-id="e5a5b-125">Command line</span></span>|<span data-ttu-id="e5a5b-126">명령줄 컴파일러에 전달 하는 모든 파일</span><span class="sxs-lookup"><span data-stu-id="e5a5b-126">Public to all files passed to the command-line compiler</span></span>|  
|<span data-ttu-id="e5a5b-127">`#Const` 코드에서 문</span><span class="sxs-lookup"><span data-stu-id="e5a5b-127">`#Const` statement in code</span></span>|<span data-ttu-id="e5a5b-128">이전에 선언 된 파일의 전용</span><span class="sxs-lookup"><span data-stu-id="e5a5b-128">Private to the file in which it is declared</span></span>|  
  
|<span data-ttu-id="e5a5b-129">프로젝트 디자이너의 상수를 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="e5a5b-129">To set constants in the Project Designer</span></span>|  
|---|  
|<span data-ttu-id="e5a5b-130">-실행 파일을 만들기 전에 다음을 수행 합니다 상수에서 설정 된 **프로젝트 디자이너** 에 제공 된 단계를 수행 하 여 [프로젝트 관리 및 솔루션 속성](/visualstudio/ide/managing-project-and-solution-properties)합니다.</span><span class="sxs-lookup"><span data-stu-id="e5a5b-130">-   Before creating your executable file, set constants in the **Project Designer** by following the steps provided in [Managing Project and Solution Properties](/visualstudio/ide/managing-project-and-solution-properties).</span></span>|  
  
|<span data-ttu-id="e5a5b-131">명령줄에서 상수를 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="e5a5b-131">To set constants at the command line</span></span>|  
|---|  
|<span data-ttu-id="e5a5b-132">-사용는 **/d** 스위치 조건부 컴파일 상수를 다음 예제와 같이 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5a5b-132">-   Use the **/d** switch to enter conditional compilation constants, as in the following example:</span></span><br />     `vbc MyProj.vb /d:conFrenchVersion=–1:conANSI=0`<br />     <span data-ttu-id="e5a5b-133">공간은 간의 필요 하지 않습니다는 **/d** 스위치와 첫 번째 상수입니다.</span><span class="sxs-lookup"><span data-stu-id="e5a5b-133">No space is required between the **/d** switch and the first constant.</span></span> <span data-ttu-id="e5a5b-134">자세한 내용은 참조 [/define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e5a5b-134">For more information, see [/define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md).</span></span><br />     <span data-ttu-id="e5a5b-135">명령줄 선언에 입력 된 선언을 재정의 **프로젝트 디자이너**, 있지만 삭제 하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e5a5b-135">Command-line declarations override declarations entered in the **Project Designer**, but do not erase them.</span></span> <span data-ttu-id="e5a5b-136">인수에 설정 **프로젝트 디자이너** 다음에 컴파일할 계속 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5a5b-136">Arguments set in **Project Designer** remain in effect for subsequent compilations.</span></span><br />     <span data-ttu-id="e5a5b-137">코드 자체 상수를 작성할 때 규칙이 없습니다 엄격한 해당 배치에 대 한 범위가 선언 된 전체 모듈 되므로 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5a5b-137">When writing constants in the code itself, there are no strict rules as to their placement, since their scope is the entire module in which they are declared.</span></span>|  
  
|<span data-ttu-id="e5a5b-138">코드에서 상수를 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="e5a5b-138">To set constants in your code</span></span>|  
|---|  
|<span data-ttu-id="e5a5b-139">-사용 되는 모듈의 선언 블록에 상수를 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="e5a5b-139">-   Place the constants in the declaration block of the module in which they are used.</span></span> <span data-ttu-id="e5a5b-140">이렇게 하면 코드가 구성 하 고 쉽게 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5a5b-140">This helps keep your code organized and easier to read.</span></span>|  
  
## <a name="related-topics"></a><span data-ttu-id="e5a5b-141">관련 항목</span><span class="sxs-lookup"><span data-stu-id="e5a5b-141">Related Topics</span></span>  
  
|<span data-ttu-id="e5a5b-142">제목</span><span class="sxs-lookup"><span data-stu-id="e5a5b-142">Title</span></span>|<span data-ttu-id="e5a5b-143">설명</span><span class="sxs-lookup"><span data-stu-id="e5a5b-143">Description</span></span>|  
|---|---|  
|[<span data-ttu-id="e5a5b-144">프로그램 구조 및 코드 규칙</span><span class="sxs-lookup"><span data-stu-id="e5a5b-144">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)|<span data-ttu-id="e5a5b-145">코드를 더 쉽게 읽고 유지 관리를 제안 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5a5b-145">Provides suggestions for making your code easy to read and maintain.</span></span>|  
  
## <a name="reference"></a><span data-ttu-id="e5a5b-146">참조</span><span class="sxs-lookup"><span data-stu-id="e5a5b-146">Reference</span></span>  
 [<span data-ttu-id="e5a5b-147">#Const 지시문</span><span class="sxs-lookup"><span data-stu-id="e5a5b-147">#Const Directive</span></span>](../../../visual-basic/language-reference/directives/const-directive.md)  
  
 [<span data-ttu-id="e5a5b-148">#If...Then...#Else 지시문</span><span class="sxs-lookup"><span data-stu-id="e5a5b-148">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
  
 [<span data-ttu-id="e5a5b-149">/define (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e5a5b-149">/define (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/define.md)
