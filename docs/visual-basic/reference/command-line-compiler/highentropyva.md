---
title: "/highentropyva (Visual Basic) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- highentropyva compiler option (Visual Basic)
- /highentropyva compiler option (Visual Basic)
ms.assetid: ff25f20a-6ca2-467b-9e52-5cf439f5028e
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
ms.openlocfilehash: ef482f142e07e96eabf93bd2223b0d24f351553b
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="highentropyva-visual-basic"></a><span data-ttu-id="a45f5-102">/highentropyva(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a45f5-102">/highentropyva (Visual Basic)</span></span>
<span data-ttu-id="a45f5-103">나타냅니다로 표시 된 실행 파일이 나 64 비트 실행 파일 여부는 [/platform:anycpu](../../../visual-basic/reference/command-line-compiler/platform.md) 컴파일러 옵션은 높은 엔트로피 주소 공간 레이아웃 불규칙화 (ASLR)를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="a45f5-103">Indicates whether a 64-bit executable or an executable that's marked by the [/platform:anycpu](../../../visual-basic/reference/command-line-compiler/platform.md) compiler option supports high entropy Address Space Layout Randomization (ASLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a45f5-104">구문</span><span class="sxs-lookup"><span data-stu-id="a45f5-104">Syntax</span></span>  
  
```  
/highentropyva[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="a45f5-105">인수</span><span class="sxs-lookup"><span data-stu-id="a45f5-105">Arguments</span></span>  
 <span data-ttu-id="a45f5-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="a45f5-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="a45f5-107">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="a45f5-107">Optional.</span></span> <span data-ttu-id="a45f5-108">기본적으로 해제 되어 옵션 또는 지정 하는 경우 `/highentropyva-`합니다.</span><span class="sxs-lookup"><span data-stu-id="a45f5-108">The option is off by default or if you specify `/highentropyva-`.</span></span> <span data-ttu-id="a45f5-109">지정 하는 경우에 옵션은 `/highentropyva` 또는 `/highentropyva+`합니다.</span><span class="sxs-lookup"><span data-stu-id="a45f5-109">The option is on if you specify `/highentropyva` or `/highentropyva+`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a45f5-110">주의</span><span class="sxs-lookup"><span data-stu-id="a45f5-110">Remarks</span></span>  
 <span data-ttu-id="a45f5-111">이 옵션을 지정 하는 경우에 Windows 커널의 호환 되는 버전 커널 ASLR의 일부로 프로세스의 주소 공간 레이아웃을 임의 때 더 높은 수준의 엔트로피를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a45f5-111">If you specify this option, compatible versions of the Windows kernel can use higher degrees of entropy when the kernel randomizes the address space layout of a process as part of ASLR.</span></span> <span data-ttu-id="a45f5-112">커널 더 높은 수준의 엔트로피를 사용 하면 스택 및 힙과 같은 메모리 영역에 더 많은 주소를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a45f5-112">If the kernel uses higher degrees of entropy, a larger number of addresses can be allocated to memory regions such as stacks and heaps.</span></span> <span data-ttu-id="a45f5-113">따라서 특정 메모리 영역의 위치를 추측하기 어려워집니다.</span><span class="sxs-lookup"><span data-stu-id="a45f5-113">As a result, it is more difficult to guess the location of a particular memory region.</span></span>  
  
 <span data-ttu-id="a45f5-114">옵션을 설정 하면 대상 실행 파일 및 모든 모듈에 대 그에 따라 달라 지는 수 있어야 64 비트 프로세스로 실행 되 고 이러한 모듈은 4gb (기가바이트) 보다 큰 포인터 값을 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="a45f5-114">When the option is on, the target executable and any modules on which it depends must be able to handle pointer values that are larger than 4 gigabytes (GB) when those modules are running as 64-bit processes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a45f5-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a45f5-115">See Also</span></span>  
 <span data-ttu-id="a45f5-116">[Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="a45f5-116">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="a45f5-117"> [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="a45f5-117"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>
