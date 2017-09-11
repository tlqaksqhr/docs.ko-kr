---
title: "샘플 컴파일 명령줄 (Visual Basic) | Microsoft 문서"
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
- command line, compilers
- compilation, command-line
- command-line compilers
- compiling source code, from command line
- Visual Basic compiler, sample command lines
ms.assetid: 5bfbb487-5f47-4267-969a-39dfb917beeb
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
ms.openlocfilehash: e58006c05f498ec1a9dbf5194fbc9bcdd281ab63
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="sample-compilation-command-lines-visual-basic"></a><span data-ttu-id="f0025-102">샘플 컴파일 명령줄(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f0025-102">Sample Compilation Command Lines (Visual Basic)</span></span>
<span data-ttu-id="f0025-103">컴파일하는 대신 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 내에서 프로그램 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)], 실행 파일 (.exe) 파일 또는 동적 연결 라이브러리 (.dll) 파일을 생성 하는 명령줄에서 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0025-103">As an alternative to compiling [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] programs from within [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)], you can compile from the command line to produce executable (.exe) files or dynamic-link library (.dll) files.</span></span>  
  
 <span data-ttu-id="f0025-104">[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 명령줄 컴파일러는 입력 및 출력 파일, 어셈블리 및 디버그를 제어 하는 옵션 및 전처리기 옵션의 전체 집합을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0025-104">The [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] command-line compiler supports a complete set of options that control input and output files, assemblies, and debug and preprocessor options.</span></span> <span data-ttu-id="f0025-105">각 옵션은 동일 하 게 사용 하는 두 가지 형태로 사용할 수 있는: `-``option` 및 `/``option`합니다.</span><span class="sxs-lookup"><span data-stu-id="f0025-105">Each option is available in two interchangeable forms: `-``option` and `/``option`.</span></span> <span data-ttu-id="f0025-106">이 설명서 표시는 `/``option` 폼입니다.</span><span class="sxs-lookup"><span data-stu-id="f0025-106">This documentation shows only the `/``option` form.</span></span>  
  
 <span data-ttu-id="f0025-107">다음 표에서 용도 맞게 수정할 수 있는 일부 예제 명령줄을 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0025-107">The following table lists some sample command lines you can modify for your own use.</span></span>  
  
|<span data-ttu-id="f0025-108">후</span><span class="sxs-lookup"><span data-stu-id="f0025-108">To</span></span>|<span data-ttu-id="f0025-109">기능</span><span class="sxs-lookup"><span data-stu-id="f0025-109">Use</span></span>|  
|--------|---------|  
|<span data-ttu-id="f0025-110">File.vb 컴파일하고 File.exe 만들기</span><span class="sxs-lookup"><span data-stu-id="f0025-110">Compile File.vb and create File.exe</span></span>|`vbc /reference:Microsoft.VisualBasic.dll File.vb`|  
|<span data-ttu-id="f0025-111">File.vb 컴파일하고 File.dll 만들기</span><span class="sxs-lookup"><span data-stu-id="f0025-111">Compile File.vb and create File.dll</span></span>|`vbc /target:library File.vb`|  
|<span data-ttu-id="f0025-112">File.vb 컴파일하고 My.exe 만들기</span><span class="sxs-lookup"><span data-stu-id="f0025-112">Compile File.vb and create My.exe</span></span>|`vbc /out:My.exe File.vb`|  
|<span data-ttu-id="f0025-113">모든 컴파일 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 에 최적화 된 현재 디렉터리에 파일 및 `DEBUG` 기호를 정의 File2.exe를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0025-113">Compile all [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] files in the current directory, with optimizations on and the `DEBUG` symbol defined, producing File2.exe</span></span>|`vbc /define:DEBUG=1 /optimize /out:File2.exe *.vb`|  
|<span data-ttu-id="f0025-114">모든 컴파일 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 로고 또는 경고를 표시 하지 않고 File2.dll의 디버그 버전을 생성 하는 현재 디렉터리의 파일</span><span class="sxs-lookup"><span data-stu-id="f0025-114">Compile all [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] files in the current directory, producing a debug version of File2.dll without displaying the logo or warnings</span></span>|`vbc /target:library /out:File2.dll /nowarn /nologo /debug *.vb`|  
|<span data-ttu-id="f0025-115">모든 컴파일 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Something.dll 현재 디렉터리의 파일</span><span class="sxs-lookup"><span data-stu-id="f0025-115">Compile all [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] files in the current directory to Something.dll</span></span>|`vbc /target:library /out:Something.dll *.vb`|  
  
 <span data-ttu-id="f0025-116">Microsoft를 명령줄에서 컴파일하는 경우 명시적으로 참조 해야 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 를 통해 런타임 라이브러리는 `/reference` 컴파일러 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="f0025-116">When compiling from the command line, you must explicitly reference the Microsoft [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] run-time library through the `/reference` compiler option.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="f0025-117">Visual Studio IDE를 사용 하 여 프로젝트를 빌드할 때 연결 된 작업에 대 한 정보를 표시할 수 있습니다 **vbc** 명령을 출력 창에 해당 컴파일러 옵션을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0025-117">When you build a project by using the Visual Studio IDE, you can display information about the associated **vbc** command with its compiler options in the output window.</span></span> <span data-ttu-id="f0025-118">이 정보를 표시 하려면 열에서 [옵션 대화 상자, 프로젝트 및 솔루션, 빌드 및 실행](https://docs.microsoft.com/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run)로 설정한는 **MSBuild 프로젝트 빌드 출력의 자세한 정도** 를 **보통** 또는 더 높은 수준의 자세한 정도입니다.</span><span class="sxs-lookup"><span data-stu-id="f0025-118">To display this information, open the [Options Dialog Box,  Projects and Solutions, Build and Run](https://docs.microsoft.com/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), and then set the **MSBuild project build output verbosity** to **Normal** or a higher level of verbosity.</span></span> <span data-ttu-id="f0025-119">자세한 내용은 [방법: 빌드 로그 파일 보기, 저장 및 구성](http://msdn.microsoft.com/library/75d38b76-26d6-4f43-bbe7-cbacd7cc81e7)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f0025-119">For more information, see [How to: View, Save, and Configure Build Log Files](http://msdn.microsoft.com/library/75d38b76-26d6-4f43-bbe7-cbacd7cc81e7).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0025-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f0025-120">See Also</span></span>  
 <span data-ttu-id="f0025-121">[Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="f0025-121">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="f0025-122"> [조건부 컴파일](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)</span><span class="sxs-lookup"><span data-stu-id="f0025-122"> [Conditional Compilation](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)</span></span>
