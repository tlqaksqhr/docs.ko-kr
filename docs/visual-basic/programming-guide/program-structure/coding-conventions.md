---
title: "Visual Basic 코딩 규칙"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- coding conventions [Visual Basic], Visual Basic
- examples [Visual Basic], coding conventions
- Visual Basic code, conventions
ms.assetid: c1df130b-fec6-49a5-becf-0a7e494a1d0f
caps.latest.revision: "48"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: afea862fb8783da3e69fd9828e0ded67fb81b00e
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="visual-basic-coding-conventions"></a><span data-ttu-id="1f21f-102">Visual Basic 코딩 규칙</span><span class="sxs-lookup"><span data-stu-id="1f21f-102">Visual Basic Coding Conventions</span></span>
<span data-ttu-id="1f21f-103">Microsoft 예제 및이 항목의 지침에 따라 설명서를 개발 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f21f-103">Microsoft develops samples and documentation that follow the guidelines in this topic.</span></span> <span data-ttu-id="1f21f-104">동일한 코딩 규칙을 따르는 경우는 다음과 같은 이점을 얻을 수 있습니다 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f21f-104">If you follow the same coding conventions, you may gain the following benefits:</span></span>  
  
-   <span data-ttu-id="1f21f-105">코드는 판독기 레이아웃이 아닌 내용에 집중할 수 있도록 일관 된 모양을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="1f21f-105">Your code will have a consistent look, so that readers can better focus on content, not layout.</span></span>  
  
-   <span data-ttu-id="1f21f-106">읽는 사람이 이해 코드 보다 신속 하 게 이전 경험을 기반으로 예상할 수 때문에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f21f-106">Readers understand your code more quickly because they can make assumptions based on previous experience.</span></span>  
  
-   <span data-ttu-id="1f21f-107">복사, 변경 및 코드를 더 쉽게 유지 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f21f-107">You can copy, change, and maintain the code more easily.</span></span>  
  
-   <span data-ttu-id="1f21f-108">Visual basic 코드 "모범 사례" 보여 주는 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f21f-108">You help ensure that your code demonstrates "best practices" for Visual Basic.</span></span>  
  
## <a name="naming-conventions"></a><span data-ttu-id="1f21f-109">명명 규칙</span><span class="sxs-lookup"><span data-stu-id="1f21f-109">Naming Conventions</span></span>  
  
-   <span data-ttu-id="1f21f-110">이름 지정 지침에 대 한 정보를 참조 하십시오. [명명 지침](../../../standard/design-guidelines/naming-guidelines.md) 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="1f21f-110">For information about naming guidelines, see [Naming Guidelines](../../../standard/design-guidelines/naming-guidelines.md) topic.</span></span>  
  
-   <span data-ttu-id="1f21f-111">변수 이름의 일부로 "내" 또는 "my"를 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="1f21f-111">Do not use "My" or "my" as part of a variable name.</span></span> <span data-ttu-id="1f21f-112">이 연습와 혼동는 `My` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="1f21f-112">This practice creates confusion with the `My` objects.</span></span>  
  
-   <span data-ttu-id="1f21f-113">지침에 맞게 자동으로 생성 된 코드에서 개체의 이름을 변경할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1f21f-113">You do not have to change the names of objects in auto-generated code to make them fit the guidelines.</span></span>  
  
## <a name="layout-conventions"></a><span data-ttu-id="1f21f-114">레이아웃 규칙</span><span class="sxs-lookup"><span data-stu-id="1f21f-114">Layout Conventions</span></span>  
  
-   <span data-ttu-id="1f21f-115">공백, 탭을 삽입 하 고 4 공간 들여쓰기와 스마트 들여쓰기를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f21f-115">Insert tabs as spaces, and use smart indenting with four-space indents.</span></span>  
  
-   <span data-ttu-id="1f21f-116">사용 하 여 **(다시 포맷)의 코드를 나열 하는 매우** 코드 편집기에서 코드의 서식을 다시 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f21f-116">Use **Pretty listing (reformatting) of code** to reformat your code in the code editor.</span></span> <span data-ttu-id="1f21f-117">자세한 내용은 참조 [옵션, 텍스트 편집기, 기본 (Visual Basic)](/visualstudio/ide/reference/options-text-editor-basic-visual-basic)합니다.</span><span class="sxs-lookup"><span data-stu-id="1f21f-117">For more information, see [Options, Text Editor, Basic (Visual Basic)](/visualstudio/ide/reference/options-text-editor-basic-visual-basic).</span></span>  
  
