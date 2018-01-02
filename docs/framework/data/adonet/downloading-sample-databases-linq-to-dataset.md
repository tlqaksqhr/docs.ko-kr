---
title: "샘플 데이터베이스 다운로드(LINQ to DataSet)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eb42a7af-d410-4b7f-b4a8-13c72ce6fd09
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: b984fdef7f7f43e266ec4ba42b04990aced159c6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="downloading-sample-databases-linq-to-dataset"></a>샘플 데이터베이스 다운로드(LINQ to DataSet)
샘플 및 연습에는 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 설명서 AdventureWorks 예제 데이터베이스를 사용 합니다. 이 제품은 Microsoft 다운로드 사이트에서 무료로 다운로드할 수 있습니다. [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 설명서의 샘플과 연습에서는 SQL Server를 데이터 저장소로 사용합니다. SQL Server 대신 무료로 사용할 수 있는 SQL Server Express Edition을 데이터 저장소로 사용할 수도 있습니다.  
  
## <a name="downloading-and-installing-the-adventureworks-database"></a>AdventureWorks 데이터베이스 다운로드 및 설치  
  
#### <a name="to-download-and-install-the-adventureworks-sample-database-for-sql-server"></a>SQL Server용 AdventureWorks 샘플 데이터베이스를 다운로드하고 설치하려면  
  
1.  Internet Explorer를 엽니다.  
  
2.  이동 하 여 [SQL Server 2005 예제 및 예제 데이터베이스](http://go.microsoft.com/fwlink/?linkid=31046) 웹 사이트입니다.  
  
3.  지침에 따라 프로세서 유형에 해당하는 AdventureWorks 샘플 데이터베이스(예: AdventureWorksDB.msi)를 다운로드하고 .MSI 파일을 로컬 컴퓨터에 저장합니다.  
  
4.  다운로드한 파일이나 SQL Server 설치 프로그램을 실행하는 동안 이전 버전의 AdventureWorks가 설치되어 있으면 AdventureWorks.msi를 실행하기 전에 이전 버전을 제거해야 합니다.  
  
#### <a name="to-remove-a-previous-download-of-an-adventureworks-sample-database"></a>AdventureWorks 샘플 데이터베이스의 이전 다운로드를 제거하려면  
  
1.  AdventureWorks 또는 AdventureWorksDW 데이터베이스를 삭제합니다.  
  
2.  **프로그램 추가 / 제거**선택, **AdventureWorksDB** 또는 **AdventureWorksBI** 클릭 **제거**합니다.  
  
#### <a name="to-remove-an-adventureworks-sample-database-previously-installed-using-setup"></a>설치 프로그램을 사용하여 이전에 설치된 AdventureWorks 샘플 데이터베이스를 제거하려면  
  
1.  AdventureWorks 또는 AdventureWorksDW 데이터베이스를 삭제합니다.  
  
2.  **프로그램 추가 / 제거**선택, **Microsoft SQL Server 2005** 클릭 **변경**합니다.  
  
3.  **구성 요소 선택**선택, **워크스테이션 구성 요소** 클릭 하 고 **다음**합니다.  
  
4.  **SQL Server 설치 마법사 시작**, 클릭 **다음**합니다.  
  
5.  **시스템 구성 검사**, 클릭 **다음**합니다.  
  
6.  **인스턴스 변경 또는 제거**, 클릭 **설치 구성 요소 변경**합니다.  
  
7.  **기능 선택**를 확장 하 고는 **문서, 예제 및 예제 데이터베이스** 노드.  
  
8.  선택 **예제 코드 및 응용 프로그램**합니다. 확장 **예제 데이터베이스**, 샘플 데이터베이스를 제거할 수 있으며, 선택 선택 **모든 기능을 사용할 수 없게 됩니다**합니다. **다음**을 클릭합니다.  
  
9. 클릭 **설치** 설치 마법사를 마칩니다.  
  
#### <a name="to-attach-the-adventureworks-sample-database-files-to-an-instance-of-sql-server"></a>AdventureWorks 샘플 데이터베이스 파일을 SQL Server 인스턴스에 연결하려면  
  
1.  파일 예제 데이터베이스 설치 관리자 파일을 다운로드 한 후 두 번 클릭은 **AdventureWorksDB.msi** 파일 (또는 다운로드 한 파일)는 데이터베이스를 설치 합니다. 기본적으로 데이터베이스는 c:\Program Files\Microsoft SQL Server\MSSQL.1\MSSQL\Data에 설치됩니다.  
  
2.  다음 스크립트 SQLCMD 또는 SQL Server Management Studio를 실행하여 AdventureWorks 데이터베이스 파일을 SQL Server 인스턴스에 연결합니다.  
  
    ```  
    exec sp_attach_db @dbname=N'AdventureWorks', @filename1=N'C:\Program Files\Microsoft SQL Server\MSSQL.1\MSSQL\Data\AdventureWorks_Data.mdf', @filename2=N'C:\Program Files\Microsoft SQL Server\MSSQL.1\MSSQL\Data\AdventureWorks_log.ldf'  
    ```  
  
     이러한 파일을 다른 드라이브나 디렉터리에 설치한 경우에는 `sp_attach_db` 저장 프로시저를 실행하기 전에 경로를 올바르게 수정해야 합니다.  
  
## <a name="downloading-sql-server-express-edition"></a>SQL Server Express Edition 다운로드  
 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 단원의 샘플과 연습에서는 SQL Server 2005를 데이터 저장소로 사용하지만 SQL Server Express Edition을 대신 사용하도록 수정할 수 있습니다. SQL Server Express Edition은 무료로 제공되며 응용 프로그램과 함께 재배포할 수 있습니다. [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]를 사용하고 있는 경우에는 SQL Server Express Edition이 Pro 이상의 에디션에 포함되어 있습니다.  
  
#### <a name="to-download-and-install-sql-server-express-edition"></a>SQL Server Express Edition을 다운로드하여 설치하려면  
  
1.  Internet Explorer를 시작합니다.  
  
2.  이동 하는 [Microsoft SQL Server 2005 Express Edition](http://go.microsoft.com/fwlink/?LinkID=31070) 페이지를 다운로드 합니다.  
  
3.  웹 사이트의 설치 지침을 따릅니다.  
  
## <a name="see-also"></a>참고 항목  
 [시작](../../../../docs/framework/data/adonet/getting-started-linq-to-dataset.md)
