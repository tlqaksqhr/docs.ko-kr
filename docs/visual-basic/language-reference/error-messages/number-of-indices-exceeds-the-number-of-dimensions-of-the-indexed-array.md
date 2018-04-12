---
title: 인덱스 수가 인덱싱된 배열의 차수보다 많습니다.
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30106
- vbc30106
helpviewer_keywords:
- BC30106
ms.assetid: 2c5363e1-62c2-4f5a-b675-c7337aeb363d
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8fdf031734d441daca2073925f6d45d6ba9f1f52
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="number-of-indices-exceeds-the-number-of-dimensions-of-the-indexed-array"></a><span data-ttu-id="23e3f-102">인덱스 수가 인덱싱된 배열의 차수보다 많습니다.</span><span class="sxs-lookup"><span data-stu-id="23e3f-102">Number of indices exceeds the number of dimensions of the indexed array</span></span>
<span data-ttu-id="23e3f-103">배열 요소에 액세스하는 데 사용하는 인덱스 수는 정확하게 배열의 순위, 즉 배열에 선언된 차원 수와 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="23e3f-103">The number of indices used to access an array element must be exactly the same as the rank of the array, that is, the number of dimensions declared for it.</span></span>  
  
 <span data-ttu-id="23e3f-104">**오류 ID:** BC30106</span><span class="sxs-lookup"><span data-stu-id="23e3f-104">**Error ID:** BC30106</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="23e3f-105">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="23e3f-105">To correct this error</span></span>  
  
-   <span data-ttu-id="23e3f-106">첨자의 총 수가 배열의 같아질 때까지 배열 참조에서 아래 첨자를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="23e3f-106">Remove subscripts from the array reference until the total number of subscripts equals the rank of the array.</span></span> <span data-ttu-id="23e3f-107">예:</span><span class="sxs-lookup"><span data-stu-id="23e3f-107">For example:</span></span>  
  
    ```vb  
    Dim gameBoard(3, 3) As String  
  
    ' Incorrect code. The array has two dimensions.  
    gameBoard(1, 1, 1) = "X"  
    gameBoard(2, 1, 1) = "O"  
  
    ' Correct code.  
    gameBoard(0, 0) = "X"  
    gameBoard(1, 0) = "O"  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="23e3f-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="23e3f-108">See Also</span></span>  
 [<span data-ttu-id="23e3f-109">배열</span><span class="sxs-lookup"><span data-stu-id="23e3f-109">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)
