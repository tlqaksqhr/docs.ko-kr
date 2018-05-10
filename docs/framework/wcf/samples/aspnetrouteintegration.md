---
title: AspNetRouteIntegration
ms.date: 03/30/2017
ms.assetid: 0638ce0e-d053-47df-a447-688e447a03fb
ms.openlocfilehash: 671857b0ace2e18f0dac7fd8033a20f3af889c8b
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="aspnetrouteintegration"></a>AspNetRouteIntegration
이 샘플에서는 ASP.NET 경로 사용 하 여 Windows Communication Foundation (WCF) 나머지 서비스를 호스트 하는 방법을 보여 줍니다. [Basic Resource Service](../../../../docs/framework/wcf/samples/basic-resource-service.md) 샘플이이 시나리오의 자체 호스팅된 버전을 표시 하 고 심층에서 서비스 구현에 설명 합니다. 이 항목에서는 ASP.NET 통합 기능을 중점적으로 설명합니다. ASP.NET 라우팅에 대 한 자세한 내용은 참조 <xref:System.Web.Routing>합니다.  
  
## <a name="sample-details"></a>샘플 세부 정보  
 WCF 서비스는 리소스 지향/REST 방식으로 고객 컬렉션을 노출 합니다. SOAP 기반 WCF 서비스와 마찬가지로 서비스는.svc 파일을 사용 하 여 ASP.NET에서 호스팅할 수 있습니다. 그러나 서비스에 대한 URL에 .svc를 포함해야 하므로 HTTP 시나리오의 경우에는 이 서비스가 적절하지 않을 수도 있습니다. 또한 .svc 파일을 서비스 라이브러리와 함께 배포해야 합니다. 이 샘플에서와 같이 ASP.NET 경로를 사용하여 서비스를 호스팅하면 이러한 제한을 피할 수 있습니다.  
  
 이 샘플에서는 Global.asax 파일에 <xref:System.ServiceModel.Activation.ServiceRoute>를 추가하여 ASP.NET에서 서비스를 호스팅합니다. <xref:System.ServiceModel.Activation.ServiceRoute>는 서비스 유형(이 경우 ‘Service’), 서비스에 사용할 서비스 호스트 팩터리의 유형(이 경우 <xref:System.ServiceModel.Activation.WebServiceHostFactory>) 및 서비스의 HTTP 기본 주소(이 경우 ‘~/Customers’)를 지정합니다.  
  
 또한 이 샘플에는 <xref:System.Web.Routing.UrlRoutingModule>을 추가하여 ASP.NET 경로를 설정하는 Web.config와 서비스에 대한 구성이 포함되어 있습니다. 구성 기본값 WCF 서비스를 구성 하는 특히 <xref:System.ServiceModel.Description.WebHttpEndpoint> 있는 <xref:System.ServiceModel.Description.WebHttpEndpoint.HelpEnabled%2A> 설정을 `true`합니다. WCF 인프라가 자동 HTML 기반 도움말 페이지를 만듭니다. 결과적으로, `http://localhost/Customers/help` 방법의 예제에서 서비스 및 서비스의 HTTP 응답-예를 들어, 액세스 하는 방법을 요청 HTTP를 생성 하는 방법에 대 한 정보를 제공 하는 고객 세부 정보는 XML 또는 JSON으로 표현 됩니다.  
  
 이러한 방식으로 고객 컬렉션(보다 일반적으로는 모든 리소스)을 노출하면 클라이언트가 URI와 HTTP `GET`, `PUT`, `DELETE` 및 `POST`를 사용하여 일관된 방식으로 서비스와 상호 작용할 수 있습니다.  
  
 Client 프로젝트의 Program.cs에서는 <xref:System.Net.HttpWebRequest>를 사용하여 이러한 클라이언트를 작성하는 방법을 보여 줍니다. 이 방법은 WCF 서비스에 액세스하는 여러 방법 중 하나일 뿐입니다. WCF 채널 팩터리와 같은 다른.NET Framework 클래스를 사용 하 여 서비스에 액세스할 수 이기도 및 <xref:System.Net.WebClient>합니다. SDK의 다른 샘플 (와 같은 [기본 HTTP 서비스](../../../../docs/framework/wcf/samples/basic-http-service.md) 샘플 및 [선택 영역 자동 서식](../../../../docs/framework/wcf/samples/automatic-format-selection.md) 샘플) WCF 서비스와 통신 하도록 이러한 클래스를 사용 하는 방법을 보여 줍니다.  
  
 이 샘플은 다음의 세 프로젝트로 구성되어 있습니다.  
  
 서비스  
 ASP.NET에서 호스팅되는 WCF HTTP 서비스가 포함된 웹 응용 프로그램 프로젝트입니다.  
  
 클라이언트  
 서비스를 호출하는 콘솔 응용 프로그램 프로젝트입니다.  
  
 Common  
 클라이언트 및 서비스에서 사용되는 `Customer` 형식이 포함된 공유 라이브러리입니다. 클라이언트 콘솔 응용 프로그램이 실행되면 클라이언트에서는 서비스로 요청을 보내고 응답의 관련 정보를 콘솔 창에 씁니다.  
  
#### <a name="to-use-this-sample"></a>이 샘플을 사용하려면  
  
1.  [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]에서 ASP.NET Routes Integration 샘플의 솔루션을 엽니다.  
  
2.  Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.  
  
3.  열려 있지 않으면 "CTRL + W, S"을 눌러 열려는 **솔루션 탐색기** 창.  
  
4.  **솔루션 탐색기** 창을 마우스 오른쪽 단추로 클릭는 **서비스** 프로젝트 및 위에 커서를 놓으면는 **디버그** 상황에 맞는 메뉴 옵션 있도록는 **시작 새 인스턴스** 상황에 맞는 메뉴에 표시 되 고 선택 **새 인스턴스 시작**합니다.  그러면 ASP.NET Development Server가 시작되어 서비스를 호스트합니다.  
  
5.  **솔루션 탐색기** 창을 마우스 오른쪽 단추로 클릭는 **클라이언트** 프로젝트 및 위에 커서를 놓으면는 **디버그** 상황에 맞는 메뉴 옵션 있도록는 **새 시작 인스턴스** 상황에 맞는 메뉴에 표시 되 고 선택 **새 인스턴스 시작**합니다.  
  
6.  클라이언트 콘솔 창이 나타나고 실행 중인 서비스의 URI와 실행 중인 서비스에 대한 HTML 도움말 페이지의 URI가 제공됩니다. 언제든지 브라우저에서 HTML 도움말 페이지의 URI를 입력하면 해당 도움말 페이지를 볼 수 있습니다. 샘플이 실행되면 클라이언트에서는 현재 활동의 상태를 씁니다.  
  
7.  아무 키나 눌러 클라이언트 콘솔 응용 프로그램을 종료합니다.  
  
8.  Shift + f 5를 눌러 서비스 디버깅을 중지 하 고 Windows 알림 영역에서 ASP.NET 개발 서버 아이콘을 마우스 오른쪽 단추로 선택한 **중지** 상황에 맞는 메뉴입니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\AspNetRouteIntegration`  
  
## <a name="see-also"></a>참고 항목
