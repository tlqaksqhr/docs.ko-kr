---
title: "ASP.NET 캐싱 통합"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f581923a-8a72-42fc-bd6a-46de2aaeecc1
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 23cdd79d72f7cb40758fafb63ee4d0f725cbfc1c
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="aspnet-caching-integration"></a>ASP.NET 캐싱 통합
이 샘플에서는 WCF 웹 HTTP 프로그래밍 모델을 사용하여 ASP.NET 출력 캐시를 활용하는 방법을 보여 줍니다. 참조 하십시오는 [Basic Resource Service](../../../../docs/framework/wcf/samples/basic-resource-service.md) 자체 호스팅 버전 심층에서 서비스 구현에 나와 있는이 시나리오의 샘플입니다. 이 항목에서는 ASP.NET 출력 캐시 통합 기능을 중점적으로 설명합니다.  
  
## <a name="demonstrates"></a>세부 항목  
 ASP.NET 출력 캐시와 통합  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\AspNetCachingIntegration`  
  
## <a name="discussion"></a>토론  
 이 샘플에서는 <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute>를 사용하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 서비스에 ASP.NET 출력 캐싱을 활용합니다. <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute>는 서비스 작업에 적용되며, 구성 파일에서 지정된 작업의 응답에 적용해야 하는 캐시 프로필의 이름을 제공합니다.  
  
 샘플 Service 프로젝트의 Service.cs 파일에서 모두는 `GetCustomer` 및 `GetCustomers` 작업으로 표시 됩니다는 <xref:System.ServiceModel.Web.AspNetCacheProfileAttribute>, 캐시 프로필 이름 "CacheFor60Seconds"를 제공 하는 합니다. 서비스 프로젝트의 Web.config 파일에서 캐시 프로필 "CacheFor60Seconds" 제공 하지 않습니다는 <`caching`> 요소의 <`system.web`> 합니다. 이 캐시 프로필의 값에는 `duration` 특성 이므로 "60"이이 프로필에 연결 된 응답은 60 초 동안 ASP.NET 출력 캐시에 캐시 됩니다. 또한이 캐시 프로필에 대 한는 `varmByParam` 특성이 너무 요청에 대 한 값이 서로 다른 "format"으로 설정 되어는 `format` 쿼리 문자열 매개 변수에서는 응답이 별도로 캐시 됩니다. 마지막으로 캐시 프로필의 `varyByHeader` 있으므로 Accept 헤더 값이 다른 요청에서는 응답이 별도로 캐시 특성이 "Accept"로 설정 되어 있습니다.  
  
 Client 프로젝트의 Program.cs에서는 <xref:System.Net.HttpWebRequest>를 사용하여 이러한 클라이언트를 작성하는 방법을 보여 줍니다. 이 방법은 WCF 서비스에 액세스하는 여러 방법 중 하나일 뿐입니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 채널 팩터리 및 <xref:System.Net.WebClient>와 같은 다른 .NET Framework 클래스를 사용하여 서비스에 액세스할 수도 있습니다. SDK의 다른 샘플 (같은 [기본 HTTP 서비스](../../../../docs/framework/wcf/samples/basic-http-service.md) 샘플 및 [선택 영역 자동 서식](../../../../docs/framework/wcf/samples/automatic-format-selection.md) 샘플)와 통신 하려면 이러한 클래스를 사용 하는 방법을 보여는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스입니다.  
  
## <a name="to-run-the-sample"></a>이 샘플을 실행하려면  
 이 샘플은 다음의 세 프로젝트로 구성되어 있습니다.  
  
-   **서비스**: ASP.NET에서 호스팅되는 WCF HTTP 서비스가 포함 된 웹 응용 프로그램 프로젝트입니다.  
  
-   **클라이언트**: 콘솔 응용 프로그램 프로젝트 서비스에 대 한 호출입니다.  
  
-   **일반적인**: 클라이언트 및 서비스에 의해 사용 되는 고객 형식을 포함 하는 공유 라이브러리입니다.  
  
 Client 콘솔 응용 프로그램이 실행되면 클라이언트에서는 서비스로 요청을 보내고 응답의 관련 정보를 콘솔 창에 씁니다.  
  
#### <a name="to-run-the-sample"></a>이 샘플을 실행하려면  
  
1.  ASP.NET Caching Integration 샘플의 솔루션을 엽니다.  
  
2.  Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.  
  
3.  경우는 **솔루션 탐색기** 창이 아직 열려 있지 않으면, CTRL + W + S를 누릅니다.  
  
4.  **솔루션 탐색기** 창을 마우스 오른쪽 단추로 클릭은 **서비스** 프로젝트를 마우스 선택 **새 인스턴스 시작**합니다. 그러면 ASP.NET Development Server가 시작되어 서비스를 호스트합니다.  
  
5.  **솔루션 탐색기** 창을 마우스 오른쪽 단추로 클릭은 **클라이언트** 프로젝트를 마우스 선택 **새 인스턴스 시작**합니다.  
  
6.  클라이언트 콘솔 창이 나타나고 실행 중인 서비스의 URI와 실행 중인 서비스에 대한 HTML 도움말 페이지의 URI가 제공됩니다. 언제든지 브라우저에서 HTML 도움말 페이지의 URI를 입력하면 해당 도움말 페이지를 볼 수 있습니다.  
  
7.  샘플이 실행되면 클라이언트에서는 현재 활동의 상태를 씁니다.  
  
8.  아무 키나 눌러 클라이언트 콘솔 응용 프로그램을 종료합니다.  
  
9. Shift+F5를 눌러 서비스 디버깅을 중지합니다.  
  
10. Windows 알림 영역에서 ASP.NET 개발 서버 아이콘을 마우스 오른쪽 단추로 클릭 하 고 선택 **중지**합니다.
