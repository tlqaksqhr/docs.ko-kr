---
title: "/recurse | Microsoft 문서"
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
- /recurse compiler option [Visual Basic]
- -recurse compiler option [Visual Basic]
- recurse compiler option [Visual Basic]
ms.assetid: 84a0b670-33ae-44c4-a46a-b90388809317
caps.latest.revision: 12
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
ms.openlocfilehash: 9ceb2f3bc9e4d0f1088258f504b7a49c58a29e35
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="recurse"></a><span data-ttu-id="9e00d-102">/recurse</span><span class="sxs-lookup"><span data-stu-id="9e00d-102">/recurse</span></span>
<span data-ttu-id="9e00d-103">지정 된 디렉터리 또는 프로젝트 디렉터리의 모든 하위 디렉터리에 소스 코드 파일을 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="9e00d-103">Compiles source-code files in all child directories of either the specified directory or the project directory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e00d-104">구문</span><span class="sxs-lookup"><span data-stu-id="9e00d-104">Syntax</span></span>  
  
```  
/recurse:[dir\]file  
```  
  
## <a name="arguments"></a><span data-ttu-id="9e00d-105">인수</span><span class="sxs-lookup"><span data-stu-id="9e00d-105">Arguments</span></span>  
 `dir`  
 <span data-ttu-id="9e00d-106">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="9e00d-106">Optional.</span></span> <span data-ttu-id="9e00d-107">검색을 시작할 원하는 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="9e00d-107">The directory in which you want the search to begin.</span></span> <span data-ttu-id="9e00d-108">지정 하지 않으면 프로젝트 디렉터리에서 검색을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e00d-108">If not specified, the search begins in the project directory.</span></span>  
  
 `file`  
 <span data-ttu-id="9e00d-109">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="9e00d-109">Required.</span></span> <span data-ttu-id="9e00d-110">검색할 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="9e00d-110">The file(s) to search for.</span></span> <span data-ttu-id="9e00d-111">와일드 카드 문자는 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e00d-111">Wildcard characters are allowed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9e00d-112">설명</span><span class="sxs-lookup"><span data-stu-id="9e00d-112">Remarks</span></span>  
 <span data-ttu-id="9e00d-113">사용 하지 않고 프로젝트 디렉터리에 일치 하는 모든 파일을 컴파일하려면 파일 이름에 와일드 카드를 사용할 수 `/recurse`합니다.</span><span class="sxs-lookup"><span data-stu-id="9e00d-113">You can use wildcards in a file name to compile all matching files in the project directory without using `/recurse`.</span></span> <span data-ttu-id="9e00d-114">출력 파일 이름은 없으므로 지정 하는 경우 컴파일러 기반 처리 하는 첫 번째 입력된 파일에 출력 파일 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e00d-114">If no output file name is specified, the compiler bases the output file name on the first input file processed.</span></span> <span data-ttu-id="9e00d-115">일반적으로 사전순으로 볼 때 컴파일된 파일의 목록에서 첫 번째 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="9e00d-115">This is generally the first file in the list of files compiled when viewed alphabetically.</span></span> <span data-ttu-id="9e00d-116">이러한 이유로 것이 좋습니다 사용 하 여 출력 파일을 지정 하는 `/out` 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="9e00d-116">For this reason, it is best to specify an output file using the `/out` option.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9e00d-117">`/recurse` 옵션은 Visual Studio 개발 환경 내에서 사용할 수 없습니다; 명령줄에서 컴파일할 때에 사용할 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e00d-117">The `/recurse` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9e00d-118">예제</span><span class="sxs-lookup"><span data-stu-id="9e00d-118">Example</span></span>  
 <span data-ttu-id="9e00d-119">다음 코드는 모든 컴파일하고 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 현재 디렉터리의 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="9e00d-119">The following code compiles all [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] files in the current directory.</span></span>  
  
```  
vbc *.vb  
```  
  
 <span data-ttu-id="9e00d-120">다음 코드를 컴파일하고 모든 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 파일에 `Test\ABC` 디렉터리와이 디렉터리를 한 다음 생성 `Test.ABC.dll`합니다.</span><span class="sxs-lookup"><span data-stu-id="9e00d-120">The following code compiles all [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] files in the `Test\ABC` directory and any directories below it, and then generates `Test.ABC.dll`.</span></span>  
  
```  
vbc /target:library /out:Test.ABC.dll /recurse:Test\ABC\*.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="9e00d-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9e00d-121">See Also</span></span>  
 <span data-ttu-id="9e00d-122">[Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="9e00d-122">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="9e00d-123"> [/out (Visual Basic)](../../../visual-basic/reference/command-line-compiler/out.md) </span><span class="sxs-lookup"><span data-stu-id="9e00d-123"> [/out (Visual Basic)](../../../visual-basic/reference/command-line-compiler/out.md) </span></span>  
<span data-ttu-id="9e00d-124"> [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="9e00d-124"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>
