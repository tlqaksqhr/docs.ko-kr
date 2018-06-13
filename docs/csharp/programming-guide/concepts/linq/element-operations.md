---
title: 요소 작업(C#)
ms.date: 07/20/2015
ms.assetid: 283206c9-3246-4c48-b01a-d9de409a7231
ms.openlocfilehash: 5c10603d9e074faf891d41fa6b39614fcc167c8a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33317449"
---
# <a name="element-operations-c"></a>요소 작업(C#)
요소 작업은 시퀀스에서 특정 단일 요소를 반환합니다.  
  
 다음 섹션에는 요소 작업을 수행하는 표준 쿼리 연산자 메서드가 나열되어 있습니다.  
  
## <a name="methods"></a>메서드  
  
|메서드 이름|설명|C# 쿼리 식 구문|추가 정보|  
|-----------------|-----------------|---------------------------------|----------------------|  
|ElementAt|컬렉션의 지정된 인덱스에 있는 요소를 반환합니다.|해당 사항 없음.|<xref:System.Linq.Enumerable.ElementAt%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.ElementAt%2A?displayProperty=nameWithType>|  
|ElementAtOrDefault|컬렉션의 지정된 인덱스에 있는 요소를 반환하거나 인덱스가 범위를 벗어나면 기본값을 반환합니다.|해당 사항 없음.|<xref:System.Linq.Enumerable.ElementAtOrDefault%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.ElementAtOrDefault%2A?displayProperty=nameWithType>|  
|First|컬렉션의 첫 번째 요소 또는 특정 조건에 맞는 첫 번째 요소를 반환합니다.|해당 사항 없음.|<xref:System.Linq.Enumerable.First%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.First%2A?displayProperty=nameWithType>|  
|FirstOrDefault|컬렉션의 첫 번째 요소 또는 특정 조건에 맞는 첫 번째 요소를 반환합니다. 이러한 요소가 없으면 기본값을 반환합니다.|해당 사항 없음.|<xref:System.Linq.Enumerable.FirstOrDefault%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.FirstOrDefault%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.FirstOrDefault%60%601%28System.Linq.IQueryable%7B%60%600%7D%29?displayProperty=nameWithType>|  
|마지막|컬렉션의 마지막 요소 또는 특정 조건에 맞는 마지막 요소를 반환합니다.|해당 사항 없음.|<xref:System.Linq.Enumerable.Last%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Last%2A?displayProperty=nameWithType>|  
|LastOrDefault|컬렉션의 마지막 요소 또는 특정 조건에 맞는 마지막 요소를 반환합니다. 이러한 요소가 없으면 기본값을 반환합니다.|해당 사항 없음.|<xref:System.Linq.Enumerable.LastOrDefault%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.LastOrDefault%2A?displayProperty=nameWithType>|  
|Single|컬렉션의 유일한 요소 또는 특정 조건에 맞는 유일한 요소를 반환합니다.|해당 사항 없음.|<xref:System.Linq.Enumerable.Single%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Single%2A?displayProperty=nameWithType>|  
|SingleOrDefault|컬렉션의 유일한 요소 또는 특정 조건에 맞는 유일한 요소를 반환합니다. 이러한 요소가 없거나 컬렉션에 정확히 하나의 요소가 포함되지 않은 경우 기본값을 반환합니다.|해당 사항 없음.|<xref:System.Linq.Enumerable.SingleOrDefault%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.SingleOrDefault%2A?displayProperty=nameWithType>|  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Linq>  
 [표준 쿼리 연산자 개요(C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [방법: 디렉터리 트리에서 가장 큰 파일을 하나 이상 쿼리(LINQ)(C#)](../../../../csharp/programming-guide/concepts/linq/how-to-query-for-the-largest-file-or-files-in-a-directory-tree-linq.md)
