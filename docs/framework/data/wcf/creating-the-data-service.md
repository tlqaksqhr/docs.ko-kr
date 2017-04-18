---
title: "데이터 서비스 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-oob"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 34d1d971-5e18-4c22-9bf6-d3612e27ea59
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# 데이터 서비스 만들기
이 작업에서는 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]를 사용하여 Northwind 샘플 데이터베이스를 기반으로 하는 [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] 피드를 노출하는 샘플 데이터 서비스를 만듭니다. 작업에 필요한 기본 단계는 다음과 같습니다.  
  
1.  [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 웹 응용 프로그램을 만듭니다.  
  
2.  [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)] 도구를 사용하여 데이터 모델을 정의합니다.  
  
3.  웹 응용 프로그램에 데이터 서비스를 추가합니다.  
  
4.  데이터 서비스에 액세스할 수 있도록 설정합니다.  
  
> [!NOTE]
>  이 작업을 완료할 때 만드는 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 웹 응용 프로그램은 [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]에서 제공하는 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Development Server에서 실행됩니다.  [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Development Server는 로컬 컴퓨터에서의 액세스만 지원합니다.  개발 중에 보다 쉽게 데이터 서비스를 테스트하고 관련 문제를 해결하려면 IIS\(인터넷 정보 서비스\)를 사용하여 데이터 서비스를 호스트하는 응용 프로그램을 실행하는 것이 좋습니다.  자세한 내용은 [방법: IIS에서 실행되는 WCF Data Services 개발](../../../../docs/framework/data/wcf/how-to-develop-a-wcf-data-service-running-on-iis.md)을 참조하세요.  
  
### ASP.NET 웹 응용 프로그램을 만들려면  
  
1.  [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]의 **파일** 메뉴에서 **새로 만들기**를 선택한 다음 **프로젝트**를 선택합니다.  
  
2.  **새 프로젝트** 대화 상자의 [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] 또는 [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] 아래에서 **웹** 템플릿을 선택한 다음 **ASP.NET 웹 응용 프로그램**을 선택합니다.  
  
    > [!NOTE]
    >  [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] Web Developer를 사용하는 경우 새 웹 응용 프로그램 대신 새 웹 사이트를 만들어야 합니다.  
  
3.  프로젝트 이름으로 `NorthwindService`를 입력합니다.  
  
4.  **확인**을 클릭합니다.  
  
5.  \(선택 사항\) 웹 응용 프로그램의 특정 포트 번호를 지정합니다.  참고: 포트 번호 `12345`가 퀵 스타트의 나머지 부분에서 사용됩니다.  
  
    1.  **솔루션 탐색기**에서 방금 만든 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 프로젝트의 이름을 마우스 오른쪽 단추로 클릭하고 **속성**을 클릭합니다.  
  
    2.  **웹** 탭을 선택하고 **특정 포트** 텍스트 상자의 값을 `12345`로 설정합니다.  
  
### 데이터 모델을 정의하려면  
  
1.  **솔루션 탐색기**에서 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 프로젝트의 이름을 마우스 오른쪽 단추로 클릭한 다음 **새 항목 추가**를 클릭합니다.  
  
2.  **새 항목 추가** 대화 상자에서 **데이터** 템플릿을 클릭한 다음 **ADO.NET 엔터티 데이터 모델**을 선택합니다.  
  
3.  데이터 모델의 이름으로 `Northwind.edmx`를 입력합니다.  
  
4.  [!INCLUDE[adonet_edm](../../../../includes/adonet-edm-md.md)] 마법사에서 **데이터베이스에서 생성**을 선택하고 **다음**을 클릭합니다.  
  
5.  다음 단계 중 하나를 수행하여 데이터 모델을 데이터베이스에 연결하고 **다음**을 클릭합니다.  
  
    -   데이터베이스 연결이 구성되어 있지 않은 경우 **새 연결**을 클릭하고 새 연결을 만듭니다.  자세한 내용은 [방법: SQL Server 데이터베이스에 대한 연결 만들기](http://go.microsoft.com/fwlink/?LinkId=123631)를 참조하세요.  이 [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)] 인스턴스에는 Northwind 샘플 데이터베이스가 연결되어 있어야 합니다.  
  
         또는  
  
    -   Northwind 데이터베이스에 연결할 수 있도록 데이터베이스 연결이 이미 구성되어 있는 경우 연결 목록에서 해당 연결을 선택합니다.  
  
6.  마법사의 마지막 페이지에서 데이터베이스의 모든 테이블에 대한 확인란을 선택하고 뷰 및 저장 프로시저에 대한 확인란의 선택을 취소합니다.  
  
7.  **마침**을 클릭하여 마법사를 닫습니다.  
  
    > [!NOTE]
    >  생성된 이 데이터 모델은 엔터티 형식의 외래 키 속성을 노출합니다.  [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] 2008을 사용하여 만들어진 데이터 모델에는 이러한 외래 키 속성이 포함되지 않습니다.  이 때문에 이 버전의 Northwind 데이터 서비스에 액세스하기 전에 [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] 2008을 사용하여 만들어진 Northwind 데이터 서비스에 액세스하기 위해 만들어진 모든 클라이언트 응용 프로그램의 클라이언트 데이터 서비스 클래스를 업데이트해야 합니다.  
  
### 데이터 서비스를 만들려면  
  
1.  **솔루션 탐색기**에서 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 프로젝트의 이름을 마우스 오른쪽 단추로 클릭한 다음 **새 항목 추가**를 클릭합니다.  
  
2.  **새 항목 추가** 대화 상자에서 **WCF Data Services**를 선택합니다.  
  
3.  서비스 이름으로 `Northwind`를 입력합니다.  
  
     [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]에서 새 서비스의 XML 태그와 코드 파일이 만들어집니다.  기본적으로 코드 편집기 창이 열립니다.  **솔루션 탐색기**에서 이 서비스의 이름은 Northwind.svc.cs 또는 Northwind.svc.vb로 나타납니다.  
  
4.  데이터 서비스 코드에서 데이터 서비스를 정의하는 클래스 정의의 `/* TODO: put your data source class name here */` 주석을 데이터 모델의 엔터티 컨테이너인 형식\(이 경우 `NorthwindEntities`\)으로 바꿉니다.  클래스 정의는 다음과 같이 나타납니다.  
  
     [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart service/cs/northwind.svc.cs#servicedefinition)]
     [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart service/vb/northwind.svc.vb#servicedefinition)]  
  
### 데이터 서비스 리소스에 액세스할 수 있도록 설정하려면  
  
1.  데이터 서비스 코드에서 `InitializeService` 함수의 자리 표시자 코드를 다음 코드로 바꿉니다.  
  
     [!code-csharp[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart service/cs/northwind.svc.cs#allreadconfig)]
     [!code-vb[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart service/vb/northwind.svc.vb#allreadconfig)]  
  
     이렇게 하면 권한 있는 클라이언트가 지정된 엔터티 집합의 리소스에 대한 읽기 및 쓰기 액세스 권한을 가질 수 있습니다.  
  
    > [!NOTE]
    >  [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 응용 프로그램에 액세스할 수 있는 클라이언트는 데이터 서비스에 의해 노출되는 리소스에도 액세스할 수 있습니다.  리소스에 무단으로 액세스할 수 없도록 하려면 프로덕션 데이터 서비스에서 응용 프로그램 자체에도 보안을 설정해야 합니다.  자세한 내용은 [WCF Data Services에 보안 설정](../../../../docs/framework/data/wcf/securing-wcf-data-services.md)을 참조하세요.  
  
## 다음 단계  
 Northwind 샘플 데이터베이스를 기반으로 하는 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 피드를 노출하는 새 데이터 서비스를 성공적으로 만들었으며 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 웹 응용 프로그램에 대한 사용 권한이 있는 클라이언트의 피드에 액세스할 수 있도록 설정했습니다.  다음에는 [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]에서 데이터 서비스를 시작하고 웹 브라우저를 통해 HTTP GET 요청을 전송하여 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 피드에 액세스합니다.  
  
 [웹 브라우저에서 서비스 액세스](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)  
  
## 참고 항목  
 [ADO.NET Entity Data Model  Tools](http://msdn.microsoft.com/ko-kr/91076853-0881-421b-837a-f582f36be527)