---
title: "C# 코딩 규칙(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- coding conventions, C#
- Visual C#, coding conventions
- C# language, coding conventions
ms.assetid: f4f60de9-d49b-4fb6-bab1-20e19ea24710
caps.latest.revision: 32
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 9f32fdc0eb1954cdac30c39e05c74d43301d850c
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="c-coding-conventions-c-programming-guide"></a><span data-ttu-id="f0285-102">C# 코딩 규칙(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="f0285-102">C# Coding Conventions (C# Programming Guide)</span></span>
<span data-ttu-id="f0285-103">[C# Language Specification](http://go.microsoft.com/fwlink/?LinkId=199552)(C# 언어 사양)에서는 코딩 표준을 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f0285-103">The [C# Language Specification](http://go.microsoft.com/fwlink/?LinkId=199552) does not define a coding standard.</span></span> <span data-ttu-id="f0285-104">그러나 이 항목의 지침은 Microsoft에서 샘플과 설명서를 개발하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0285-104">However, the guidelines in this topic are used by Microsoft to develop samples and documentation.</span></span>  
  
 <span data-ttu-id="f0285-105">코딩 규칙은 다음과 같은 용도로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0285-105">Coding conventions serve the following purposes:</span></span>  
  
-   <span data-ttu-id="f0285-106">코드를 확인하는 사용자들이 레이아웃이 아닌 내용에 집중할 수 있도록 일관성 있게 표시되는 코드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f0285-106">They create a consistent look to the code, so that readers can focus on content, not layout.</span></span>  
  
-   <span data-ttu-id="f0285-107">코드를 확인하는 사용자들이 이전 경험을 토대로 한 가정을 통해 코드를 보다 빠르게 이해할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0285-107">They enable readers to understand the code more quickly by making assumptions based on previous experience.</span></span>  
  
-   <span data-ttu-id="f0285-108">코드를 보다 쉽게 복사, 변경 및 유지 관리할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0285-108">They facilitate copying, changing, and maintaining the code.</span></span>  
  
-   <span data-ttu-id="f0285-109">C# 모범 사례를 제시합니다.</span><span class="sxs-lookup"><span data-stu-id="f0285-109">They demonstrate C# best practices.</span></span>  
  
## <a name="naming-conventions"></a><span data-ttu-id="f0285-110">명명 규칙</span><span class="sxs-lookup"><span data-stu-id="f0285-110">Naming Conventions</span></span>  
  
-   <span data-ttu-id="f0285-111">[using 지시문](../../../csharp/language-reference/keywords/using-directive.md)이 포함되지 않는 간단한 예제에서 네임스페이스 한정자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f0285-111">In short examples that do not include [using directives](../../../csharp/language-reference/keywords/using-directive.md), use namespace qualifications.</span></span> <span data-ttu-id="f0285-112">프로젝트에서 네임스페이스를 기본적으로 가져오는 경우에는 해당 네임스페이스의 이름을 정규화하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0285-112">If you know that a namespace is imported by default in a project, you do not have to fully qualify the names from that namespace.</span></span> <span data-ttu-id="f0285-113">정규화된 이름은 한 줄에 표시하기가 너무 길면 다음 예제에 나와 있는 것처럼 점(.)으로 분할할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0285-113">Qualified names can be broken after a dot (.) if they are too long for a single line, as shown in the following example.</span></span>  
  
     <span data-ttu-id="f0285-114">[!code-cs[csProgGuideCodingConventions#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="f0285-114">[!code-cs[csProgGuideCodingConventions#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_1.cs)]</span></span>  
  
-   <span data-ttu-id="f0285-115">다른 지침에 맞도록 조정하기 위해 Visual Studio 디자이너 도구를 사용하여 만든 개체 이름을 변경할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f0285-115">You do not have to change the names of objects that were created by using the Visual Studio designer tools to make them fit other guidelines.</span></span>  
  
## <a name="layout-conventions"></a><span data-ttu-id="f0285-116">레이아웃 규칙</span><span class="sxs-lookup"><span data-stu-id="f0285-116">Layout Conventions</span></span>  
 <span data-ttu-id="f0285-117">효율적인 레이아웃에서는 서식을 사용하여 코드 구조를 강조하고 코드를 보다 쉽게 읽을 수 있도록 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="f0285-117">Good layout uses formatting to emphasize the structure of your code and to make the code easier to read.</span></span> <span data-ttu-id="f0285-118">Microsoft 예제 및 샘플은 다음 규칙을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="f0285-118">Microsoft examples and samples conform to the following conventions:</span></span>  
  
-   <span data-ttu-id="f0285-119">기본 코드 편집기 설정(스마트 들여쓰기, 4자 들여쓰기, 탭을 공백으로 저장)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f0285-119">Use the default Code Editor settings (smart indenting, four-character indents, tabs saved as spaces).</span></span> <span data-ttu-id="f0285-120">자세한 내용은 [옵션, 텍스트 편집기, C#, 서식](/visualstudio/ide/reference/options-text-editor-csharp-formatting)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f0285-120">For more information, see [Options, Text Editor, C#, Formatting](/visualstudio/ide/reference/options-text-editor-csharp-formatting).</span></span>  
  
-   <span data-ttu-id="f0285-121">문을 한 줄에 하나씩만 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="f0285-121">Write only one statement per line.</span></span>  
  
-   <span data-ttu-id="f0285-122">선언을 한 줄에 하나씩만 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="f0285-122">Write only one declaration per line.</span></span>  
  
-   <span data-ttu-id="f0285-123">연속 줄이 자동으로 들여쓰기되지 않으면 탭 정지 하나(공백 4개)만큼 들여씁니다.</span><span class="sxs-lookup"><span data-stu-id="f0285-123">If continuation lines are not indented automatically, indent them one tab stop (four spaces).</span></span>  
  
-   <span data-ttu-id="f0285-124">메서드 정의와 속성 정의 간에는 빈 줄을 하나 이상 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f0285-124">Add at least one blank line between method definitions and property definitions.</span></span>  
  
-   <span data-ttu-id="f0285-125">다음 코드에 나와 있는 것처럼 괄호를 사용하여 식의 절을 명확하게 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="f0285-125">Use parentheses to make clauses in an expression apparent, as shown in the following code.</span></span>  
  
     <span data-ttu-id="f0285-126">[!code-cs[csProgGuideCodingConventions#2](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="f0285-126">[!code-cs[csProgGuideCodingConventions#2](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_2.cs)]</span></span>  
  
## <a name="commenting-conventions"></a><span data-ttu-id="f0285-127">주석 규칙</span><span class="sxs-lookup"><span data-stu-id="f0285-127">Commenting Conventions</span></span>  
  
-   <span data-ttu-id="f0285-128">코드 줄의 끝이 아닌 별도의 줄에 주석을 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="f0285-128">Place the comment on a separate line, not at the end of a line of code.</span></span>  
  
-   <span data-ttu-id="f0285-129">주석 텍스트는 대문자로 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="f0285-129">Begin comment text with an uppercase letter.</span></span>  
  
-   <span data-ttu-id="f0285-130">주석 텍스트 끝에는 마침표를 붙입니다.</span><span class="sxs-lookup"><span data-stu-id="f0285-130">End comment text with a period.</span></span>  
  
-   <span data-ttu-id="f0285-131">다음 코드에 나와 있는 것처럼 주석 구분 기호(//)와 주석 텍스트 사이에 공백을 하나 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="f0285-131">Insert one space between the comment delimiter (//) and the comment text, as shown in the following example.</span></span>  
  
     <span data-ttu-id="f0285-132">[!code-cs[csProgGuideCodingConventions#3](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="f0285-132">[!code-cs[csProgGuideCodingConventions#3](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_3.cs)]</span></span>  
  
-   <span data-ttu-id="f0285-133">서식이 지정된 별표 블록으로 주석을 묶지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f0285-133">Do not create formatted blocks of asterisks around comments.</span></span>  
  
## <a name="language-guidelines"></a><span data-ttu-id="f0285-134">언어 지침</span><span class="sxs-lookup"><span data-stu-id="f0285-134">Language Guidelines</span></span>  
 <span data-ttu-id="f0285-135">다음 섹션에서는 C# 팀이 코드 예제와 샘플을 준비할 때 따르는 방식에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f0285-135">The following sections describe practices that the C# team follows to prepare code examples and samples.</span></span>  
  
### <a name="string-data-type"></a><span data-ttu-id="f0285-136">문자열 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="f0285-136">String Data Type</span></span>  
  
-   <span data-ttu-id="f0285-137">다음 코드에 나와 있는 것처럼 `+` 연산자를 사용하여 짧은 문자열을 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="f0285-137">Use the `+` operator to concatenate short strings, as shown in the following code.</span></span>  
  
     <span data-ttu-id="f0285-138">[!code-cs[csProgGuideCodingConventions#6](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="f0285-138">[!code-cs[csProgGuideCodingConventions#6](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_4.cs)]</span></span>  
  
-   <span data-ttu-id="f0285-139">특히 많은 양의 텍스트를 사용할 때 문자열을 루프에 추가하려면 <xref:System.Text.StringBuilder> 개체를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f0285-139">To append strings in loops, especially when you are working with large amounts of text, use a <xref:System.Text.StringBuilder> object.</span></span>  
  
     <span data-ttu-id="f0285-140">[!code-cs[csProgGuideCodingConventions#7](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="f0285-140">[!code-cs[csProgGuideCodingConventions#7](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_5.cs)]</span></span>  
  
### <a name="implicitly-typed-local-variables"></a><span data-ttu-id="f0285-141">암시적으로 형식화한 지역 변수</span><span class="sxs-lookup"><span data-stu-id="f0285-141">Implicitly Typed Local Variables</span></span>  
  
-   <span data-ttu-id="f0285-142">할당 오른쪽에서 변수 형식이 명확하거나 정확한 형식이 중요하지 않으면 지역 변수에 대해 [암시적 형식](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f0285-142">Use [implicit typing](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md) for local variables when the type of the variable is obvious from the right side of the assignment, or when the precise type is not important.</span></span>  
  
     <span data-ttu-id="f0285-143">[!code-cs[csProgGuideCodingConventions#8](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="f0285-143">[!code-cs[csProgGuideCodingConventions#8](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_6.cs)]</span></span>  
  
-   <span data-ttu-id="f0285-144">할당 오른쪽에서 변수 형식이 명확하지 않으면 [var](../../../csharp/language-reference/keywords/var.md)를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f0285-144">Do not use [var](../../../csharp/language-reference/keywords/var.md) when the type is not apparent from the right side of the assignment.</span></span>  
  
     <span data-ttu-id="f0285-145">[!code-cs[csProgGuideCodingConventions#9](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="f0285-145">[!code-cs[csProgGuideCodingConventions#9](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_7.cs)]</span></span>  
  
-   <span data-ttu-id="f0285-146">변수 이름을 사용하여 변수 형식을 지정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f0285-146">Do not rely on the variable name to specify the type of the variable.</span></span> <span data-ttu-id="f0285-147">이렇게 하면 형식이 올바르게 지정되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0285-147">It might not be correct.</span></span>  
  
     <span data-ttu-id="f0285-148">[!code-cs[csProgGuideCodingConventions#10](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_8.cs)]</span><span class="sxs-lookup"><span data-stu-id="f0285-148">[!code-cs[csProgGuideCodingConventions#10](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_8.cs)]</span></span>  
  
-   <span data-ttu-id="f0285-149">[dynamic](../../../csharp/language-reference/keywords/dynamic.md) 대신 `var`를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f0285-149">Avoid the use of `var` in place of [dynamic](../../../csharp/language-reference/keywords/dynamic.md).</span></span>  
  
-   <span data-ttu-id="f0285-150">[for](../../../csharp/language-reference/keywords/for.md) 및 [foreach](../../../csharp/language-reference/keywords/foreach-in.md) 루프의 루프 변수 형식을 결정하려면 암시적 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f0285-150">Use implicit typing to determine the type of the loop variable in [for](../../../csharp/language-reference/keywords/for.md) and [foreach](../../../csharp/language-reference/keywords/foreach-in.md) loops.</span></span>  
  
     <span data-ttu-id="f0285-151">다음 예제에서는 `for` 문에서 암시적 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f0285-151">The following example uses implicit typing in a `for` statement.</span></span>  
  
     <span data-ttu-id="f0285-152">[!code-cs[csProgGuideCodingConventions#11](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_9.cs)]</span><span class="sxs-lookup"><span data-stu-id="f0285-152">[!code-cs[csProgGuideCodingConventions#11](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_9.cs)]</span></span>  
  
     <span data-ttu-id="f0285-153">다음 예제에서는 `foreach` 문에서 암시적 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f0285-153">The following example uses implicit typing in a `foreach` statement.</span></span>  
  
     <span data-ttu-id="f0285-154">[!code-cs[csProgGuideCodingConventions#12](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_10.cs)]</span><span class="sxs-lookup"><span data-stu-id="f0285-154">[!code-cs[csProgGuideCodingConventions#12](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_10.cs)]</span></span>  
  
### <a name="unsigned-data-type"></a><span data-ttu-id="f0285-155">부호 없는 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="f0285-155">Unsigned Data Type</span></span>  
  
-   <span data-ttu-id="f0285-156">일반적으로는 부호 없는 형식 대신 `int`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f0285-156">In general, use `int` rather than unsigned types.</span></span> <span data-ttu-id="f0285-157">`int`는 C# 전체에서 일반적으로 사용되며, `int`를 사용하는 경우 다른 라이브러리와 보다 쉽게 상호 작용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0285-157">The use of `int` is common throughout C#, and it is easier to interact with other libraries when you use `int`.</span></span>  
  
### <a name="arrays"></a><span data-ttu-id="f0285-158">배열</span><span class="sxs-lookup"><span data-stu-id="f0285-158">Arrays</span></span>  
  
-   <span data-ttu-id="f0285-159">선언 줄에서 배열을 초기화할 때는 간결한 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f0285-159">Use the concise syntax when you initialize arrays on the declaration line.</span></span>  
  
     <span data-ttu-id="f0285-160">[!code-cs[csProgGuideCodingConventions#13](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_11.cs)]</span><span class="sxs-lookup"><span data-stu-id="f0285-160">[!code-cs[csProgGuideCodingConventions#13](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_11.cs)]</span></span>  
  
### <a name="delegates"></a><span data-ttu-id="f0285-161">대리자</span><span class="sxs-lookup"><span data-stu-id="f0285-161">Delegates</span></span>  
  
-   <span data-ttu-id="f0285-162">대리자 형식의 인스턴스를 만들려면 간결한 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f0285-162">Use the concise syntax to create instances of a delegate type.</span></span>  
  
     <span data-ttu-id="f0285-163">[!code-cs[csProgGuideCodingConventions#14](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_12.cs)]</span><span class="sxs-lookup"><span data-stu-id="f0285-163">[!code-cs[csProgGuideCodingConventions#14](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_12.cs)]</span></span>  
  
     <span data-ttu-id="f0285-164">[!code-cs[csProgGuideCodingConventions#15](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_13.cs)]</span><span class="sxs-lookup"><span data-stu-id="f0285-164">[!code-cs[csProgGuideCodingConventions#15](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_13.cs)]</span></span>  
  
### <a name="try-catch-and-using-statements-in-exception-handling"></a><span data-ttu-id="f0285-165">예외 처리의 try-catch 및 using 문</span><span class="sxs-lookup"><span data-stu-id="f0285-165">try-catch and using Statements in Exception Handling</span></span>  
  
-   <span data-ttu-id="f0285-166">대부분의 예외 처리에서는 [try-catch](../../../csharp/language-reference/keywords/try-catch.md) 문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f0285-166">Use a [try-catch](../../../csharp/language-reference/keywords/try-catch.md) statement for most exception handling.</span></span>  
  
     <span data-ttu-id="f0285-167">[!code-cs[csProgGuideCodingConventions#16](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_14.cs)]</span><span class="sxs-lookup"><span data-stu-id="f0285-167">[!code-cs[csProgGuideCodingConventions#16](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_14.cs)]</span></span>  
  
-   <span data-ttu-id="f0285-168">C# [using 문](../../../csharp/language-reference/keywords/using-statement.md)을 사용하면 코드를 간소화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0285-168">Simplify your code by using the C# [using statement](../../../csharp/language-reference/keywords/using-statement.md).</span></span> <span data-ttu-id="f0285-169">`finally` 블록의 코드가 <xref:System.IDisposable.Dispose%2A> 메서드 호출뿐인 [try-finally](../../../csharp/language-reference/keywords/try-finally.md) 문이 있는 경우에는 `using` 문을 대신 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f0285-169">If you have a [try-finally](../../../csharp/language-reference/keywords/try-finally.md) statement in which the only code in the `finally` block is a call to the <xref:System.IDisposable.Dispose%2A> method, use a `using` statement instead.</span></span>  
  
     <span data-ttu-id="f0285-170">[!code-cs[csProgGuideCodingConventions#17](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_15.cs)]</span><span class="sxs-lookup"><span data-stu-id="f0285-170">[!code-cs[csProgGuideCodingConventions#17](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_15.cs)]</span></span>  
  
### <a name="-and-124124-operators"></a><span data-ttu-id="f0285-171">&& 및 &#124;&#124; 연산자</span><span class="sxs-lookup"><span data-stu-id="f0285-171">&& and &#124;&#124; Operators</span></span>  
  
-   <span data-ttu-id="f0285-172">예외를 방지하고 불필요한 비교를 건너뛰어 성능을 개선하려면 비교를 수행할 때 다음 예제에 나와 있는 것처럼 [&](../../../csharp/language-reference/operators/and-operator.md) 대신 [&&](../../../csharp/language-reference/operators/conditional-and-operator.md)를 사용하고 [&#124;](../../../csharp/language-reference/operators/or-operator.md) 대신 [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f0285-172">To avoid exceptions and increase performance by skipping unnecessary comparisons, use [&&](../../../csharp/language-reference/operators/conditional-and-operator.md) instead of [&](../../../csharp/language-reference/operators/and-operator.md) and [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md) instead of [&#124;](../../../csharp/language-reference/operators/or-operator.md) when you perform comparisons, as shown in the following example.</span></span>  
  
     <span data-ttu-id="f0285-173">[!code-cs[csProgGuideCodingConventions#18](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_16.cs)]</span><span class="sxs-lookup"><span data-stu-id="f0285-173">[!code-cs[csProgGuideCodingConventions#18](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_16.cs)]</span></span>  
  
### <a name="new-operator"></a><span data-ttu-id="f0285-174">New 연산자</span><span class="sxs-lookup"><span data-stu-id="f0285-174">New Operator</span></span>  
  
-   <span data-ttu-id="f0285-175">다음 선언에 나와 있는 것처럼 암시적 형식이 포함된 간결한 형태의 개체 인스턴스화를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f0285-175">Use the concise form of object instantiation, with implicit typing, as shown in the following declaration.</span></span>  
  
     <span data-ttu-id="f0285-176">[!code-cs[csProgGuideCodingConventions#19](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_17.cs)]</span><span class="sxs-lookup"><span data-stu-id="f0285-176">[!code-cs[csProgGuideCodingConventions#19](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_17.cs)]</span></span>  
  
     <span data-ttu-id="f0285-177">위의 줄은 다음 선언과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="f0285-177">The previous line is equivalent to the following declaration.</span></span>  
  
     <span data-ttu-id="f0285-178">[!code-cs[csProgGuideCodingConventions#20](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_18.cs)]</span><span class="sxs-lookup"><span data-stu-id="f0285-178">[!code-cs[csProgGuideCodingConventions#20](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_18.cs)]</span></span>  
  
-   <span data-ttu-id="f0285-179">개체를 간편하게 만들려면 개체 이니셜라이저를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f0285-179">Use object initializers to simplify object creation.</span></span>  
  
     <span data-ttu-id="f0285-180">[!code-cs[csProgGuideCodingConventions#21](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_19.cs)]</span><span class="sxs-lookup"><span data-stu-id="f0285-180">[!code-cs[csProgGuideCodingConventions#21](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_19.cs)]</span></span>  
  
### <a name="event-handling"></a><span data-ttu-id="f0285-181">이벤트 처리</span><span class="sxs-lookup"><span data-stu-id="f0285-181">Event Handling</span></span>  
  
-   <span data-ttu-id="f0285-182">나중에 제거할 필요가 없는 이벤트 처리기를 정의하는 경우 람다 식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f0285-182">If you are defining an event handler that you do not need to remove later, use a lambda expression.</span></span>  
  
     <span data-ttu-id="f0285-183">[!code-cs[csProgGuideCodingConventions#22](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_20.cs)]</span><span class="sxs-lookup"><span data-stu-id="f0285-183">[!code-cs[csProgGuideCodingConventions#22](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_20.cs)]</span></span>  
  
     <span data-ttu-id="f0285-184">[!code-cs[csProgGuideCodingConventions#23](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_21.cs)]</span><span class="sxs-lookup"><span data-stu-id="f0285-184">[!code-cs[csProgGuideCodingConventions#23](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_21.cs)]</span></span>  
  
### <a name="static-members"></a><span data-ttu-id="f0285-185">정적 멤버</span><span class="sxs-lookup"><span data-stu-id="f0285-185">Static Members</span></span>  
  
-   <span data-ttu-id="f0285-186">*ClassName.StaticMember*와 같이 클래스 이름을 사용하여 [static](../../../csharp/language-reference/keywords/static.md) 멤버를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="f0285-186">Call [static](../../../csharp/language-reference/keywords/static.md) members by using the class name: *ClassName.StaticMember*.</span></span> <span data-ttu-id="f0285-187">이렇게 하면 정적 액세스가 명확하게 표시되므로 코드를 보다 쉽게 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0285-187">This practice makes code more readable by making static access clear.</span></span>  <span data-ttu-id="f0285-188">파생 클래스 이름을 사용하여 기본 클래스에 정의된 정적 멤버를 정규화해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0285-188">Do not qualify a static member defined in a base class with the name of a derived class.</span></span>  <span data-ttu-id="f0285-189">이 코드는 컴파일되기는 하지만 가독성이 떨어지며 나중에 파생 클래스와 이름이 같은 정적 멤버를 추가하면 코드가 손상될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0285-189">While that code compiles, the code readability is misleading, and the code may break in the future if you add a static member with the same name to the derived class.</span></span>  
  
### <a name="linq-queries"></a><span data-ttu-id="f0285-190">LINQ 쿼리</span><span class="sxs-lookup"><span data-stu-id="f0285-190">LINQ Queries</span></span>  
  
-   <span data-ttu-id="f0285-191">쿼리 변수에 의미 있는 이름을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f0285-191">Use meaningful names for query variables.</span></span> <span data-ttu-id="f0285-192">다음 예제에서는 Seattle 거주 고객에 대해 `seattleCustomers`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f0285-192">The following example uses `seattleCustomers` for customers who are located in Seattle.</span></span>  
  
     <span data-ttu-id="f0285-193">[!code-cs[csProgGuideCodingConventions#25](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_22.cs)]</span><span class="sxs-lookup"><span data-stu-id="f0285-193">[!code-cs[csProgGuideCodingConventions#25](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_22.cs)]</span></span>  
  
-   <span data-ttu-id="f0285-194">별칭을 사용하여 익명 형식의 속성 이름 대/소문자를 올바르게 표시합니다(파스칼식 대/소문자 사용).</span><span class="sxs-lookup"><span data-stu-id="f0285-194">Use aliases to make sure that property names of anonymous types are correctly capitalized, using Pascal casing.</span></span>  
  
     <span data-ttu-id="f0285-195">[!code-cs[csProgGuideCodingConventions#26](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_23.cs)]</span><span class="sxs-lookup"><span data-stu-id="f0285-195">[!code-cs[csProgGuideCodingConventions#26](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_23.cs)]</span></span>  
  
-   <span data-ttu-id="f0285-196">결과의 속성 이름이 모호하면 속성 이름을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="f0285-196">Rename properties when the property names in the result would be ambiguous.</span></span> <span data-ttu-id="f0285-197">예를 들어 쿼리에서 고객 이름과 배포자 ID를 반환하는 경우 결과에서 이러한 정보를 `Name` 및 `ID`로 유지하는 대신 `Name`은 고객의 이름이고 `ID`는 배포자의 ID임을 명확하게 나타내도록 이름을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="f0285-197">For example, if your query returns a customer name and a distributor ID, instead of leaving them as `Name` and `ID` in the result, rename them to clarify that `Name` is the name of a customer, and `ID` is the ID of a distributor.</span></span>  
  
     <span data-ttu-id="f0285-198">[!code-cs[csProgGuideCodingConventions#27](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_24.cs)]</span><span class="sxs-lookup"><span data-stu-id="f0285-198">[!code-cs[csProgGuideCodingConventions#27](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_24.cs)]</span></span>  
  
-   <span data-ttu-id="f0285-199">쿼리 변수 및 범위 변수의 선언에서 암시적 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f0285-199">Use implicit typing in the declaration of query variables and range variables.</span></span>  
  
     <span data-ttu-id="f0285-200">[!code-cs[csProgGuideCodingConventions#25](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_22.cs)]</span><span class="sxs-lookup"><span data-stu-id="f0285-200">[!code-cs[csProgGuideCodingConventions#25](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_22.cs)]</span></span>  
  
-   <span data-ttu-id="f0285-201">위의 예제에 나와 있는 것처럼 [from](../../../csharp/language-reference/keywords/from-clause.md) 절 아래의 쿼리 절을 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="f0285-201">Align query clauses under the [from](../../../csharp/language-reference/keywords/from-clause.md) clause, as shown in the previous examples.</span></span>  
  
-   <span data-ttu-id="f0285-202">뒷부분의 쿼리 절이 필터링을 통해 범위가 좁아진 데이터 집합에 대해 작동하도록 다른 쿼리 절 앞에 [where](../../../csharp/language-reference/keywords/where-clause.md) 절을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f0285-202">Use [where](../../../csharp/language-reference/keywords/where-clause.md) clauses before other query clauses to ensure that later query clauses operate on the reduced, filtered set of data.</span></span>  
  
     <span data-ttu-id="f0285-203">[!code-cs[csProgGuideCodingConventions#29](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_25.cs)]</span><span class="sxs-lookup"><span data-stu-id="f0285-203">[!code-cs[csProgGuideCodingConventions#29](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_25.cs)]</span></span>  
  
-   <span data-ttu-id="f0285-204">내부 컬렉션에 액세스하려면 [join](../../../csharp/language-reference/keywords/join-clause.md) 절 대신 여러 `from` 절을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f0285-204">Use multiple `from` clauses instead of a [join](../../../csharp/language-reference/keywords/join-clause.md) clause to access inner collections.</span></span> <span data-ttu-id="f0285-205">예를 들어 `Student` 개체 컬렉션이 각각 테스트 점수 컬렉션을 포함하는 경우</span><span class="sxs-lookup"><span data-stu-id="f0285-205">For example, a collection of `Student` objects might each contain a collection of test scores.</span></span> <span data-ttu-id="f0285-206">다음 쿼리를 실행하면 90점보다 높은 각 점수와 해당 점수를 받은 학생의 성이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0285-206">When the following query is executed, it returns each score that is over 90, along with the last name of the student who received the score.</span></span>  
  
     <span data-ttu-id="f0285-207">[!code-cs[csProgGuideCodingConventions#30](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_26.cs)]</span><span class="sxs-lookup"><span data-stu-id="f0285-207">[!code-cs[csProgGuideCodingConventions#30](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_26.cs)]</span></span>  
  
## <a name="security"></a><span data-ttu-id="f0285-208">보안</span><span class="sxs-lookup"><span data-stu-id="f0285-208">Security</span></span>  
 <span data-ttu-id="f0285-209">[보안 코딩 지침](../../../standard/security/secure-coding-guidelines.md)의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="f0285-209">Follow the guidelines in [Secure Coding Guidelines](../../../standard/security/secure-coding-guidelines.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0285-210">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f0285-210">See Also</span></span>  
 <span data-ttu-id="f0285-211">[Visual Basic 코딩 규칙](../../../visual-basic/programming-guide/program-structure/coding-conventions.md) </span><span class="sxs-lookup"><span data-stu-id="f0285-211">[Visual Basic Coding Conventions](../../../visual-basic/programming-guide/program-structure/coding-conventions.md) </span></span>  
 [<span data-ttu-id="f0285-212">보안 코딩 지침</span><span class="sxs-lookup"><span data-stu-id="f0285-212">Secure Coding Guidelines</span></span>](../../../standard/security/secure-coding-guidelines.md)

