---
title: "/optionexplicit | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /optionexplicit
dev_langs:
- VB
helpviewer_keywords:
- /optionexplicit compiler option [Visual Basic]
- optionexplicit compiler option [Visual Basic]
- -optionexplicit compiler option [Visual Basic]
ms.assetid: 5d296ab3-bafe-4c4d-9887-78f162ed86c7
caps.latest.revision: 16
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
ms.openlocfilehash: 3d2622c08b863233c8e1088bad252b37b3b38b04
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="optionexplicit"></a><span data-ttu-id="ab4f7-102">/optionexplicit</span><span class="sxs-lookup"><span data-stu-id="ab4f7-102">/optionexplicit</span></span>
<span data-ttu-id="ab4f7-103">사용 하기 전에 선언 되지 않은 경우에 컴파일러 오류 보고를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-103">Causes the compiler to report errors if variables are not declared before they are used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab4f7-104">구문</span><span class="sxs-lookup"><span data-stu-id="ab4f7-104">Syntax</span></span>  
  
```  
/optionexplicit[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="ab4f7-105">인수</span><span class="sxs-lookup"><span data-stu-id="ab4f7-105">Arguments</span></span>  
 <span data-ttu-id="ab4f7-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="ab4f7-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="ab4f7-107">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-107">Optional.</span></span> <span data-ttu-id="ab4f7-108">지정 `/optionexplicit+` 변수를 명시적으로 선언 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-108">Specify `/optionexplicit+` to require explicit declaration of variables.</span></span> <span data-ttu-id="ab4f7-109">`/optionexplicit+` 옵션 기본 인증 이며 동일 `/optionexplicit`합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-109">The `/optionexplicit+` option is the default and is the same as `/optionexplicit`.</span></span> <span data-ttu-id="ab4f7-110">`/optionexplicit-` 옵션을 사용 하면 암시적 변수 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-110">The `/optionexplicit-` option enables implicit declaration of variables.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ab4f7-111">주의</span><span class="sxs-lookup"><span data-stu-id="ab4f7-111">Remarks</span></span>  
 <span data-ttu-id="ab4f7-112">소스 코드 파일을 포함 하는 경우는 [Option Explicit 문](../../../visual-basic/language-reference/statements/option-explicit-statement.md), 문은 재정의 `/optionexplicit` 명령줄 컴파일러 설정을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-112">If the source code file contains an [Option Explicit Statement](../../../visual-basic/language-reference/statements/option-explicit-statement.md), the statement overrides the `/optionexplicit` command-line compiler setting.</span></span>  
  
### <a name="to-set-optionexplicit-in-the-visual-studio-ide"></a><span data-ttu-id="ab4f7-113">Visual Studio IDE에서 /optionexplicit을 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="ab4f7-113">To set /optionexplicit in the Visual Studio IDE</span></span>  
  
1.  <span data-ttu-id="ab4f7-114">**솔루션 탐색기**에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-114">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="ab4f7-115">에 **프로젝트** 메뉴를 클릭 하 여 **속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-115">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="ab4f7-116">자세한 내용은 [프로젝트 디자이너 소개](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-116">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span>  
  
2.  <span data-ttu-id="ab4f7-117">클릭 하 고 **컴파일** 탭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-117">Click the **Compile** tab.</span></span>  
  
3.  <span data-ttu-id="ab4f7-118">값을 수정 된 **Option Explicit** 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-118">Modify the value in the **Option Explicit** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ab4f7-119">예제</span><span class="sxs-lookup"><span data-stu-id="ab4f7-119">Example</span></span>  
 <span data-ttu-id="ab4f7-120">다음 코드를 컴파일한 경우 `/optionexplicit-` 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab4f7-120">The following code compiles when `/optionexplicit-` is used.</span></span>  
  
 <span data-ttu-id="ab4f7-121">[!code-vb[VbVbalrCompiler #&5;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/optionexplicit_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="ab4f7-121">[!code-vb[VbVbalrCompiler#5](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/optionexplicit_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab4f7-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ab4f7-122">See Also</span></span>  
 <span data-ttu-id="ab4f7-123">[Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="ab4f7-123">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="ab4f7-124"> [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) </span><span class="sxs-lookup"><span data-stu-id="ab4f7-124"> [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) </span></span>  
<span data-ttu-id="ab4f7-125"> [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md) </span><span class="sxs-lookup"><span data-stu-id="ab4f7-125"> [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md) </span></span>  
<span data-ttu-id="ab4f7-126"> [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) </span><span class="sxs-lookup"><span data-stu-id="ab4f7-126"> [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) </span></span>  
<span data-ttu-id="ab4f7-127"> [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="ab4f7-127"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="ab4f7-128"> [Option Explicit 문](../../../visual-basic/language-reference/statements/option-explicit-statement.md) </span><span class="sxs-lookup"><span data-stu-id="ab4f7-128"> [Option Explicit Statement](../../../visual-basic/language-reference/statements/option-explicit-statement.md) </span></span>  
<span data-ttu-id="ab4f7-129"> [옵션 대화 상자, 프로젝트, Visual Basic 기본값](https://docs.microsoft.com/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)</span><span class="sxs-lookup"><span data-stu-id="ab4f7-129"> [Visual Basic Defaults, Projects, Options Dialog Box](https://docs.microsoft.com/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)</span></span>
