---
title: -verbose
ms.date: 03/13/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- verbose compiler option [Visual Basic]
- -verbose compiler option [Visual Basic]
- /verbose compiler option [Visual Basic]
ms.assetid: d1aec0c1-0261-421d-9adc-5b13756100be
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f0523409e53a8c7ea34de7dcc24b1bce2885a183
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/22/2018
---
# <a name="-verbose"></a><span data-ttu-id="b15bd-102">-verbose</span><span class="sxs-lookup"><span data-stu-id="b15bd-102">-verbose</span></span>
<span data-ttu-id="b15bd-103">컴파일러가 상태 및 오류에 대 한 자세한 정보 메시지를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="b15bd-103">Causes the compiler to produce verbose status and error messages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b15bd-104">구문</span><span class="sxs-lookup"><span data-stu-id="b15bd-104">Syntax</span></span>  
  
```  
-verbose[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="b15bd-105">인수</span><span class="sxs-lookup"><span data-stu-id="b15bd-105">Arguments</span></span>  
 <span data-ttu-id="b15bd-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="b15bd-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="b15bd-107">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="b15bd-107">Optional.</span></span> <span data-ttu-id="b15bd-108">지정 `-verbose` 지정 하는 것과 같습니다 `-verbose+`, 자세한 정보 메시지를 내보낼 컴파일러가 합니다.</span><span class="sxs-lookup"><span data-stu-id="b15bd-108">Specifying `-verbose` is the same as specifying `-verbose+`, which causes the compiler to emit verbose messages.</span></span> <span data-ttu-id="b15bd-109">이 옵션의 기본값은 `-verbose-`합니다.</span><span class="sxs-lookup"><span data-stu-id="b15bd-109">The default for this option is `-verbose-`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b15bd-110">설명</span><span class="sxs-lookup"><span data-stu-id="b15bd-110">Remarks</span></span>  
 <span data-ttu-id="b15bd-111">`-verbose` 옵션은 컴파일러에서 생성 한 오류의 총 수에 대 한 정보를 표시 합니다. 모듈에 의해 로드 되 고 있는 어셈블리를 보고 하 고 현재 컴파일 중인 파일을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="b15bd-111">The `-verbose` option displays information about the total number of errors issued by the compiler, reports which assemblies are being loaded by a module, and displays which files are currently being compiled.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b15bd-112">`-verbose` 옵션은 Visual Studio 개발 환경 내에서 사용할 수 없습니다; 명령줄에서 컴파일할 경우에 사용할 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b15bd-112">The `-verbose` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b15bd-113">예제</span><span class="sxs-lookup"><span data-stu-id="b15bd-113">Example</span></span>  
 <span data-ttu-id="b15bd-114">다음 코드에서는 `In.vb` 자세한 상태 정보를 표시 하려면 컴파일러를 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="b15bd-114">The following code compiles `In.vb` and directs the compiler to display verbose status information.</span></span>  
  
```console  
vbc -verbose in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="b15bd-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b15bd-115">See Also</span></span>  
 [<span data-ttu-id="b15bd-116">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="b15bd-116">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="b15bd-117">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="b15bd-117">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
