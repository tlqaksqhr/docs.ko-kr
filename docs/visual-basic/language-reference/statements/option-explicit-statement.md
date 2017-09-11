---
title: "Option Explicit 문 (Visual Basic) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Explicit
- vb.OptionExplicit
dev_langs:
- VB
helpviewer_keywords:
- declaring variables, explicit
- forced variable declaration in Option Explicit statement
- Explicit keyword
- explicit variable declaration
- Option Explicit statement
ms.assetid: e82ac1ad-2cd3-49b2-b985-8bcf016f3fcc
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
ms.openlocfilehash: 4283599d9ed2ad9075ab0b2f404f1a12a31437ec
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="option-explicit-statement-visual-basic"></a><span data-ttu-id="f4d66-102">Option Explicit 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f4d66-102">Option Explicit Statement (Visual Basic)</span></span>
<span data-ttu-id="f4d66-103">파일의 모든 변수에 대해 명시적으로 강제 또는 변수의 암시적 선언을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4d66-103">Forces explicit declaration of all variables in a file, or allows implicit declarations of variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4d66-104">구문</span><span class="sxs-lookup"><span data-stu-id="f4d66-104">Syntax</span></span>  
  
```  
Option Explicit { On | Off }  
```  
  
## <a name="parts"></a><span data-ttu-id="f4d66-105">요소</span><span class="sxs-lookup"><span data-stu-id="f4d66-105">Parts</span></span>  
 `On`  
 <span data-ttu-id="f4d66-106">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="f4d66-106">Optional.</span></span> <span data-ttu-id="f4d66-107">수 있도록 `Option Explicit` 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4d66-107">Enables `Option Explicit` checking.</span></span> <span data-ttu-id="f4d66-108">경우 `On` 또는 `Off` 를 지정 하지 않으면 기본값은 `On`합니다.</span><span class="sxs-lookup"><span data-stu-id="f4d66-108">If `On` or `Off` is not specified, the default is `On`.</span></span>  
  
 `Off`  
 <span data-ttu-id="f4d66-109">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="f4d66-109">Optional.</span></span> <span data-ttu-id="f4d66-110">사용 하지 않도록 설정 `Option Explicit` 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4d66-110">Disables `Option Explicit` checking.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f4d66-111">주의</span><span class="sxs-lookup"><span data-stu-id="f4d66-111">Remarks</span></span>  
 <span data-ttu-id="f4d66-112">때 `Option Explicit On` 또는 `Option Explicit` 를 사용 하 여 모든 변수를 명시적으로 선언 해야 파일에 표시 되는 `Dim` 또는 `ReDim` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="f4d66-112">When `Option Explicit On` or `Option Explicit` appears in a file, you must explicitly declare all variables by using the `Dim` or `ReDim` statements.</span></span> <span data-ttu-id="f4d66-113">선언 되지 않은 변수 이름을 사용 하려고 하면 컴파일 타임에 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4d66-113">If you try to use an undeclared variable name, an error occurs at compile time.</span></span> <span data-ttu-id="f4d66-114">`Option Explicit Off` 문에 변수 선언의 암시적 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4d66-114">The `Option Explicit Off` statement allows implicit declaration of variables.</span></span>  
  
 <span data-ttu-id="f4d66-115">`Option Explicit` 문은 사용하는 경우 파일에서 다른 소스 코드 문 앞에 나와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4d66-115">If used, the `Option Explicit` statement must appear in a file before any other source code statements.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f4d66-116">설정 `Option Explicit` 를 `Off` 는 일반적으로 없는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f4d66-116">Setting `Option Explicit` to `Off` is generally not a good practice.</span></span> <span data-ttu-id="f4d66-117">프로그램이 실행 될 때 예기치 않은 결과가 발생 하나 이상의 위치에서 변수 이름을 잘못 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4d66-117">You could misspell a variable name in one or more locations, which would cause unexpected results when the program is run.</span></span>  
  
