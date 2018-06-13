---
title: 이 배열은 고정되었거나 임시로 잠겨 있습니다(Visual Basic).
ms.date: 07/20/2015
f1_keywords:
- vbrID10
ms.assetid: de6713a6-51d7-4edb-8515-d5fb544e2091
ms.openlocfilehash: e912bd202603d9a0f427418708ad584c7d6203e9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33593566"
---
# <a name="this-array-is-fixed-or-temporarily-locked-visual-basic"></a><span data-ttu-id="45a21-102">이 배열은 고정되었거나 임시로 잠겨 있습니다(Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="45a21-102">This array is fixed or temporarily locked (Visual Basic)</span></span>
<span data-ttu-id="45a21-103">이 오류는 다음과 같은 가능한 원인을 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45a21-103">This error has the following possible causes:</span></span>  
  
-   <span data-ttu-id="45a21-104">사용 하 여 `ReDim` 고정 크기 배열 요소의 수를 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a21-104">Using `ReDim` to change the number of elements of a fixed-size array.</span></span>  
  
-   <span data-ttu-id="45a21-105">하나의 요소가 전달 인수로 프로시저에 모듈 수준 동적 배열의 치수를 다시 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a21-105">Redimensioning a module-level dynamic array, in which one element has been passed as an argument to a procedure.</span></span> <span data-ttu-id="45a21-106">방지 하기 위해 배열이 잠긴 요소가 전달 되는 경우에 참조 매개 변수는 프로시저에서 메모리 할당 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a21-106">If an element is passed, the array is locked to prevent deallocating memory for the reference parameter within the procedure.</span></span>  
  
-   <span data-ttu-id="45a21-107">에 값을 할당 하려고는 `Variant` 배열에 포함 된 변수 이지만 `Variant` 현재 잠겨 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45a21-107">Attempting to assign a value to a `Variant` variable containing an array, but the `Variant` is currently locked.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="45a21-108">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="45a21-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="45a21-109">원래 배열을 사용 하 여 선언 하 여 고정 되지 않고 동적으로 만들 `ReDim` (경우 배열을 선언할 프로시저 내에서), 또는 (배열이 모듈 수준에서 선언 되었습니다 하는 경우 요소 수를 지정 하지 않고 선언 하 여.</span><span class="sxs-lookup"><span data-stu-id="45a21-109">Make the original array dynamic rather than fixed by declaring it with `ReDim` (if the array is declared within a procedure), or by declaring it without specifying the number of elements (if the array is declared at the module level.</span></span>  
  
2.  <span data-ttu-id="45a21-110">실제로 모듈의 모든 프로시저 내에 표시 되는 요소를 전달 해야 하는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a21-110">Determine whether you really need to pass the element, since it is visible within all procedures in the module.</span></span>  
  
3.  <span data-ttu-id="45a21-111">잠그고 기능 확인의 `Variant` 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="45a21-111">Determine what is locking the `Variant` and remedy it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45a21-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="45a21-112">See Also</span></span>  
 [<span data-ttu-id="45a21-113">배열</span><span class="sxs-lookup"><span data-stu-id="45a21-113">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)
