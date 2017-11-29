---
title: "&#39; IsNot &#39; 피연산자 형식 &#39; typename &#39; 만 비교할 수 &#39; 아무것도 &#39; 때문에, &#39; typename &#39; nullable 형식"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc32128
- vbc32128
helpviewer_keywords: BC32128
ms.assetid: 1155b23a-ad75-4bab-b9da-73f35c767a36
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ec0ae1561bfbee998e7c65f6023012c0f982a8a7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="39isnot39-operand-of-type-39typename39-can-only-be-compared-to-39nothing39-because-39typename39-is-a-nullable-type"></a>&#39; IsNot &#39; 피연산자 형식 &#39; typename &#39; 만 비교할 수 &#39; 아무것도 &#39; 때문에, &#39; typename &#39; nullable 형식
Nullable로 선언 된 변수에 비교 되었습니다 식을 이외의 `Nothing` 를 사용 하는 `IsNot` 연산자입니다.  
  
 **오류 ID:** BC32128  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  `IsNot` 연산자를 사용하여 nullable 형식을 `Nothing` 이외의 식과 비교하려면 다음 예제와 같이 nullable 형식에서 `GetType` 메서드를 호출하고 그 결과를 식과 비교합니다.  
  
```vb  
Dim number? As Integer = 5  
  
If number IsNot Nothing Then  
  If number.GetType() IsNot Type.GetType("System.Int32") Then   
  
  End If  
End If  
```  
  
## <a name="see-also"></a>참고 항목  
 [Nullable 값 형식](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)  
 [IsNot 연산자](../../../visual-basic/language-reference/operators/isnot-operator.md)
