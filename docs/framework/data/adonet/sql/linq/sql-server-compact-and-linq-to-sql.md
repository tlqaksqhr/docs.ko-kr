---
title: SQL Server Compact 및 LINQ to SQL
ms.date: 03/30/2017
ms.assetid: 59022359-a5a2-4c42-9a6a-5c0259c3ad17
ms.openlocfilehash: 74b8a7a6dfc9a4050dbba9a8c2f6969dba42656c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33355788"
---
# <a name="sql-server-compact-and-linq-to-sql"></a>SQL Server Compact 및 LINQ to SQL
SQL Server Compact는 Visual Studio와 함께 설치 된 기본 데이터베이스입니다. 자세한 내용은 참조 [PAVE 조치를 사용 하 여 SQL Server Compact (Visual Studio)](http://msdn.microsoft.com/library/13320dd1-94e5-4077-bf76-8df253695ccc)합니다.  
  
 이 항목에서는 사용법, 구성, 기능 집합 및 범위의 주요 차이점에 설명 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 지원 합니다.  
  
## <a name="characteristics-of-sql-server-compact-in-relation-to-linq-to-sql"></a>LINQ to SQL과 관련된 SQL Server Compact의 특성  
 기본적으로 SQL Server Compact 모든 Visual Studio 버전에 대 한 설치 이므로 함께 사용할 개발 컴퓨터에서 사용할 수 있는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]합니다. 하지만 SQL Server Compact를 사용 하 여 응용 프로그램의 배포 및 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] SQL Server 응용 프로그램에 대 한는 다릅니다. SQL Server Compact는 .NET Framework의 일부가 아니므로 응용 프로그램과 함께 패키지하거나 Microsoft 사이트에서 별도로 다운로드해야 합니다.  
  
 다음 특성에 주의합니다.  
  
-   SQL Server Compact는 데이터베이스 파일(.sdf 확장명)에 대해 직접 사용할 수 있는 DLL로 패키지됩니다.  
  
-   SQL Server Compact는 클라이언트 응용 프로그램과 동일한 프로세스에서 실행 됩니다. 따라서 SQL Server Compact와 통신 효율성 SQL Server와의 통신 보다 훨씬 더 높은 수 있습니다. 반면에 SQL Server Compact에서는 요구 해당 비용을 사용 하 여 관리 및 비관리 코드 간에 상호 운용이 가능 합니다.  
  
-   SQL Server Compact DLL의 크기가 작습니다. 이로 인해 전체 응용 프로그램 크기가 줄어듭니다.  
  
-   [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 런타임 및 SQLMetal 명령줄 도구에서 SQL Server Compact를 지원합니다.  
  
-   [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]에서는 SQL Server Compact를 지원하지 않습니다.  
  
## <a name="feature-set"></a>기능 집합  
 영향을 줄 수 있는 다음과 같은 방법으로 SQL Server Compact 기능 집합은 SQL server 기능 집합 보다 훨씬 더 간단 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 응용 프로그램:  
  
-   SQL Server Compact에서는 저장 프로시저나 뷰를 지원하지 않습니다.  
  
-   SQL Server Compact에서는 데이터 형식 및 SQL 함수의 하위 집합만 지원합니다.  
  
-   SQL Server Compact에서는 SQL 구문의 하위 집합만 지원합니다.  
  
-   SQL Server Compact에서는 최소한의 최적화 프로그램을 제공하므로 일부 쿼리의 시간이 초과될 수 있습니다.  
  
-   SQL Server Compact는 부분 신뢰를 지원하지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [참조](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)
