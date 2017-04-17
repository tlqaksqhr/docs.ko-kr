---
title: "SQL Server Compact 및 LINQ to SQL | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 59022359-a5a2-4c42-9a6a-5c0259c3ad17
caps.latest.revision: 5
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 5
---
# SQL Server Compact 및 LINQ to SQL
SQL Server Compact는 Visual Studio와 함께 설치된 기본 데이터베이스입니다. 자세한 내용은 [PAVE OVER Using SQL Server Compact \(Visual Studio\)](http://msdn.microsoft.com/ko-kr/13320dd1-94e5-4077-bf76-8df253695ccc)을 참조하세요.  
  
 이 항목에서는 사용법, 구성, 기능 집합 및 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 지원 범위의 주요 차이점에 대해 간략하게 설명합니다.  
  
## LINQ to SQL과 관련된 SQL Server Compact의 특성  
 기본적으로 SQL Server Compact는 모든 [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] 버전에서 설치되므로 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에 사용할 개발 컴퓨터에서 사용할 수 있습니다.  그러나 SQL Server Compact 및 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]을 사용하는 응용 프로그램의 배포는 [!INCLUDE[ssNoVersion](../../../../../../includes/ssnoversion-md.md)] 응용 프로그램의 경우와 다릅니다.  SQL Server Compact는 .NET Framework의 일부가 아니므로 응용 프로그램과 함께 패키지하거나 Microsoft 사이트에서 별도로 다운로드해야 합니다.  
  
 다음 특성에 주의합니다.  
  
-   SQL Server Compact는 데이터베이스 파일\(.sdf 확장명\)에 대해 직접 사용할 수 있는 DLL로 패키지됩니다.  
  
-   SQL Server Compact는 클라이언트 응용 프로그램과 동일한 프로세스에서 실행됩니다.  따라서 SQL Server Compact와의 통신 효율성은 [!INCLUDE[ssNoVersion](../../../../../../includes/ssnoversion-md.md)]와의 통신보다 훨씬 더 높을 수 있습니다.  반면, SQL Server Compact에서는 관리 코드와 비관리 코드 간에 상호 운용성이 요구되므로 부수적인 비용이 발생합니다.  
  
-   SQL Server Compact DLL의 크기가 너무 작습니다.  이로 인해 전체 응용 프로그램 크기가 줄어듭니다.  
  
-   [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 런타임 및 SQLMetal 명령줄 도구에서 SQL Server Compact를 지원합니다.  
  
-   [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]에서는 SQL Server Compact를 지원하지 않습니다.  
  
## 기능 집합  
 SQL Server Compact 기능 집합은 [!INCLUDE[ssNoVersion](../../../../../../includes/ssnoversion-md.md)] 기능 집합보다 훨씬 더 간단하며 다음과 같은 방법으로 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 응용 프로그램에 영향을 줄 수 있습니다.  
  
-   SQL Server Compact에서는 저장 프로시저나 뷰를 지원하지 않습니다.  
  
-   SQL Server Compact에서는 데이터 형식 및 SQL 함수의 하위 집합만 지원합니다.  
  
-   SQL Server Compact에서는 SQL 구문의 하위 집합만 지원합니다.  
  
-   SQL Server Compact에서는 최소한의 최적화 프로그램을 제공하므로  일부 쿼리의 시간이 초과될 수 있습니다.  
  
-   SQL Server Compact는 부분 신뢰를 지원하지 않습니다.  
  
## 참고 항목  
 [참조](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)