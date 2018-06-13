---
title: '&#39;&lt;methodname&gt; &#39; 에 시그니처가 동일한 정의가 여러 개'
ms.date: 07/20/2015
f1_keywords:
- vbc30269
- bc30269
helpviewer_keywords:
- BC30269
ms.assetid: 39489621-6617-4e5c-9b24-c2faf8273891
ms.openlocfilehash: 059d152cf9c3fae77ab53a4a9248b36d99614c8b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33593732"
---
# <a name="39ltmethodnamegt39-has-multiple-definitions-with-identical-signatures"></a><span data-ttu-id="6682b-102">&#39;&lt;methodname&gt; &#39; 에 시그니처가 동일한 정의가 여러 개</span><span class="sxs-lookup"><span data-stu-id="6682b-102">&#39;&lt;methodname&gt;&#39; has multiple definitions with identical signatures</span></span>
<span data-ttu-id="6682b-103">A `Function` 또는 `Sub` 프로시저 선언 이전 선언과 동일한 프로시저 이름 및 인수 목록을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6682b-103">A `Function` or `Sub` procedure declaration uses the identical procedure name and argument list as a previous declaration.</span></span> <span data-ttu-id="6682b-104">원래 프로시저를 오버 로드 하려는 경우이 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="6682b-104">One possible cause is an attempt to overload the original procedure.</span></span> <span data-ttu-id="6682b-105">오버 로드 된 프로시저는 서로 다른 인수 목록이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6682b-105">Overloaded procedures must have different argument lists.</span></span>  
  
 <span data-ttu-id="6682b-106">**오류 ID:** BC30269</span><span class="sxs-lookup"><span data-stu-id="6682b-106">**Error ID:** BC30269</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="6682b-107">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="6682b-107">To correct this error</span></span>  
  
-   <span data-ttu-id="6682b-108">프로시저 이름 또는 인수 목록, 변경 하거나 중복 된 선언을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="6682b-108">Change the procedure name or the argument list, or remove the duplicate declaration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6682b-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6682b-109">See Also</span></span>  
 [<span data-ttu-id="6682b-110">선언된 요소 참조</span><span class="sxs-lookup"><span data-stu-id="6682b-110">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [<span data-ttu-id="6682b-111">프로시저를 오버로드할 때 고려해야 할 사항</span><span class="sxs-lookup"><span data-stu-id="6682b-111">Considerations in Overloading Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/considerations-in-overloading-procedures.md)
