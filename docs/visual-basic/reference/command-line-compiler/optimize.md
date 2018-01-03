---
title: /optimize
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- optimize compiler option [Visual Basic]
- /optimize compiler option [Visual Basic]
- optimization [Visual Basic], enabling
- -optimize compiler option [Visual Basic]
ms.assetid: fcba4a97-3622-4b87-a891-0f77deab4998
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e157fb0e1fcdb3899440eed02a42b16f75541989
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="optimize"></a><span data-ttu-id="16af0-102">/optimize</span><span class="sxs-lookup"><span data-stu-id="16af0-102">/optimize</span></span>
<span data-ttu-id="16af0-103">컴파일러 최적화를 사용 하지 않도록 설정 하거나 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="16af0-103">Enables or disables compiler optimizations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16af0-104">구문</span><span class="sxs-lookup"><span data-stu-id="16af0-104">Syntax</span></span>  
  
```  
/optimize[ + | - ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="16af0-105">인수</span><span class="sxs-lookup"><span data-stu-id="16af0-105">Arguments</span></span>  
  
|<span data-ttu-id="16af0-106">용어</span><span class="sxs-lookup"><span data-stu-id="16af0-106">Term</span></span>|<span data-ttu-id="16af0-107">정의</span><span class="sxs-lookup"><span data-stu-id="16af0-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="16af0-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="16af0-108">`+` &#124; `-`</span></span>|<span data-ttu-id="16af0-109">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="16af0-109">Optional.</span></span> <span data-ttu-id="16af0-110">`/optimize-` 컴파일러 최적화 옵션을 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="16af0-110">The `/optimize-` option disables compiler optimizations.</span></span> <span data-ttu-id="16af0-111">`/optimize+` 옵션 최적화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16af0-111">The `/optimize+` option enables optimizations.</span></span> <span data-ttu-id="16af0-112">최적화는 기본적으로 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="16af0-112">By default, optimizations are disabled.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="16af0-113">설명</span><span class="sxs-lookup"><span data-stu-id="16af0-113">Remarks</span></span>  
 <span data-ttu-id="16af0-114">컴파일러 최적화를 통해 더 작지만 빠르고 효율적인 출력 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="16af0-114">Compiler optimizations make your output file smaller, faster, and more efficient.</span></span> <span data-ttu-id="16af0-115">그러나 최적화로 인해 출력 파일에서 코드가 다시 정렬 되기 때문에, `/optimize+` 디버깅이 어려워질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16af0-115">However, because optimizations result in code rearrangement in the output file, `/optimize+` can make debugging difficult.</span></span>  
  
 <span data-ttu-id="16af0-116">생성 된 모든 모듈 `/target:module` 동일한 어셈블리를 사용 해야 `/optimize` 어셈블리로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="16af0-116">All modules generated with `/target:module` for an assembly must use the same `/optimize` settings as the assembly.</span></span> <span data-ttu-id="16af0-117">자세한 내용은 참조 [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="16af0-117">For more information, see [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span></span>  
  
 <span data-ttu-id="16af0-118">결합할 수는 `/optimize` 및 `/debug` 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="16af0-118">You can combine the `/optimize` and `/debug` options.</span></span>  
  
|<span data-ttu-id="16af0-119">Visual Studio 통합된 개발 환경에서 최적화 / 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="16af0-119">To set /optimize in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="16af0-120">1.  **솔루션 탐색기**에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="16af0-120">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="16af0-121">**프로젝트** 메뉴에서 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="16af0-121">On the **Project** menu, click **Properties**.</span></span><br />     <br /><span data-ttu-id="16af0-122">2.  **컴파일** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="16af0-122">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="16af0-123">3.  **고급** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="16af0-123">3.  Click the **Advanced** button.</span></span><br /><span data-ttu-id="16af0-124">4.  수정 된 **최적화를 활성화** 확인란 합니다.</span><span class="sxs-lookup"><span data-stu-id="16af0-124">4.  Modify the **Enable optimizations** check box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="16af0-125">예</span><span class="sxs-lookup"><span data-stu-id="16af0-125">Example</span></span>  
 <span data-ttu-id="16af0-126">다음 코드에서는 `T2.vb` 하 고 컴파일러 최적화를 활성화 합니다.</span><span class="sxs-lookup"><span data-stu-id="16af0-126">The following code compiles `T2.vb` and enables compiler optimizations.</span></span>  
  
```  
vbc t2.vb /optimize  
```  
  
## <a name="see-also"></a><span data-ttu-id="16af0-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="16af0-127">See Also</span></span>  
 [<span data-ttu-id="16af0-128">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="16af0-128">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="16af0-129">/debug (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="16af0-129">/debug (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/debug.md)  
 [<span data-ttu-id="16af0-130">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="16af0-130">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="16af0-131">/target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="16af0-131">/target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)
