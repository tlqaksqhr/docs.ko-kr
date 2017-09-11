---
title: "/addmodule | Microsoft 문서"
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
- /addmodule compiler option [Visual Basic]
- addmodule compiler option [Visual Basic]
- -addmodule compiler option [Visual Basic]
ms.assetid: fb4b89d4-4926-4f20-868d-427fa28497b2
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 2db0db5b5dd94f03e67d8680624e2a4ad23587f7
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="addmodule"></a><span data-ttu-id="35f16-102">/addmodule</span><span class="sxs-lookup"><span data-stu-id="35f16-102">/addmodule</span></span>
<span data-ttu-id="35f16-103">컴파일러에서 지정된 파일의 모든 형식 정보를 현재 컴파일하고 있는 프로젝트에 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="35f16-103">Causes the compiler to make all type information from the specified file(s) available to the project you are currently compiling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35f16-104">구문</span><span class="sxs-lookup"><span data-stu-id="35f16-104">Syntax</span></span>  
  
```  
/addmodule:fileList  
```  
  
## <a name="arguments"></a><span data-ttu-id="35f16-105">인수</span><span class="sxs-lookup"><span data-stu-id="35f16-105">Arguments</span></span>  
 `fileList`  
 <span data-ttu-id="35f16-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="35f16-106">Required.</span></span> <span data-ttu-id="35f16-107">메타 데이터를 포함 하지만 어셈블리 매니페스트를 포함 하지 않는 파일의 쉼표로 구분 된 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="35f16-107">Comma-delimited list of files that contain metadata but do not contain assembly manifests.</span></span> <span data-ttu-id="35f16-108">공백이 포함 된 파일 이름은 따옴표로 묶어야 ("").</span><span class="sxs-lookup"><span data-stu-id="35f16-108">File names containing spaces should be surrounded by quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="35f16-109">주의</span><span class="sxs-lookup"><span data-stu-id="35f16-109">Remarks</span></span>  
 <span data-ttu-id="35f16-110">나열 된 파일의 `fileList` 으로 매개 변수를 생성 합니다는 `/target:module` 옵션을 또는 다른 컴파일러의 동일 `/target:module`.</span><span class="sxs-lookup"><span data-stu-id="35f16-110">The files listed by the `fileList` parameter must be created with the `/target:module` option, or with another compiler's equivalent to `/target:module`.</span></span>  
  
 <span data-ttu-id="35f16-111">모든 모듈을 사용 하 여 추가 `/addmodule` 실행 시 출력 파일과 동일한 디렉터리에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="35f16-111">All modules added with `/addmodule` must be in the same directory as the output file at run time.</span></span> <span data-ttu-id="35f16-112">즉, 컴파일 타임에 모든 디렉터리에서 모듈을 지정할 수 있습니다 되지만 모듈에서 런타임에 응용 프로그램 디렉터리에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="35f16-112">That is, you can specify a module in any directory at compile time, but the module must be in the application directory at run time.</span></span> <span data-ttu-id="35f16-113">그렇지 않은 경우는 <xref:System.TypeLoadException>오류.</xref:System.TypeLoadException></span><span class="sxs-lookup"><span data-stu-id="35f16-113">If it is not, you get a <xref:System.TypeLoadException> error.</span></span>  
  
 <span data-ttu-id="35f16-114">(암시적 또는 명시적)을 지정 하면 모든[/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) 이외의 다른 옵션 `/target:module` 와 `/addmodule`에 전달 되는 파일이 `/addmodule` 프로젝트의 어셈블리의 일부가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="35f16-114">If you specify (implicitly or explicitly) any[/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) option other than `/target:module` with `/addmodule`, the files you pass to `/addmodule` become part of the project's assembly.</span></span> <span data-ttu-id="35f16-115">어셈블리에 있는 출력 파일을 실행 해야 합니다. 또는 더 많은 파일 추가 `/addmodule`합니다.</span><span class="sxs-lookup"><span data-stu-id="35f16-115">An assembly is required to run an output file that has one or more files added with `/addmodule`.</span></span>  
  
 <span data-ttu-id="35f16-116">사용 하 여 [/reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) 어셈블리를 포함 하는 파일에서 메타 데이터를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35f16-116">Use [/reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) to import metadata from a file that contains an assembly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="35f16-117">`/addmodule` 옵션은 Visual Studio 개발 환경 내에서 사용할 수 없습니다; 명령줄에서 컴파일할 때에 사용할 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35f16-117">The `/addmodule` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="35f16-118">예제</span><span class="sxs-lookup"><span data-stu-id="35f16-118">Example</span></span>  
 <span data-ttu-id="35f16-119">다음 코드는 모듈을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="35f16-119">The following code creates a module.</span></span>  
  
 <span data-ttu-id="35f16-120">[!code-vb[VbVbalrCompiler #&47;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/addmodule_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="35f16-120">[!code-vb[VbVbalrCompiler#47](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/addmodule_1.vb)]</span></span>  
  
 <span data-ttu-id="35f16-121">다음 코드는 모듈의 형식을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="35f16-121">The following code imports the module's types.</span></span>  
  
 <span data-ttu-id="35f16-122">[!code-vb[VbVbalrCompiler #&48;](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/addmodule_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="35f16-122">[!code-vb[VbVbalrCompiler#48](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/addmodule_2.vb)]</span></span>  
  
 <span data-ttu-id="35f16-123">실행 하는 경우 `t1`, 출력 `802`합니다.</span><span class="sxs-lookup"><span data-stu-id="35f16-123">When you run `t1`, it outputs `802`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35f16-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="35f16-124">See Also</span></span>  
 <span data-ttu-id="35f16-125">[Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="35f16-125">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="35f16-126"> [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) </span><span class="sxs-lookup"><span data-stu-id="35f16-126"> [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) </span></span>  
<span data-ttu-id="35f16-127"> [/reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) </span><span class="sxs-lookup"><span data-stu-id="35f16-127"> [/reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) </span></span>  
<span data-ttu-id="35f16-128"> [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="35f16-128"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>
