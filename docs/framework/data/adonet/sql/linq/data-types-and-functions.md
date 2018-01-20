---
title: "데이터 형식 및 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 683413c5-0312-4e60-8619-9a97bdc6e62a
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: f9f97f0ae0a75dd15edcb2256d991e987388f1ae
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="data-types-and-functions"></a>데이터 형식 및 함수
다음 표에 나열된 항목에서는 CLR(공용 언어 런타임)의 멤버, 구문 및 캐스트에 대한 LINQ to SQL의 지원 정보를 설명합니다. 지원되는 멤버와 구문은 LINQ to SQL 쿼리에 사용할 수 있습니다.  
  
 표에 나와 있는 지원되지 않는 항목은 LINQ to SQL에서 해당 CLR 멤버, 구문 또는 캐스트를 SQL Server에서 실행하기 위해 변환할 수 없다는 것을 의미합니다. 이러한 항목은 코드에 사용할 수 있지만 쿼리를 Transact-SQL로 변환하기 전이나 데이터베이스에서 결과가 검색된 후에 반드시 평가해야 합니다.  
  
|항목|설명|  
|-----------|-----------------|  
|[SQL-CLR 형식 매핑](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md)|CLR 형식 및 SQL Server 형식 간의 매핑에 대한 자세한 매트릭스를 제공합니다.|  
|[기본 데이터 형식](../../../../../../docs/framework/data/adonet/sql/linq/basic-data-types.md)|[!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)]와의 동작 차이점을 요약합니다.|  
|[부울 데이터 형식](../../../../../../docs/framework/data/adonet/sql/linq/boolean-data-types.md)|[!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)]와의 동작 차이점을 요약합니다.|  
|[Null 의미 체계](../../../../../../docs/framework/data/adonet/sql/linq/null-semantics.md)|null 및 nullable 문제를 설명하는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 항목에 대한 링크를 제공합니다.|  
|[숫자 및 비교 연산자](../../../../../../docs/framework/data/adonet/sql/linq/numeric-and-comparison-operators.md)|[!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)]와의 동작 차이점을 요약합니다.|  
|[시퀀스 연산자](../../../../../../docs/framework/data/adonet/sql/linq/sequence-operators.md)|[!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)]와의 동작 차이점을 요약합니다.|  
|[System.Convert 메서드](../../../../../../docs/framework/data/adonet/sql/linq/system-convert-methods.md)|[!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)]와의 동작 차이점을 요약합니다.|  
|[System.DateTime 메서드](../../../../../../docs/framework/data/adonet/sql/linq/system-datetime-methods.md)|<xref:System.DateTime?displayProperty=nameWithType> 구조체의 멤버에 대한 LINQ to SQL의 지원 정보를 설명합니다.|  
|[System.DateTimeOffset 메서드](../../../../../../docs/framework/data/adonet/sql/linq/system-datetimeoffset-methods.md)|<xref:System.DateTimeOffset?displayProperty=nameWithType> 구조체의 멤버에 대한 LINQ to SQL의 지원 정보를 설명합니다.|  
|[System.Math 메서드](../../../../../../docs/framework/data/adonet/sql/linq/system-math-methods.md)|[!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)]와의 동작 차이점을 요약합니다.|  
|[System.Object 메서드](../../../../../../docs/framework/data/adonet/sql/linq/system-object-methods.md)|[!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)]와의 동작 차이점을 요약합니다.|  
|[System.String 메서드](../../../../../../docs/framework/data/adonet/sql/linq/system-string-methods.md)|[!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)]와의 동작 차이점을 요약합니다.|  
|[System.TimeSpan 메서드](../../../../../../docs/framework/data/adonet/sql/linq/system-timespan-methods.md)|<xref:System.TimeSpan?displayProperty=nameWithType> 구조체의 멤버에 대한 LINQ to SQL의 지원 정보를 설명합니다.|  
|[지원되지 않는 기능](../../../../../../docs/framework/data/adonet/sql/linq/unsupported-functionality.md)|[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 지원하지 않는 기능에 대해 설명합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [SQL-CLR 형식 불일치](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mismatches.md)  
 [참조](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)  
 [Visual Studio에서.NET framework 클래스 라이브러리](http://msdn.microsoft.com/library/a03e374c-3d5c-4169-937b-49857ab273ae)
