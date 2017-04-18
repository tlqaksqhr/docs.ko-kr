---
title: "ASP.NET 캐싱 통합 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f581923a-8a72-42fc-bd6a-46de2aaeecc1
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# ASP.NET 캐싱 통합
이 샘플에서는 WCF 웹 HTTP 프로그래밍 모델을 사용하여 ASP.NET 출력 캐시를 활용하는 방법을 보여 줍니다.  서비스 구현에 대해 자세히 설명하는 이 시나리오의 자체 호스팅 버전은 [기본 리소스 서비스](../../../../docs/framework/wcf/samples/basic-resource-service.md) 샘플을 참조하세요.  이 항목에서는 ASP.NET 출력 캐시 통합 기능을 중점적으로 설명합니다.  
  
## 세부 항목  
 ASP.NET 출력 캐시와 통합  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.  계속하기 전에 다음\(기본\) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [.NET Framework 4용 WCF\(Windows Communication Foundation\) 및 Windows WF\(Workflow Foundation\) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780)\(영문\)로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.  이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\AspNetCachingIntegration`  
  
## 토론  
 이 샘플에서는 <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute>를 사용하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 서비스에 ASP.NET 출력 캐싱을 활용합니다.  <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute>는 서비스 작업에 적용되며, 구성 파일에서 지정된 작업의 응답에 적용해야 하는 캐시 프로필의 이름을 제공합니다.  
  
 샘플 Service 프로젝트의 Service.cs 파일에서 `GetCustomer` 및 `GetCustomers` 작업은 모두 캐시 프로필 이름 “CacheFor60Seconds”를 제공하는 <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute>로 표시됩니다.  Service 프로젝트의 Web.config 파일에서 캐시 프로필 “CacheFor60Seconds”는 \<`system.web`\>의 \<`caching`\> 요소 아래에 제공됩니다.  이 캐시 프로필의 경우 `duration` 특성 값은 “60”이므로 이 프로필과 연결된 응답은 60초 동안 ASP.NET 출력 캐시에 캐시됩니다.  또한 이 캐시 프로필의 경우 `varmByParam` 특성이 “format”으로 설정되어 있으므로 `format` 쿼리 문자열 매개 변수의 값이 다른 요청에서는 응답이 별도로 캐시됩니다.  마지막으로 캐시 프로필의 `varyByHeader` 특성이 “Accept”로 설정되어 있으므로 Accept 헤더 값이 다른 요청에서는 응답이 별도로 캐시됩니다.  
  
 Client 프로젝트의 Program.cs에서는 <xref:System.Net.HttpWebRequest>를 사용하여 이러한 클라이언트를 작성하는 방법을 보여 줍니다.  이 방법은 WCF 서비스에 액세스하는 여러 방법 중 하나일 뿐입니다.  [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 채널 팩터리 및 <xref:System.Net.WebClient>와 같은 다른 .NET Framework 클래스를 사용하여 서비스에 액세스할 수도 있습니다.  [기본 HTTP 서비스](../../../../docs/framework/wcf/samples/basic-http-service.md) 샘플 및 [자동 포맷 선택](../../../../docs/framework/wcf/samples/automatic-format-selection.md) 샘플과 같은 SDK의 다른 샘플에서는 이러한 클래스를 사용하여 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스와 통신하는 방법을 보여 줍니다.  
  
## 이 샘플을 실행하려면  
 이 샘플은 다음의 세 프로젝트로 구성되어 있습니다.  
  
-   **Service**: ASP.NET에서 호스트되는 WCF HTTP 서비스가 포함된 웹 응용 프로그램 프로젝트입니다.  
  
-   **Client**: 서비스를 호출하는 콘솔 응용 프로그램 프로젝트입니다.  
  
-   **Common**: 클라이언트 및 서비스에서 사용되는 Customer 형식이 포함된 공유 라이브러리입니다.  
  
 Client 콘솔 응용 프로그램이 실행되면 클라이언트에서는 서비스로 요청을 보내고 응답의 관련 정보를 콘솔 창에 씁니다.  
  
#### 이 샘플을 실행하려면  
  
1.  ASP.NET Caching Integration 샘플의 솔루션을 엽니다.  
  
2.  Ctrl\+Shift\+B를 눌러 솔루션을 빌드합니다.  
  
3.  **솔루션 탐색기** 창이 아직 열려 있지 않은 경우 Ctrl\+W\+S를 눌러 엽니다.  
  
4.  **솔루션 탐색기** 창에서 **Service** 프로젝트를 마우스 오른쪽 단추로 클릭하고 **새 인스턴스 시작**을 선택합니다.  그러면 ASP.NET Development Server가 시작되어 서비스를 호스트합니다.  
  
5.  **솔루션 탐색기** 창에서 **Client** 프로젝트를 마우스 오른쪽 단추로 클릭하고 **새 인스턴스 시작**을 선택합니다.  
  
6.  클라이언트 콘솔 창이 나타나고 실행 중인 서비스의 URI와 실행 중인 서비스에 대한 HTML 도움말 페이지의 URI가 제공됩니다.  언제든지 브라우저에서 HTML 도움말 페이지의 URI를 입력하면 해당 도움말 페이지를 볼 수 있습니다.  
  
7.  샘플이 실행되면 클라이언트에서는 현재 활동의 상태를 씁니다.  
  
8.  아무 키나 눌러 클라이언트 콘솔 응용 프로그램을 종료합니다.  
  
9. Shift\+F5를 눌러 서비스 디버깅을 중지합니다.  
  
10. Windows 알림 영역에서 ASP.NET 개발 서버 아이콘을 마우스 오른쪽 단추로 클릭하고 **중지**를 선택합니다.