---
title: "LINQ to Entities의 알려진 문제 및 고려 사항 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
ms.assetid: acd71129-5ff0-4b4e-b266-c72cc0c53601
caps.latest.revision: 5
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# LINQ to Entities의 알려진 문제 및 고려 사항
이 단원에서는 [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] 쿼리와 관련하여 알려진 문제에 대한 정보를 제공합니다.  
  
-   [캐시할 수 없는 LINQ 쿼리](#LINQQueriesThatAreNotCached)  
  
-   [순서 정보 손실](#OrderingInfoLost)  
  
-   [부호 없는 정수 지원되지 않음](#UnsignedIntsUnsupported)  
  
-   [형식 변환 오류](#TypeConversionErrors)  
  
-   [스칼라가 아닌 변수 참조는 지원되지 않음](#RefNonScalarClosures)  
  
-   [SQL Server 2000에서 중첩 쿼리가 실패할 수 있음](#NestedQueriesSQL2000)  
  
-   [익명 형식으로 프로젝션](#ProjectToAnonymousType)  
  
<a name="LINQQueriesThatAreNotCached"></a>   
## 캐시할 수 없는 LINQ 쿼리  
 .NET Framework 4.5부터 시작하여 LINQ to Entities 쿼리가 자동으로 캐시됩니다.  그러나 메모리 내 컬렉션에 `Enumerable.Contains` 연산자를 적용하는 LINQ to Entities 쿼리는 자동으로 캐시되지 않습니다.  또한 메모리 내 컬렉션은 컴파일된 LINQ 쿼리에서 매개 변수화할 수 없습니다.  
  
<a name="OrderingInfoLost"></a>   
## 순서 정보 손실  
 열을 익명 형식으로 프로젝션하면 호환성 수준 "80"에서 [!INCLUDE[ssVersion2005](../../../../../../includes/ssversion2005-md.md)] 데이터베이스에 대해 실행되는 일부 쿼리에서 순서 정보가 손실됩니다.  이런 현상은 다음 예제와 같이 정렬 순서 목록에 있는 열 이름이 선택기의 열 이름과 일치할 때 발생합니다.  
  
 [!code-csharp[DP L2E Conceptual Examples#SBUDT543840](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#sbudt543840)]
 [!code-vb[DP L2E Conceptual Examples#SBUDT543840](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#sbudt543840)]  
  
<a name="UnsignedIntsUnsupported"></a>   
## 부호 없는 정수 지원되지 않음  
 [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)]가 부호 없는 정수를 지원하지 않으므로 [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] 쿼리에는 부호 없는 정수 형식을 지정할 수 없습니다. 부호 없는 정수를 지정할 경우 다음 예제에서와 같이 쿼리 식 변환 도중 <xref:System.ArgumentException> 예외가 throw됩니다.  다음 예제에서는 ID 48000인 주문을 쿼리합니다.  
  
 [!code-csharp[DP L2E Conceptual Examples#UIntAsQueryParam](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#uintasqueryparam)]
 [!code-vb[DP L2E Conceptual Examples#UIntAsQueryParam](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#uintasqueryparam)]  
  
<a name="TypeConversionErrors"></a>   
## 형식 변환 오류  
 Visual Basic에서 `CByte` 함수를 사용하여 값이 1인 SQL Server 비트 형식의 열에 속성이 매핑되면 "산술 오버플로 오류" 메시지와 함께 <xref:System.Data.SqlClient.SqlException>이 throw됩니다.  다음 예제는 AdventureWorks 샘플 데이터베이스의 `Product.MakeFlag` 열을 쿼리하며, 쿼리 결과가 반복되면 예외가 throw됩니다.  
  
 [!code-vb[DP L2E Conceptual Examples#SBUDT544355](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#sbudt544355)]  
  
<a name="RefNonScalarClosures"></a>   
## 스칼라가 아닌 변수 참조는 지원되지 않음  
 엔터티와 같이 스칼라가 아닌 변수를 쿼리에서 참조할 수 없습니다.  이러한 쿼리가 실행되면 <xref:System.NotSupportedException> 예외가 throw되고 "`EntityType` 형식의 상수 값을 만들 수 없습니다.  이 컨텍스트에서는 기본 형식\('Int32, String 및 Guid'\)만 지원됩니다."라는 메시지가 표시됩니다.  
  
> [!NOTE]
>  스칼라 변수 컬렉션 참조가 지원됨  
  
 [!code-csharp[DP L2E Conceptual Examples#SBUDT555877](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#sbudt555877)]
 [!code-vb[DP L2E Conceptual Examples#SBUDT555877](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#sbudt555877)]  
  
<a name="NestedQueriesSQL2000"></a>   
## SQL Server 2000에서 중첩 쿼리가 실패할 수 있음  
 SQL Server 2000을 사용할 경우 세 수준 이상으로 중첩된 Transact\-SQL 쿼리를 생성하는 LINQ to Entities 쿼리가 실패할 수 있습니다.  
  
<a name="ProjectToAnonymousType"></a>   
## 익명 형식으로 프로젝션  
 <xref:System.Data.Objects.ObjectQuery%601>에서 <xref:System.Data.Objects.ObjectQuery%601.Include%2A> 메서드를 사용하여 관련 개체를 포함하도록 초기 쿼리 경로를 정의한 다음 LINQ를 사용하여 반환된 개체를 익명 형식으로 프로젝션하면 Include 메서드에 지정된 개체가 쿼리 결과에 포함되지 않습니다.  
  
 [!code-csharp[DP L2E Conceptual Examples#ProjToAnonType1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#projtoanontype1)]
 [!code-vb[DP L2E Conceptual Examples#ProjToAnonType1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#projtoanontype1)]  
  
 관련 개체를 가져오려면 반환된 형식을 익명 형식으로 프로젝션하지 말아야 합니다.  
  
 [!code-csharp[DP L2E Conceptual Examples#ProjToAnonType2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#projtoanontype2)]
 [!code-vb[DP L2E Conceptual Examples#ProjToAnonType2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#projtoanontype2)]  
  
## 참고 항목  
 [LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/linq-to-entities.md)