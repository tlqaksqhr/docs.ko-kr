---
title: "&#39; ReDim &#39; 차원 수를 변경할 수 없습니다."
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrArray_RankMismatch
ms.assetid: 52505298-9985-4682-8f6e-ff7d56077f34
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8cf3713c72bd07803935065780e894c130911a6c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="39redim39-cannot-change-the-number-of-dimensions"></a><span data-ttu-id="eaaa7-102">&#39; ReDim &#39; 차원 수를 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="eaaa7-102">&#39;ReDim&#39; cannot change the number of dimensions</span></span>
<span data-ttu-id="eaaa7-103">작업에서 `ReDim` 문을 사용하여 배열 차수(차원 수)를 변경하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="eaaa7-103">An operation attempts to use the `ReDim` statement to change the rank (number of dimensions) of an array.</span></span> <span data-ttu-id="eaaa7-104">`ReDim` 은 이전에 선언된 배열의 차원 크기를 하나 이상 변경할 수 있지만 배열 차수를 변경할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="eaaa7-104">`ReDim` can change the size of one or more dimensions of an array that has already been formally declared, but it cannot change an array's rank.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="eaaa7-105">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="eaaa7-105">To correct this error</span></span>  
  
-   <span data-ttu-id="eaaa7-106">해당 차원의 크기가 아닌 배열의 차수를 변경하려는지 확인하고 가능한 경우 `Dim` 을 사용하여 원하는 차수의 새 배열을 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="eaaa7-106">Ensure that you intend to change the array's rank and not the sizes of its dimensions, and if possible, use `Dim` to declare a new array with the desired rank.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eaaa7-107">참고 항목</span><span class="sxs-lookup"><span data-stu-id="eaaa7-107">See Also</span></span>  
 [<span data-ttu-id="eaaa7-108">Visual Basic의 배열</span><span class="sxs-lookup"><span data-stu-id="eaaa7-108">Arrays in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/arrays/index.md)  
 [<span data-ttu-id="eaaa7-109">Visual Basic의 배열 크기</span><span class="sxs-lookup"><span data-stu-id="eaaa7-109">Array dimensions in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/arrays/array-dimensions.md)  
 [<span data-ttu-id="eaaa7-110">ReDim 문</span><span class="sxs-lookup"><span data-stu-id="eaaa7-110">ReDim Statement</span></span>](../../visual-basic/language-reference/statements/redim-statement.md)  
 [<span data-ttu-id="eaaa7-111">Dim 문</span><span class="sxs-lookup"><span data-stu-id="eaaa7-111">Dim Statement</span></span>](../../visual-basic/language-reference/statements/dim-statement.md)
