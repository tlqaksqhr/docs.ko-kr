---
title: /recurse
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /recurse compiler option [Visual Basic]
- -recurse compiler option [Visual Basic]
- recurse compiler option [Visual Basic]
ms.assetid: 84a0b670-33ae-44c4-a46a-b90388809317
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: bb69c7c44dcc2e8da5eb8a76f7d22f936a6d948f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="recurse"></a><span data-ttu-id="30b39-102">/recurse</span><span class="sxs-lookup"><span data-stu-id="30b39-102">/recurse</span></span>
<span data-ttu-id="30b39-103">지정된 된 디렉터리 또는 프로젝트 디렉터리의 모든 하위 디렉터리의 소스 코드 파일을 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="30b39-103">Compiles source-code files in all child directories of either the specified directory or the project directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30b39-104">구문</span><span class="sxs-lookup"><span data-stu-id="30b39-104">Syntax</span></span>  
  
```  
/recurse:[dir\]file  
```  
  
## <a name="arguments"></a><span data-ttu-id="30b39-105">인수</span><span class="sxs-lookup"><span data-stu-id="30b39-105">Arguments</span></span>  
 `dir`  
 <span data-ttu-id="30b39-106">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="30b39-106">Optional.</span></span> <span data-ttu-id="30b39-107">검색을 시작하려는 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="30b39-107">The directory in which you want the search to begin.</span></span> <span data-ttu-id="30b39-108">지정 하지 않으면 프로젝트 디렉터리에서 검색을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="30b39-108">If not specified, the search begins in the project directory.</span></span>  
  
 `file`  
 <span data-ttu-id="30b39-109">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="30b39-109">Required.</span></span> <span data-ttu-id="30b39-110">검색할 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="30b39-110">The file(s) to search for.</span></span> <span data-ttu-id="30b39-111">와일드카드 문자가 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="30b39-111">Wildcard characters are allowed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="30b39-112">설명</span><span class="sxs-lookup"><span data-stu-id="30b39-112">Remarks</span></span>  
 <span data-ttu-id="30b39-113">사용 하지 않고 프로젝트 디렉터리에 있는 모든 파일을 컴파일하는 파일 이름에 와일드 카드를 사용할 수 `/recurse`합니다.</span><span class="sxs-lookup"><span data-stu-id="30b39-113">You can use wildcards in a file name to compile all matching files in the project directory without using `/recurse`.</span></span> <span data-ttu-id="30b39-114">출력 파일 이름은 없으므로 지정 하는 경우 컴파일러 기반 처리 하는 첫 번째 입력된 파일에 출력 파일 이름을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="30b39-114">If no output file name is specified, the compiler bases the output file name on the first input file processed.</span></span> <span data-ttu-id="30b39-115">이 일반적으로 사전순으로 볼 때 컴파일된 파일의 목록에서 첫 번째 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="30b39-115">This is generally the first file in the list of files compiled when viewed alphabetically.</span></span> <span data-ttu-id="30b39-116">이러한 이유로 것이 가장 좋습니다 사용 하 여 출력 파일을 지정 하는 `/out` 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="30b39-116">For this reason, it is best to specify an output file using the `/out` option.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="30b39-117">`/recurse` 옵션은 Visual Studio 개발 환경 내에서 사용할 수 없습니다; 명령줄에서 컴파일할 경우에 사용할 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="30b39-117">The `/recurse` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="30b39-118">예제</span><span class="sxs-lookup"><span data-stu-id="30b39-118">Example</span></span>  
 <span data-ttu-id="30b39-119">다음 코드를 컴파일하고 모든 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 현재 디렉터리에 있는 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="30b39-119">The following code compiles all [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] files in the current directory.</span></span>  
  
```  
vbc *.vb  
```  
  
 <span data-ttu-id="30b39-120">다음 코드를 컴파일하고 모든 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 파일에 `Test\ABC` 디렉터리와이 디렉터리, 한 다음 생성 `Test.ABC.dll`합니다.</span><span class="sxs-lookup"><span data-stu-id="30b39-120">The following code compiles all [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] files in the `Test\ABC` directory and any directories below it, and then generates `Test.ABC.dll`.</span></span>  
  
```  
vbc /target:library /out:Test.ABC.dll /recurse:Test\ABC\*.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="30b39-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="30b39-121">See Also</span></span>  
 [<span data-ttu-id="30b39-122">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="30b39-122">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="30b39-123">/out (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="30b39-123">/out (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/out.md)  
 [<span data-ttu-id="30b39-124">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="30b39-124">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
