---
title: "프로그램 구조 및 코드 규칙(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- coding conventions
- Visual Basic code, coding conventions
- coding conventions [Visual Basic], Visual Basic
- programs [Visual Basic], structure
- program structure [Visual Basic]
- naming conventions [Visual Basic], Visual Basic
- best practices [Visual Basic], coding conventions
- conventions [Visual Basic], Visual Basic coding
- Visual Basic code
- programming [Visual Basic], Visual Basic coding conventions
ms.assetid: dd9be76f-6944-4e78-ad72-0b6084a3fc13
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b38ba9623a20dcd1be4bc96f4aff1eb646b0a053
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="program-structure-and-code-conventions-visual-basic"></a><span data-ttu-id="054bf-102">프로그램 구조 및 코드 규칙(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="054bf-102">Program Structure and Code Conventions (Visual Basic)</span></span>
<span data-ttu-id="054bf-103">이 섹션에서는 일반적인 소개 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 프로그램 구조는 간단한 제공 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] "Hello, World"를 프로그래밍 하 고 설명 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 코드 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="054bf-103">This section introduces the typical [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] program structure, provides a simple [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] program, "Hello, World", and discusses [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] code conventions.</span></span> <span data-ttu-id="054bf-104">코드 규칙은 프로그램의 논리에 없는 있지만 물리적 구조 및 모양에 집중 하는 제안 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="054bf-104">Code conventions are suggestions that focus not on a program's logic but on its physical structure and appearance.</span></span> <span data-ttu-id="054bf-105">그 뒤에 더 쉽게 코드를 읽고, 이해 하며 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="054bf-105">Following them makes your code easier to read, understand, and maintain.</span></span> <span data-ttu-id="054bf-106">코드 규칙 다른 규칙 으로부터 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="054bf-106">Code conventions can include, among others:</span></span>  
  
-   <span data-ttu-id="054bf-107">레이블 및 주석 코드는 표준화 된 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="054bf-107">Standardized formats for labeling and commenting code.</span></span>  
  
-   <span data-ttu-id="054bf-108">간격, 서식 및 코드 들여쓰기에 대 한 지침입니다.</span><span class="sxs-lookup"><span data-stu-id="054bf-108">Guidelines for spacing, formatting, and indenting code.</span></span>  
  
