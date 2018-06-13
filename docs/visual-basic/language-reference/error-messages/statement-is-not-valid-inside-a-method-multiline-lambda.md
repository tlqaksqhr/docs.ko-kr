---
title: 문은은 메서드를 여러 줄 람다 내부 유효 하지 않습니다.
ms.date: 07/20/2015
f1_keywords:
- vbc30024
- bc30024
helpviewer_keywords:
- BC30024
ms.assetid: 758e7a8f-429b-42c1-9a78-778e5b480e04
ms.openlocfilehash: cef5beea16c8589a884b7d3533e0543454783999
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33598857"
---
# <a name="statement-is-not-valid-inside-a-methodmultiline-lambda"></a><span data-ttu-id="e9da4-102">메서드 내부에는 문을 사용할 수 없습니다./multiline lambda</span><span class="sxs-lookup"><span data-stu-id="e9da4-102">Statement is not valid inside a method/multiline lambda</span></span>
<span data-ttu-id="e9da4-103">문이에서 유효 하지 않음을 `Sub`, `Function`, 속성 `Get`, 속성 또는 `Set` 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="e9da4-103">The statement is not valid within a `Sub`, `Function`, property `Get`, or property `Set` procedure.</span></span> <span data-ttu-id="e9da4-104">일부 문이 모듈 또는 클래스 수준에 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9da4-104">Some statements can be placed at the module or class level.</span></span> <span data-ttu-id="e9da4-105">다른 사용자와 같은 `Option Strict`, 네임 스페이스 수준 이어야 하며 다른 모든 선언 앞에 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9da4-105">Others, such as `Option Strict`, must be at namespace level and precede all other declarations.</span></span>  
  
 <span data-ttu-id="e9da4-106">**오류 ID:** BC30024</span><span class="sxs-lookup"><span data-stu-id="e9da4-106">**Error ID:** BC30024</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e9da4-107">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="e9da4-107">To correct this error</span></span>  
  
-   <span data-ttu-id="e9da4-108">문을 프로시저에서 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="e9da4-108">Remove the statement from the procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9da4-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e9da4-109">See Also</span></span>  
 [<span data-ttu-id="e9da4-110">Sub 문</span><span class="sxs-lookup"><span data-stu-id="e9da4-110">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="e9da4-111">Function 문</span><span class="sxs-lookup"><span data-stu-id="e9da4-111">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
 [<span data-ttu-id="e9da4-112">Get 문</span><span class="sxs-lookup"><span data-stu-id="e9da4-112">Get Statement</span></span>](../../../visual-basic/language-reference/statements/get-statement.md)  
 [<span data-ttu-id="e9da4-113">Set 문</span><span class="sxs-lookup"><span data-stu-id="e9da4-113">Set Statement</span></span>](../../../visual-basic/language-reference/statements/set-statement.md)
