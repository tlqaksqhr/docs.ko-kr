---
title: "조인 작업 (Visual Basic) | Microsoft 문서"
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
ms.assetid: 39ab4854-ac84-4738-9d0b-3cb79be84db4
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
ms.openlocfilehash: dce1adb5b918674bc8ee8fc48c8ff5b3c3814a88
ms.lasthandoff: 03/13/2017

---
# <a name="join-operations-visual-basic"></a>조인 작업 (Visual Basic)
A *조인* 두 데이터 소스의 개체를 다른 데이터 소스에서 공통 특성을 공유 하는 개체와 하나 이상의 데이터 원본에 연결 하는 것입니다.  
  
 서로 간의 관계를 직접 적용할 수 없는 데이터 소스를 대상으로 하는 쿼리에서는 조인이 중요한 작업입니다. 개체 지향 프로그래밍에서 데이터 소스 간의 관계를 직접 적용할 수 없다는 것은 모델링되지 않은 개체 간에 상관 관계가 있음을 의미할 수 있습니다(예: 단방향 관계에서 반대 방향을 사용). 단방향 관계의 예로는 Customer 클래스가 City 형식 속성을 포함하는데 City 클래스는 Customer 개체의 컬렉션인 속성을 포함하지 않는 경우가 있습니다. City 개체 목록이 있는 경우 각 구/군/시의 모든 고객을 찾으려면 조인 작업을 사용하면 됩니다.  
  
 <xref:System.Linq.Enumerable.Join%2A>및 <xref:System.Linq.Enumerable.GroupJoin%2A>.</xref:System.Linq.Enumerable.GroupJoin%2A> </xref:System.Linq.Enumerable.Join%2A> LINQ 프레임 워크에서 제공 하는 조인 메서드는 이러한 메서드는 해당 키가 같은지 여부에 따라 두 데이터 소스는 조인 또는 동등 조인을 수행 합니다. 비교를 위해 Transact-SQL에서는 '같음'이 아닌 '보다 작음' 연산자와 같은 조인 연산자를 지원합니다. 관계형 데이터베이스 용어에서 <xref:System.Linq.Enumerable.Join%2A>는 유형의 조인 내부 조인을 구현에서 다른 데이터 집합에는 일치 항목이 있는 개체만 반환 됩니다.</xref:System.Linq.Enumerable.Join%2A> <xref:System.Linq.Enumerable.GroupJoin%2A>메서드에, 관계형 데이터베이스에서에서 직접 해당 하는 않지만 내부 조인 및 왼쪽된 우선 외부 조인의 상위 집합을 구현 합니다.</xref:System.Linq.Enumerable.GroupJoin%2A> 왼쪽된 우선 외부 조인을 다른 데이터 소스에 관계가 있는 요소가 없더라도 첫 번째 (왼쪽된) 데이터 소스의 각 요소를 반환 하는 조인이입니다.  
  
 다음 그림에서는 내부 조인 또는 왼쪽 우선 외부 조인에 포함된 두 집합 및 해당 집합 내의 요소를 개념적으로 보여줍니다.  
  
 ![내부/외부를 보여 주는 두 개의 겹치는 원입니다. ] (../../../../csharp/programming-guide/concepts/linq/media/joincircles.png "JoinCircles")  
  
## <a name="methods"></a>메서드  
  
|메서드 이름|설명|Visual Basic 쿼리 식 구문|추가 정보|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|Join|키 선택기 함수를 기준으로 두 시퀀스를 조인한 다음 값 쌍을 추출합니다.|`From x In …, y In … Where x.a = y.a`<br /><br /> 또는<br /><br /> `Join … [As …]In … On …`|<xref:System.Linq.Enumerable.Join%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Join%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Join%2A?displayProperty=fullName></xref:System.Linq.Queryable.Join%2A?displayProperty=fullName>|  
|GroupJoin|키 선택기 함수를 기준으로 두 시퀀스를 조인한 다음 결과로 생성된 일치 항목을 요소마다 그룹화합니다.|`Group Join … In … On …`|<xref:System.Linq.Enumerable.GroupJoin%2A?displayProperty=fullName></xref:System.Linq.Enumerable.GroupJoin%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.GroupJoin%2A?displayProperty=fullName></xref:System.Linq.Queryable.GroupJoin%2A?displayProperty=fullName>|  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Linq></xref:System.Linq>   
 [표준 쿼리 연산자 개요 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)   
 [익명 형식](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)   
 [방법: 조인 및 교차곱 쿼리 작성](http://msdn.microsoft.com/library/d8072ede-0521-4670-9bec-1778ceeb875b)   
 [Join 절](../../../../visual-basic/language-reference/queries/join-clause.md)   
 [방법: 서로 다른 파일 (Visual Basic) (LINQ)의 콘텐츠 조인](../../../../visual-basic/programming-guide/concepts/linq/how-to-join-content-from-dissimilar-files-linq.md)   
 [방법: 개체 컬렉션 (Visual Basic) (LINQ) 여러 소스에서 채우기](../../../../visual-basic/programming-guide/concepts/linq/how-to-populate-object-collections-from-multiple-sources-linq.md)
