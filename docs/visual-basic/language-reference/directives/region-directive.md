---
title: "#Region 지시문 | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Region
- vb.#Region
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic compiler, compiler directives
- '#region directive'
- region directive (#region)
- '#Region keyword'
ms.assetid: 90a6a104-3cbf-47d0-bdc4-b585d0921b87
caps.latest.revision: 14
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
ms.openlocfilehash: 86b8e9ce99a8c12e290f5efdc5a5c4da57f350d9
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="region-directive"></a>#<span data-ttu-id="3ff6d-102">Region 지시문</span><span class="sxs-lookup"><span data-stu-id="3ff6d-102">Region Directive</span></span>
<span data-ttu-id="3ff6d-103">Visual Basic 파일에서 코드 섹션을 축소하고 숨깁니다.</span><span class="sxs-lookup"><span data-stu-id="3ff6d-103">Collapses and hides sections of code in Visual Basic files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ff6d-104">구문</span><span class="sxs-lookup"><span data-stu-id="3ff6d-104">Syntax</span></span>  
  
```  
  
      #Region "identifier_string"  
#End Region  
```  
  
## <a name="parts"></a><span data-ttu-id="3ff6d-105">요소</span><span class="sxs-lookup"><span data-stu-id="3ff6d-105">Parts</span></span>  
  
|<span data-ttu-id="3ff6d-106">용어</span><span class="sxs-lookup"><span data-stu-id="3ff6d-106">Term</span></span>|<span data-ttu-id="3ff6d-107">정의</span><span class="sxs-lookup"><span data-stu-id="3ff6d-107">Definition</span></span>|  
|---|---|  
|`identifier_string`|<span data-ttu-id="3ff6d-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="3ff6d-108">Required.</span></span> <span data-ttu-id="3ff6d-109">축소된 경우 영역의 제목 역할을 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="3ff6d-109">String that acts as the title of a region when it is collapsed.</span></span> <span data-ttu-id="3ff6d-110">영역은 기본적으로 축소되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ff6d-110">Regions are collapsed by default.</span></span>|  
|`#End Region`|<span data-ttu-id="3ff6d-111">`#Region` 블록을 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="3ff6d-111">Terminates the `#Region` block.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3ff6d-112">설명</span><span class="sxs-lookup"><span data-stu-id="3ff6d-112">Remarks</span></span>  
 <span data-ttu-id="3ff6d-113">`#Region` 지시문을 사용하면 Visual Studio 코드 편집기의 개요 기능을 사용할 때 확장하거나 축소할 코드 블록을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3ff6d-113">Use the `#Region` directive to specify a block of code to expand or collapse when using the outlining feature of the Visual Studio Code Editor.</span></span> <span data-ttu-id="3ff6d-114">을 배치할 수 또는 *중첩*, 비슷한 영역에 함께 그룹화 할 다른 영역에 영역입니다.</span><span class="sxs-lookup"><span data-stu-id="3ff6d-114">You can place, or *nest*, regions within other regions to group similar regions together.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3ff6d-115">예제</span><span class="sxs-lookup"><span data-stu-id="3ff6d-115">Example</span></span>  
 <span data-ttu-id="3ff6d-116">이 예제에서는 `#Region` 지시문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3ff6d-116">This example uses the `#Region` directive.</span></span>  
  
 <span data-ttu-id="3ff6d-117">[!code-vb[VbVbalrConditionalComp #&4;](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/region-directive_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="3ff6d-117">[!code-vb[VbVbalrConditionalComp#4](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/region-directive_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ff6d-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3ff6d-118">See Also</span></span>  
 <span data-ttu-id="3ff6d-119">[#If... ... #Else 지시문](../../../visual-basic/language-reference/directives/if-then-else-directives.md) </span><span class="sxs-lookup"><span data-stu-id="3ff6d-119">[#If...Then...#Else Directives](../../../visual-basic/language-reference/directives/if-then-else-directives.md) </span></span>  
<span data-ttu-id="3ff6d-120"> [개요](https://docs.microsoft.com/visualstudio/ide/outlining) </span><span class="sxs-lookup"><span data-stu-id="3ff6d-120"> [Outlining](https://docs.microsoft.com/visualstudio/ide/outlining) </span></span>  
<span data-ttu-id="3ff6d-121"> [방법: 코드 섹션 축소 및 숨기기](../../../visual-basic/programming-guide/program-structure/how-to-collapse-and-hide-sections-of-code.md)</span><span class="sxs-lookup"><span data-stu-id="3ff6d-121"> [How to: Collapse and Hide Sections of Code](../../../visual-basic/programming-guide/program-structure/how-to-collapse-and-hide-sections-of-code.md)</span></span>
