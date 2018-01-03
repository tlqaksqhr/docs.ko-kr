---
title: /optionexplicit
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: /optionexplicit
helpviewer_keywords:
- /optionexplicit compiler option [Visual Basic]
- optionexplicit compiler option [Visual Basic]
- -optionexplicit compiler option [Visual Basic]
ms.assetid: 5d296ab3-bafe-4c4d-9887-78f162ed86c7
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1e701addb31b361e55f2761f441c23deaef7c10d
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="optionexplicit"></a><span data-ttu-id="a0de0-102">/optionexplicit</span><span class="sxs-lookup"><span data-stu-id="a0de0-102">/optionexplicit</span></span>
<span data-ttu-id="a0de0-103">사용 하면 컴파일러 오류 보고를 사용 하기 전에 선언 되지 않은 경우.</span><span class="sxs-lookup"><span data-stu-id="a0de0-103">Causes the compiler to report errors if variables are not declared before they are used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0de0-104">구문</span><span class="sxs-lookup"><span data-stu-id="a0de0-104">Syntax</span></span>  
  
```  
/optionexplicit[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="a0de0-105">인수</span><span class="sxs-lookup"><span data-stu-id="a0de0-105">Arguments</span></span>  
 <span data-ttu-id="a0de0-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="a0de0-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="a0de0-107">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="a0de0-107">Optional.</span></span> <span data-ttu-id="a0de0-108">지정 `/optionexplicit+` 명시적 변수 선언이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0de0-108">Specify `/optionexplicit+` to require explicit declaration of variables.</span></span> <span data-ttu-id="a0de0-109">`/optionexplicit+` 옵션은 기본값 이므로 동일 `/optionexplicit`합니다.</span><span class="sxs-lookup"><span data-stu-id="a0de0-109">The `/optionexplicit+` option is the default and is the same as `/optionexplicit`.</span></span> <span data-ttu-id="a0de0-110">`/optionexplicit-` 옵션을 사용 하면 변수를 암시적으로 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0de0-110">The `/optionexplicit-` option enables implicit declaration of variables.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a0de0-111">설명</span><span class="sxs-lookup"><span data-stu-id="a0de0-111">Remarks</span></span>  
 <span data-ttu-id="a0de0-112">소스 코드 파일을 포함 하는 경우는 [Option Explicit 문](../../../visual-basic/language-reference/statements/option-explicit-statement.md), 문이 재정의 `/optionexplicit` 명령줄 컴파일러 설정을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0de0-112">If the source code file contains an [Option Explicit Statement](../../../visual-basic/language-reference/statements/option-explicit-statement.md), the statement overrides the `/optionexplicit` command-line compiler setting.</span></span>  
  
### <a name="to-set-optionexplicit-in-the-visual-studio-ide"></a><span data-ttu-id="a0de0-113">/Optionexplicit Visual Studio IDE에서 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="a0de0-113">To set /optionexplicit in the Visual Studio IDE</span></span>  
  
1.  <span data-ttu-id="a0de0-114">**솔루션 탐색기**에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a0de0-114">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="a0de0-115">**프로젝트** 메뉴에서 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a0de0-115">On the **Project** menu, click **Properties**.</span></span>   
  
2.  <span data-ttu-id="a0de0-116">**컴파일** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a0de0-116">Click the **Compile** tab.</span></span>  
  
3.  <span data-ttu-id="a0de0-117">값을 수정 된 **Option Explicit** 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="a0de0-117">Modify the value in the **Option Explicit** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a0de0-118">예</span><span class="sxs-lookup"><span data-stu-id="a0de0-118">Example</span></span>  
 <span data-ttu-id="a0de0-119">다음 코드를 컴파일한 경우 `/optionexplicit-` 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0de0-119">The following code compiles when `/optionexplicit-` is used.</span></span>  
  
 [!code-vb[VbVbalrCompiler#5](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/optionexplicit_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="a0de0-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a0de0-120">See Also</span></span>  
 [<span data-ttu-id="a0de0-121">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="a0de0-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="a0de0-122">/optioncompare</span><span class="sxs-lookup"><span data-stu-id="a0de0-122">/optioncompare</span></span>](../../../visual-basic/reference/command-line-compiler/optioncompare.md)  
 [<span data-ttu-id="a0de0-123">/optionstrict</span><span class="sxs-lookup"><span data-stu-id="a0de0-123">/optionstrict</span></span>](../../../visual-basic/reference/command-line-compiler/optionstrict.md)  
 [<span data-ttu-id="a0de0-124">/optioninfer</span><span class="sxs-lookup"><span data-stu-id="a0de0-124">/optioninfer</span></span>](../../../visual-basic/reference/command-line-compiler/optioninfer.md)  
 [<span data-ttu-id="a0de0-125">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="a0de0-125">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="a0de0-126">Option Explicit 문</span><span class="sxs-lookup"><span data-stu-id="a0de0-126">Option Explicit Statement</span></span>](../../../visual-basic/language-reference/statements/option-explicit-statement.md)  
 [<span data-ttu-id="a0de0-127">옵션 대화 상자, 프로젝트, Visual Basic 기본값</span><span class="sxs-lookup"><span data-stu-id="a0de0-127">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
