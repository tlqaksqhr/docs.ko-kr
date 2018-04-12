---
title: '&#39; 각 &#39;에 대 한 형식 &#39; &lt;typename&gt;&#39;의 여러 인스턴스 &#39; 구현 때문에 System.Collections.Generic.IEnumerable (Of T) &#39;'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc32096
- bc32096
helpviewer_keywords:
- BC32096
ms.assetid: ed20d09c-913f-482e-89f8-c0a596c3ec24
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a74178f3f0b2e7589b87046973473582993f3ed9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="39for-each39-on-type-39lttypenamegt39-is-ambiguous-because-the-type-implements-multiple-instantiations-of-39systemcollectionsgenericienumerableof-t39"></a>&#39; 각 &#39;에 대 한 형식 &#39; &lt;typename&gt;&#39;의 여러 인스턴스 &#39; 구현 때문에 System.Collections.Generic.IEnumerable (Of T) &#39;
A `For Each` 에 둘 이상의 반복기 변수를 지정 하는 문을 <xref:System.Collections.IEnumerable.GetEnumerator%2A> 메서드.  
  
 반복기 변수를 구현 하는 형식 이어야 합니다는 <xref:System.Collections.IEnumerable?displayProperty=nameWithType> 또는 <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> 인터페이스 중 하나에 `Collections` 의 네임 스페이스는 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]합니다. 둘 이상의 생성 된 제네릭 인터페이스를 각 구문에 대 한 다른 형식 인수를 사용 하 여 구현 하는 클래스에 대 한 것 같습니다. 이 작업을 수행 하는 클래스에서 반복기 변수를 사용 하는 경우 해당 변수가 둘 이상의 <xref:System.Collections.IEnumerable.GetEnumerator%2A> 메서드. 이 경우 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 호출할 메서드를 선택할 수 없습니다.  
  
 **오류 ID:** BC32096  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   사용 하 여 [DirectCast 연산자](../../../visual-basic/language-reference/operators/directcast-operator.md) 또는 [TryCast 연산자](../../../visual-basic/language-reference/operators/trycast-operator.md) 반복기 변수 형식을 정의 하는 인터페이스로 캐스팅할 수는 <xref:System.Collections.IEnumerable.GetEnumerator%2A> 사용할 방법을 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [For Each...Next 문](../../../visual-basic/language-reference/statements/for-each-next-statement.md)  
 [인터페이스](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
