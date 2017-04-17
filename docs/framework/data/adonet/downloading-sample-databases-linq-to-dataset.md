---
title: "샘플 데이터베이스 다운로드(LINQ to DataSet) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: eb42a7af-d410-4b7f-b4a8-13c72ce6fd09
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# 샘플 데이터베이스 다운로드(LINQ to DataSet)
[!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 설명서의 샘플과 연습에서는 AdventureWorks 샘플 데이터베이스를 사용합니다.  이 제품은 Microsoft 다운로드 사이트에서 무료로 다운로드할 수 있습니다. [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 설명서의 샘플과 연습에서는 SQL Server를 데이터 저장소로 사용합니다.  SQL Server 대신 무료로 사용할 수 있는 SQL Server Express Edition을 데이터 저장소로 사용할 수도 있습니다.  
  
## AdventureWorks 데이터베이스 다운로드 및 설치  
  
#### SQL Server용 AdventureWorks 샘플 데이터베이스를 다운로드하고 설치하려면  
  
1.  Internet Explorer를 엽니다.  
  
2.  [SQL Server 2005 샘플 및 샘플 데이터베이스](http://go.microsoft.com/fwlink/?linkid=31046)\(영문\) 웹 사이트로 이동하세요.  
  
3.  지침에 따라 프로세서 유형에 해당하는 AdventureWorks 샘플 데이터베이스\(예: AdventureWorksDB.msi\)를 다운로드하고 .MSI 파일을 로컬 컴퓨터에 저장합니다.  
  
4.  다운로드한 파일이나 SQL Server 설치 프로그램을 실행하는 동안 이전 버전의 AdventureWorks가 설치되어 있으면 AdventureWorks.msi를 실행하기 전에 이전 버전을 제거해야 합니다.  
  
#### AdventureWorks 샘플 데이터베이스의 이전 다운로드를 제거하려면  
  
1.  AdventureWorks 또는 AdventureWorksDW 데이터베이스를 삭제합니다.  
  
2.  **프로그램 추가\/제거**에서 **AdventureWorksDB** 또는 **AdventureWorksBI**를 선택하고 **제거**를 클릭합니다.  
  
#### 설치 프로그램을 사용하여 이전에 설치된 AdventureWorks 샘플 데이터베이스를 제거하려면  
  
1.  AdventureWorks 또는 AdventureWorksDW 데이터베이스를 삭제합니다.  
  
2.  **프로그램 추가\/제거**에서 **Microsoft SQL Server 2005**를 선택하고 **변경**을 클릭합니다.  
  
3.  **구성 요소 선택**에서 **워크스테이션 구성 요소**를 선택하고 **다음**을 클릭합니다.  
  
4.  **SQL Server 설치 마법사 시작**에서 **다음**을 클릭합니다.  
  
5.  **시스템 구성 검사**에서 **다음**을 클릭합니다.  
  
6.  **인스턴스 변경 또는 제거**에서 **설치된 구성 요소 변경**을 클릭합니다.  
  
7.  **기능 선택**에서 **설명서, 샘플 및 샘플 데이터베이스** 노드를 확장합니다.  
  
8.  **샘플 코드 및 응용 프로그램**을 선택합니다.  **샘플 데이터베이스**를 확장한 다음 제거할 샘플 데이터베이스를 선택하고 **모든 기능을 사용할 수 없습니다.**를 선택합니다.  **다음**을 클릭합니다.  
  
9. **설치**를 클릭하고 설치 마법사를 종료합니다.  
  
#### AdventureWorks 샘플 데이터베이스 파일을 SQL Server 인스턴스에 연결하려면  
  
1.  파일 샘플 데이터베이스 설치 관리자 파일을 다운로드한 후 **AdventureWorksDB.msi** 파일\(또는 다운로드한 파일\)을 두 번 클릭하여 데이터베이스를 설치합니다.  기본적으로 데이터베이스는 c:\\Program Files\\Microsoft SQL Server\\MSSQL.1\\MSSQL\\Data에 설치됩니다.  
  
2.  다음 스크립트 SQLCMD 또는 SQL Server Management Studio를 실행하여 AdventureWorks 데이터베이스 파일을 SQL Server 인스턴스에 연결합니다.  
  
    ```  
    exec sp_attach_db @dbname=N'AdventureWorks', @filename1=N'C:\Program Files\Microsoft SQL Server\MSSQL.1\MSSQL\Data\AdventureWorks_Data.mdf', @filename2=N'C:\Program Files\Microsoft SQL Server\MSSQL.1\MSSQL\Data\AdventureWorks_log.ldf'  
    ```  
  
     이러한 파일을 다른 드라이브나 디렉터리에 설치한 경우에는 `sp_attach_db` 저장 프로시저를 실행하기 전에 경로를 올바르게 수정해야 합니다.  
  
## SQL Server Express Edition 다운로드  
 [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] 단원의 샘플과 연습에서는 SQL Server 2005를 데이터 저장소로 사용하지만 SQL Server Express Edition을 대신 사용하도록 수정할 수 있습니다.  SQL Server Express Edition은 무료로 제공되며 응용 프로그램과 함께 재배포할 수 있습니다.  [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]를 사용하고 있는 경우에는 SQL Server Express Edition이 Pro 이상의 에디션에 포함되어 있습니다.  
  
#### SQL Server Express Edition을 다운로드하여 설치하려면  
  
1.  Internet Explorer를 시작합니다.  
  
2.  [Microsoft SQL Server 2005 Express Edition](http://go.microsoft.com/fwlink/?LinkID=31070)\(영문\) 다운로드 페이지로 이동하세요.  
  
3.  웹 사이트의 설치 지침을 따릅니다.  
  
## 참고 항목  
 [시작](../../../../docs/framework/data/adonet/getting-started-linq-to-dataset.md)