---
title: SOAP 및 HTTP 끝점
ms.date: 03/30/2017
ms.assetid: e3c8be75-9dda-4afa-89b6-a82cb3b73cf8
ms.openlocfilehash: 4c8a4695dbcaee2f0e7584418fbeac12815fa967
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33809520"
---
# <a name="soap-and-http-endpoints"></a>SOAP 및 HTTP 끝점
이 샘플에는 RPC 기반 서비스를 구현 하 고 SOAP 형식 및 WCF 웹 프로그래밍 모델을 사용 하 여 "Plain Old XML" (POX) 형식에 노출 하는 방법을 보여 줍니다. 참조는 [기본 HTTP 서비스](../../../../docs/framework/wcf/samples/basic-http-service.md) 서비스에 대 한 HTTP 바인딩에 대 한 자세한 내용은 샘플입니다. 이 샘플에서는 서로 다른 바인딩을 사용하는 SOAP 및 HTTP를 통해 동일한 서비스를 노출하는 데 관련된 세부 정보를 중점적으로 다룹니다.  
  
## <a name="demonstrates"></a>세부 항목  
 SOAP 및 WCF를 사용 하 여 HTTP를 통한 RPC 서비스를 노출 합니다.  
  
## <a name="discussion"></a>토론  
 이 샘플은 두 가지 구성 요소로 구성 되어: WCF 서비스와 SOAP 및 HTTP 바인딩을 사용 하 여 서비스 작업을 호출 하는 콘솔 응용 프로그램 (클라이언트)를 포함 하는 웹 응용 프로그램 프로젝트 (서비스).  
  
 WCF 서비스에는 두 가지 작업, – 노출`GetData` 및 `PutData` -입력으로 전달 된 문자열을 에코 하 합니다. 서비스 작업에는 <xref:System.ServiceModel.Web.WebGetAttribute> 및<xref:System.ServiceModel.Web.WebInvokeAttribute>가 주석으로 추가됩니다. 이러한 특성은 해당 작업의 HTTP 프로젝션을 제어합니다. 또한 서비스 작업에는 SOAP 바인딩을 통해 노출되도록 설정하는 <xref:System.ServiceModel.OperationContractAttribute>가 주석으로 추가됩니다. 서비스의 `PutData` 메서드는 <xref:System.ServiceModel.Web.WebFaultException>을 throw하며, 이 예외는 HTTP 상태 코드를 사용하여 HTTP를 통해 다시 보내지고 SOAP을 통해 SOAP 오류로 다시 보내집니다.  
  
 Web.config 파일 3 끝점으로 WCF 서비스를 구성 합니다.  
  
-   SOAP 기반 클라이언트에서 액세스할 수 있도록 서비스 메타데이터를 노출하는 ~/service.svc/mex 끝점  
  
-   클라이언트가 HTTP 바인딩을 사용하여 서비스에 액세스할 수 있도록 하는 ~/service.svc/http 끝점  
  
-   클라이언트가 SOAP 및 HTTP 바인딩을 사용하여 서비스에 액세스할 수 있도록 하는 ~/service.svc/soap 끝점  
  
 HTTP 끝점은 `webHttp`가 `helpEnabled`로 설정된 <`true`> 표준 끝점을 사용하여 구성됩니다. 따라서 서비스에서는 HTTP 기반 클라이언트가 서비스에 액세스하는 데 사용할 수 있는 XHTML 기반 도움말 페이지를 ~/service.svc/http/help에 노출합니다.  
  
 클라이언트 프로젝트는 SOAP 프록시를 사용 하 여 서비스에 액세스 하는 방법을 보여 줍니다 (통해 생성 된 **서비스 참조 추가**) 사용 하 여 서비스에 액세스 하 고 <xref:System.Net.WebClient>합니다.  
  
 이 샘플은 웹 호스팅 서비스와 콘솔 응용 프로그램으로 구성되어 있습니다. 콘솔 응용 프로그램이 실행되면 클라이언트에서는 서비스로 요청을 보내고 응답의 관련 정보를 콘솔 창에 씁니다.  
  
#### <a name="to-run-the-sample"></a>이 샘플을 실행하려면  
  
1.  SOAP and HTTP Endpoints 샘플의 솔루션을 엽니다.  
  
2.  Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.  
  
3.  키를 눌러 CTRL + W, S를 열고 열려 있지 않으면는 **솔루션 탐색기** 창.  
  
4.  **솔루션 탐색기** 창에서 마우스 오른쪽 단추로 클릭는 **서비스** 프로젝트 및 위에 커서를 놓으면는 **디버그** 상황에 맞는 메뉴 옵션 있도록는 **새 시작 인스턴스** 상황에 맞는 메뉴가 나타납니다. 클릭 **새 인스턴스 시작**합니다. 그러면 ASP.NET Development Server가 시작되어 서비스를 호스트합니다.  
  
5.  솔루션 탐색기 창에서 클라이언트 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 위에 커서를 놓으면는 **디버그** 상황에 맞는 메뉴 옵션 있도록는 **새 인스턴스 시작** 상황에 맞는 메뉴가 나타납니다. 클릭 **새 인스턴스 시작**합니다.  
  
6.  클라이언트 콘솔 창이 나타나고 실행 중인 서비스의 URI와 실행 중인 서비스에 대한 HTML 도움말 페이지의 URI가 제공됩니다. 언제든지 브라우저에서 HTML 도움말 페이지의 URI를 입력하면 해당 도움말 페이지를 볼 수 있습니다.  
  
7.  샘플이 실행되면 클라이언트에서는 현재 활동의 상태를 씁니다.  
  
8.  아무 키나 눌러 클라이언트 콘솔 응용 프로그램을 종료합니다.  
  
9. Shift+F5를 눌러 서비스 디버깅을 중지합니다.  
  
10. Windows 알림 영역에서 ASP.NET 개발 서버 아이콘을 마우스 오른쪽 단추로 클릭 하 고 선택 **중지** 상황에 맞는 메뉴입니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\SoapAndHttpEndpoints`
