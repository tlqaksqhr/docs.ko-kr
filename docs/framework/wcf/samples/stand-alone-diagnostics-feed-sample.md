---
title: "독립형 진단 피드 샘플"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d31c6c1f-292c-4d95-8e23-ed8565970ea5
caps.latest.revision: "26"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 89de6bcbb44ca70592697ccf891099446b230ce6
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="stand-alone-diagnostics-feed-sample"></a>독립형 진단 피드 샘플
이 샘플에서는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]를 사용하여 배포를 위한 RSS/ATOM 피드를 만드는 방법을 보여 줍니다. 기본 "Hello World" 프로그램에서는 개체 모델의 기본 사항 및 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 서비스에 이 프로그램을 설정하는 방법을 보여 줍니다.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 모델 배포는 특수 데이터 형식인 <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter>를 반환하는 서비스 작업으로 제공됩니다. <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter>의 인스턴스는 피드를 RSS 2.0 및 ATOM 1.0 형식으로 serialize할 수 있습니다. 다음 샘플 코드에서는 사용된 계약을 보여 줍니다.  
  
```  
[ServiceContract(Namespace = "")]  
    interface IDiagnosticsService  
    {  
        [OperationContract]  
        //The [WebGet] attribute controls how WCF dispatches  
        //HTTP requests to service operations based on a URI suffix  
        //(the part of the request URI after the endpoint address)  
        //using the HTTP GET method. The UriTemplate specifies a relative  
        //path of 'feed', and specifies that the format is  
        //supplied using a query string.   
        [WebGet(UriTemplate="feed?format={format}")]  
        [ServiceKnownType(typeof(Atom10FeedFormatter))]  
        [ServiceKnownType(typeof(Rss20FeedFormatter))]  
        SyndicationFeedFormatter GetProcesses(string format);  
    }  
```  
  
 `GetProcesses`가 서비스 작업에 HTTP GET 요청을 디스패치하는 방법을 제어하고 보낸 메시지 형식을 지정할 수 있도록 하는 <xref:System.ServiceModel.Web.WebGetAttribute> 특성을 사용하여 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 작업에 주석을 추가합니다.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스처럼 배포 피드는 관리되는 응용 프로그램에서 자체 호스트될 수 있습니다. 배포 서비스가 제대로 작동하려면 특정 바인딩(<xref:System.ServiceModel.WebHttpBinding>) 및 특정 끝점 동작(<xref:System.ServiceModel.Description.WebHttpBehavior>)이 필요합니다. 새 <xref:System.ServiceModel.Web.WebServiceHost> 클래스는 특정 구성 없이 이러한 끝점을 만들기 위해 다음과 같이 편리한 API를 제공합니다.  
  
```  
WebServiceHost host = new WebServiceHost(typeof(ProcessService), new Uri("http://localhost:8000/diagnostics"));  
  
            //The WebServiceHost will automatically provide a default endpoint at the base address  
            //using the proper binding (the WebHttpBinding) and endpoint behavior (the WebHttpBehavior)  
```  
  
 또는 IIS에서 호스트되는 .svc 파일 내에서 <xref:System.ServiceModel.Activation.WebServiceHostFactory>를 사용하여 동일한 기능을 제공할 수 있습니다(이 방법은 샘플 코드에서 설명하지 않음).  
  
```  
<%@ ServiceHost Language="C#|VB" Debug="true" Service="ProcessService" %>  
```  
  
 이 서비스는 표준 HTTP GET을 사용하여 요청을 받기 때문에 RSS 또는 ATOM 인식 클라이언트를 사용하여 서비스에 액세스할 수 있습니다. 예를 들어, Internet Explorer 7과 같은 RSS 인식 브라우저에서 http://localhost:8000/diagnostics/feed/?format=atom 또는 http://localhost:8000/diagnostics/feed/?format=rss로 이동하면 이 서비스의 출력을 볼 수 있습니다.  
  
 사용할 수도 있습니다는 [어떻게 the WCF 배포 개체 모델에 매핑됩니다 Atom 및 RSS](../../../../docs/framework/wcf/feature-details/how-the-wcf-syndication-object-model-maps-to-atom-and-rss.md) 존재 하지 않는 배포 된 데이터를 읽고 명령적 코드를 사용 하 여 처리 합니다.  
  
```  
XmlReader reader = XmlReader.Create( "http://localhost:8000/diagnostics/feed/?format=rss",  
new XmlReaderSettings()  
{  
//MaxCharactersInDocument can be used to control the maximum amount of data   
//read from the reader and helps prevent OutOfMemoryException  
MaxCharactersInDocument = 1024 * 64  
} );  
  
SyndicationFeed feed = SyndicationFeed.Load( reader );  
  
foreach (SyndicationItem i in feed.Items)  
{  
        XmlSyndicationContent content = i.Content as XmlSyndicationContent;  
        ProcessData pd = content.ReadContent<ProcessData>();  
  
        Console.WriteLine(i.Title.Text);  
        Console.WriteLine(pd.ToString());  
}  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1.  설정의 지침에 설명 된 대로 가졌는지 컴퓨터에서 HTTP 및 HTTPS에 대 한 올바른 주소 등록 권한을 확인 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.  
  
2.  솔루션을 빌드합니다.  
  
3.  콘솔 응용 프로그램을 실행합니다.  
  
4.  콘솔 응용 프로그램을 실행하는 동안 RSS 인식 브라우저를 사용하여 http://localhost:8000/diagnostics/feed/?format=atom 또는 http://localhost:8000/diagnostics/feed/?format=rss로 이동합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Syndication\DiagnosticsFeed`  
  
## <a name="see-also"></a>참고 항목  
 [WCF 웹 HTTP 프로그래밍 모델](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)  
 [WCF 배포](../../../../docs/framework/wcf/feature-details/wcf-syndication.md)