-   <span data-ttu-id="054bf-109">개체, 변수 및 프로시저에 대 한 명명 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="054bf-109">Naming conventions for objects, variables, and procedures.</span></span>  
  
 <span data-ttu-id="054bf-110">다음 항목의 프로그래밍에 대 한 지침을 제공 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 좋은 사용 예제를 보여 프로그램.</span><span class="sxs-lookup"><span data-stu-id="054bf-110">The following topics present a set of programming guidelines for [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] programs, along with examples of good usage.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="054bf-111">단원 내용</span><span class="sxs-lookup"><span data-stu-id="054bf-111">In This Section</span></span>  
 [<span data-ttu-id="054bf-112">Visual Basic 프로그램의 구조</span><span class="sxs-lookup"><span data-stu-id="054bf-112">Structure of a Visual Basic Program</span></span>](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)  
 <span data-ttu-id="054bf-113">구성 하는 요소에 간략하게는 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 프로그램.</span><span class="sxs-lookup"><span data-stu-id="054bf-113">Provides an overview of the elements that make up a [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] program.</span></span>  
  
 [<span data-ttu-id="054bf-114">Visual Basic의 main 프로시저</span><span class="sxs-lookup"><span data-stu-id="054bf-114">Main Procedure in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/main-procedure.md)  
 <span data-ttu-id="054bf-115">가리키고 응용 프로그램에 대해 전체적으로 제어 하는 시작 하는 데 사용 하는 절차를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="054bf-115">Discusses the procedure that serves as the starting point and overall control for your application.</span></span>  
  
 [<span data-ttu-id="054bf-116">참조 및 Imports 문</span><span class="sxs-lookup"><span data-stu-id="054bf-116">References and the Imports Statement</span></span>](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)  
 <span data-ttu-id="054bf-117">다른 어셈블리의 개체를 참조 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="054bf-117">Discusses how to reference objects in other assemblies.</span></span>  
  
 [<span data-ttu-id="054bf-118">Visual Basic의 네임 스페이스</span><span class="sxs-lookup"><span data-stu-id="054bf-118">Namespaces in Visual Basic</span></span>](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 <span data-ttu-id="054bf-119">네임 스페이스 어셈블리 내에서 개체를 구성 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="054bf-119">Describes how namespaces organize objects within assemblies.</span></span>  
  
 [<span data-ttu-id="054bf-120">Visual Basic 명명 규칙</span><span class="sxs-lookup"><span data-stu-id="054bf-120">Visual Basic Naming Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)  
 <span data-ttu-id="054bf-121">프로시저, 상수, 변수, 인수 및 개체 이름을 지정 하기 위한 일반 지침이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="054bf-121">Includes general guidelines for naming procedures, constants, variables, arguments, and objects.</span></span>  
  
 [<span data-ttu-id="054bf-122">Visual Basic 코딩 규칙</span><span class="sxs-lookup"><span data-stu-id="054bf-122">Visual Basic Coding Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/coding-conventions.md)  
 <span data-ttu-id="054bf-123">이 설명서의 예제를 개발에 사용 되는 지침을 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="054bf-123">Reviews the guidelines used in developing the samples in this documentation.</span></span>  
  
 [<span data-ttu-id="054bf-124">조건부 컴파일</span><span class="sxs-lookup"><span data-stu-id="054bf-124">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 <span data-ttu-id="054bf-125">다른 사용자를 무시 하도록 컴파일러에 지시 하는 동안 코드의 특정 요소를 선택적으로 컴파일하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="054bf-125">Describes how to compile particular blocks of code selectively while directing the compiler to ignore others.</span></span>  
  
 [<span data-ttu-id="054bf-126">방법: 코드에서 문 분리 및 결합</span><span class="sxs-lookup"><span data-stu-id="054bf-126">How to: Break and Combine Statements in Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)  
 <span data-ttu-id="054bf-127">긴 문은 여러 줄으로 나눈 다음 짧은 문을 한 줄에 결합 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="054bf-127">Shows how to divide long statements into multiple lines and combine short statements on one line.</span></span>  
  
 [<span data-ttu-id="054bf-128">방법: 코드 섹션 축소 및 숨기기</span><span class="sxs-lookup"><span data-stu-id="054bf-128">How to: Collapse and Hide Sections of Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-collapse-and-hide-sections-of-code.md)  
 <span data-ttu-id="054bf-129">코드 섹션 축소 및 숨기기 하는 방법을 보여 줍니다.는 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 코드 편집기.</span><span class="sxs-lookup"><span data-stu-id="054bf-129">Shows how to collapse and hide sections of code in the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] code editor.</span></span>  
  
 [<span data-ttu-id="054bf-130">방법: Label 문</span><span class="sxs-lookup"><span data-stu-id="054bf-130">How to: Label Statements</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)  
 <span data-ttu-id="054bf-131">사용 하기 위해 문 같은 식별 하는 코드 줄을 표시 하는 방법을 보여 줍니다. `On Error Goto`합니다.</span><span class="sxs-lookup"><span data-stu-id="054bf-131">Shows how to mark a line of code to identify it for use with statements such as `On Error Goto`.</span></span>  
  
 [<span data-ttu-id="054bf-132">코드의 특수 문자</span><span class="sxs-lookup"><span data-stu-id="054bf-132">Special Characters in Code</span></span>](../../../visual-basic/programming-guide/program-structure/special-characters-in-code.md)  
 <span data-ttu-id="054bf-133">위치와 방법을 보여 줍니다. 숫자가 아닌 및-알파벳 이외의 문자를 사용 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="054bf-133">Shows how and where to use non-numeric and non-alphabetic characters.</span></span>  
  
 [<span data-ttu-id="054bf-134">코드 주석</span><span class="sxs-lookup"><span data-stu-id="054bf-134">Comments in Code</span></span>](../../../visual-basic/programming-guide/program-structure/comments-in-code.md)  
 <span data-ttu-id="054bf-135">코드에 설명 주석을 추가 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="054bf-135">Discusses how to add descriptive comments to your code.</span></span>  
  
 [<span data-ttu-id="054bf-136">코드에서 요소 이름으로 사용되는 키워드</span><span class="sxs-lookup"><span data-stu-id="054bf-136">Keywords as Element Names in Code</span></span>](../../../visual-basic/programming-guide/program-structure/keywords-as-element-names-in-code.md)  
 <span data-ttu-id="054bf-137">대괄호를 사용 하는 방법에 설명 (`[]`)도 변수 이름을 구분 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="054bf-137">Describes how to use brackets (`[]`) to delimit variable names that are also [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] keywords.</span></span>  
  
 [<span data-ttu-id="054bf-138">Me, My, MyBase 및 MyClass</span><span class="sxs-lookup"><span data-stu-id="054bf-138">Me, My, MyBase, and MyClass</span></span>](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 <span data-ttu-id="054bf-139">요소를 참조 하는 다양 한 방법을 설명는 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 프로그램.</span><span class="sxs-lookup"><span data-stu-id="054bf-139">Describes various ways to refer to elements of a [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] program.</span></span>  
  
 [<span data-ttu-id="054bf-140">Visual Basic 제한 사항</span><span class="sxs-lookup"><span data-stu-id="054bf-140">Visual Basic Limitations</span></span>](../../../visual-basic/programming-guide/program-structure/limitations.md)  
 <span data-ttu-id="054bf-141">설명의 내에서 알려진된 코딩 제한 사항 제거 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="054bf-141">Discusses the removal of known coding limits within [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="054bf-142">관련 단원</span><span class="sxs-lookup"><span data-stu-id="054bf-142">Related Sections</span></span>  
 [<span data-ttu-id="054bf-143">글꼴 표시 및 코드 규칙</span><span class="sxs-lookup"><span data-stu-id="054bf-143">Typographic and Code Conventions</span></span>](../../../visual-basic/language-reference/typographic-and-code-conventions.md)  
 <span data-ttu-id="054bf-144">에 대 한 표준 코딩 규칙을 제공 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="054bf-144">Provides standard coding conventions for [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span>  
  
 [<span data-ttu-id="054bf-145">코드 작성</span><span class="sxs-lookup"><span data-stu-id="054bf-145">Writing Code</span></span>](/visualstudio/ide/writing-code-in-the-code-and-text-editor)  
 <span data-ttu-id="054bf-146">보다 쉽게 작성 하 고 코드를 관리할 수 있도록 지 원하는 기능을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="054bf-146">Describes features that make it easier for you to write and manage your code.</span></span>
