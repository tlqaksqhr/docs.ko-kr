---
title: "제네릭 인터페이스 (Visual Basic)에 대 한 분산 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: cf4096d0-4bb3-45a9-9a6b-f01e29a60333
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: c53c27bdb085213046553fc4b08f11336880a7c2
ms.lasthandoff: 03/13/2017

---
# <a name="variance-in-generic-interfaces-visual-basic"></a>(Visual Basic) 제네릭 인터페이스의 가변성
.NET framework 4에는 여러 기존 제네릭 인터페이스에 대 한 분산 지원이 추가 되었습니다. 분산 지원을 통해 이러한 인터페이스를 구현 하는 클래스를 암시적으로 변환 합니다. 다음 인터페이스는 현재 variant:  
  
-   <xref:System.Collections.Generic.IEnumerable%601>(T는 공변 (covariant))</xref:System.Collections.Generic.IEnumerable%601>  
  
-   <xref:System.Collections.Generic.IEnumerator%601>(T는 공변 (covariant))</xref:System.Collections.Generic.IEnumerator%601>  
  
-   <xref:System.Linq.IQueryable%601>(T는 공변 (covariant))</xref:System.Linq.IQueryable%601>  
  
-   <xref:System.Linq.IGrouping%602>(`TKey` 및 `TElement` 는 공변 (covariant))</xref:System.Linq.IGrouping%602>  
  
-   <xref:System.Collections.Generic.IComparer%601>(T는 반공 변)</xref:System.Collections.Generic.IComparer%601>  
  
-   <xref:System.Collections.Generic.IEqualityComparer%601>(T는 반공 변)</xref:System.Collections.Generic.IEqualityComparer%601>  
  
-   <xref:System.IComparable%601>(T는 반공 변)</xref:System.IComparable%601>  
  
 공변성 (covariance) 인터페이스의 제네릭 형식 매개 변수에 의해 정의 된 것 보다 더 많이 파생 된 반환 형식을 갖는 메서드를 허용 합니다. 공변성 (covariance) 기능을 설명 하기 위해 이러한 제네릭 인터페이스를 고려: `IEnumerable(Of Object)` 및 `IEnumerable(Of String)`합니다. `IEnumerable(Of String)` 인터페이스를 상속 하지 않는 `IEnumerable(Of Object)` 인터페이스입니다. 그러나는 `String` 형식 상속지 않습니다는 `Object` 형식의 경우에 따라 서로 이러한 인터페이스의 개체를 할당 하는 것이 좋습니다. 이 다음 코드 예제에 표시 됩니다.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
 .NET Framework의 이전 버전에서는이 코드는 Visual basic에서 컴파일 오류가 발생 `Option Strict On`합니다. 이제 사용할 수 있지만 `strings` 대신 `objects`때문에 앞의 예제에 표시 된 것 처럼는 <xref:System.Collections.Generic.IEnumerable%601>인터페이스는 공변 (covariant).</xref:System.Collections.Generic.IEnumerable%601>  
  
 반 공변성 인터페이스의 제네릭 매개 변수로 지정 된 것 보다 더 적게 파생 된 인수 형식을 갖는 메서드를 허용 합니다. 를 설명 하기 위해 반 공변성을 만들었다고 가정는 `BaseComparer` 클래스의 인스턴스를 비교 하는 `BaseClass` 클래스입니다. `BaseComparer` 클래스는 `IEqualityComparer(Of BaseClass)` 인터페이스를 구현합니다. 때문에 <xref:System.Collections.Generic.IEqualityComparer%601>인터페이스는 이제 반공 변을 사용할 수 있습니다 `BaseComparer` 상속 하는 클래스의 인스턴스를 비교 하는 `BaseClass` 클래스</xref:System.Collections.Generic.IEqualityComparer%601> 이 다음 코드 예제에 표시 됩니다.  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
 더 많은 예제를 참조 하십시오. [(Visual Basic) 제네릭 컬렉션 용 인터페이스의 가변성 사용 하 여](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md)합니다.  
  
 제네릭 인터페이스의 가변성은 참조 형식 에서만 지원 됩니다. 값 형식 차이 지원 하지 않습니다. 예를 들어 `IEnumerable(Of Integer)` 로 암시적으로 변환할 수 없는 `IEnumerable(Of Object)`이므로 정수 값 형식으로 표시 됩니다.  
  
<CodeContentPlaceHolder>2</CodeContentPlaceHolder>  
 Variant 인터페이스를 구현 하는 클래스는 여전히 고정 하는 것이 중요 이기도 합니다. 예를 들어 있지만 <xref:System.Collections.Generic.List%601>공변 (covariant) 인터페이스를 구현 <xref:System.Collections.Generic.IEnumerable%601>, 암시적으로 변환할 수 없습니다 `List(Of Object)` 를 `List(Of String)`.</xref:System.Collections.Generic.IEnumerable%601> </xref:System.Collections.Generic.List%601> 다음 코드 예제에 나와 있습니다.  
  
```vb  
' The following statement generates a compiler error  
' because classes are invariant.  
' Dim list As List(Of Object) = New List(Of String)  
  
' You can use the interface object instead.  
Dim listObjects As IEnumerable(Of Object) = New List(Of String)  
```  
  
## <a name="see-also"></a>참고 항목  
 [(Visual Basic) 제네릭 컬렉션 용 인터페이스의 가변성 사용](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md)   
 [Variant 제네릭 인터페이스 만들기 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/creating-variant-generic-interfaces.md)   
 [제네릭 인터페이스](http://msdn.microsoft.com/library/88bf5b04-d371-4edb-ba38-01ec7cabaacf)   
 [(Visual Basic) 대리자의 가변성](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)
