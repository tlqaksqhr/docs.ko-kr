---
title: 인덱스 수가 인덱싱된 배열의 차수보다 많습니다.
ms.date: 07/20/2015
f1_keywords:
- bc30106
- vbc30106
helpviewer_keywords:
- BC30106
ms.assetid: 2c5363e1-62c2-4f5a-b675-c7337aeb363d
ms.openlocfilehash: d40a19aefdca65773d3d8e37a43d99178586fb1c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33593438"
---
# <a name="number-of-indices-exceeds-the-number-of-dimensions-of-the-indexed-array"></a><span data-ttu-id="50fd9-102">인덱스 수가 인덱싱된 배열의 차수보다 많습니다.</span><span class="sxs-lookup"><span data-stu-id="50fd9-102">Number of indices exceeds the number of dimensions of the indexed array</span></span>
<span data-ttu-id="50fd9-103">배열 요소에 액세스하는 데 사용하는 인덱스 수는 정확하게 배열의 순위, 즉 배열에 선언된 차원 수와 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="50fd9-103">The number of indices used to access an array element must be exactly the same as the rank of the array, that is, the number of dimensions declared for it.</span></span>  
  
 <span data-ttu-id="50fd9-104">**오류 ID:** BC30106</span><span class="sxs-lookup"><span data-stu-id="50fd9-104">**Error ID:** BC30106</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="50fd9-105">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="50fd9-105">To correct this error</span></span>  
  
-   <span data-ttu-id="50fd9-106">첨자의 총 수가 배열의 같아질 때까지 배열 참조에서 아래 첨자를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="50fd9-106">Remove subscripts from the array reference until the total number of subscripts equals the rank of the array.</span></span> <span data-ttu-id="50fd9-107">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="50fd9-107">For example:</span></span>  
  
    ```vb  
    Dim gameBoard(3, 3) As String  
  
    ' Incorrect code. The array has two dimensions.  
    gameBoard(1, 1, 1) = "X"  
    gameBoard(2, 1, 1) = "O"  
  
    ' Correct code.  
    gameBoard(0, 0) = "X"  
    gameBoard(1, 0) = "O"  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="50fd9-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="50fd9-108">See Also</span></span>  
 [<span data-ttu-id="50fd9-109">배열</span><span class="sxs-lookup"><span data-stu-id="50fd9-109">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)
