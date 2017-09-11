---
title: "Visual Basic 코딩 규칙 | Microsoft 문서"
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
- coding conventions, Visual Basic
- examples [Visual Basic], coding conventions
- Visual Basic code, conventions
ms.assetid: c1df130b-fec6-49a5-becf-0a7e494a1d0f
caps.latest.revision: 48
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
ms.openlocfilehash: 16d4ddccd3a16c48e58f297faf8909148899013f
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="visual-basic-coding-conventions"></a><span data-ttu-id="8d80a-102">Visual Basic 코딩 규칙</span><span class="sxs-lookup"><span data-stu-id="8d80a-102">Visual Basic Coding Conventions</span></span>
<span data-ttu-id="8d80a-103">Microsoft 예제 및이 항목의 지침에 따라 설명서를 개발 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d80a-103">Microsoft develops samples and documentation that follow the guidelines in this topic.</span></span> <span data-ttu-id="8d80a-104">동일한 코딩 규칙을 따르는 경우에 다음과 같은 이점을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d80a-104">If you follow the same coding conventions, you may gain the following benefits:</span></span>  
  
-   <span data-ttu-id="8d80a-105">코드는 판독기 레이아웃이 아닌 내용에 집중할 수 있도록 일관 된 모양을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="8d80a-105">Your code will have a consistent look, so that readers can better focus on content, not layout.</span></span>  
  
-   <span data-ttu-id="8d80a-106">판독기 코드를 이해 더 신속 하 게 이전 경험을 기반으로 예상할 수 수 있기 때문에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d80a-106">Readers understand your code more quickly because they can make assumptions based on previous experience.</span></span>  
  
-   <span data-ttu-id="8d80a-107">복사, 변경 및 코드를 더 쉽게 유지 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d80a-107">You can copy, change, and maintain the code more easily.</span></span>  
  
-   <span data-ttu-id="8d80a-108">Visual basic 코드 "모범 사례" 보여 주는 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d80a-108">You help ensure that your code demonstrates "best practices" for Visual Basic.</span></span>  
  
## <a name="naming-conventions"></a><span data-ttu-id="8d80a-109">명명 규칙</span><span class="sxs-lookup"><span data-stu-id="8d80a-109">Naming Conventions</span></span>  
  
