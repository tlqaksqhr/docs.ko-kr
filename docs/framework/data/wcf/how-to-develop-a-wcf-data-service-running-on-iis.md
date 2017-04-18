---
title: "방법: IIS에서 실행되는 WCF Data Services 개발 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-oob"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "WCF Data Services, 배포"
  - "WCF Data Services, 개발"
  - "WCF Data Services, 호스팅"
ms.assetid: f6f768c5-4989-49e3-a36f-896ab4ded86e
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# 방법: IIS에서 실행되는 WCF Data Services 개발
이 항목에서는 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]를 사용하여 IIS\(인터넷 정보 서비스\)에서 실행되는 ASP.NET 웹 응용 프로그램이 호스트하는 Northwind 샘플 데이터베이스를 기반으로 데이터 서비스를 만드는 방법을 보여 줍니다.  ASP.NET Development Server에서 실행되는 ASP.NET 웹 응용 프로그램으로 동일한 Northwind 데이터 서비스를 만드는 방법의 예제는 [WCF Data Services 퀵 스타트](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)를 참조하세요.  
  
> [!NOTE]
>  Northwind 데이터 서비스를 만들려면 로컬 컴퓨터에 Northwind 샘플 데이터베이스를 설치해야 합니다.  샘플 데이터베이스를 다운로드하려면 다운로드 페이지 [SQL Server용 샘플 데이터베이스](http://go.microsoft.com/fwlink/?linkid=24758)를 참조하세요.  
  
 이 항목에서는 Entity Framework 공급자를 사용하여 데이터 서비스를 만드는 방법을 보여 줍니다.  다른 데이터 서비스 공급자를 사용할 수 있습니다.  자세한 내용은 [데이터 서비스 공급자](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)을 참조하세요.  
  
 서비스를 만든 후 데이터 서비스 리소스에 대한 액세스 권한을 명시적으로 부여해야 합니다.  자세한 내용은 [방법: 데이터 서비스에 액세스할 수 있도록 설정](../../../../docs/framework/data/wcf/how-to-enable-access-to-the-data-service-wcf-data-services.md)을 참조하세요.  
  
### IIS에서 실행되는 ASP.NET 웹 응용 프로그램을 만들려면  
  
1.  Visual Studio의 **파일** 메뉴에서 **새로 만들기**를 선택한 다음 **프로젝트**를 선택합니다.  
  
2.  **새 프로젝트** 대화 상자에서 Visual Basic 또는 Visual C\#을 프로그래밍 언어로 선택합니다.  
  
3.  **템플릿** 창에서 **ASP.NET 웹 응용 프로그램**을 선택합니다.  참고: Visual Studio Web Developer를 사용하는 경우 새 웹 응용 프로그램 대신 새 웹 사이트를 만들어야 합니다.  
  
4.  프로젝트 이름으로 `NorthwindService`를 입력합니다.  
  
5.  **확인**을 클릭합니다.  
  
6.  **프로젝트** 메뉴에서 **NorthwindService 속성**을 선택합니다.  
  
7.  **웹** 탭을 선택한 다음 **로컬 IIS 웹 서버 사용**을 선택합니다.  
  
8.  **가상 디렉터리 만들기**를 클릭한 다음 **확인**을 클릭합니다.  
  
9. 관리자 권한으로 실행되는 명령 프롬프트에서 운영 체제에 따라 다음 명령 중 하나를 실행합니다.  
  
    -   32비트 시스템:  
  
        ```ms-dos  
        "%windir%\Microsoft.NET\Framework\v3.0\Windows Communication Foundation\ServiceModelReg.exe" -i  
        ```  
  
    -   64비트 시스템:  
  
        ```ms-dos  
        "%windir%\Microsoft.NET\Framework64\v3.0\Windows Communication Foundation\ServiceModelReg.exe" -i  
        ```  
  
     이렇게 하면 WCF\(Windows Communication Foundation\)가 컴퓨터에 등록됩니다.  
  
10. 관리자 권한으로 실행되는 명령 프롬프트에서 운영 체제에 따라 다음 명령 중 하나를 실행합니다.  
  
    -   32비트 시스템:  
  
        ```ms-dos  
        "%windir%\Microsoft.NET\Framework\v4.0.30319\aspnet_regiis.exe" -i -enable  
        ```  
  
    -   64비트 시스템:  
  
        ```ms-dos  
        "%windir%\Microsoft.NET\Framework64\v4.0.30319\aspnet_regiis.exe" -i -enable  
        ```  
  
     이렇게 하면 WCF가 컴퓨터에 설치된 후 IIS가 제대로 실행됩니다.  또한 IIS를 다시 시작해야 할 수도 있습니다.  
  
11. ASP.NET 응용 프로그램이 IIS7에서 실행되는 경우 다음 단계도 수행해야 합니다.  
  
    1.  IIS 관리자를 열고 **기본 웹 사이트** 아래의 PhotoService 응용 프로그램으로 이동합니다.  
  
    2.  **기능 보기**에서 **인증**을 두 번 클릭합니다.  
  
    3.  **인증** 페이지에서 **익명 인증**을 선택합니다.  
  
    4.  **작업** 창에서 **편집**을 클릭하여 익명 사용자가 사이트에 연결할 보안 주체를 설정합니다.  
  
    5.  **익명 인증 자격 증명 편집** 대화 상자에서 **응용 프로그램 풀 ID**를 선택합니다.  
  
    > [!IMPORTANT]
    >  Network Service 계정을 사용하는 경우 해당 계정과 연결된 모든 내부 네트워크 액세스 권한이 익명 사용자에게 부여됩니다.  
  
12. SQL Server Management Studio, sqlcmd.exe 유틸리티 또는 Visual Studio의 Transact\-SQL 편집기를 사용하여 Northwind 데이터베이스가 연결된 SQL Server 인스턴스에 대해 다음 Transact\-SQL 명령을 실행합니다.  
  
    ```sql  
    CREATE LOGIN [NT AUTHORITY\NETWORK SERVICE] FROM WINDOWS;  
    GO   
    ```  
  
     이렇게 하면 IIS를 실행하는 데 사용되는 Windows 계정에 대한 로그인이 SQL Server 인스턴스에서 만들어집니다.  이에 따라 IIS에서 SQL Server 인스턴스에 연결할 수 있습니다.  
  
13. Northwind 데이터베이스가 연결된 상태에서 다음 Transact\-SQL 명령을 실행합니다.  
  
    ```sql  
    USE Northwind  
    GO  
    CREATE USER [NT AUTHORITY\NETWORK SERVICE]   
    FOR LOGIN [NT AUTHORITY\NETWORK SERVICE] WITH DEFAULT_SCHEMA=[dbo];  
    GO  
    ALTER LOGIN [NT AUTHORITY\NETWORK SERVICE]   
    WITH DEFAULT_DATABASE=[Northwind];   
    GO  
    EXEC sp_addrolemember 'db_datareader', 'NT AUTHORITY\NETWORK SERVICE'  
    GO  
    EXEC sp_addrolemember 'db_datawriter', 'NT AUTHORITY\NETWORK SERVICE'  
    GO   
    ```  
  
     이렇게 하면 새 로그인에 권한이 부여되어 IIS에서 Northwind 데이터베이스에 있는 데이터를 읽고 Northwind 데이터베이스에 데이터를 쓸 수 있습니다.  
  
### 데이터 모델을 정의하려면  
  
1.  **솔루션 탐색기**에서 ASP.NET 프로젝트의 이름을 마우스 오른쪽 단추로 클릭하고 **새 항목 추가**를 클릭합니다.  
  
2.  **새 항목 추가** 대화 상자에서 **ADO.NET Entity Data Model**을 선택합니다.  
  
3.  데이터 모델의 이름으로 `Northwind.edmx`를 입력합니다.  
  
4.  엔터티 데이터 모델 마법사에서 **데이터베이스에서 생성**을 선택하고 **다음**을 클릭합니다.  
  
5.  다음 단계 중 하나를 수행하여 데이터 모델을 데이터베이스에 연결하고 **다음**을 클릭합니다.  
  
    -   데이터베이스 연결이 구성되어 있지 않은 경우 **새 연결**을 클릭하고 새 연결을 만듭니다.  자세한 내용은 [방법: SQL Server 데이터베이스에 대한 연결 만들기](http://go.microsoft.com/fwlink/?LinkId=123631)를 참조하세요.  이 [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] 인스턴스에는 Northwind 샘플 데이터베이스가 연결되어 있어야 합니다.  
  
         또는  
  
    -   Northwind 데이터베이스에 연결할 수 있도록 데이터베이스 연결이 이미 구성되어 있는 경우 연결 목록에서 해당 연결을 선택합니다.  
  
6.  마법사의 마지막 페이지에서 데이터베이스의 모든 테이블에 대한 확인란을 선택하고 뷰 및 저장 프로시저에 대한 확인란의 선택을 취소합니다.  
  
7.  **마침**을 클릭하여 마법사를 닫습니다.  
  
    > [!NOTE]
    >  생성된 이 데이터 모델은 엔터티 형식의 외래 키 속성을 노출합니다.  Visual Studio 2008을 사용하여 만들어진 데이터 모델에는 이러한 외래 키 속성이 포함되지 않습니다.  이 때문에 이 버전의 Northwind 데이터 서비스에 액세스하기 전에 Visual Studio 2008을 사용하여 만들어진 Northwind 데이터 서비스에 액세스하기 위해 만들어진 모든 클라이언트 응용 프로그램의 클라이언트 데이터 서비스 클래스를 업데이트해야 합니다.  
  
### 데이터 서비스를 만들려면  
  
1.  **솔루션 탐색기**에서 ASP.NET 프로젝트 이름을 마우스 오른쪽 단추로 클릭하고 **새 항목 추가**를 클릭합니다.  
  
2.  **새 항목 추가** 대화 상자에서 **ADO.NET 데이터 서비스**를 선택합니다.  
  
3.  서비스 이름으로 `Northwind`를 입력합니다.  
  
     Visual Studio에서 새 서비스의 XML 태그 및 코드 파일이 생성됩니다.  기본적으로 코드 편집기 창이 열립니다.  **솔루션 탐색기**에서 이 서비스의 이름은 Northwind.svc.cs 또는 Northwind.svc.vb로 나타납니다.  
  
4.  데이터 서비스 코드에서 데이터 서비스를 정의하는 클래스 정의의 `/* TODO: put your data source class name here */` 주석을 데이터 모델의 엔터티 컨테이너인 형식\(이 경우 `NorthwindEntities`\)으로 바꿉니다.  클래스 정의는 다음과 같이 나타납니다.  
  
     [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart service/cs/northwind.svc.cs#servicedefinition)]
     [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart service/vb/northwind.svc.vb#servicedefinition)]  
  
## 참고 항목  
 [데이터를 서비스로 노출](../../../../docs/framework/data/wcf/exposing-your-data-as-a-service-wcf-data-services.md)