-   <span data-ttu-id="1f21f-118">줄 당 하나의 문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f21f-118">Use only one statement per line.</span></span> <span data-ttu-id="1f21f-119">Visual Basic 줄 구분 기호 문자 (:)를 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="1f21f-119">Don't use the Visual Basic line separator character (:).</span></span>  
  
-   <span data-ttu-id="1f21f-120">언어에서 허용 하는 경우 암시적 줄 연속 문자를 위해 명시적 줄 연속 문자 "_"를 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="1f21f-120">Avoid using the explicit line continuation character "_" in favor of implicit line continuation wherever the language allows it.</span></span>  
  
-   <span data-ttu-id="1f21f-121">줄 마다 선언은 하나씩만 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f21f-121">Use only one declaration per line.</span></span>  
  
-   <span data-ttu-id="1f21f-122">경우 **(다시 포맷)의 코드를 나열 하는 매우** 하지 않는 형식 연속 줄 자동으로, 수동으로 들여쓰기 연속 된 줄을 탭 정지 하나 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f21f-122">If **Pretty listing (reformatting) of code** doesn't format continuation lines automatically, manually indent continuation lines one tab stop.</span></span> <span data-ttu-id="1f21f-123">그러나 항상 왼쪽 맞춤 목록의 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="1f21f-123">However, always left-align items in a list.</span></span>  
  
    ```  
    a As Integer,  
    b As Integer  
    ```  
  
-   <span data-ttu-id="1f21f-124">메서드 및 속성 정의 사이 하나 이상의 빈 줄을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f21f-124">Add at least one blank line between method and property definitions.</span></span>  
  
## <a name="commenting-conventions"></a><span data-ttu-id="1f21f-125">주석 규칙</span><span class="sxs-lookup"><span data-stu-id="1f21f-125">Commenting Conventions</span></span>  
  
-   <span data-ttu-id="1f21f-126">코드 줄의 끝에 대신 별도 줄에 설명을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f21f-126">Put comments on a separate line instead of at the end of a line of code.</span></span>  
  
-   <span data-ttu-id="1f21f-127">마침표로 종료 주석 텍스트 및 주석 텍스트는 대문자로 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f21f-127">Start comment text with an uppercase letter, and end comment text with a period.</span></span>  
  
-   <span data-ttu-id="1f21f-128">주석 구분 기호 (') 및 메모 텍스트 사이 공백을 하나 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f21f-128">Insert one space between the comment delimiter (') and the comment text.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#2](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_1.vb)]  
  
-   <span data-ttu-id="1f21f-129">에 서식이 지정 된 별표 블록으로를 둘러싸고지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1f21f-129">Do not surround comments with formatted blocks of asterisks.</span></span>  
  
## <a name="program-structure"></a><span data-ttu-id="1f21f-130">프로그램 구조</span><span class="sxs-lookup"><span data-stu-id="1f21f-130">Program Structure</span></span>  
  
-   <span data-ttu-id="1f21f-131">사용 하는 경우는 `Main` 새 콘솔 응용 프로그램에 대 한 기본 구조를 사용 하 고 사용 하는 메서드를 `My` 명령줄 인수에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f21f-131">When you use the `Main` method, use the default construct for new console applications, and use `My` for command-line arguments.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#3](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_2.vb)]  
  
## <a name="language-guidelines"></a><span data-ttu-id="1f21f-132">언어 지침</span><span class="sxs-lookup"><span data-stu-id="1f21f-132">Language Guidelines</span></span>  
  
### <a name="string-data-type"></a><span data-ttu-id="1f21f-133">String 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="1f21f-133">String Data Type</span></span>  
  
