---
title: '&#39;ReDim&#39; 차원 수를 변경할 수 없습니다'
ms.date: 07/20/2015
f1_keywords:
- vbrArray_RankMismatch
ms.assetid: 52505298-9985-4682-8f6e-ff7d56077f34
ms.openlocfilehash: bfd4096141833b85a2126340ef549e1e1d1f8e3c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33640383"
---
# <a name="39redim39-cannot-change-the-number-of-dimensions"></a><span data-ttu-id="a9357-102">&#39;ReDim&#39; 차원 수를 변경할 수 없습니다</span><span class="sxs-lookup"><span data-stu-id="a9357-102">&#39;ReDim&#39; cannot change the number of dimensions</span></span>
<span data-ttu-id="a9357-103">작업에서 `ReDim` 문을 사용하여 배열 차수(차원 수)를 변경하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9357-103">An operation attempts to use the `ReDim` statement to change the rank (number of dimensions) of an array.</span></span> <span data-ttu-id="a9357-104">`ReDim` 은 이전에 선언된 배열의 차원 크기를 하나 이상 변경할 수 있지만 배열 차수를 변경할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a9357-104">`ReDim` can change the size of one or more dimensions of an array that has already been formally declared, but it cannot change an array's rank.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a9357-105">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="a9357-105">To correct this error</span></span>  
  
-   <span data-ttu-id="a9357-106">해당 차원의 크기가 아닌 배열의 차수를 변경하려는지 확인하고 가능한 경우 `Dim` 을 사용하여 원하는 차수의 새 배열을 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="a9357-106">Ensure that you intend to change the array's rank and not the sizes of its dimensions, and if possible, use `Dim` to declare a new array with the desired rank.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9357-107">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a9357-107">See Also</span></span>  
 [<span data-ttu-id="a9357-108">Visual Basic의 배열</span><span class="sxs-lookup"><span data-stu-id="a9357-108">Arrays in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/arrays/index.md)  
 [<span data-ttu-id="a9357-109">Visual Basic의 배열 크기</span><span class="sxs-lookup"><span data-stu-id="a9357-109">Array dimensions in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/arrays/array-dimensions.md)  
 [<span data-ttu-id="a9357-110">ReDim 문</span><span class="sxs-lookup"><span data-stu-id="a9357-110">ReDim Statement</span></span>](../../visual-basic/language-reference/statements/redim-statement.md)  
 [<span data-ttu-id="a9357-111">Dim 문</span><span class="sxs-lookup"><span data-stu-id="a9357-111">Dim Statement</span></span>](../../visual-basic/language-reference/statements/dim-statement.md)
