---
title: "For 루프 제어 변수를 통해 선언되는 배열은 초기 크기를 지정하여 선언할 수 없습니다."
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc32039
- bc32039
helpviewer_keywords: BC32039
ms.assetid: 1d8b6560-c9eb-4b71-a038-24c6f5a5ce46
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0635e1b18b24a241fabad6d67da34f8dde9530db
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="array-declared-as-for-loop-control-variable-cannot-be-declared-with-an-initial-size"></a>For 루프 제어 변수를 통해 선언되는 배열은 초기 크기를 지정하여 선언할 수 없습니다.
A `For Each` 루프는 배열을 사용 하 여 해당 *요소* 반복 변수는 있지만 해당 배열을 초기화 합니다.  
  
 다음 문에서이 오류를 생성 될 방법을 보여 줍니다.  
  
```  
Dim arrayList As New List(Of Integer())  
For Each listElement() As Integer In arrayList  
For Each listElement(1) As Integer In arrayList  
```  
  
 첫 번째 `For Each` 문에 요소에 액세스 하는 올바른 방법은 `arrayList`합니다. 두 번째 `For Each` 문은이 오류를 생성 합니다.  
  
 **오류 ID:** BC32039  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   선언에서 초기화를 제거는 *요소* 반복 변수입니다.  
  
## <a name="see-also"></a>참고 항목  
 [For...Next 문](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [배열](../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [컬렉션](http://msdn.microsoft.com/library/e76533a9-5033-4a0b-b003-9c2be60d185b)
