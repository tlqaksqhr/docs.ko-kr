---
title: "(LINQ to XML) 연결 된 쿼리의 성능 (Visual Basic) | Microsoft 문서"
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
ms.assetid: 589f2adc-69f9-404d-b9d6-4c28dabea7f7
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: dd5b63f255107c5864108cfbb87bef6e53a971a0
ms.contentlocale: ko-kr
ms.lasthandoff: 03/13/2017


---
# <a name="performance-of-chained-queries-linq-to-xml-visual-basic"></a>(LINQ to XML) 연결 된 쿼리의 성능 (Visual Basic)
LINQ(및 LINQ to XML)의 가장 큰 이점 중 하나는 연결된 쿼리가 보다 크고 복잡한 하나의 쿼리처럼 잘 수행될 수 있다는 것입니다.  
  
 연결된 쿼리는 다른 쿼리를 소스로 사용하는 쿼리입니다. 예를 들어 다음과 같은 간단한 코드에서 `query2`는 `query1`을 소스로 사용합니다.  
  
```vb  
Dim root As New XElement("Root", New XElement("Child", 1), New XElement("Child", 2), New XElement("Child", 3), New XElement("Child", 4))  
  
Dim query1 = From x In root.Elements("Child") Where CInt(x) >= 3x  
  
Dim query2 = From e In query1 Where CInt(e) Mod 2 = 0e  
  
For Each i As var In query2  
    Console.WriteLine("{0}", CInt(i))  
Next  
```  
  
 이 예제는 다음과 같은 출력을 생성합니다.  
  
```  
4  
```  
  
 이 연결된 쿼리는 연결된 목록을 반복하는 것과 같은 성능을 제공합니다.  
  
-   <xref:System.Xml.Linq.XContainer.Elements%2A>축은 기본적으로 연결 된 목록을 반복으로 동일한 성능을.</xref:System.Xml.Linq.XContainer.Elements%2A> <xref:System.Xml.Linq.XContainer.Elements%2A>지연 된 실행을 사용 하는 반복기로 구현 됩니다.</xref:System.Xml.Linq.XContainer.Elements%2A> 이는 연결된 목록을 반복하는 작업뿐만 아니라 반복기 개체 할당, 실행 상태 추적 등의 다른 작업도 수행함을 의미합니다. 이러한 작업은 두 가지 범주로 나눌 수 있습니다. 하나는 반복기가 설정될 때 수행되는 작업이며, 다른 하나는 각 반복에서 수행되는 작업입니다. 설정 작업은 그 양이 작고 정해져 있지만 각 반복에서 수행되는 작업의 양은 소스 컬렉션에 포함된 항목 수에 비례합니다.  
  
-   `query1`, `Where` 절로 인해 쿼리를 호출 하 여 <xref:System.Linq.Enumerable.Where%2A>메서드.</xref:System.Linq.Enumerable.Where%2A> 이 메서드는 또한 반복기로 구현됩니다. 설정 작업은 람다 식을 참조하는 대리자에 대한 인스턴스화 작업과 반복기에 대한 일반 설정 작업으로 구성됩니다. 각 반복에서 대리자는 조건자를 실행하기 위해 호출됩니다. 설정 작업과 각 반복에서 수행되는 작업은 축 반복에서 수행되는 작업과 비슷합니다.  
  
-   `query1`, select 절로 인해 쿼리를 호출 하 여 <xref:System.Linq.Enumerable.Select%2A>메서드.</xref:System.Linq.Enumerable.Select%2A> 이 메서드는 것과 같은 성능을 <xref:System.Linq.Enumerable.Where%2A>메서드.</xref:System.Linq.Enumerable.Where%2A>  
  
-   `query2`의 `Where` 절과 `Select` 절은 모두 `query1`의 해당 절과 같은 성능을 제공합니다.  
  
 따라서 `query2`의 반복은 소스로 사용된 첫 번째 쿼리의 항목 수에 정비례합니다. 즉, 선형 시간으로 실행됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [성능 (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/performance-linq-to-xml.md)

