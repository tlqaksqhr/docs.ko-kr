---
title: 배열 범위는 형식 지정자에 사용할 수 없습니다.
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30638
- bc30638
helpviewer_keywords:
- BC30638
ms.assetid: 93b654f4-70fa-4a48-baed-ffae42075550
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 770f86ca960110965b6917a22d284678ff8b6f8c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="array-bounds-cannot-appear-in-type-specifiers"></a><span data-ttu-id="a557a-102">배열 범위는 형식 지정자에 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a557a-102">Array bounds cannot appear in type specifiers</span></span>
<span data-ttu-id="a557a-103">배열 크기는 데이터 형식 지정자의 일환으로 선언할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a557a-103">Array sizes cannot be declared as part of a data type specifier.</span></span>  
  
 <span data-ttu-id="a557a-104">**오류 ID:** BC30638</span><span class="sxs-lookup"><span data-stu-id="a557a-104">**Error ID:** BC30638</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a557a-105">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="a557a-105">To correct this error</span></span>  
  
-   <span data-ttu-id="a557a-106">이름 바로 뒤에 변수 형식, 다음 배열 크기를 지정 하는 대신 다음 예제와 같이 배열의 크기를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a557a-106">Specify the size of the array immediately following the variable name instead of placing the array size after the type, as shown in the following example.</span></span>  
  
    ```  
    Dim Array(8) As Integer   
    ```  
  
-   <span data-ttu-id="a557a-107">배열을 정의 하 고 다음 예제와 같이 사용 하 여 원하는 수의 요소를 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="a557a-107">Define an array and initialize it with the desired number of elements, as shown in the following example.</span></span>  
  
    ```  
    Dim Array2() As Integer = New Integer(8) {}  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="a557a-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a557a-108">See Also</span></span>  
 [<span data-ttu-id="a557a-109">배열</span><span class="sxs-lookup"><span data-stu-id="a557a-109">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)
