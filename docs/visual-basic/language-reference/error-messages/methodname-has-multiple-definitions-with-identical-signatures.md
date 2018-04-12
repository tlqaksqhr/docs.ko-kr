---
title: '&#39; &lt;methodname&gt;&#39;에 시그니처가 동일한 정의가 여러 개'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30269
- bc30269
helpviewer_keywords:
- BC30269
ms.assetid: 39489621-6617-4e5c-9b24-c2faf8273891
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1a71d51690d6318a559a94ac81de625289d7587d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="39ltmethodnamegt39-has-multiple-definitions-with-identical-signatures"></a><span data-ttu-id="e68f9-102">&#39; &lt;methodname&gt;&#39;에 시그니처가 동일한 정의가 여러 개</span><span class="sxs-lookup"><span data-stu-id="e68f9-102">&#39;&lt;methodname&gt;&#39; has multiple definitions with identical signatures</span></span>
<span data-ttu-id="e68f9-103">A `Function` 또는 `Sub` 프로시저 선언 이전 선언과 동일한 프로시저 이름 및 인수 목록을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e68f9-103">A `Function` or `Sub` procedure declaration uses the identical procedure name and argument list as a previous declaration.</span></span> <span data-ttu-id="e68f9-104">원래 프로시저를 오버 로드 하려는 경우이 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="e68f9-104">One possible cause is an attempt to overload the original procedure.</span></span> <span data-ttu-id="e68f9-105">오버 로드 된 프로시저는 서로 다른 인수 목록이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e68f9-105">Overloaded procedures must have different argument lists.</span></span>  
  
 <span data-ttu-id="e68f9-106">**오류 ID:** BC30269</span><span class="sxs-lookup"><span data-stu-id="e68f9-106">**Error ID:** BC30269</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e68f9-107">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="e68f9-107">To correct this error</span></span>  
  
-   <span data-ttu-id="e68f9-108">프로시저 이름 또는 인수 목록, 변경 하거나 중복 된 선언을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="e68f9-108">Change the procedure name or the argument list, or remove the duplicate declaration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e68f9-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e68f9-109">See Also</span></span>  
 [<span data-ttu-id="e68f9-110">선언된 요소 참조</span><span class="sxs-lookup"><span data-stu-id="e68f9-110">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [<span data-ttu-id="e68f9-111">프로시저를 오버로드할 때 고려해야 할 사항</span><span class="sxs-lookup"><span data-stu-id="e68f9-111">Considerations in Overloading Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/considerations-in-overloading-procedures.md)
