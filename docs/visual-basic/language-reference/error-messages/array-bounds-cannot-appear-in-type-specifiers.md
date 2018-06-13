---
title: 배열 범위는 형식 지정자에 사용할 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- vbc30638
- bc30638
helpviewer_keywords:
- BC30638
ms.assetid: 93b654f4-70fa-4a48-baed-ffae42075550
ms.openlocfilehash: 45787db51de562f2266c587fd2bb15ef29ebefbe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33583685"
---
# <a name="array-bounds-cannot-appear-in-type-specifiers"></a><span data-ttu-id="1cb99-102">배열 범위는 형식 지정자에 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1cb99-102">Array bounds cannot appear in type specifiers</span></span>
<span data-ttu-id="1cb99-103">배열 크기는 데이터 형식 지정자의 일환으로 선언할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1cb99-103">Array sizes cannot be declared as part of a data type specifier.</span></span>  
  
 <span data-ttu-id="1cb99-104">**오류 ID:** BC30638</span><span class="sxs-lookup"><span data-stu-id="1cb99-104">**Error ID:** BC30638</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1cb99-105">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="1cb99-105">To correct this error</span></span>  
  
-   <span data-ttu-id="1cb99-106">이름 바로 뒤에 변수 형식, 다음 배열 크기를 지정 하는 대신 다음 예제와 같이 배열의 크기를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cb99-106">Specify the size of the array immediately following the variable name instead of placing the array size after the type, as shown in the following example.</span></span>  
  
    ```  
    Dim Array(8) As Integer   
    ```  
  
-   <span data-ttu-id="1cb99-107">배열을 정의 하 고 다음 예제와 같이 사용 하 여 원하는 수의 요소를 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cb99-107">Define an array and initialize it with the desired number of elements, as shown in the following example.</span></span>  
  
    ```  
    Dim Array2() As Integer = New Integer(8) {}  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="1cb99-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1cb99-108">See Also</span></span>  
 [<span data-ttu-id="1cb99-109">배열</span><span class="sxs-lookup"><span data-stu-id="1cb99-109">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)
