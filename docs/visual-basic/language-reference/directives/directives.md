---
title: 지시문(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- directives, Visual Basic compiler
- Visual Basic code, directives
- directives
ms.assetid: 20d5fe65-490a-4c23-88c2-ee4f490ed762
ms.openlocfilehash: 38d54feae5cf7bf41a825d1f6000811e2b56f319
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33584646"
---
# <a name="directives-visual-basic"></a><span data-ttu-id="09f05-102">지시문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="09f05-102">Directives (Visual Basic)</span></span>
<span data-ttu-id="09f05-103">이 섹션의 항목에서는 Visual Basic 소스 코드 컴파일러 지시문을 문서화합니다.</span><span class="sxs-lookup"><span data-stu-id="09f05-103">The topics in this section document the Visual Basic source code compiler directives.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="09f05-104">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="09f05-104">In This Section</span></span>  
 <span data-ttu-id="09f05-105">[#Const 지시문](../../../visual-basic/language-reference/directives/const-directive.md) -컴파일러 상수를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="09f05-105">[#Const Directive](../../../visual-basic/language-reference/directives/const-directive.md) -- Define a compiler constant</span></span>  
  
 <span data-ttu-id="09f05-106">[#ExternalSource 지시문](../../../visual-basic/language-reference/directives/externalsource-directive.md) -소스 줄과 소스 외부에 있는 텍스트 간의 매핑을 나타냅니다</span><span class="sxs-lookup"><span data-stu-id="09f05-106">[#ExternalSource Directive](../../../visual-basic/language-reference/directives/externalsource-directive.md) -- Indicate a mapping between source lines and text external to the source</span></span>  
  
 <span data-ttu-id="09f05-107">[#If 중... ... #Else 지시문](../../../visual-basic/language-reference/directives/if-then-else-directives.md) -선택한 코드 블록을 컴파일</span><span class="sxs-lookup"><span data-stu-id="09f05-107">[#If...Then...#Else Directives](../../../visual-basic/language-reference/directives/if-then-else-directives.md) -- Compile selected blocks of code</span></span>  
  
 <span data-ttu-id="09f05-108">[#Region 지시문](../../../visual-basic/language-reference/directives/region-directive.md) --축소 및 숨기기 Visual Studio 편집기에서 코드의 섹션</span><span class="sxs-lookup"><span data-stu-id="09f05-108">[#Region Directive](../../../visual-basic/language-reference/directives/region-directive.md) -- Collapse and hide sections of code in the Visual Studio editor</span></span>  
  
 <span data-ttu-id="09f05-109">**#Disable, #Enable** --사용 하지 않도록 설정 하 고 코드 영역에 대 한 특정 경고를 활성화 합니다.</span><span class="sxs-lookup"><span data-stu-id="09f05-109">**#Disable, #Enable** -- Disable and enable specific warnings for regions of code.</span></span>  
  
```vb  
#Disable Warning BC42356 ' suppress warning about no awaits in this method  
    Async Function TestAsync() As Task  
        Console.WriteLine("testing")  
    End Function  
#Enable Warning BC42356  
```  
  
 <span data-ttu-id="09f05-110">쉼표로 구분된 경고 코드 목록도 사용하거나 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09f05-110">You can disable and enable a comma-separated list of warning codes too.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="09f05-111">관련 단원</span><span class="sxs-lookup"><span data-stu-id="09f05-111">Related Sections</span></span>  
 [<span data-ttu-id="09f05-112">Visual Basic 언어 참조</span><span class="sxs-lookup"><span data-stu-id="09f05-112">Visual Basic Language Reference</span></span>](../../../visual-basic/language-reference/index.md)  
  
 [<span data-ttu-id="09f05-113">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="09f05-113">Visual Basic</span></span>](../../../visual-basic/index.md)
