---
title: '방법: IIS에서 실행되는 WCF Data Services 개발'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, developing
- WCF Data Services, deploying
- WCF Data Services, hosting
ms.assetid: f6f768c5-4989-49e3-a36f-896ab4ded86e
caps.latest.revision: 5
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f9df38d200be864ab24efdb0d002fe7b75cfc3e4
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-develop-a-wcf-data-service-running-on-iis"></a>방법: IIS에서 실행되는 WCF Data Services 개발
이 항목에서는 사용 하는 방법을 보여 줍니다. [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 인터넷 정보 서비스 (IIS)에서 실행 중인 ASP.NET 웹 응용 프로그램에 의해 호스팅되는 Northwind 샘플 데이터베이스를 기반으로 하는 데이터 서비스를 만드는 합니다. ASP.NET 개발 서버에서 실행 되는 ASP.NET 웹 응용 프로그램으로 동일한 Northwind 데이터 서비스를 만드는 방법의 예제를 보려면는 [WCF Data Services 퀵 스타트](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)합니다.  
  
> [!NOTE]
>  Northwind 데이터 서비스를 만들려면 로컬 컴퓨터에 Northwind 샘플 데이터베이스를 설치해야 합니다. 이 샘플 데이터베이스를 다운로드하려면 [SQL Server용 샘플 데이터베이스](http://go.microsoft.com/fwlink/?linkid=24758)다운로드 페이지를 참조하세요.  
  
 이 항목에서는 Entity Framework 공급자를 사용하여 데이터 서비스를 만드는 방법을 보여 줍니다. 다른 데이터 서비스 공급자를 사용할 수 있습니다. 자세한 내용은 참조 [데이터 서비스 공급자](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)합니다.  
  
 서비스를 만든 후 데이터 서비스 리소스에 대한 액세스 권한을 명시적으로 부여해야 합니다. 자세한 내용은 참조 [하는 방법: 데이터 서비스에 대 한 액세스 사용](../../../../docs/framework/data/wcf/how-to-enable-access-to-the-data-service-wcf-data-services.md)합니다.  
  
### <a name="to-create-the-aspnet-web-application-that-runs-on-iis"></a>IIS에서 실행되는 ASP.NET 웹 응용 프로그램을 만들려면  
  
1.  Visual Studio에서에 **파일** 메뉴 선택 **새로**를 선택한 후 **프로젝트**합니다.  
  
2.  에 **새 프로젝트** 대화 상자에서 Visual Basic 또는 Visual C#의 프로그래밍 언어로 선택 합니다.  
  
3.  에 **템플릿** 창 선택 **ASP.NET 웹 응용 프로그램**합니다. 참고: Visual Studio Web Developer를 사용하는 경우 새 웹 응용 프로그램 대신 새 웹 사이트를 만들어야 합니다.  
  
4.  형식 `NorthwindService` 프로젝트의 이름으로 합니다.  
  
5.  **확인**을 클릭합니다.  
  
6.  에 **프로젝트** 메뉴 선택 **NorthwindService 속성**합니다.  
  
7.  선택 된 **웹** 탭을 선택한 다음 선택 **로컬 IIS 웹 서버 사용**합니다.  
  
8.  클릭 **가상 디렉터리 만들기** 클릭 하 고 **확인**합니다.  
  
9. 관리자 권한으로 실행되는 명령 프롬프트에서 운영 체제에 따라 다음 명령 중 하나를 실행합니다.  
  
    -   32비트 시스템:  
  
        ```console
        "%windir%\Microsoft.NET\Framework\v3.0\Windows Communication Foundation\ServiceModelReg.exe" -i  
        ```  
  
    -   64비트 시스템:  
  
        ```console
        "%windir%\Microsoft.NET\Framework64\v3.0\Windows Communication Foundation\ServiceModelReg.exe" -i  
        ```  
  
     이렇게 하면 WCF(Windows Communication Foundation)가 컴퓨터에 등록됩니다.  
  
10. 관리자 권한으로 실행되는 명령 프롬프트에서 운영 체제에 따라 다음 명령 중 하나를 실행합니다.  
  
    -   32비트 시스템:  
  
        ```console
        "%windir%\Microsoft.NET\Framework\v4.0.30319\aspnet_regiis.exe" -i -enable  
        ```  
  
    -   64비트 시스템:  
  
        ```console
        "%windir%\Microsoft.NET\Framework64\v4.0.30319\aspnet_regiis.exe" -i -enable  
        ```  
  
     이렇게 하면 WCF가 컴퓨터에 설치된 후 IIS가 제대로 실행됩니다. 또한 IIS를 다시 시작해야 할 수도 있습니다.  
  
11. ASP.NET 응용 프로그램이 IIS7에서 실행되는 경우 다음 단계도 수행해야 합니다.  
  
    1.  IIS 관리자를 열고 아래의 PhotoService 응용 프로그램으로 이동 **기본 웹 사이트**합니다.  
  
    2.  **기능 보기**를 두 번 클릭 **인증**합니다.  
  
    3.  에 **인증** 페이지에서 **익명 인증**합니다.  
  
    4.  에 **동작** 창에서 클릭 **편집** 보안을 설정 하는 보안 주체는 익명 사용자에서 사이트에 연결 됩니다.  
  
    5.  에 **익명 인증 자격 증명 편집** 대화 상자에서 **응용 프로그램 풀 id**합니다.  
  
    > [!IMPORTANT]
    >  Network Service 계정을 사용하는 경우 해당 계정과 연결된 모든 내부 네트워크 액세스 권한이 익명 사용자에게 부여됩니다.  
  
12. SQL Server Management Studio, sqlcmd.exe 유틸리티 또는 Visual Studio의 Transact-SQL 편집기를 사용하여 Northwind 데이터베이스가 연결된 SQL Server 인스턴스에 대해 다음 Transact-SQL 명령을 실행합니다.  
  
    ```sql  
    CREATE LOGIN [NT AUTHORITY\NETWORK SERVICE] FROM WINDOWS;  
    GO   
    ```  
  
     이렇게 하면 IIS를 실행하는 데 사용되는 Windows 계정에 대한 로그인이 SQL Server 인스턴스에서 만들어집니다. 이에 따라 IIS에서 SQL Server 인스턴스에 연결할 수 있습니다.  
  
13. Northwind 데이터베이스가 연결된 상태에서 다음 Transact-SQL 명령을 실행합니다.  
  
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
  
### <a name="to-define-the-data-model"></a>데이터 모델을 정의하려면  
  
1.  **솔루션 탐색기**ASP.NET 프로젝트의 이름을 마우스 오른쪽 단추로 클릭 한 다음 클릭 **새 항목 추가 합니다.**  
  
2.  에 **새 항목 추가** 대화 상자에서 **ADO.NET 엔터티 데이터 모델**합니다.  
  
3.  데이터 모델의 이름으로 입력 `Northwind.edmx`합니다.  
  
4.  엔터티 데이터 모델 마법사에서 선택 **데이터베이스에서 생성**, 클릭 하 고 **다음**합니다.  
  
5.  다음 단계 중 하나를 수행 하 여 데이터 모델 데이터베이스에 연결 하 고 클릭 **다음**:  
  
    -   데이터베이스 연결이 이미 구성 되어 있으면 클릭 **새 연결** 고 새 연결을 만듭니다. 자세한 내용은 참조 [하는 방법: SQL Server 데이터베이스에 대 한 연결 만들기](http://go.microsoft.com/fwlink/?LinkId=123631)합니다. 이 SQL Server 인스턴스에는 Northwind 샘플 데이터베이스가 연결되어 있어야 합니다.  
  
         \- 또는 -  
  
    -   Northwind 데이터베이스에 연결할 수 있도록 데이터베이스 연결이 이미 구성되어 있는 경우 연결 목록에서 해당 연결을 선택합니다.  
  
6.  마법사의 마지막 페이지에서 데이터베이스의 모든 테이블에 대한 확인란을 선택하고 뷰 및 저장 프로시저에 대한 확인란의 선택을 취소합니다.  
  
7.  클릭 **마침** 마법사를 닫습니다.  
  
    > [!NOTE]
    >  생성된 이 데이터 모델은 엔터티 형식의 외래 키 속성을 노출합니다. Visual Studio 2008을 사용하여 만들어진 데이터 모델에는 이러한 외래 키 속성이 포함되지 않습니다. 이 때문에 이 버전의 Northwind 데이터 서비스에 액세스하기 전에 Visual Studio 2008을 사용하여 만들어진 Northwind 데이터 서비스에 액세스하기 위해 만들어진 모든 클라이언트 응용 프로그램의 클라이언트 데이터 서비스 클래스를 업데이트해야 합니다.  
  
### <a name="to-create-the-data-service"></a>데이터 서비스를 만들려면  
  
1.  **솔루션 탐색기**ASP.NET 프로젝트 이름을 마우스 오른쪽 단추로 클릭 한 다음 클릭 **새 항목 추가**합니다.  
  
2.  에 **새 항목 추가** 대화 상자에서 **ADO.NET 데이터 서비스**합니다.  
  
3.  서비스의 이름으로 입력 `Northwind`합니다.  
  
     Visual Studio에서 새 서비스의 XML 태그 및 코드 파일이 생성됩니다. 기본적으로 코드 편집기 창이 열립니다. **솔루션 탐색기**, 서비스 이름은, 확장명을 갖습니다. svc.cs 또는. svc.vb 합니다.  
  
4.  데이터 서비스 코드에서 데이터 서비스를 정의하는 클래스 정의의 `/* TODO: put your data source class name here */` 주석을 데이터 모델의 엔터티 컨테이너인 형식(이 경우 `NorthwindEntities`)으로 바꿉니다. 클래스 정의는 다음과 같이 나타납니다.  
  
     [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart service/cs/northwind.svc.cs#servicedefinition)]
     [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart service/vb/northwind.svc.vb#servicedefinition)]  
  
## <a name="see-also"></a>참고 항목  
 [서비스로 데이터 노출](../../../../docs/framework/data/wcf/exposing-your-data-as-a-service-wcf-data-services.md)