## <a name="when-an-option-explicit-statement-is-not-present"></a><span data-ttu-id="f4d66-118">Option Explicit 문 현재 없는 경우</span><span class="sxs-lookup"><span data-stu-id="f4d66-118">When an Option Explicit Statement Is Not Present</span></span>  
 <span data-ttu-id="f4d66-119">소스 코드에 없는 경우는 `Option Explicit` 문는 **Option Explicit** 에 설정 된 [컴파일 페이지, 프로젝트 디자이너 (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic) 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f4d66-119">If the source code does not contain an `Option Explicit` statement, the **Option Explicit** setting on the [Compile Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic) is used.</span></span> <span data-ttu-id="f4d66-120">명령줄 컴파일러를 사용 하는 경우는 [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) 컴파일러 옵션을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4d66-120">If the command-line compiler is used, the [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) compiler option is used.</span></span>  
  
#### <a name="to-set-option-explicit-in-the-ide"></a><span data-ttu-id="f4d66-121">IDE에서 Option Explicit 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="f4d66-121">To set Option Explicit in the IDE</span></span>  
  
1.  <span data-ttu-id="f4d66-122">**솔루션 탐색기**, 프로젝트를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4d66-122">In **Solution Explorer**, select a project.</span></span> <span data-ttu-id="f4d66-123">에 **프로젝트** 메뉴를 클릭 하 여 **속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="f4d66-123">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="f4d66-124">자세한 내용은 [프로젝트 디자이너 소개](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f4d66-124">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span>  
  
2.  <span data-ttu-id="f4d66-125">클릭 하 고 **컴파일** 탭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4d66-125">Click the **Compile** tab.</span></span>  
  
3.  <span data-ttu-id="f4d66-126">값을 설정 된 **Option Explicit** 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="f4d66-126">Set the value in the **Option Explicit** box.</span></span>  
  
 <span data-ttu-id="f4d66-127">새 프로젝트를 만들 때는 **Option Explicit** 에 설정 된 **컴파일** 로 설정 되는 **Option Explicit** 에서 설정는 **VB 기본값** 대화 상자.</span><span class="sxs-lookup"><span data-stu-id="f4d66-127">When you create a new project, the **Option Explicit** setting on the **Compile** tab is set to the **Option Explicit** setting in the **VB Defaults** dialog box.</span></span> <span data-ttu-id="f4d66-128">에 액세스 하려면는 **VB 기본값** 대화 상자의 **도구** 메뉴를 클릭 하 여 **옵션**합니다.</span><span class="sxs-lookup"><span data-stu-id="f4d66-128">To access the **VB Defaults** dialog box, on the **Tools** menu, click **Options**.</span></span> <span data-ttu-id="f4d66-129">에 **옵션** 대화 상자에서 **프로젝트 및 솔루션**를 클릭 하 고 **VB 기본값**합니다.</span><span class="sxs-lookup"><span data-stu-id="f4d66-129">In the **Options** dialog box, expand **Projects and Solutions**, and then click **VB Defaults**.</span></span> <span data-ttu-id="f4d66-130">초기 기본 설정은 **VB 기본값** 는 `On`합니다.</span><span class="sxs-lookup"><span data-stu-id="f4d66-130">The initial default setting in **VB Defaults** is `On`.</span></span>  
  
#### <a name="to-set-option-explicit-on-the-command-line"></a><span data-ttu-id="f4d66-131">명령줄에서 Option Explicit 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="f4d66-131">To set Option Explicit on the command line</span></span>  
  
-   <span data-ttu-id="f4d66-132">포함은 [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) 컴파일러 옵션에는 **vbc** 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="f4d66-132">Include the [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) compiler option in the **vbc** command.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f4d66-133">예제</span><span class="sxs-lookup"><span data-stu-id="f4d66-133">Example</span></span>  
 <span data-ttu-id="f4d66-134">다음 예제에서는 `Option Explicit` 문을 모든 변수에 대해 명시적 선언을 강제 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4d66-134">The following example uses the `Option Explicit` statement to force explicit declaration of all variables.</span></span> <span data-ttu-id="f4d66-135">선언 되지 않은 변수를 사용 하려고 하면 컴파일 타임에 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="f4d66-135">Attempting to use an undeclared variable causes an error at compile time.</span></span>  
  
 <span data-ttu-id="f4d66-136">[!code-vb[VbVbalrStatements #&47;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-explicit-statement_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="f4d66-136">[!code-vb[VbVbalrStatements#47](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-explicit-statement_1.vb)]</span></span>  
  
 <span data-ttu-id="f4d66-137">[!code-vb[VbVbalrStatements #&48;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-explicit-statement_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="f4d66-137">[!code-vb[VbVbalrStatements#48](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-explicit-statement_2.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4d66-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f4d66-138">See Also</span></span>  
 <span data-ttu-id="f4d66-139">[Dim 문](../../../visual-basic/language-reference/statements/dim-statement.md) </span><span class="sxs-lookup"><span data-stu-id="f4d66-139">[Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md) </span></span>  
<span data-ttu-id="f4d66-140"> [ReDim 문](../../../visual-basic/language-reference/statements/redim-statement.md) </span><span class="sxs-lookup"><span data-stu-id="f4d66-140"> [ReDim Statement](../../../visual-basic/language-reference/statements/redim-statement.md) </span></span>  
<span data-ttu-id="f4d66-141"> [Option Compare 문](../../../visual-basic/language-reference/statements/option-compare-statement.md) </span><span class="sxs-lookup"><span data-stu-id="f4d66-141"> [Option Compare Statement](../../../visual-basic/language-reference/statements/option-compare-statement.md) </span></span>  
<span data-ttu-id="f4d66-142"> [Option Strict 문](../../../visual-basic/language-reference/statements/option-strict-statement.md) </span><span class="sxs-lookup"><span data-stu-id="f4d66-142"> [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md) </span></span>  
<span data-ttu-id="f4d66-143"> [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) </span><span class="sxs-lookup"><span data-stu-id="f4d66-143"> [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) </span></span>  
<span data-ttu-id="f4d66-144"> [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) </span><span class="sxs-lookup"><span data-stu-id="f4d66-144"> [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) </span></span>  
<span data-ttu-id="f4d66-145"> [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md) </span><span class="sxs-lookup"><span data-stu-id="f4d66-145"> [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md) </span></span>  
<span data-ttu-id="f4d66-146"> [옵션 대화 상자, 프로젝트, Visual Basic 기본값](https://docs.microsoft.com/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)</span><span class="sxs-lookup"><span data-stu-id="f4d66-146"> [Visual Basic Defaults, Projects, Options Dialog Box](https://docs.microsoft.com/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)</span></span>
