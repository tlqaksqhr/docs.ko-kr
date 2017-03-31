---
title: "요소 작업(C#) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 283206c9-3246-4c48-b01a-d9de409a7231
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 0cada4f5dae6eab5511870395133c2ef67ca796e
ms.lasthandoff: 03/13/2017

---
# <a name="element-operations-c"></a>요소 작업(C#)
요소 작업은 시퀀스에서 특정 단일 요소를 반환합니다.  
  
 다음 섹션에는 요소 작업을 수행하는 표준 쿼리 연산자 메서드가 나열되어 있습니다.  
  
## <a name="methods"></a>메서드  
  
|메서드 이름|설명|C# 쿼리 식 구문|추가 정보|  
|-----------------|-----------------|---------------------------------|----------------------|  
|ElementAt|컬렉션의 지정된 인덱스에 있는 요소를 반환합니다.|해당 사항 없음.|<xref:System.Linq.Enumerable.ElementAt%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.ElementAt%2A?displayProperty=fullName>|  
|ElementAtOrDefault|컬렉션의 지정된 인덱스에 있는 요소를 반환하거나 인덱스가 범위를 벗어나면 기본값을 반환합니다.|해당 사항 없음.|<xref:System.Linq.Enumerable.ElementAtOrDefault%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.ElementAtOrDefault%2A?displayProperty=fullName>|  
|First|컬렉션의 첫 번째 요소 또는 특정 조건에 맞는 첫 번째 요소를 반환합니다.|해당 사항 없음.|<xref:System.Linq.Enumerable.First%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.First%2A?displayProperty=fullName>|  
|FirstOrDefault|컬렉션의 첫 번째 요소 또는 특정 조건에 맞는 첫 번째 요소를 반환합니다. 이러한 요소가 없으면 기본값을 반환합니다.|해당 사항 없음.|<xref:System.Linq.Enumerable.FirstOrDefault%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.FirstOrDefault%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.FirstOrDefault%60%601%28System.Linq.IQueryable%7B%60%600%7D%29?displayProperty=fullName>|  
|마지막|컬렉션의 마지막 요소 또는 특정 조건에 맞는 마지막 요소를 반환합니다.|해당 사항 없음.|<xref:System.Linq.Enumerable.Last%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Last%2A?displayProperty=fullName>|  
|LastOrDefault|컬렉션의 마지막 요소 또는 특정 조건에 맞는 마지막 요소를 반환합니다. 이러한 요소가 없으면 기본값을 반환합니다.|해당 사항 없음.|<xref:System.Linq.Enumerable.LastOrDefault%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.LastOrDefault%2A?displayProperty=fullName>|  
|Single|컬렉션의 유일한 요소 또는 특정 조건에 맞는 유일한 요소를 반환합니다.|해당 사항 없음.|<xref:System.Linq.Enumerable.Single%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Single%2A?displayProperty=fullName>|  
|SingleOrDefault|컬렉션의 유일한 요소 또는 특정 조건에 맞는 유일한 요소를 반환합니다. 이러한 요소가 없거나 컬렉션에 정확히 하나의 요소가 포함되지 않은 경우 기본값을 반환합니다.|해당 사항 없음.|<xref:System.Linq.Enumerable.SingleOrDefault%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.SingleOrDefault%2A?displayProperty=fullName>|  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Linq>   
 [표준 쿼리 연산자 개요(C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)   
 [방법: 디렉터리 트리에서 가장 큰 파일을 하나 이상 쿼리(LINQ)(C#)](../../../../csharp/programming-guide/concepts/linq/how-to-query-for-the-largest-file-or-files-in-a-directory-tree-linq.md)
