---
title: "앞에 오는 &#39;. &#39; 또는 &#39;! &#39; 내에 나타날 수는 &#39; 사용 &#39; 문"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30157
- bc30157
helpviewer_keywords: BC30157
ms.assetid: 70daaee1-14f9-45b7-9f30-53794310b95e
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 961f2d737123ab68b200d5fc7658cb81291a5de6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="leading-3939-or-3939-can-only-appear-inside-a-39with39-statement"></a><span data-ttu-id="79acb-102">앞에 오는 &#39;. &#39; 또는 &#39;! &#39; 내에 나타날 수는 &#39; 사용 &#39; 문</span><span class="sxs-lookup"><span data-stu-id="79acb-102">Leading &#39;.&#39; or &#39;!&#39; can only appear inside a &#39;With&#39; statement</span></span>
<span data-ttu-id="79acb-103">마침표 (.) 또는 느낌표 (!)를 내에 있지 않은 한 `With` 왼쪽에 식이 없는 합니다.</span><span class="sxs-lookup"><span data-stu-id="79acb-103">A period (.) or exclamation point (!) that is not inside a `With` block occurs without an expression on the left.</span></span> <span data-ttu-id="79acb-104">멤버 액세스 (`.`) 및 사전 멤버 액세스 (`!`) 멤버를 포함 하는 요소를 지정 하는 식이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="79acb-104">Member access (`.`) and dictionary member access (`!`) require an expression specifying the element that contains the member.</span></span> <span data-ttu-id="79acb-105">이 값은 왼쪽 접근자의 또는의 대상으로 즉시 표시 해야 합니다는 `With` 멤버 액세스를 포함 하는 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="79acb-105">This must appear immediately to the left of the accessor or as the target of a `With` block containing the member access.</span></span>  
  
 <span data-ttu-id="79acb-106">**오류 ID:** BC30157</span><span class="sxs-lookup"><span data-stu-id="79acb-106">**Error ID:** BC30157</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="79acb-107">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="79acb-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="79acb-108">확인 하는 `With` 블록 형식이 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="79acb-108">Ensure that the `With` block is correctly formatted.</span></span>  
  
2.  <span data-ttu-id="79acb-109">없는 경우 없는 `With` 블록에서 멤버를 포함 하는 정의 된 요소가 계산 되는 접근자의 왼쪽에 식을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="79acb-109">If there is no `With` block, add an expression to the left of the accessor that evaluates to a defined element containing the member.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79acb-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="79acb-110">See Also</span></span>  
 [<span data-ttu-id="79acb-111">코드의 특수 문자</span><span class="sxs-lookup"><span data-stu-id="79acb-111">Special Characters in Code</span></span>](../../../visual-basic/programming-guide/program-structure/special-characters-in-code.md)  
 [<span data-ttu-id="79acb-112">With...End With 문</span><span class="sxs-lookup"><span data-stu-id="79acb-112">With...End With Statement</span></span>](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
