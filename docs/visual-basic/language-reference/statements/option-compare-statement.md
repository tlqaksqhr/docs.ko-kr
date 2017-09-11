---
title: "Option Compare 문 | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Compare
- vb.OptionCompare
dev_langs:
- VB
helpviewer_keywords:
- case sensitivity, Option Compare statement
- Compare keyword
- binary comparison
- strings [Visual Basic], returning from functions
- binary comparison, Option Compare statement
- strings [Visual Basic], comparing
- string comparison [Visual Basic], Option Compare statement
- Text keyword, Option Compare statement
- Binary keyword, Option Compare statement
- string comparison [Visual Basic], sorting data
- Option Compare statement
- text [Visual Basic], comparing
ms.assetid: 54e8eeeb-3b0d-4fb9-acce-fbfbd5975f6e
caps.latest.revision: 37
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
ms.sourcegitcommit: 31905a37f09db5f5192123f0118252fbe8b02eff
ms.openlocfilehash: 00618cd914c06b896d68b4074464af866f747895
ms.contentlocale: ko-kr
ms.lasthandoff: 05/26/2017

---
# <a name="option-compare-statement"></a><span data-ttu-id="d6dbc-102">Option Compare 문</span><span class="sxs-lookup"><span data-stu-id="d6dbc-102">Option Compare Statement</span></span>
<span data-ttu-id="d6dbc-103">문자열 데이터를 비교할 때 사용할 기본 비교 방법을 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="d6dbc-103">Declares the default comparison method to use when comparing string data.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6dbc-104">구문</span><span class="sxs-lookup"><span data-stu-id="d6dbc-104">Syntax</span></span>  
  
```  
Option Compare { Binary | Text }  
```  
  
## <a name="parts"></a><span data-ttu-id="d6dbc-105">요소</span><span class="sxs-lookup"><span data-stu-id="d6dbc-105">Parts</span></span>  
  
