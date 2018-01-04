---
title: "LINQ to SQL 샘플"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5f39db9e-0e62-42c9-8c98-bb8b54cec98c
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 06273f3ac7dd159adac4c058a23c187f44417d94
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="linq-to-sql-sample"></a>LINQ to SQL 샘플
이 샘플에서는 SQL Server 데이터베이스의 테이블에 있는 LINQ to SQL 쿼리 엔터티를 사용하는 활동을 만드는 방법을 보여 줍니다.  
  
> [!IMPORTANT]
>  컴퓨터에 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\Samples\WCFWFCardspace`  
>   
>  이 디렉터리가 없으면 이 페이지의 맨 위에 있는 다운로드 샘플 링크를 클릭하세요. 그러면 모든 [!INCLUDE[wf1](../../../../includes/wf1-md.md)], [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 및 [!INCLUDE[infocard](../../../../includes/infocard-md.md)] 샘플이 다운로드되고 설치됩니다. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\Samples\WCFWFCardSpace\WF\Scenario\ActivityLibrary\Linq\LinqToSql`  
  
## <a name="activity-details-for-findinsqltable"></a>FindInSqlTable의 활동 세부 정보  
 이 활동을 사용하면 사용자가 LINQ to SQL을 사용하여 데이터베이스에 있는 테이블의 엔터티를 쿼리할 수 있습니다. 활동 사용자가 람다 식 형식의 LINQ 조건자를 제공하여 결과를 필터링할 수도 있습니다. 조건자를 제공하지 않으면 전체 테이블이 반환됩니다. 다음 표에서는 활동의 속성 및 반환 값에 대해 자세히 설명합니다.  
  
|속성 또는 반환 값|설명|  
|------------------------------|-----------------|  
|`Collection` 속성|소스 컬렉션을 지정하는 필수 속성입니다.|  
|`Predicate` 속성|람다 식 형식으로 컬렉션의 필터를 지정하는 필수 속성입니다.|  
|반환 값|필터링된 컬렉션입니다.|  
  
## <a name="code-sample-that-uses-the-custom-activity"></a>사용자 지정 활동을 사용하는 코드 샘플  
 다음 코드 예제에서는 `FindInSqlTable` 사용자 지정 활동을 사용하여 `Employee`라는 SQL Server 테이블에서 `Role` 열이 `SDE`인 모든 행을 찾습니다.  
  
```csharp  
new FindInSqlTable<Employee>   
{  
    ConnectionString = @"Data Source=.\SQLExpress;Initial Catalog=LinqToSqlSample;Integrated Security=True",                          
    Predicate = new LambdaValue<Func<Employee, bool>>(c => new Func<Employee, bool>(emp => emp.Role.Equals("SDE"))),  
    Result = new OutArgument<IList<Employee>>(employees)  
},  
```  
  
#### <a name="to-use-this-sample"></a>이 샘플을 사용하려면  
  
1.  명령 프롬프트를 엽니다.  
  
2.  이 샘플이 들어 있는 폴더로 이동합니다.  
  
3.  Setup.cmd 명령 파일을 실행합니다.  
  
    > [!NOTE]
    >  Setup.cmd 스크립트가 로컬 컴퓨터 SQL Server Express에 샘플 데이터베이스를 설치하려고 시도합니다. 다른 SQL Server 인스턴스에 설치하려면 Setup.cmd를 편집합니다.  
  
     Setup.cmd 스크립트가 다음 동작을 수행합니다.  
  
    -   LinqToSqlSample이라는 데이터베이스를 만듭니다.  
  
    -   Roles 테이블을 만듭니다.  
  
    -   Employees 테이블을 만듭니다.  
  
    -   Roles 테이블에 세 개의 레코드를 삽입합니다.  
  
    -   Employees 테이블에 12개의 레코드를 삽입합니다.  
  
4.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]을 사용하여 LinqToSQL.sln 솔루션 파일을 엽니다.  
  
5.  Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.  
  
6.  F5 키를 눌러 솔루션을 실행합니다.  
  
#### <a name="to-uninstall-the-linqtosql-sample-database"></a>LinqToSql 샘플 데이터베이스를 제거하려면  
  
1.  명령 프롬프트를 엽니다.  
  
2.  이 샘플이 들어 있는 폴더로 이동합니다.  
  
3.  Cleanup.cmd 명령 파일을 실행합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\Liiinq\LinqToSql`  
  
## <a name="see-also"></a>참고 항목  
 [LINQ to SQL](http://go.microsoft.com/fwlink/?LinkId=150376)  
 [시작 (LINQ to SQL)](http://go.microsoft.com/fwlink/?LinkId=150377)