-   <span data-ttu-id="8d80a-110">이름 지정 지침에 대 한 정보를 참조 하십시오. [명명 지침](http://msdn.microsoft.com/library/fc076d66-9b5f-42d3-aa65-61d970c794a3) 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="8d80a-110">For information about naming guidelines, see [Naming Guidelines](http://msdn.microsoft.com/library/fc076d66-9b5f-42d3-aa65-61d970c794a3) topic.</span></span>  
  
-   <span data-ttu-id="8d80a-111">변수 이름의 일부로 "내" 또는 "my"를 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="8d80a-111">Do not use "My" or "my" as part of a variable name.</span></span> <span data-ttu-id="8d80a-112">이 사례와 혼동의 `My` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="8d80a-112">This practice creates confusion with the `My` objects.</span></span>  
  
-   <span data-ttu-id="8d80a-113">지침에 맞게 자동으로 생성 된 코드에서 개체의 이름을 변경할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8d80a-113">You do not have to change the names of objects in auto-generated code to make them fit the guidelines.</span></span>  
  
## <a name="layout-conventions"></a><span data-ttu-id="8d80a-114">레이아웃 규칙</span><span class="sxs-lookup"><span data-stu-id="8d80a-114">Layout Conventions</span></span>  
  
-   <span data-ttu-id="8d80a-115">공백, 탭을 삽입 하 고&4; 공간 들여쓰기와 스마트 들여쓰기를 사용 하 여 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="8d80a-115">Insert tabs as spaces, and use smart indenting with four-space indents.</span></span>  
  
-   <span data-ttu-id="8d80a-116">사용 하 여 **(다시 포맷)의 코드를 나열 하는 상당히** 코드 편집기에서 코드를 다시 포맷 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d80a-116">Use **Pretty listing (reformatting) of code** to reformat your code in the code editor.</span></span> <span data-ttu-id="8d80a-117">자세한 내용은 참조 [옵션, 텍스트 편집기, 기본 (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/options-text-editor-basic-visual-basic)합니다.</span><span class="sxs-lookup"><span data-stu-id="8d80a-117">For more information, see [Options, Text Editor, Basic (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/options-text-editor-basic-visual-basic).</span></span>  
  
-   <span data-ttu-id="8d80a-118">줄당 하나의 문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d80a-118">Use only one statement per line.</span></span> <span data-ttu-id="8d80a-119">Visual Basic 줄 구분 기호 문자 (:)을 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="8d80a-119">Don't use the Visual Basic line separator character (:).</span></span>  
  
-   <span data-ttu-id="8d80a-120">언어에서 허용 하는 경우 항상 암시적 줄 연속 문자를 기준으로 명시적 줄 연속 문자 "_"을 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="8d80a-120">Avoid using the explicit line continuation character "_" in favor of implicit line continuation wherever the language allows it.</span></span>  
  
-   <span data-ttu-id="8d80a-121">하나의 선언을 한 줄을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d80a-121">Use only one declaration per line.</span></span>  
  
-   <span data-ttu-id="8d80a-122">경우 **(다시 포맷)의 코드를 나열 하는 상당히** 하지 형식 연속 줄 수동으로 자동으로 들여쓰기 연속 된 줄을 탭 정지 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="8d80a-122">If **Pretty listing (reformatting) of code** doesn't format continuation lines automatically, manually indent continuation lines one tab stop.</span></span> <span data-ttu-id="8d80a-123">그러나 항상 왼쪽 맞춤 목록에서 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="8d80a-123">However, always left-align items in a list.</span></span>  
  
    ```  
    a As Integer,  
    b As Integer  
    ```  
  
-   <span data-ttu-id="8d80a-124">메서드 및 속성 정의 사이 하나 이상의 빈 줄을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d80a-124">Add at least one blank line between method and property definitions.</span></span>  
  
## <a name="commenting-conventions"></a><span data-ttu-id="8d80a-125">주석 규칙</span><span class="sxs-lookup"><span data-stu-id="8d80a-125">Commenting Conventions</span></span>  
  
-   <span data-ttu-id="8d80a-126">코드 줄의 끝에 대신 별도 줄에 설명을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d80a-126">Put comments on a separate line instead of at the end of a line of code.</span></span>  
  
-   <span data-ttu-id="8d80a-127">마침표로 종료 주석 텍스트 및 주석 텍스트는 대문자로 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d80a-127">Start comment text with an uppercase letter, and end comment text with a period.</span></span>  
  
-   <span data-ttu-id="8d80a-128">주석 구분 기호 (')와 주석 텍스트 사이 공백을 하나 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d80a-128">Insert one space between the comment delimiter (') and the comment text.</span></span>  
  
     <span data-ttu-id="8d80a-129">[!code-vb[VbVbalrGuidelines #&2;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="8d80a-129">[!code-vb[VbVbalrGuidelines#2](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_1.vb)]</span></span>  
  
-   <span data-ttu-id="8d80a-130">에 서식이 지정 된 별표 블록으로 묶습니다 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="8d80a-130">Do not surround comments with formatted blocks of asterisks.</span></span>  
  
## <a name="program-structure"></a><span data-ttu-id="8d80a-131">프로그램 구조</span><span class="sxs-lookup"><span data-stu-id="8d80a-131">Program Structure</span></span>  
  
-   <span data-ttu-id="8d80a-132">사용 하는 경우는 `Main` 새 콘솔 응용 프로그램에 대 한 기본 구조를 사용 하 고 사용 하는 메서드를 `My` 명령줄 인수에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d80a-132">When you use the `Main` method, use the default construct for new console applications, and use `My` for command-line arguments.</span></span>  
  
     <span data-ttu-id="8d80a-133">[!code-vb[VbVbalrGuidelines #&3;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="8d80a-133">[!code-vb[VbVbalrGuidelines#3](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_2.vb)]</span></span>  
  
## <a name="language-guidelines"></a><span data-ttu-id="8d80a-134">언어 지침</span><span class="sxs-lookup"><span data-stu-id="8d80a-134">Language Guidelines</span></span>  
  
### <a name="string-data-type"></a><span data-ttu-id="8d80a-135">String 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="8d80a-135">String Data Type</span></span>  
  
-   <span data-ttu-id="8d80a-136">문자열을 연결 하려면 앰퍼샌드 (&)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d80a-136">To concatenate strings, use an ampersand (&).</span></span>  
  
     <span data-ttu-id="8d80a-137">[!code-vb[VbVbalrGuidelines #&4;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="8d80a-137">[!code-vb[VbVbalrGuidelines#4](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_3.vb)]</span></span>  
  
-   <span data-ttu-id="8d80a-138">문자열을 루프를 추가 하려면 사용 된 <xref:System.Text.StringBuilder>개체.</xref:System.Text.StringBuilder></span><span class="sxs-lookup"><span data-stu-id="8d80a-138">To append strings in loops, use the <xref:System.Text.StringBuilder> object.</span></span>  
  
     <span data-ttu-id="8d80a-139">[!code-vb[VbVbalrGuidelines #&5;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="8d80a-139">[!code-vb[VbVbalrGuidelines#5](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_4.vb)]</span></span>  
  
### <a name="relaxed-delegates-in-event-handlers"></a><span data-ttu-id="8d80a-140">완화 된 대리자 이벤트 처리기에</span><span class="sxs-lookup"><span data-stu-id="8d80a-140">Relaxed Delegates in Event Handlers</span></span>  
 <span data-ttu-id="8d80a-141">이벤트 처리기에 (개체와 EventArgs) 인수를 명시적으로 적합 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8d80a-141">Do not explicitly qualify the arguments (Object and EventArgs) to event handlers.</span></span> <span data-ttu-id="8d80a-142">이벤트 (예를 들어 보낸 사람 e EventArgs 개체로)에 전달 되는 이벤트 인수를 사용 하지 않는 경우에 완화 된 대리자를 사용 하 고 코드에서 이벤트 인수를:</span><span class="sxs-lookup"><span data-stu-id="8d80a-142">If you are not using the event arguments that are passed to an event (for example, sender as Object, e as EventArgs), use relaxed delegates, and leave out the event arguments in your code:</span></span>  
  
 <span data-ttu-id="8d80a-143">[!code-vb[VbVbalrGuidelines #&7;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="8d80a-143">[!code-vb[VbVbalrGuidelines#7](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_5.vb)]</span></span>  
  
### <a name="unsigned-data-type"></a><span data-ttu-id="8d80a-144">부호 없는 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="8d80a-144">Unsigned Data Type</span></span>  
  
-   <span data-ttu-id="8d80a-145">사용 하 여 `Integer` 는 필요한 제외 하 고 부호 없는 형식 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d80a-145">Use `Integer` rather than unsigned types, except where they are necessary.</span></span>  
  
### <a name="arrays"></a><span data-ttu-id="8d80a-146">배열</span><span class="sxs-lookup"><span data-stu-id="8d80a-146">Arrays</span></span>  
  
-   <span data-ttu-id="8d80a-147">선언 줄에서 배열을 초기화할 때는 간단한 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d80a-147">Use the short syntax when you initialize arrays on the declaration line.</span></span> <span data-ttu-id="8d80a-148">예를 들어 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d80a-148">For example, use the following syntax.</span></span>  
  
     <span data-ttu-id="8d80a-149">[!code-vb[VbVbalrGuidelines #&8;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="8d80a-149">[!code-vb[VbVbalrGuidelines#8](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_6.vb)]</span></span>  
  
     <span data-ttu-id="8d80a-150">다음 구문을 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="8d80a-150">Do not use the following syntax.</span></span>  
  
     <span data-ttu-id="8d80a-151">[!code-vb[VbVbalrGuidelines #&9;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="8d80a-151">[!code-vb[VbVbalrGuidelines#9](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_7.vb)]</span></span>  
  
-   <span data-ttu-id="8d80a-152">변수 아니라 형식에 배열 지정자를 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="8d80a-152">Put the array designator on the type, not on the variable.</span></span> <span data-ttu-id="8d80a-153">예를 들어 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d80a-153">For example, use the following syntax:</span></span>  
  
     <span data-ttu-id="8d80a-154">[!code-vb[VbVbalrGuidelines #&11;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_8.vb)]</span><span class="sxs-lookup"><span data-stu-id="8d80a-154">[!code-vb[VbVbalrGuidelines#11](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_8.vb)]</span></span>  
  
     <span data-ttu-id="8d80a-155">다음 구문을 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8d80a-155">Do not use the following syntax:</span></span>  
  
     <span data-ttu-id="8d80a-156">[!code-vb[VbVbalrGuidelines #&10;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_9.vb)]</span><span class="sxs-lookup"><span data-stu-id="8d80a-156">[!code-vb[VbVbalrGuidelines#10](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_9.vb)]</span></span>  
  
-   <span data-ttu-id="8d80a-157">선언 하 고 기본 데이터 형식의 배열을 초기화할 때 {} 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d80a-157">Use the { } syntax when you declare and initialize arrays of basic data types.</span></span> <span data-ttu-id="8d80a-158">예를 들어 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d80a-158">For example, use the following syntax:</span></span>  
  
     <span data-ttu-id="8d80a-159">[!code-vb[VbVbalrGuidelines #&12;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_10.vb)]</span><span class="sxs-lookup"><span data-stu-id="8d80a-159">[!code-vb[VbVbalrGuidelines#12](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_10.vb)]</span></span>  
  
     <span data-ttu-id="8d80a-160">다음 구문을 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8d80a-160">Do not use the following syntax:</span></span>  
  
     <span data-ttu-id="8d80a-161">[!code-vb[VbVbalrGuidelines #&13;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_11.vb)]</span><span class="sxs-lookup"><span data-stu-id="8d80a-161">[!code-vb[VbVbalrGuidelines#13](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_11.vb)]</span></span>  
  
### <a name="use-the-with-keyword"></a><span data-ttu-id="8d80a-162">사용 하는 With 키워드</span><span class="sxs-lookup"><span data-stu-id="8d80a-162">Use the With Keyword</span></span>  
 <span data-ttu-id="8d80a-163">사용 하 여 일련의 하나 이상의 개체에 대 한 호출을 수행 하면 고려는 `With` 키워드:</span><span class="sxs-lookup"><span data-stu-id="8d80a-163">When you make a series of calls to one object, consider using the `With` keyword:</span></span>  
  
 <span data-ttu-id="8d80a-164">[!code-vb[VbVbalrGuidelines #&15;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_12.vb)]</span><span class="sxs-lookup"><span data-stu-id="8d80a-164">[!code-vb[VbVbalrGuidelines#15](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_12.vb)]</span></span>  
  
### <a name="use-the-trycatch-and-using-statements-when-you-use-exception-handling"></a><span data-ttu-id="8d80a-165">Try를 사용 하 여... Catch 및 예외 처리를 사용 하는 때를 사용 하 여 문</span><span class="sxs-lookup"><span data-stu-id="8d80a-165">Use the Try...Catch and Using Statements when you use Exception Handling</span></span>  
 <span data-ttu-id="8d80a-166">사용 하지 않는 `On Error Goto`합니다.</span><span class="sxs-lookup"><span data-stu-id="8d80a-166">Do not use `On Error Goto`.</span></span>  
  
### <a name="use-the-isnot-keyword"></a><span data-ttu-id="8d80a-167">IsNot 키워드를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="8d80a-167">Use the IsNot Keyword</span></span>  
 <span data-ttu-id="8d80a-168">사용 하 여 `IsNot` 키워드 대신 `Not...Is Nothing`합니다.</span><span class="sxs-lookup"><span data-stu-id="8d80a-168">Use the `IsNot` keyword instead of `Not...Is Nothing`.</span></span>  
  
### <a name="new-keyword"></a><span data-ttu-id="8d80a-169">New 키워드</span><span class="sxs-lookup"><span data-stu-id="8d80a-169">New Keyword</span></span>  
  
-   <span data-ttu-id="8d80a-170">간단한 인스턴스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d80a-170">Use short instantiation.</span></span> <span data-ttu-id="8d80a-171">예를 들어 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d80a-171">For example, use the following syntax:</span></span>  
  
     <span data-ttu-id="8d80a-172">[!code-vb[VbVbalrGuidelines #&21;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_13.vb)]</span><span class="sxs-lookup"><span data-stu-id="8d80a-172">[!code-vb[VbVbalrGuidelines#21](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_13.vb)]</span></span>  
  
     <span data-ttu-id="8d80a-173">앞의 줄이 하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8d80a-173">The preceding line is equivalent to this:</span></span>  
  
     <span data-ttu-id="8d80a-174">[!code-vb[VbVbalrGuidelines #&22;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_14.vb)]</span><span class="sxs-lookup"><span data-stu-id="8d80a-174">[!code-vb[VbVbalrGuidelines#22](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_14.vb)]</span></span>  
  
-   <span data-ttu-id="8d80a-175">매개 변수가 없는 생성자 대신 새 개체에 대 한 개체 이니셜라이저를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d80a-175">Use object initializers for new objects instead of the parameterless constructor:</span></span>  
  
     <span data-ttu-id="8d80a-176">[!code-vb[VbVbalrGuidelines&23;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_15.vb)]</span><span class="sxs-lookup"><span data-stu-id="8d80a-176">[!code-vb[VbVbalrGuidelines#23](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_15.vb)]</span></span>  
  
### <a name="event-handling"></a><span data-ttu-id="8d80a-177">이벤트 처리</span><span class="sxs-lookup"><span data-stu-id="8d80a-177">Event Handling</span></span>  
  
-   <span data-ttu-id="8d80a-178">사용 하 여 `Handles` 대신 `AddHandler`:</span><span class="sxs-lookup"><span data-stu-id="8d80a-178">Use `Handles` rather than `AddHandler`:</span></span>  
  
     <span data-ttu-id="8d80a-179">[!code-vb[VbVbalrGuidelines #&24;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_16.vb)]</span><span class="sxs-lookup"><span data-stu-id="8d80a-179">[!code-vb[VbVbalrGuidelines#24](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_16.vb)]</span></span>  
  
-   <span data-ttu-id="8d80a-180">사용 하 여 `AddressOf`, 대리자를 명시적으로 인스턴스화합니다 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8d80a-180">Use `AddressOf`, and do not instantiate the delegate explicitly:</span></span>  
  
     <span data-ttu-id="8d80a-181">[!code-vb[VbVbalrGuidelines #&25;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_17.vb)]</span><span class="sxs-lookup"><span data-stu-id="8d80a-181">[!code-vb[VbVbalrGuidelines#25](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_17.vb)]</span></span>  
  
-   <span data-ttu-id="8d80a-182">이벤트를 정의 하는 경우 간단한 구문을 사용 하 고 대리자를 정의 하 여 컴파일러가 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d80a-182">When you define an event, use the short syntax, and let the compiler define the delegate:</span></span>  
  
     <span data-ttu-id="8d80a-183">[!code-vb[VbVbalrGuidelines #&26;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_18.vb)]</span><span class="sxs-lookup"><span data-stu-id="8d80a-183">[!code-vb[VbVbalrGuidelines#26](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_18.vb)]</span></span>  
  
-   <span data-ttu-id="8d80a-184">이벤트 인지 여부를 확인 하지 않는 `Nothing` (null)를 호출 하기 전에 `RaiseEvent` 메서드.</span><span class="sxs-lookup"><span data-stu-id="8d80a-184">Do not verify whether an event is `Nothing` (null) before you call the `RaiseEvent` method.</span></span> <span data-ttu-id="8d80a-185">`RaiseEvent`에 대 한 검사 `Nothing` 전에 이벤트를 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="8d80a-185">`RaiseEvent` checks for `Nothing` before it raises the event.</span></span>  
  
### <a name="using-shared-members"></a><span data-ttu-id="8d80a-186">공유 멤버를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="8d80a-186">Using Shared Members</span></span>  
 <span data-ttu-id="8d80a-187">호출 `Shared` 클래스 이름에서가 아니라 인스턴스 변수를 사용 하 여 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="8d80a-187">Call `Shared` members by using the class name, not from an instance variable.</span></span>  
  
### <a name="use-xml-literals"></a><span data-ttu-id="8d80a-188">XML 리터럴을 사용 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8d80a-188">Use XML Literals</span></span>  
 <span data-ttu-id="8d80a-189">XML 리터럴 XML (예를 들어, 로드, 쿼리 및 변환)를 사용 하 여 작업할 때 발생 하는 가장 일반적인 작업을 간소화 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d80a-189">XML literals simplify the most common tasks that you encounter when you work with XML (for example, load, query, and transform).</span></span> <span data-ttu-id="8d80a-190">XML을 개발할 때 다음이 지침을 따르십시오.</span><span class="sxs-lookup"><span data-stu-id="8d80a-190">When you develop with XML, follow these guidelines:</span></span>  
  
-   <span data-ttu-id="8d80a-191">XML 리터럴을 사용 하 여 XML 문서 및 XML Api를 직접 호출 하는 대신 조각을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8d80a-191">Use XML literals to create XML documents and fragments instead of calling XML APIs directly.</span></span>  
  
-   <span data-ttu-id="8d80a-192">XML 리터럴에 대 한 성능 최적화를 활용 하기 위해 파일 또는 프로젝트 수준에서 XML 네임 스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8d80a-192">Import XML namespaces at the file or project level to take advantage of the performance optimizations for XML literals.</span></span>  
  
-   <span data-ttu-id="8d80a-193">XML 축 속성을 사용 하 여 특성과 해당 요소는 XML 문서에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d80a-193">Use the XML axis properties to access elements and attributes in an XML document.</span></span>  
  
-   <span data-ttu-id="8d80a-194">포함된 식을 사용 하 여 값을 포함 하 고와 같은 API 호출을 사용 하는 대신 기존 값에서 XML을 만들 수는 `Add` 메서드:</span><span class="sxs-lookup"><span data-stu-id="8d80a-194">Use embedded expressions to include values and to create XML from existing values instead of using API calls such as the `Add` method:</span></span>  
  
     <span data-ttu-id="8d80a-195">[!code-vb[VbVbalrGuidelines #&27;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_19.vb)]</span><span class="sxs-lookup"><span data-stu-id="8d80a-195">[!code-vb[VbVbalrGuidelines#27](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_19.vb)]</span></span>  
  
### <a name="linq-queries"></a><span data-ttu-id="8d80a-196">LINQ 쿼리</span><span class="sxs-lookup"><span data-stu-id="8d80a-196">LINQ Queries</span></span>  
  
-   <span data-ttu-id="8d80a-197">쿼리 변수에 의미 있는 이름을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d80a-197">Use meaningful names for query variables:</span></span>  
  
     <span data-ttu-id="8d80a-198">[!code-vb[VbVbalrGuidelines #&28;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_20.vb)]</span><span class="sxs-lookup"><span data-stu-id="8d80a-198">[!code-vb[VbVbalrGuidelines#28](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_20.vb)]</span></span>  
  
-   <span data-ttu-id="8d80a-199">익명 형식의 속성 이름이 소문자를 올바르게 표시 파스칼식 대를 사용 하 여 확인할 수 있도록 쿼리에서 요소에 대 한 이름 대/소문자 구분:</span><span class="sxs-lookup"><span data-stu-id="8d80a-199">Provide names for elements in a query to make sure that property names of anonymous types are correctly capitalized using Pascal casing:</span></span>  
  
     <span data-ttu-id="8d80a-200">[!code-vb[VbVbalrGuidelines #&29;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_21.vb)]</span><span class="sxs-lookup"><span data-stu-id="8d80a-200">[!code-vb[VbVbalrGuidelines#29](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_21.vb)]</span></span>  
  
-   <span data-ttu-id="8d80a-201">결과의 속성 이름이 모호하면 속성 이름을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="8d80a-201">Rename properties when the property names in the result would be ambiguous.</span></span> <span data-ttu-id="8d80a-202">예를 들어 쿼리에서 고객 이름 및 주문 ID를 반환 바꾸라는 그대로 유지 하는 대신 `Name` 및 `ID` 결과에서:</span><span class="sxs-lookup"><span data-stu-id="8d80a-202">For example, if your query returns a customer name and an order ID, rename them instead of leaving them as `Name` and `ID` in the result:</span></span>  
  
     <span data-ttu-id="8d80a-203">[!code-vb[VbVbalrGuidelines #&30;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_22.vb)]</span><span class="sxs-lookup"><span data-stu-id="8d80a-203">[!code-vb[VbVbalrGuidelines#30](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_22.vb)]</span></span>  
  
-   <span data-ttu-id="8d80a-204">쿼리 변수 및 범위 변수 선언에 형식 유추를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d80a-204">Use type inference in the declaration of query variables and range variables:</span></span>  
  
     <span data-ttu-id="8d80a-205">[!code-vb[VbVbalrGuidelines #&31;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_23.vb)]</span><span class="sxs-lookup"><span data-stu-id="8d80a-205">[!code-vb[VbVbalrGuidelines#31](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_23.vb)]</span></span>  
  
-   <span data-ttu-id="8d80a-206">아래의 쿼리 절을 정렬 된 `From` 문:</span><span class="sxs-lookup"><span data-stu-id="8d80a-206">Align query clauses under the `From` statement:</span></span>  
  
     <span data-ttu-id="8d80a-207">[!code-vb[VbVbalrGuidelines #&32;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_24.vb)]</span><span class="sxs-lookup"><span data-stu-id="8d80a-207">[!code-vb[VbVbalrGuidelines#32](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_24.vb)]</span></span>  
  
-   <span data-ttu-id="8d80a-208">사용 하 여 `Where` 다른 앞 절 쿼리 절 나중 쿼리 절이 필터링된 된 데이터 집합에서 실행 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d80a-208">Use `Where` clauses before other query clauses so that later query clauses operate on the filtered set of data:</span></span>  
  
     <span data-ttu-id="8d80a-209">[!code-vb[VbVbalrGuidelines #&33;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_25.vb)]</span><span class="sxs-lookup"><span data-stu-id="8d80a-209">[!code-vb[VbVbalrGuidelines#33](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_25.vb)]</span></span>  
  
-   <span data-ttu-id="8d80a-210">사용 하 여는 `Join` 절을 사용 하는 대신 조인 작업을 명시적으로 정의 된 `Where` 암시적으로 조인 작업을 정의 하는 절:</span><span class="sxs-lookup"><span data-stu-id="8d80a-210">Use the `Join` clause to explicitly define a join operation instead of using the `Where` clause to implicitly define a join operation:</span></span>  
  
     <span data-ttu-id="8d80a-211">[!code-vb[VbVbalrGuidelines #&34;](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_26.vb)]</span><span class="sxs-lookup"><span data-stu-id="8d80a-211">[!code-vb[VbVbalrGuidelines#34](../../../visual-basic/programming-guide/program-structure/codesnippet/VisualBasic/coding-conventions_26.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d80a-212">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8d80a-212">See Also</span></span>  
 [<span data-ttu-id="8d80a-213">보안 코딩 지침</span><span class="sxs-lookup"><span data-stu-id="8d80a-213">Secure Coding Guidelines</span></span>](http://msdn.microsoft.com/library/4f882d94-262b-4494-b0a6-ba9ba1f5f177)
