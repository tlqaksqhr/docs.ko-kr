---
title: 샘플 컴파일 명령줄(Visual Basic)
ms.date: 03/13/2018
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- command line [Visual Basic], compilers
- compilation [Visual Basic], command-line
- command-line compilers
- compiling source code [Visual Basic], from command line
- Visual Basic compiler, sample command lines
ms.assetid: 5bfbb487-5f47-4267-969a-39dfb917beeb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cf20e2916efd2eb10065be22c319e34ddb2bda9a
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2018
---
# <a name="sample-compilation-command-lines-visual-basic"></a><span data-ttu-id="562f9-102">샘플 컴파일 명령줄 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="562f9-102">Sample compilation command lines (Visual Basic)</span></span>
<span data-ttu-id="562f9-103">Visual Basic 프로그램 내에서 컴파일 하는 대신 [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)], 실행 파일 (.exe) 또는 동적 연결 라이브러리 (.dll) 파일을 생성 하기 위해 명령줄에서 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="562f9-103">As an alternative to compiling Visual Basic programs from within [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)], you can compile from the command line to produce executable (.exe) files or dynamic-link library (.dll) files.</span></span>  
  
 <span data-ttu-id="562f9-104">Visual Basic 명령줄 컴파일러 입출력 파일, 어셈블리 및 디버그 및 전처리기 옵션을 제어 하는 옵션 집합을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="562f9-104">The Visual Basic command-line compiler supports a complete set of options that control input and output files, assemblies, and debug and preprocessor options.</span></span> <span data-ttu-id="562f9-105">각 옵션은 서로 바꿔 사용할 수 있는 두 가지 형태로 사용할 수 있는: `-option` 및 `/option`합니다.</span><span class="sxs-lookup"><span data-stu-id="562f9-105">Each option is available in two interchangeable forms: `-option` and `/option`.</span></span> <span data-ttu-id="562f9-106">이 설명서 표시는 `-option` 폼입니다.</span><span class="sxs-lookup"><span data-stu-id="562f9-106">This documentation shows only the `-option` form.</span></span>  
  
 <span data-ttu-id="562f9-107">다음 표에서 일부 예제 명령줄 사용자만 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="562f9-107">The following table lists some sample command lines you can modify for your own use.</span></span>  
  
|<span data-ttu-id="562f9-108">대상</span><span class="sxs-lookup"><span data-stu-id="562f9-108">To</span></span>|<span data-ttu-id="562f9-109">사용</span><span class="sxs-lookup"><span data-stu-id="562f9-109">Use</span></span>|  
|--------|---------|  
|<span data-ttu-id="562f9-110">File.vb 컴파일하고 File.exe 만들기</span><span class="sxs-lookup"><span data-stu-id="562f9-110">Compile File.vb and create File.exe</span></span>|`vbc -reference:Microsoft.VisualBasic.dll File.vb`|  
|<span data-ttu-id="562f9-111">File.vb 컴파일하고 File.dll 만들기</span><span class="sxs-lookup"><span data-stu-id="562f9-111">Compile File.vb and create File.dll</span></span>|`vbc -target:library File.vb`|  
|<span data-ttu-id="562f9-112">File.vb 컴파일하고 My.exe 만들기</span><span class="sxs-lookup"><span data-stu-id="562f9-112">Compile File.vb and create My.exe</span></span>|`vbc -out:My.exe File.vb`|  
|<span data-ttu-id="562f9-113">File.vb 컴파일하고 라이브러리와 File.dll 이라는 참조 어셈블리를 만들</span><span class="sxs-lookup"><span data-stu-id="562f9-113">Compile File.vb and create both a library and a reference assembly named File.dll</span></span>|`vbc -target:library -ref:.\debug\bin\ref\file.dll File.vb`|
|<span data-ttu-id="562f9-114">최적화 된 현재 디렉터리에 있는 모든 Visual Basic 파일에서 컴파일 및 `DEBUG` File2.exe 생성 정의 기호</span><span class="sxs-lookup"><span data-stu-id="562f9-114">Compile all Visual Basic files in the current directory, with optimizations on and the `DEBUG` symbol defined, producing File2.exe</span></span>|`vbc -define:DEBUG=1 -optimize -out:File2.exe *.vb`|  
|<span data-ttu-id="562f9-115">로고 또는 경고를 표시 하지 않고 File2.dll의 디버그 버전을 생성 하는 현재 디렉터리에 있는 모든 Visual Basic 파일을 컴파일하십시오.</span><span class="sxs-lookup"><span data-stu-id="562f9-115">Compile all Visual Basic files in the current directory, producing a debug version of File2.dll without displaying the logo or warnings</span></span>|`vbc -target:library -out:File2.dll -nowarn -nologo -debug *.vb`|  
|<span data-ttu-id="562f9-116">현재 디렉터리 Something.dll에 있는 모든 Visual Basic 파일을 컴파일하십시오.</span><span class="sxs-lookup"><span data-stu-id="562f9-116">Compile all Visual Basic files in the current directory to Something.dll</span></span>|`vbc -target:library -out:Something.dll *.vb`|  
  
> [!TIP]
>  <span data-ttu-id="562f9-117">연결 된 작업에 대 한 정보를 표시할 수는 Visual Studio IDE를 사용 하 여 프로젝트를 빌드할 때 **vbc** 명령을 출력 창에 해당 컴파일러 옵션을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="562f9-117">When you build a project by using the Visual Studio IDE, you can display information about the associated **vbc** command with its compiler options in the output window.</span></span> <span data-ttu-id="562f9-118">이 정보를 표시 하려면 엽니다는 [옵션 대화 상자, 프로젝트 및 솔루션, 빌드 및 실행](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run)를 설정한는 **MSBuild 프로젝트 빌드 출력의 자세한 정도** 를 **보통** 또는 더 높은 수준의 세부 정보 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="562f9-118">To display this information, open the [Options Dialog Box,  Projects and Solutions, Build and Run](/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run), and then set the **MSBuild project build output verbosity** to **Normal** or a higher level of verbosity.</span></span>   
  
## <a name="see-also"></a><span data-ttu-id="562f9-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="562f9-119">See Also</span></span>  
 [<span data-ttu-id="562f9-120">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="562f9-120">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="562f9-121">조건부 컴파일</span><span class="sxs-lookup"><span data-stu-id="562f9-121">Conditional Compilation</span></span>](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)
