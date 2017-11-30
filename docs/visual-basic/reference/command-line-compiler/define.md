---
title: /define(Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- -d compiler option [Visual Basic]
- /d compiler option [Visual Basic]
- -define compiler option [Visual Basic]
- d compiler option [Visual Basic]
- /define compiler option [Visual Basic]
- define compiler option [Visual Basic]
ms.assetid: f735c57d-1cf9-4f2f-a26f-0de630fd4077
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8bc3056c3e2d7a4aad469d3bf2c404f5f5248384
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="define-visual-basic"></a><span data-ttu-id="c9042-102">/define(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c9042-102">/define (Visual Basic)</span></span>
<span data-ttu-id="c9042-103">조건부 컴파일러 상수를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c9042-103">Defines conditional compiler constants.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9042-104">구문</span><span class="sxs-lookup"><span data-stu-id="c9042-104">Syntax</span></span>  
  
```  
/define:["]symbol[=value][,symbol[=value]]["]  
' -or-  
/d:["]symbol[=value][,symbol[=value]]["]  
```  
  
## <a name="arguments"></a><span data-ttu-id="c9042-105">인수</span><span class="sxs-lookup"><span data-stu-id="c9042-105">Arguments</span></span>  
  
|<span data-ttu-id="c9042-106">용어</span><span class="sxs-lookup"><span data-stu-id="c9042-106">Term</span></span>|<span data-ttu-id="c9042-107">정의</span><span class="sxs-lookup"><span data-stu-id="c9042-107">Definition</span></span>|  
|---|---|  
|`symbol`|<span data-ttu-id="c9042-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="c9042-108">Required.</span></span> <span data-ttu-id="c9042-109">정의할 기호입니다.</span><span class="sxs-lookup"><span data-stu-id="c9042-109">The symbol to define.</span></span>|  
|`value`|<span data-ttu-id="c9042-110">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="c9042-110">Optional.</span></span> <span data-ttu-id="c9042-111">`symbol`을 할당할 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c9042-111">The value to assign `symbol`.</span></span> <span data-ttu-id="c9042-112">경우 `value` 문자열이 백슬래시/따옴표 시퀀스로 묶어야 (\\") 따옴표 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9042-112">If `value` is a string, it must be surrounded by backslash/quotation-mark sequences (\\") instead of quotation marks.</span></span> <span data-ttu-id="c9042-113">값을 지정하지 않으면 True가 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9042-113">If no value is specified, then it is taken to be True.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c9042-114">설명</span><span class="sxs-lookup"><span data-stu-id="c9042-114">Remarks</span></span>  
 <span data-ttu-id="c9042-115">`/define` 옵션을 사용하는 경우의 결과는 소스 파일에서 `#Const` 전처리기 지시문을 사용하는 것과 비슷합니다. 단, `/define`으로 정의하는 상수는 공용 상수이며 프로젝트의 모든 파일에 적용된다는 차이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9042-115">The `/define` option has an effect  similar to using a `#Const` preprocessor directive in your source file, except that constants defined with `/define` are public and apply to all files in the project.</span></span>  
  
 <span data-ttu-id="c9042-116">이 옵션으로 만든 기호를 `#If`...`Then`...`#Else` 지시문과 함께 사용하면 소스 파일을 조건부 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9042-116">You can use symbols created by this option with the `#If`...`Then`...`#Else` directive to compile source files conditionally.</span></span>  
  
 <span data-ttu-id="c9042-117">`/d`는 약식 `/define`입니다.</span><span class="sxs-lookup"><span data-stu-id="c9042-117">`/d` is the short form of `/define`.</span></span>  
  
 <span data-ttu-id="c9042-118">쉼표를 사용해 기호 정의를 구분하여 `/define`으로 여러 기호를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9042-118">You can define multiple symbols with `/define` by using a comma to separate symbol definitions.</span></span>  
  
|<span data-ttu-id="c9042-119">Visual Studio 통합 개발 환경에서 /define을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="c9042-119">To set /define in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="c9042-120">1.  **솔루션 탐색기**에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c9042-120">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="c9042-121">**프로젝트** 메뉴에서 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c9042-121">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="c9042-122">자세한 내용은 [프로젝트 디자이너 소개](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c9042-122">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="c9042-123">2.  **컴파일** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c9042-123">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="c9042-124">3.  **고급**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c9042-124">3.  Click **Advanced**.</span></span><br /><span data-ttu-id="c9042-125">4.  값을 수정 된 **사용자 지정 상수** 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="c9042-125">4.  Modify the value in the **Custom Constants** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c9042-126">예제</span><span class="sxs-lookup"><span data-stu-id="c9042-126">Example</span></span>  
 <span data-ttu-id="c9042-127">다음 코드는 두 조건부 컴파일러 상수를 정의한 다음 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c9042-127">The following code defines and then uses two conditional compiler constants.</span></span>  
  
 [!code-vb[VbVbalrCompiler#45](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/define_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="c9042-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c9042-128">See Also</span></span>  
 [<span data-ttu-id="c9042-129">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="c9042-129">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="c9042-130">#If...Then...#Else 지시문</span><span class="sxs-lookup"><span data-stu-id="c9042-130">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
 [<span data-ttu-id="c9042-131">#Const 지시문</span><span class="sxs-lookup"><span data-stu-id="c9042-131">#Const Directive</span></span>](../../../visual-basic/language-reference/directives/const-directive.md)  
 [<span data-ttu-id="c9042-132">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="c9042-132">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
