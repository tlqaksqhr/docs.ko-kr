---
title: "/optimize | Microsoft 문서"
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
- optimize compiler option [Visual Basic]
- /optimize compiler option [Visual Basic]
- optimization, enabling
- -optimize compiler option [Visual Basic]
ms.assetid: fcba4a97-3622-4b87-a891-0f77deab4998
caps.latest.revision: 15
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
ms.openlocfilehash: f01ab17d4a2f5d123538294a7a13d7a6d7a40267
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="optimize"></a><span data-ttu-id="76c61-102">/optimize</span><span class="sxs-lookup"><span data-stu-id="76c61-102">/optimize</span></span>
<span data-ttu-id="76c61-103">컴파일러 최적화를 사용 하지 않도록 설정 하거나 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="76c61-103">Enables or disables compiler optimizations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76c61-104">구문</span><span class="sxs-lookup"><span data-stu-id="76c61-104">Syntax</span></span>  
  
```  
/optimize[ + | - ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="76c61-105">인수</span><span class="sxs-lookup"><span data-stu-id="76c61-105">Arguments</span></span>  
  
|<span data-ttu-id="76c61-106">용어</span><span class="sxs-lookup"><span data-stu-id="76c61-106">Term</span></span>|<span data-ttu-id="76c61-107">정의</span><span class="sxs-lookup"><span data-stu-id="76c61-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="76c61-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="76c61-108">`+` &#124; `-`</span></span>|<span data-ttu-id="76c61-109">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="76c61-109">Optional.</span></span> <span data-ttu-id="76c61-110">`/optimize-` 옵션 컴파일러 최적화를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="76c61-110">The `/optimize-` option disables compiler optimizations.</span></span> <span data-ttu-id="76c61-111">`/optimize+` 옵션 최적화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76c61-111">The `/optimize+` option enables optimizations.</span></span> <span data-ttu-id="76c61-112">기본적으로 최적화가 해제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="76c61-112">By default, optimizations are disabled.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="76c61-113">주의</span><span class="sxs-lookup"><span data-stu-id="76c61-113">Remarks</span></span>  
 <span data-ttu-id="76c61-114">컴파일러 최적화가 신속 하 게 작고 효율적 출력 파일을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="76c61-114">Compiler optimizations make your output file smaller, faster, and more efficient.</span></span> <span data-ttu-id="76c61-115">그러나 최적화로 인해 출력 파일에서 코드가 다시 정렬 되기 때문에, `/optimize+` 디버깅이 어려워질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76c61-115">However, because optimizations result in code rearrangement in the output file, `/optimize+` can make debugging difficult.</span></span>  
  
 <span data-ttu-id="76c61-116">모든 모듈을 사용 하 여 생성 `/target:module` 동일한 어셈블리 사용 해야 `/optimize` 어셈블리로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="76c61-116">All modules generated with `/target:module` for an assembly must use the same `/optimize` settings as the assembly.</span></span> <span data-ttu-id="76c61-117">자세한 내용은 참조 [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="76c61-117">For more information, see [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md).</span></span>  
  
 <span data-ttu-id="76c61-118">결합할 수는 `/optimize` 및 `/debug` 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="76c61-118">You can combine the `/optimize` and `/debug` options.</span></span>  
  
|<span data-ttu-id="76c61-119">설정 / Visual Studio 통합된 개발 환경에서 최적화</span><span class="sxs-lookup"><span data-stu-id="76c61-119">To set /optimize in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="76c61-120">1.  **솔루션 탐색기**에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="76c61-120">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="76c61-121">에 **프로젝트** 메뉴를 클릭 하 여 **속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="76c61-121">On the **Project** menu, click **Properties**.</span></span><br />     <span data-ttu-id="76c61-122">자세한 내용은 [프로젝트 디자이너 소개](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="76c61-122">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="76c61-123">2.  클릭 하 고 **컴파일** 탭 합니다.</span><span class="sxs-lookup"><span data-stu-id="76c61-123">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="76c61-124">3.  **고급** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="76c61-124">3.  Click the **Advanced** button.</span></span><br /><span data-ttu-id="76c61-125">4.  수정 된 **최적화를 활성화** 확인란입니다.</span><span class="sxs-lookup"><span data-stu-id="76c61-125">4.  Modify the **Enable optimizations** check box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="76c61-126">예제</span><span class="sxs-lookup"><span data-stu-id="76c61-126">Example</span></span>  
 <span data-ttu-id="76c61-127">다음 코드에서는 `T2.vb` 컴파일러 최적화를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76c61-127">The following code compiles `T2.vb` and enables compiler optimizations.</span></span>  
  
```  
vbc t2.vb /optimize  
```  
  
## <a name="see-also"></a><span data-ttu-id="76c61-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="76c61-128">See Also</span></span>  
 <span data-ttu-id="76c61-129">[Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="76c61-129">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="76c61-130"> [/debug (Visual Basic)](../../../visual-basic/reference/command-line-compiler/debug.md) </span><span class="sxs-lookup"><span data-stu-id="76c61-130"> [/debug (Visual Basic)](../../../visual-basic/reference/command-line-compiler/debug.md) </span></span>  
<span data-ttu-id="76c61-131"> [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="76c61-131"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="76c61-132"> [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)</span><span class="sxs-lookup"><span data-stu-id="76c61-132"> [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)</span></span>