-   <span data-ttu-id="1f21f-134">문자열을 연결 하려면 앰퍼샌드를 사용 (&).</span><span class="sxs-lookup"><span data-stu-id="1f21f-134">To concatenate strings, use an ampersand (&).</span></span>  
  
     [!code-vb[VbVbalrGuidelines#4](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_3.vb)]  
  
-   <span data-ttu-id="1f21f-135">루프에 문자열에 추가 하려면 사용 하 여는 <xref:System.Text.StringBuilder> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="1f21f-135">To append strings in loops, use the <xref:System.Text.StringBuilder> object.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#5](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_4.vb)]  
  
### <a name="relaxed-delegates-in-event-handlers"></a><span data-ttu-id="1f21f-136">완화 된 대리자 이벤트 처리기</span><span class="sxs-lookup"><span data-stu-id="1f21f-136">Relaxed Delegates in Event Handlers</span></span>  
 <span data-ttu-id="1f21f-137">이벤트 처리기에 (개체 및 EventArgs) 인수를 명시적으로 적합 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1f21f-137">Do not explicitly qualify the arguments (Object and EventArgs) to event handlers.</span></span> <span data-ttu-id="1f21f-138">이벤트 (예를 들어 보낸 사람 개체로, EventArgs e)에 전달 되는 이벤트 인수를 사용 하지 않는 경우에 완화 된 대리자를 사용 하 고 코드에서 이벤트 인수를:</span><span class="sxs-lookup"><span data-stu-id="1f21f-138">If you are not using the event arguments that are passed to an event (for example, sender as Object, e as EventArgs), use relaxed delegates, and leave out the event arguments in your code:</span></span>  
  
 [!code-vb[VbVbalrGuidelines#7](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_5.vb)]  
  
### <a name="unsigned-data-type"></a><span data-ttu-id="1f21f-139">부호 없는 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="1f21f-139">Unsigned Data Type</span></span>  
  
-   <span data-ttu-id="1f21f-140">사용 하 여 `Integer` 는 필요한 제외 하 고 부호 없는 형식 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f21f-140">Use `Integer` rather than unsigned types, except where they are necessary.</span></span>  
  
### <a name="arrays"></a><span data-ttu-id="1f21f-141">배열</span><span class="sxs-lookup"><span data-stu-id="1f21f-141">Arrays</span></span>  
  
-   <span data-ttu-id="1f21f-142">선언 줄에서 배열을 초기화할 때 간단한 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f21f-142">Use the short syntax when you initialize arrays on the declaration line.</span></span> <span data-ttu-id="1f21f-143">예를 들어 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f21f-143">For example, use the following syntax.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#8](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_6.vb)]  
  
     <span data-ttu-id="1f21f-144">다음 구문을 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="1f21f-144">Do not use the following syntax.</span></span>  
  
     [!code-vb[VbVbalrGuidelines#9](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_7.vb)]  
  
-   <span data-ttu-id="1f21f-145">변수가 아니라 형식에 배열 지정자를 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="1f21f-145">Put the array designator on the type, not on the variable.</span></span> <span data-ttu-id="1f21f-146">예를 들어 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f21f-146">For example, use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#11](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_8.vb)]  
  
     <span data-ttu-id="1f21f-147">다음 구문을 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="1f21f-147">Do not use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#10](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_9.vb)]  
  
-   <span data-ttu-id="1f21f-148">선언 하 고 기본 데이터 형식의 배열을 초기화할 때 {} 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f21f-148">Use the { } syntax when you declare and initialize arrays of basic data types.</span></span> <span data-ttu-id="1f21f-149">예를 들어 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f21f-149">For example, use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#12](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_10.vb)]  
  
     <span data-ttu-id="1f21f-150">다음 구문을 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="1f21f-150">Do not use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#13](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_11.vb)]  
  
### <a name="use-the-with-keyword"></a><span data-ttu-id="1f21f-151">사용 하는 키워드와 함께</span><span class="sxs-lookup"><span data-stu-id="1f21f-151">Use the With Keyword</span></span>  
 <span data-ttu-id="1f21f-152">사용 하는 일련의 하나 이상의 개체에 대 한 호출을 수행 하면 고려는 `With` 키워드:</span><span class="sxs-lookup"><span data-stu-id="1f21f-152">When you make a series of calls to one object, consider using the `With` keyword:</span></span>  
  
 [!code-vb[VbVbalrGuidelines#15](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_12.vb)]  
  
### <a name="use-the-trycatch-and-using-statements-when-you-use-exception-handling"></a><span data-ttu-id="1f21f-153">Try 사용 함 Catch 및 문을 사용 하 여 예외 처리를 사용 하는 경우</span><span class="sxs-lookup"><span data-stu-id="1f21f-153">Use the Try...Catch and Using Statements when you use Exception Handling</span></span>  
 <span data-ttu-id="1f21f-154">사용 하지 마십시오 `On Error Goto`합니다.</span><span class="sxs-lookup"><span data-stu-id="1f21f-154">Do not use `On Error Goto`.</span></span>  
  
### <a name="use-the-isnot-keyword"></a><span data-ttu-id="1f21f-155">IsNot 키워드를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="1f21f-155">Use the IsNot Keyword</span></span>  
 <span data-ttu-id="1f21f-156">사용 하 여 `IsNot` 키워드 대신 `Not...Is Nothing`합니다.</span><span class="sxs-lookup"><span data-stu-id="1f21f-156">Use the `IsNot` keyword instead of `Not...Is Nothing`.</span></span>  
  
### <a name="new-keyword"></a><span data-ttu-id="1f21f-157">New 키워드</span><span class="sxs-lookup"><span data-stu-id="1f21f-157">New Keyword</span></span>  
  
-   <span data-ttu-id="1f21f-158">간단한 인스턴스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f21f-158">Use short instantiation.</span></span> <span data-ttu-id="1f21f-159">예를 들어 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f21f-159">For example, use the following syntax:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#21](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_13.vb)]  
  
     <span data-ttu-id="1f21f-160">앞의 줄이 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1f21f-160">The preceding line is equivalent to this:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#22](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_14.vb)]  
  
-   <span data-ttu-id="1f21f-161">매개 변수가 없는 생성자 대신 새 개체에 대 한 개체 이니셜라이저를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f21f-161">Use object initializers for new objects instead of the parameterless constructor:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#23](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_15.vb)]  
  
### <a name="event-handling"></a><span data-ttu-id="1f21f-162">이벤트 처리</span><span class="sxs-lookup"><span data-stu-id="1f21f-162">Event Handling</span></span>  
  
-   <span data-ttu-id="1f21f-163">사용 하 여 `Handles` 대신 `AddHandler`:</span><span class="sxs-lookup"><span data-stu-id="1f21f-163">Use `Handles` rather than `AddHandler`:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#24](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_16.vb)]  
  
-   <span data-ttu-id="1f21f-164">사용 하 여 `AddressOf`, 대리자를 명시적으로 인스턴스화합니다 않습니다:</span><span class="sxs-lookup"><span data-stu-id="1f21f-164">Use `AddressOf`, and do not instantiate the delegate explicitly:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#25](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_17.vb)]  
  
-   <span data-ttu-id="1f21f-165">이벤트를 정의 하는 경우 간단한 구문을 사용 하 고 고 컴파일러에서 대리자를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f21f-165">When you define an event, use the short syntax, and let the compiler define the delegate:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#26](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_18.vb)]  
  
-   <span data-ttu-id="1f21f-166">이벤트 인지를 확인 하지 않습니다 `Nothing` (null)를 호출 하기 전에 `RaiseEvent` 메서드.</span><span class="sxs-lookup"><span data-stu-id="1f21f-166">Do not verify whether an event is `Nothing` (null) before you call the `RaiseEvent` method.</span></span> <span data-ttu-id="1f21f-167">`RaiseEvent`에 대 한 확인 `Nothing` 전에 이벤트를 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="1f21f-167">`RaiseEvent` checks for `Nothing` before it raises the event.</span></span>  
  
### <a name="using-shared-members"></a><span data-ttu-id="1f21f-168">공유 멤버 사용</span><span class="sxs-lookup"><span data-stu-id="1f21f-168">Using Shared Members</span></span>  
 <span data-ttu-id="1f21f-169">호출 `Shared` 클래스 이름에서가 아니라 인스턴스 변수를 사용 하 여 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="1f21f-169">Call `Shared` members by using the class name, not from an instance variable.</span></span>  
  
### <a name="use-xml-literals"></a><span data-ttu-id="1f21f-170">XML 리터럴을 사용 하십시오.</span><span class="sxs-lookup"><span data-stu-id="1f21f-170">Use XML Literals</span></span>  
 <span data-ttu-id="1f21f-171">XML 리터럴의 XML (예를 들어, 로드, 쿼리 및 변환)를 사용 하 여 작업할 때 발생할 수 있는 가장 일반적인 작업을 간소화 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f21f-171">XML literals simplify the most common tasks that you encounter when you work with XML (for example, load, query, and transform).</span></span> <span data-ttu-id="1f21f-172">XML로 개발 하는 경우 다음이 지침을 따르십시오.</span><span class="sxs-lookup"><span data-stu-id="1f21f-172">When you develop with XML, follow these guidelines:</span></span>  
  
-   <span data-ttu-id="1f21f-173">XML 리터럴을 사용 하 여 XML 문서 및 XML Api를 직접 호출 하는 대신 조각을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1f21f-173">Use XML literals to create XML documents and fragments instead of calling XML APIs directly.</span></span>  
  
-   <span data-ttu-id="1f21f-174">XML 리터럴에 대 한 성능 최적화를 활용 하도록 파일 또는 프로젝트 수준에서 XML 네임 스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1f21f-174">Import XML namespaces at the file or project level to take advantage of the performance optimizations for XML literals.</span></span>  
  
-   <span data-ttu-id="1f21f-175">XML 축 속성을 사용 하 여 특성과 해당 요소는 XML 문서에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f21f-175">Use the XML axis properties to access elements and attributes in an XML document.</span></span>  
  
-   <span data-ttu-id="1f21f-176">포함된 식을 사용 하 여 값을 포함 하 고와 같은 API 호출을 사용 하는 대신 기존 값에서 XML을 만들 수는 `Add` 메서드:</span><span class="sxs-lookup"><span data-stu-id="1f21f-176">Use embedded expressions to include values and to create XML from existing values instead of using API calls such as the `Add` method:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#27](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_19.vb)]  
  
### <a name="linq-queries"></a><span data-ttu-id="1f21f-177">LINQ 쿼리</span><span class="sxs-lookup"><span data-stu-id="1f21f-177">LINQ Queries</span></span>  
  
-   <span data-ttu-id="1f21f-178">쿼리 변수에 대 한 의미 있는 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f21f-178">Use meaningful names for query variables:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#28](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_20.vb)]  
  
-   <span data-ttu-id="1f21f-179">익명 형식의 속성 이름이 올바르게 대문자로 표시 되도록 파스칼식을 사용 하 여 쿼리에서 요소에 대 한 이름을 제공 대/소문자 구분:</span><span class="sxs-lookup"><span data-stu-id="1f21f-179">Provide names for elements in a query to make sure that property names of anonymous types are correctly capitalized using Pascal casing:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#29](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_21.vb)]  
  
-   <span data-ttu-id="1f21f-180">결과의 속성 이름이 모호하면 속성 이름을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="1f21f-180">Rename properties when the property names in the result would be ambiguous.</span></span> <span data-ttu-id="1f21f-181">예를 들어 쿼리에서 고객 이름 및 주문 ID를 반환 하는 경우 이름을 그대로 두는 대신 `Name` 및 `ID` 결과에서:</span><span class="sxs-lookup"><span data-stu-id="1f21f-181">For example, if your query returns a customer name and an order ID, rename them instead of leaving them as `Name` and `ID` in the result:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#30](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_22.vb)]  
  
-   <span data-ttu-id="1f21f-182">쿼리 변수 및 범위 변수 선언에서 형식 유추를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f21f-182">Use type inference in the declaration of query variables and range variables:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#31](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_23.vb)]  
  
-   <span data-ttu-id="1f21f-183">아래의 쿼리 절을 정렬 된 `From` 문:</span><span class="sxs-lookup"><span data-stu-id="1f21f-183">Align query clauses under the `From` statement:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#32](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_24.vb)]  
  
-   <span data-ttu-id="1f21f-184">사용 하 여 `Where` 뒷부분의 쿼리 절 데이터의 필터링 된 집합에서 사용할 수 있도록 다른 앞에 절 쿼리 절:</span><span class="sxs-lookup"><span data-stu-id="1f21f-184">Use `Where` clauses before other query clauses so that later query clauses operate on the filtered set of data:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#33](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_25.vb)]  
  
-   <span data-ttu-id="1f21f-185">사용 하 여는 `Join` 절을 사용 하는 대신 조인 작업을 명시적으로 정의 된 `Where` 암시적으로 조인 작업을 정의 하는 절:</span><span class="sxs-lookup"><span data-stu-id="1f21f-185">Use the `Join` clause to explicitly define a join operation instead of using the `Where` clause to implicitly define a join operation:</span></span>  
  
     [!code-vb[VbVbalrGuidelines#34](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_26.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="1f21f-186">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1f21f-186">See Also</span></span>  
 [<span data-ttu-id="1f21f-187">보안 코딩 지침</span><span class="sxs-lookup"><span data-stu-id="1f21f-187">Secure Coding Guidelines</span></span>](../../../standard/security/secure-coding-guidelines.md)
