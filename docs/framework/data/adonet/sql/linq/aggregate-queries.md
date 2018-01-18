---
title: "집계 쿼리"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 13ec5580-05ce-4a1f-9d3d-8660be7891a2
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: d4aa6c0a9103bc4a906ecdfb51a55069e6b8b790
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="aggregate-queries"></a>집계 쿼리
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서는 `Average`, `Count`, `Max`, `Min` 및 `Sum` 집계 연산자가 지원됩니다. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 집계 연산자의 다음과 같은 특징에 유의하세요.  
  
-   집계 쿼리는 즉시 실행됩니다.  
  
     자세한 내용은 [LINQ 쿼리 소개(C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)를 참조하세요.  
  
-   집계 쿼리는 일반적으로 컬렉션 대신 숫자를 반환합니다.  
  
     자세한 내용은 참조 [집계 작업](http://msdn.microsoft.com/library/36d97c83-5de5-457d-971d-10a69365e7c4)합니다.  
  
-   익명 형식에 대해서 집계를 호출할 수 없습니다.  
  
 다음 항목의 예제에서는 Northwind 샘플 데이터베이스를 사용합니다. 자세한 내용은 참조 [샘플 데이터베이스 다운로드](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [숫자 시퀀스에서 평균 값 반환](../../../../../../docs/framework/data/adonet/sql/linq/return-the-average-value-from-a-numeric-sequence.md)  
 <xref:System.Linq.Enumerable.Average%2A> 연산자를 사용하는 방법을 보여 줍니다.  
  
 [시퀀스의 요소 수 계산](../../../../../../docs/framework/data/adonet/sql/linq/count-the-number-of-elements-in-a-sequence.md)  
 <xref:System.Linq.Enumerable.Count%2A> 연산자를 사용하는 방법을 보여 줍니다.  
  
 [숫자 시퀀스에서 최대값 찾기](../../../../../../docs/framework/data/adonet/sql/linq/find-the-maximum-value-in-a-numeric-sequence.md)  
 <xref:System.Linq.Enumerable.Max%2A> 연산자를 사용하는 방법을 보여 줍니다.  
  
 [숫자 시퀀스에서 최소값 찾기](../../../../../../docs/framework/data/adonet/sql/linq/find-the-minimum-value-in-a-numeric-sequence.md)  
 <xref:System.Linq.Enumerable.Min%2A> 연산자를 사용하는 방법을 보여 줍니다.  
  
 [숫자 시퀀스에서 값의 합계 계산](../../../../../../docs/framework/data/adonet/sql/linq/compute-the-sum-of-values-in-a-numeric-sequence.md)  
 <xref:System.Linq.Enumerable.Sum%2A> 연산자를 사용하는 방법을 보여 줍니다.  
  
## <a name="related-sections"></a>관련 단원  
 [쿼리 예제](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)  
 Visual Basic 및 C#의 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 쿼리에 대한 링크를 제공합니다.  
  
 [쿼리 개념](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)  
 [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)]의 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 쿼리 설계 개념을 설명하는 항목에 대한 링크를 제공합니다.  
  
 [LINQ 쿼리 소개(C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)  
 [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)]의 쿼리 작동 방식을 설명합니다.
