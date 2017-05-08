---
title: ".NET Framework 클라이언트 응용 프로그램 만들기(WCF Data Services 퀵 스타트) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-oob"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 41ade767-eeab-437d-9121-9797e8fb8045
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# .NET Framework 클라이언트 응용 프로그램 만들기(WCF Data Services 퀵 스타트)
이 작업은 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 퀵 스타트의 마지막 작업입니다.  이 작업에서는 솔루션에 콘솔 응용 프로그램을 추가하고, 이 새 클라이언트 응용 프로그램에 [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] 피드에 대한 참조를 추가하고, 생성된 클라이언트 데이터 서비스 클래스와 클라이언트 라이브러리를 사용하여 클라이언트 응용 프로그램에서 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 피드에 액세스합니다.  
  
> [!NOTE]
>  데이터 피드에 액세스하기 위해 .NET Framework 기반 클라이언트 응용 프로그램이 필요하지는 않습니다.  [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 피드를 사용하는 모든 응용 프로그램 구성 요소에서 데이터 서비스에 액세스할 수 있습니다.  자세한 내용은 [클라이언트 응용 프로그램에서 데이터 서비스 사용](../../../../docs/framework/data/wcf/using-a-data-service-in-a-client-application-wcf-data-services.md)을 참조하세요.  
  
### Visual Studio를 사용하여 클라이언트 응용 프로그램을 만들려면  
  
1.  **솔루션 탐색기**에서 솔루션을 마우스 오른쪽 단추로 클릭하고 **추가**, **새 프로젝트**를 차례로 클릭합니다.  
  
2.  **프로젝트 형식**에서 **Windows**를 클릭하고 **템플릿** 창에서 **WPF 응용 프로그램**을 선택합니다.  
  
3.  프로젝트 이름으로 `NorthwindClient`를 입력하고 **확인**을 클릭합니다.  
  
4.  MainWindow.xaml 파일을 열고 XAML 코드를 다음 코드로 바꿉니다.  
  
     [!code-xml[Astoria Quickstart Client#Window1Xaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart client/vb/window1.xaml#window1xaml)]  
  
### 프로젝트에 데이터 서비스 참조를 추가하려면  
  
1.  NorthwindClient 프로젝트를 마우스 오른쪽 단추로 클릭하고 **서비스 참조 추가**, **검색**을 차례로 클릭합니다.  
  
     첫 번째 작업에서 만든 Northwind 데이터 서비스가 표시됩니다.  
  
2.  **네임스페이스** 텍스트 상자에 `Northwind`를 입력하고 **확인**을 클릭합니다.  
  
     데이터 서비스 리소스에 개체로 액세스하고 상호 작용하는 데 사용되는 데이터 클래스가 포함된 새 코드 파일이 프로젝트에 추가됩니다.  데이터 클래스는 `NorthwindClient.Northwind` 네임스페이스에 만들어집니다.  
  
### WPF 응용 프로그램에서 데이터 서비스 데이터에 액세스하려면  
  
1.  **솔루션 탐색기**의 **NorthwindClient**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **참조 추가**를 클릭합니다.  
  
2.  참조 추가 대화 상자에서 **.NET** 탭을 클릭하고 System.Data.Services.Client.dll 어셈블리를 선택한 다음 **확인**을 클릭합니다.  **솔루션 탐색기**의 **NorthwindClient**에서 MainWindow.xaml 파일의 코드 페이지를 열고 다음 `using` 문\(Visual Basic에서는 `Imports`\)을 추가합니다.  
  
     [!code-csharp[Astoria Quickstart Client#Using](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart client/cs/window1.xaml.cs#using)]
     [!code-vb[Astoria Quickstart Client#Using](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart client/vb/window1.xaml.vb#using)]  
  
3.  해당 데이터 서비스를 쿼리하고 결과를 <xref:System.Data.Services.Client.DataServiceCollection%601>에 바인딩하는 다음 코드를 `MainWindow` 클래스에 삽입합니다.  
  
    > [!NOTE]
    >  Northwind 데이터 서비스 인스턴스를 호스트하는 서버 및 포트로 호스트 이름 `localhost:12345`를 바꾸어야 합니다.  
  
     [!code-csharp[Astoria Quickstart Client#QueryCode](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart client/cs/window1.xaml.cs#querycode)]
     [!code-vb[Astoria Quickstart Client#QueryCode](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart client/vb/window1.xaml.vb#querycode)]  
  
4.  변경 내용을 저장하는 다음 코드를 `MainWindow` 클래스에 삽입합니다.  
  
     [!code-csharp[Astoria Quickstart Client#SaveChanges](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart client/cs/window1.xaml.cs#savechanges)]
     [!code-vb[Astoria Quickstart Client#SaveChanges](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart client/vb/window1.xaml.vb#savechanges)]  
  
### NorthwindClient 응용 프로그램을 빌드 및 실행하려면  
  
1.  **솔루션 탐색기**에서 NorthwindClient 프로젝트를 마우스 오른쪽 단추로 클릭하고 **시작 프로젝트로 설정**을 선택합니다.  
  
2.  F5 키를 눌러 응용 프로그램을 시작합니다.  
  
     솔루션이 빌드되고 클라이언트 응용 프로그램이 시작됩니다.  서비스에서 데이터가 요청되고 콘솔에 표시됩니다.  
  
3.  데이터 표의 **Quantity** 열에 있는 값을 편집한 다음 **저장**을 클릭합니다.  
  
     변경 내용이 데이터 서비스에 저장됩니다.  
  
    > [!NOTE]
    >  이 버전의 NorthwindClient 응용 프로그램은 엔터티의 추가와 삭제를 지원하지 않습니다.  
  
## 다음 단계  
 샘플 Northwind [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 피드에 액세스하는 클라이언트 응용 프로그램을 성공적으로 만들었으며  [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 퀵 스타트도 완료했습니다.  [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 응용 프로그램의 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 피드에 액세스하는 방법[!INCLUDE[crabout](../../../../includes/crabout-md.md)] [WCF Data Services 클라이언트 라이브러리](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)을 참조하세요.  
  
## 참고 항목  
 [시작](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)   
 [리소스](../../../../docs/framework/data/wcf/wcf-data-services-resources.md)