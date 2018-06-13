---
title: -highentropyva (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- highentropyva compiler option (Visual Basic)
- /highentropyva compiler option (Visual Basic)
ms.assetid: ff25f20a-6ca2-467b-9e52-5cf439f5028e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fef3f922d3089eaca1762ffe35fa38cfe94baf22
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33656332"
---
# <a name="-highentropyva-visual-basic"></a><span data-ttu-id="14926-102">-highentropyva (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="14926-102">-highentropyva (Visual Basic)</span></span>
<span data-ttu-id="14926-103">나타냅니다 64 비트 실행 파일 또는로 표시 된 실행 개체는 [/platform:anycpu](../../../visual-basic/reference/command-line-compiler/platform.md) 컴파일러 옵션은 높은 엔트로피 주소 공간 레이아웃 불규칙화 (ASLR)를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="14926-103">Indicates whether a 64-bit executable or an executable that's marked by the [/platform:anycpu](../../../visual-basic/reference/command-line-compiler/platform.md) compiler option supports high entropy Address Space Layout Randomization (ASLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14926-104">구문</span><span class="sxs-lookup"><span data-stu-id="14926-104">Syntax</span></span>  
  
```  
-highentropyva[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="14926-105">인수</span><span class="sxs-lookup"><span data-stu-id="14926-105">Arguments</span></span>  
 <span data-ttu-id="14926-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="14926-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="14926-107">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="14926-107">Optional.</span></span> <span data-ttu-id="14926-108">기본적으로 해제 되어 옵션 또는 지정 하는 경우 `-highentropyva-`합니다.</span><span class="sxs-lookup"><span data-stu-id="14926-108">The option is off by default or if you specify `-highentropyva-`.</span></span> <span data-ttu-id="14926-109">지정 하는 경우에 옵션은 `-highentropyva` 또는 `-highentropyva+`합니다.</span><span class="sxs-lookup"><span data-stu-id="14926-109">The option is on if you specify `-highentropyva` or `-highentropyva+`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="14926-110">설명</span><span class="sxs-lookup"><span data-stu-id="14926-110">Remarks</span></span>  
 <span data-ttu-id="14926-111">이 옵션을 지정 하면 Windows 커널의 호환 되는 버전 커널 ASLR의 일부로 프로세스의 주소 공간 레이아웃을 임의 할 때 보다 높은 수준의 엔트로피를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14926-111">If you specify this option, compatible versions of the Windows kernel can use higher degrees of entropy when the kernel randomizes the address space layout of a process as part of ASLR.</span></span> <span data-ttu-id="14926-112">커널에서 더 높은 수준의 엔트로피를 사용 하는 경우 스택 및 힙과 같은 메모리 영역에 더 많은 주소를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14926-112">If the kernel uses higher degrees of entropy, a larger number of addresses can be allocated to memory regions such as stacks and heaps.</span></span> <span data-ttu-id="14926-113">따라서 특정 메모리 영역의 위치를 추측하기 어려워집니다.</span><span class="sxs-lookup"><span data-stu-id="14926-113">As a result, it is more difficult to guess the location of a particular memory region.</span></span>  
  
 <span data-ttu-id="14926-114">이 옵션이 설정 되는 대상 실행 파일 및 모든 모듈에는 해당 모듈 64 비트 프로세스로 실행 하는 경우 4 기가바이트 (GB) 보다 큰 포인터 값을 처리 있어야 그에 따라 달라 지는 합니다.</span><span class="sxs-lookup"><span data-stu-id="14926-114">When the option is on, the target executable and any modules on which it depends must be able to handle pointer values that are larger than 4 gigabytes (GB) when those modules are running as 64-bit processes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14926-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="14926-115">See Also</span></span>  
 [<span data-ttu-id="14926-116">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="14926-116">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="14926-117">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="14926-117">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
