---
title: Option Explicit 문(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Explicit
- vb.OptionExplicit
helpviewer_keywords:
- declaring variables [Visual Basic], explicit
- forced variable declaration in Option Explicit statement [Visual Basic]
- Explicit keyword
- explicit variable declaration
- Option Explicit statement [Visual Basic]
ms.assetid: e82ac1ad-2cd3-49b2-b985-8bcf016f3fcc
ms.openlocfilehash: 3a2d81b1441052c132e4739dfe6045f8c3a026d4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604603"
---
# <a name="option-explicit-statement-visual-basic"></a><span data-ttu-id="119af-102">Option Explicit 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="119af-102">Option Explicit Statement (Visual Basic)</span></span>
<span data-ttu-id="119af-103">모든 변수는 파일에 명시적으로 강제 또는 암시적 선언을 변수의 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="119af-103">Forces explicit declaration of all variables in a file, or allows implicit declarations of variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="119af-104">구문</span><span class="sxs-lookup"><span data-stu-id="119af-104">Syntax</span></span>  
  
```  
Option Explicit { On | Off }  
```  
  
## <a name="parts"></a><span data-ttu-id="119af-105">요소</span><span class="sxs-lookup"><span data-stu-id="119af-105">Parts</span></span>  
 `On`  
 <span data-ttu-id="119af-106">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="119af-106">Optional.</span></span> <span data-ttu-id="119af-107">수 있도록 `Option Explicit` 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="119af-107">Enables `Option Explicit` checking.</span></span> <span data-ttu-id="119af-108">경우 `On` 또는 `Off` 를 지정 하지 않으면 기본값은 `On`합니다.</span><span class="sxs-lookup"><span data-stu-id="119af-108">If `On` or `Off` is not specified, the default is `On`.</span></span>  
  
 `Off`  
 <span data-ttu-id="119af-109">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="119af-109">Optional.</span></span> <span data-ttu-id="119af-110">사용 하지 않도록 설정 `Option Explicit` 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="119af-110">Disables `Option Explicit` checking.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="119af-111">설명</span><span class="sxs-lookup"><span data-stu-id="119af-111">Remarks</span></span>  
 <span data-ttu-id="119af-112">때 `Option Explicit On` 또는 `Option Explicit` 를 사용 하 여 모든 변수를 명시적으로 선언 해야는 파일에 표시 되는 `Dim` 또는 `ReDim` 문.</span><span class="sxs-lookup"><span data-stu-id="119af-112">When `Option Explicit On` or `Option Explicit` appears in a file, you must explicitly declare all variables by using the `Dim` or `ReDim` statements.</span></span> <span data-ttu-id="119af-113">선언 되지 않은 변수 이름을 사용 하려고 하면 컴파일 타임에 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="119af-113">If you try to use an undeclared variable name, an error occurs at compile time.</span></span> <span data-ttu-id="119af-114">`Option Explicit Off` 문은 암시적 선언의 변수를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="119af-114">The `Option Explicit Off` statement allows implicit declaration of variables.</span></span>  
  
 <span data-ttu-id="119af-115">`Option Explicit` 문은 사용하는 경우 파일에서 다른 소스 코드 문 앞에 나와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="119af-115">If used, the `Option Explicit` statement must appear in a file before any other source code statements.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="119af-116">설정 `Option Explicit` 를 `Off` 없는 일반적으로 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="119af-116">Setting `Option Explicit` to `Off` is generally not a good practice.</span></span> <span data-ttu-id="119af-117">하나 이상의 위치에서 변수 이름을 잘못 입력할 수 있습니다. 그러면 프로그램이 실행될 때 예기치 않은 결과가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="119af-117">You could misspell a variable name in one or more locations, which would cause unexpected results when the program is run.</span></span>  
  
## <a name="when-an-option-explicit-statement-is-not-present"></a><span data-ttu-id="119af-118">Option Explicit 문 현재 없는 경우</span><span class="sxs-lookup"><span data-stu-id="119af-118">When an Option Explicit Statement Is Not Present</span></span>  
 <span data-ttu-id="119af-119">소스 코드에 포함 되어 있지 않으면는 `Option Explicit` 문는 **Option Explicit** 에 설정 된 [컴파일 페이지, 프로젝트 디자이너 (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="119af-119">If the source code does not contain an `Option Explicit` statement, the **Option Explicit** setting on the [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) is used.</span></span> <span data-ttu-id="119af-120">명령줄 컴파일러를 사용 하는 경우는 [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) 컴파일러 옵션을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="119af-120">If the command-line compiler is used, the [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) compiler option is used.</span></span>  
  
#### <a name="to-set-option-explicit-in-the-ide"></a><span data-ttu-id="119af-121">IDE에서 Option Explicit을 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="119af-121">To set Option Explicit in the IDE</span></span>  
  
1.  <span data-ttu-id="119af-122">**솔루션 탐색기**에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="119af-122">In **Solution Explorer**, select a project.</span></span> <span data-ttu-id="119af-123">**프로젝트** 메뉴에서 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="119af-123">On the **Project** menu, click **Properties**.</span></span>  
  
2.  <span data-ttu-id="119af-124">**컴파일** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="119af-124">Click the **Compile** tab.</span></span>  
  
3.  <span data-ttu-id="119af-125">값을 설정는 **Option Explicit** 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="119af-125">Set the value in the **Option Explicit** box.</span></span>  
  
 <span data-ttu-id="119af-126">새 프로젝트를 만들 때는 **Option Explicit** 에 설정 된 **컴파일** 탭으로 설정 됩니다는 **Option Explicit** 에서 설정는 **VB 기본값**대화 상자.</span><span class="sxs-lookup"><span data-stu-id="119af-126">When you create a new project, the **Option Explicit** setting on the **Compile** tab is set to the **Option Explicit** setting in the **VB Defaults** dialog box.</span></span> <span data-ttu-id="119af-127">에 액세스 하려면는 **VB 기본값** 대화 상자의 **도구** 메뉴를 클릭 하 여 **옵션**합니다.</span><span class="sxs-lookup"><span data-stu-id="119af-127">To access the **VB Defaults** dialog box, on the **Tools** menu, click **Options**.</span></span> <span data-ttu-id="119af-128">**옵션** 대화 상자에서 **프로젝트 및 솔루션**을 확장하고 **VB 기본값**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="119af-128">In the **Options** dialog box, expand **Projects and Solutions**, and then click **VB Defaults**.</span></span> <span data-ttu-id="119af-129">초기 기본 설정은 **VB 기본값** 은 `On`합니다.</span><span class="sxs-lookup"><span data-stu-id="119af-129">The initial default setting in **VB Defaults** is `On`.</span></span>  
  
#### <a name="to-set-option-explicit-on-the-command-line"></a><span data-ttu-id="119af-130">명령줄에서 Option Explicit을 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="119af-130">To set Option Explicit on the command line</span></span>  
  
-   <span data-ttu-id="119af-131">포함 된 [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) 컴파일러 옵션에는 **vbc** 명령 합니다.</span><span class="sxs-lookup"><span data-stu-id="119af-131">Include the [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) compiler option in the **vbc** command.</span></span>  
  
## <a name="example"></a><span data-ttu-id="119af-132">예제</span><span class="sxs-lookup"><span data-stu-id="119af-132">Example</span></span>  
 <span data-ttu-id="119af-133">다음 예제에서는 `Option Explicit` 문을 명시적으로 모든 변수 선언에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="119af-133">The following example uses the `Option Explicit` statement to force explicit declaration of all variables.</span></span> <span data-ttu-id="119af-134">선언 되지 않은 변수를 사용 하려고 하면 컴파일 타임에 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="119af-134">Attempting to use an undeclared variable causes an error at compile time.</span></span>  
  
 [!code-vb[VbVbalrStatements#47](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-explicit-statement_1.vb)]  
  
 [!code-vb[VbVbalrStatements#48](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-explicit-statement_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="119af-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="119af-135">See Also</span></span>  
 [<span data-ttu-id="119af-136">Dim 문</span><span class="sxs-lookup"><span data-stu-id="119af-136">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
 [<span data-ttu-id="119af-137">ReDim 문</span><span class="sxs-lookup"><span data-stu-id="119af-137">ReDim Statement</span></span>](../../../visual-basic/language-reference/statements/redim-statement.md)  
 [<span data-ttu-id="119af-138">Option Compare 문</span><span class="sxs-lookup"><span data-stu-id="119af-138">Option Compare Statement</span></span>](../../../visual-basic/language-reference/statements/option-compare-statement.md)  
 [<span data-ttu-id="119af-139">Option Strict 문</span><span class="sxs-lookup"><span data-stu-id="119af-139">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [<span data-ttu-id="119af-140">/optioncompare</span><span class="sxs-lookup"><span data-stu-id="119af-140">/optioncompare</span></span>](../../../visual-basic/reference/command-line-compiler/optioncompare.md)  
 [<span data-ttu-id="119af-141">/optionexplicit</span><span class="sxs-lookup"><span data-stu-id="119af-141">/optionexplicit</span></span>](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)  
 [<span data-ttu-id="119af-142">/optionstrict</span><span class="sxs-lookup"><span data-stu-id="119af-142">/optionstrict</span></span>](../../../visual-basic/reference/command-line-compiler/optionstrict.md)  
 [<span data-ttu-id="119af-143">옵션 대화 상자, 프로젝트, Visual Basic 기본값</span><span class="sxs-lookup"><span data-stu-id="119af-143">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