|<span data-ttu-id="d6dbc-106">용어</span><span class="sxs-lookup"><span data-stu-id="d6dbc-106">Term</span></span>|<span data-ttu-id="d6dbc-107">정의</span><span class="sxs-lookup"><span data-stu-id="d6dbc-107">Definition</span></span>|  
|---|---|  
|`Binary`|<span data-ttu-id="d6dbc-108">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="d6dbc-108">Optional.</span></span> <span data-ttu-id="d6dbc-109">문자의 내부 이진 표현에서 파생된 정렬 순서에 따라 문자열을 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="d6dbc-109">Results in string comparisons based on a sort order derived from the internal binary representations of the characters.</span></span><br /><br /> <span data-ttu-id="d6dbc-110">이 유형의 비교는 문자열에 텍스트로 해석할 수 없는 문자가 포함될 수 있는 경우 특히 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="d6dbc-110">This type of comparison is useful especially if the strings can contain characters that are not to be interpreted as text.</span></span> <span data-ttu-id="d6dbc-111">이 경우 대/소문자 미구분 등의 영문자 동일 여부에 따라 비교 결과가 달라지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d6dbc-111">In this case, you do not want to bias comparisons with alphabetical equivalences, such as case insensitivity.</span></span>|  
|`Text`|<span data-ttu-id="d6dbc-112">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="d6dbc-112">Optional.</span></span> <span data-ttu-id="d6dbc-113">시스템의 로캘에 따라 결정되는 대/소문자 미구분 텍스트 정렬 순서에 따라 문자열을 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="d6dbc-113">Results in string comparisons based on a case-insensitive text sort order determined by your system's locale.</span></span><br /><br /> <span data-ttu-id="d6dbc-114">문자열에 텍스트 문자만 포함되며 대/소문자 미구분, 밀접하게 관련된 문자 등의 영문자 동일 여부를 고려하여 이러한 문자를 비교하려는 경우에는 이 유형의 비교가 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="d6dbc-114">This type of comparison is useful if your strings contain all text characters, and you want to compare them taking into account alphabetic equivalences such as case insensitivity and closely related letters.</span></span> <span data-ttu-id="d6dbc-115">예를 들어 `A`와 `a`를 같은 문자로 간주하고 `Ä` 및 `ä`가 `B` 및 `b` 앞에 온다고 간주할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6dbc-115">For example, you might want to consider `A` and `a` to be equal, and `Ä` and `ä` to come before `B` and `b`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d6dbc-116">설명</span><span class="sxs-lookup"><span data-stu-id="d6dbc-116">Remarks</span></span>  
 <span data-ttu-id="d6dbc-117">`Option Compare` 문은 사용하는 경우 파일에서 다른 소스 코드 문 앞에 나와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6dbc-117">If used, the `Option Compare` statement must appear in a file before any other source code statements.</span></span>  
  
 <span data-ttu-id="d6dbc-118">`Option Compare` 문은 문자열 비교 방법(`Binary` 또는 `Text`)을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d6dbc-118">The `Option Compare` statement specifies the string comparison method (`Binary` or `Text`).</span></span>  <span data-ttu-id="d6dbc-119">기본 텍스트 비교 방법은 `Binary`입니다.</span><span class="sxs-lookup"><span data-stu-id="d6dbc-119">The default text comparison method is `Binary`.</span></span>  
  
 <span data-ttu-id="d6dbc-120">`Binary` 비교에서는 각 문자열 내 각 문자의 숫자 유니코드 값을 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="d6dbc-120">A `Binary` comparison compares the numeric Unicode value of each character in each string.</span></span> <span data-ttu-id="d6dbc-121">`Text` 비교에서는 현재 문화권의 어휘 의미에 따라 각 유니코드 문자를 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="d6dbc-121">A `Text` comparison compares each Unicode character based on its lexical meaning in the current culture.</span></span>  
  
 <span data-ttu-id="d6dbc-122">Microsoft windows에서 정렬 순서는 코드 페이지에 의해 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6dbc-122">In Microsoft Windows, sort order is determined by the code page.</span></span> <span data-ttu-id="d6dbc-123">자세한 내용은 [코드 페이지](https://docs.microsoft.com/cpp/c-runtime-library/code-pages) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d6dbc-123">For more information, see [Code Pages](https://docs.microsoft.com/cpp/c-runtime-library/code-pages).</span></span>  
  
 <span data-ttu-id="d6dbc-124">다음 예제에서는 `Option Compare Binary`를 사용하여 영어/유럽어 코드 페이지(ANSI 1252)의 문자를 정렬합니다. 그러면 일반적인 이진 정렬 순서가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6dbc-124">In the following example, characters in the English/European code page (ANSI 1252) are sorted by using `Option Compare Binary`, which produces a typical binary sort order.</span></span>  
  
 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`  
  
 <span data-ttu-id="d6dbc-125">
          `Option Compare Text`를 사용하여 같은 코드 페이지의 같은 문자를 정렬하면 다음 텍스트 정렬 순서가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6dbc-125">When the same characters in the same code page are sorted by using `Option Compare Text`, the following text sort order is produced.</span></span>  
  
 `(A=a) < (À = à) < (B=b) < (E=e) < (Ê = ê) < (Z=z) < (Ø = ø)`  
  
## <a name="when-an-option-compare-statement-is-not-present"></a><span data-ttu-id="d6dbc-126">Option Compare 문이 없는 경우</span><span class="sxs-lookup"><span data-stu-id="d6dbc-126">When an Option Compare Statement Is Not Present</span></span>  
 <span data-ttu-id="d6dbc-127">소스 코드에 없는 경우는 `Option Compare` 문는 **옵션 비교** 에 설정 된 [컴파일 페이지, 프로젝트 디자이너 (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic) 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6dbc-127">If the source code does not contain an `Option Compare` statement, the **Option Compare** setting on the [Compile Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic) is used.</span></span> <span data-ttu-id="d6dbc-128">으로 지정한 설정이 명령줄 컴파일러를 사용 하는 경우는 [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) 컴파일러 옵션을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6dbc-128">If you use the command-line compiler, the setting specified by the [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) compiler option is used.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
#### <a name="to-set-option-compare-in-the-ide"></a><span data-ttu-id="d6dbc-129">IDE에서 Option Compare를 설정하려면</span><span class="sxs-lookup"><span data-stu-id="d6dbc-129">To set Option Compare in the IDE</span></span>  
  
1.  <span data-ttu-id="d6dbc-130">**솔루션 탐색기**, 프로젝트를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6dbc-130">In **Solution Explorer**, select a project.</span></span> <span data-ttu-id="d6dbc-131">에 **프로젝트** 메뉴를 클릭 하 여 **속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="d6dbc-131">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="d6dbc-132">자세한 내용은 참조 [NIB: 프로젝트 디자이너를 사용 하 여 프로젝트 속성 관리](http://msdn.microsoft.com/en-us/983f3c18-832f-4666-afec-74b716ff3e0e)합니다.</span><span class="sxs-lookup"><span data-stu-id="d6dbc-132">For more information, see [NIB: Managing Project Properties with the Project Designer](http://msdn.microsoft.com/en-us/983f3c18-832f-4666-afec-74b716ff3e0e).</span></span>  
  
2.  <span data-ttu-id="d6dbc-133">클릭 하 고 **컴파일** 탭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6dbc-133">Click the **Compile** tab.</span></span>  
  
3.  <span data-ttu-id="d6dbc-134">값을 설정 된 **Option Compare** 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="d6dbc-134">Set the value in the **Option Compare** box.</span></span>  
  
 <span data-ttu-id="d6dbc-135">프로젝트를 만들 때는 **Option Compare** 설정에 **컴파일** 로 설정 되는 **Option Compare** 에서 설정는 **옵션** 대화 상자.</span><span class="sxs-lookup"><span data-stu-id="d6dbc-135">When you create a project, the **Option Compare** setting on the **Compile** tab is set to the **Option Compare** setting in the **Options** dialog box.</span></span> <span data-ttu-id="d6dbc-136">이 설정을 변경 하는 **도구** 메뉴를 클릭 하 여 **옵션**합니다.</span><span class="sxs-lookup"><span data-stu-id="d6dbc-136">To change this setting, on the **Tools** menu, click **Options**.</span></span> <span data-ttu-id="d6dbc-137">에 **옵션** 대화 상자에서 **프로젝트 및 솔루션**를 클릭 하 고 **VB 기본값**합니다.</span><span class="sxs-lookup"><span data-stu-id="d6dbc-137">In the **Options** dialog box, expand **Projects and Solutions**, and then click **VB Defaults**.</span></span> <span data-ttu-id="d6dbc-138">초기 기본 설정은 **VB 기본값** 는 **이진**합니다.</span><span class="sxs-lookup"><span data-stu-id="d6dbc-138">The initial default setting in **VB Defaults** is **Binary**.</span></span>  
  
#### <a name="to-set-option-compare-on-the-command-line"></a><span data-ttu-id="d6dbc-139">명령줄에서 Option Compare를 설정하려면</span><span class="sxs-lookup"><span data-stu-id="d6dbc-139">To set Option Compare on the command line</span></span>  
  
-   <span data-ttu-id="d6dbc-140">포함은 [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) 컴파일러 옵션에는 **vbc** 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="d6dbc-140">Include the [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) compiler option in the **vbc** command.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d6dbc-141">예제</span><span class="sxs-lookup"><span data-stu-id="d6dbc-141">Example</span></span>  
 <span data-ttu-id="d6dbc-142">다음 예제에서는 `Option Compare` 문을 사용하여 이진 비교를 기본 문자열 비교 방법으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d6dbc-142">The following example uses the `Option Compare` statement to set the binary comparison as the default string comparison method.</span></span> <span data-ttu-id="d6dbc-143">이 코드를 사용하려면 `Option Compare Binary` 문의 주석 처리를 제거하여 소스 파일 맨 위에 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="d6dbc-143">To use this code, uncomment the `Option Compare Binary` statement, and put it at the top of the source file.</span></span>  
  
 <span data-ttu-id="d6dbc-144">[!code-vb[VbVbalrStatements #&45;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-compare-statement_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="d6dbc-144">[!code-vb[VbVbalrStatements#45](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-compare-statement_1.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="d6dbc-145">예제</span><span class="sxs-lookup"><span data-stu-id="d6dbc-145">Example</span></span>  
 <span data-ttu-id="d6dbc-146">다음 예제에서는 `Option Compare` 문을 사용하여 대/소문자 미구분 텍스트 정렬 순서를 기본 문자열 비교 방법으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d6dbc-146">The following example uses the `Option Compare` statement to set the case-insensitive text sort order as the default string comparison method.</span></span> <span data-ttu-id="d6dbc-147">이 코드를 사용하려면 `Option Compare Text` 문의 주석 처리를 제거하여 소스 파일 맨 위에 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="d6dbc-147">To use this code, uncomment the `Option Compare Text` statement, and put it at the top of the source file.</span></span>  
  
 <span data-ttu-id="d6dbc-148">[!code-vb[VbVbalrStatements #&46;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-compare-statement_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="d6dbc-148">[!code-vb[VbVbalrStatements#46](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-compare-statement_2.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6dbc-149">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d6dbc-149">See Also</span></span>  
 <span data-ttu-id="d6dbc-150"><xref:Microsoft.VisualBasic.Strings.InStr%2A></xref:Microsoft.VisualBasic.Strings.InStr%2A></span><span class="sxs-lookup"><span data-stu-id="d6dbc-150"><xref:Microsoft.VisualBasic.Strings.InStr%2A></span></span>   
 <span data-ttu-id="d6dbc-151"><xref:Microsoft.VisualBasic.Strings.InStrRev%2A></xref:Microsoft.VisualBasic.Strings.InStrRev%2A></span><span class="sxs-lookup"><span data-stu-id="d6dbc-151"><xref:Microsoft.VisualBasic.Strings.InStrRev%2A></span></span>   
 <span data-ttu-id="d6dbc-152"><xref:Microsoft.VisualBasic.Strings.Replace%2A></xref:Microsoft.VisualBasic.Strings.Replace%2A></span><span class="sxs-lookup"><span data-stu-id="d6dbc-152"><xref:Microsoft.VisualBasic.Strings.Replace%2A></span></span>   
 <span data-ttu-id="d6dbc-153"><xref:Microsoft.VisualBasic.Strings.Split%2A></xref:Microsoft.VisualBasic.Strings.Split%2A></span><span class="sxs-lookup"><span data-stu-id="d6dbc-153"><xref:Microsoft.VisualBasic.Strings.Split%2A></span></span>   
 <span data-ttu-id="d6dbc-154"><xref:Microsoft.VisualBasic.Strings.StrComp%2A></xref:Microsoft.VisualBasic.Strings.StrComp%2A></span><span class="sxs-lookup"><span data-stu-id="d6dbc-154"><xref:Microsoft.VisualBasic.Strings.StrComp%2A></span></span>   
<span data-ttu-id="d6dbc-155"> [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) </span><span class="sxs-lookup"><span data-stu-id="d6dbc-155"> [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) </span></span>  
<span data-ttu-id="d6dbc-156"> [비교 연산자](../../../visual-basic/language-reference/operators/comparison-operators.md) </span><span class="sxs-lookup"><span data-stu-id="d6dbc-156"> [Comparison Operators](../../../visual-basic/language-reference/operators/comparison-operators.md) </span></span>  
<span data-ttu-id="d6dbc-157"> [Visual Basic의 비교 연산자](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md) </span><span class="sxs-lookup"><span data-stu-id="d6dbc-157"> [Comparison Operators in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md) </span></span>  
<span data-ttu-id="d6dbc-158"> [Like 연산자](../../../visual-basic/language-reference/operators/like-operator.md) </span><span class="sxs-lookup"><span data-stu-id="d6dbc-158"> [Like Operator](../../../visual-basic/language-reference/operators/like-operator.md) </span></span>  
<span data-ttu-id="d6dbc-159"> [문자열 함수](../../../visual-basic/language-reference/functions/string-functions.md) </span><span class="sxs-lookup"><span data-stu-id="d6dbc-159"> [String Functions](../../../visual-basic/language-reference/functions/string-functions.md) </span></span>  
<span data-ttu-id="d6dbc-160"> [Option Explicit 문](../../../visual-basic/language-reference/statements/option-explicit-statement.md) </span><span class="sxs-lookup"><span data-stu-id="d6dbc-160"> [Option Explicit Statement](../../../visual-basic/language-reference/statements/option-explicit-statement.md) </span></span>  
<span data-ttu-id="d6dbc-161"> [Option Strict 문](../../../visual-basic/language-reference/statements/option-strict-statement.md)</span><span class="sxs-lookup"><span data-stu-id="d6dbc-161"> [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md)</span></span>
