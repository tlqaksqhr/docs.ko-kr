---
title: 기본 HTTP 서비스
ms.date: 03/30/2017
ms.assetid: 27048b43-8a54-4f2a-9952-594bbfab10ad
ms.openlocfilehash: 0f93b43a08f586e99d8a49379cfb2e283ff7918d
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33808860"
---
# <a name="basic-http-service"></a>기본 HTTP 서비스
이 샘플에는 많이 Windows Communication Foundation (WCF) REST 프로그래밍 모델을 사용 하 여 "POX" (Plain Old XML) 서비스 라고 하는 HTTP 기반, RPC 기반 서비스를 구현 하는 방법을 보여 줍니다. 이 샘플은 두 가지 구성 요소로 구성 됩니다.: 자체 호스팅된 WCF HTTP 서비스 (Service.cs)와 서비스를 만들고를 호출 하는 콘솔 응용 프로그램 (Program.cs).  
  
## <a name="sample-details"></a>샘플 세부 정보  
 WCF 서비스에는 두 가지 작업을 노출 `EchoWithGet` 및 `EchoWithPost`, 입력으로 전달 된 문자열을 반환 하는 합니다.  
  
 `EchoWithGet` 작업에는 <xref:System.ServiceModel.Web.WebGetAttribute>가 주석으로 추가되어 있어 해당 작업이 HTTP `GET` 요청을 처리함을 나타냅니다. <xref:System.ServiceModel.Web.WebGetAttribute>는 <xref:System.UriTemplate>을 명시적으로 지정하지 않으므로 이 작업을 위해서는 이름이 `s`인 쿼리 문자열 매개 변수를 사용하여 입력 문자열을 전달해야 합니다. 서비스에 필요한 URI 형식은 <xref:System.ServiceModel.Web.WebGetAttribute.UriTemplate%2A> 속성을 사용하여 사용자 지정할 수 있습니다.  
  
 `EchoWithPost` 작업에는 <xref:System.ServiceModel.Web.WebInvokeAttribute>가 주석으로 추가되어 있어 해당 작업이 `GET` 작업이 아니며 의도하지 않은 결과가 발생함을 나타냅니다. <xref:System.ServiceModel.Web.WebInvokeAttribute>는 `Method`를 명시적으로 지정하지 않으므로 이 작업은 XML 형식과 같이 요청 본문에 문자열이 있는 HTTP `POST` 요청을 처리합니다. 요청에 대한 HTTP 메서드 및 URI 형식은 각각 <xref:System.ServiceModel.Web.WebInvokeAttribute.Method%2A> 및 <xref:System.ServiceModel.Web.WebInvokeAttribute.UriTemplate> 속성을 사용하여 사용자 지정할 수 있습니다.  
  
 App.config 파일은 <xref:System.ServiceModel.Description.WebHttpEndpoint> 속성이 <xref:System.ServiceModel.Description.WebHttpEndpoint.HelpEnabled%2A>로 설정된 기본 `true`로 WCF 서비스를 구성합니다. WCF 인프라가 자동 HTML 기반 도움말 페이지를 만듭니다. 결과적으로, `http://localhost:8000/Customers/help` 서비스에 대 한 HTTP 요청을 생성 하는 방법 및 서비스의 HTTP 응답을 사용 하는 방법에 대 한 정보를 제공 하 합니다.  
  
 Program.cs 서비스 및 프로세스 응답을 호출 하는 WCF 채널 팩터리를 사용할 수 있는 방법을 보여 줍니다. 이 방법은 WCF 서비스에 액세스하는 여러 방법 중 하나일 뿐입니다. <xref:System.Net.HttpWebRequest> 및 <xref:System.Net.WebClient> 같은 다른 .NET Framework 클래스를 사용하여 서비스에 액세스할 수도 있습니다. SDK의 다른 샘플 (와 같은 [선택 영역 자동 서식](../../../../docs/framework/wcf/samples/automatic-format-selection.md) 샘플 및 [Basic Resource Service](../../../../docs/framework/wcf/samples/basic-resource-service.md) 샘플) WCF 서비스와 통신 하도록 이러한 클래스를 사용 하는 방법을 보여 줍니다.  
  
 이 샘플은 콘솔 응용 프로그램 내에서 실행되는 자체 호스팅 서비스와 클라이언트로 구성되어 있습니다. 콘솔 응용 프로그램이 실행되면 클라이언트에서는 서비스로 요청을 보내고 응답의 관련 정보를 콘솔 창에 씁니다.  
  
#### <a name="to-use-this-sample"></a>이 샘플을 사용하려면  
  
1.  Basic Http Service 샘플의 솔루션을 엽니다. 관리자 권한으로 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]을 시작해야 샘플이 제대로 실행됩니다. 마우스 오른쪽 단추로 클릭 하 여이 작업을 수행는 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 아이콘을 선택 하면 **관리자 권한으로 실행** 상황에 맞는 메뉴입니다.  
  
2.  Ctrl+Shift+B를 눌러 솔루션을 빌드한 다음 Ctrl+F5를 눌러 디버깅하지 않고 콘솔 응용 프로그램을 실행합니다. 콘솔 창이 나타나고 실행 중인 서비스의 URI와 실행 중인 서비스에 대한 HTML 도움말 페이지의 URI가 제공됩니다. 언제든지 브라우저에서 HTML 도움말 페이지의 URI를 입력하면 해당 도움말 페이지를 볼 수 있습니다. 샘플이 실행되면 클라이언트에서는 현재 활동의 상태를 씁니다.  
  
3.  아무 키나 눌러 샘플을 종료합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\BasicHttpService`  
  
## <a name="see-also"></a>참고 항목  
 [자동 포맷 선택](../../../../docs/framework/wcf/samples/automatic-format-selection.md)  
 [기본 리소스 서비스](../../../../docs/framework/wcf/samples/basic-resource-service.md)
