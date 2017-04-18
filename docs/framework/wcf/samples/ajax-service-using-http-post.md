---
title: "AJAX Service Using HTTP POST | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1ac80f20-ac1c-4ed1-9850-7e49569ff44e
caps.latest.revision: 28
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 28
---
# AJAX Service Using HTTP POST
이 샘플에서는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]를 사용하여 HTTP POST를 사용하는 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] AJAX\(Asynchronous JavaScript and XML\) 서비스를 만드는 방법을 보여 줍니다. AJAX 서비스는 웹 브라우저 클라이언트에서 기본 JavaScript 코드를 사용하여 액세스할 수 있는 서비스입니다. 이 샘플은 [Basic AJAX Service](../../../../docs/framework/wcf/samples/basic-ajax-service.md) 샘플 위에 빌드되며, 두 샘플 사이의 차이는 HTTP GET 대신 HTTP POST를 사용한다는 것뿐입니다.  
  
 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]의 AJAX 지원은 `ScriptManager` 컨트롤을 통해 ASP.NET AJAX와 함께 사용되도록 최적화되었습니다. ASP.NET AJAX와 함께 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]를 사용한 예제를 보려면 [Ajax Samples](../../../../docs/framework/wcf/samples/ajax-service-using-http-post.md)을 참조하세요.  
  
> [!NOTE]
>  이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.  
  
 다음 샘플의 서비스는 AJAX 특정 코드가 없는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스입니다.  
  
 작업에 <xref:System.ServiceModel.Web.WebInvokeAttribute> 특성이 적용되거나 <xref:System.ServiceModel.Web.WebGetAttribute> 특성이 적용되지 않은 경우에는 기본 HTTP 동사\("POST"\)가 사용됩니다. POST 요청이 GET 요청보다 구성하기 어렵지만 해당 요청은 캐시되지 않습니다. 캐싱이 적절하지 않은 모든 작업에 POST 요청을 사용하십시오.  
  
```  
[ServiceContract(Namespace = "PostAjaxService")]  
    public interface ICalculator  
    {        [WebInvoke]  
        double Add(double n1, double n2);  
        //Other operations omitted…  
    }  
  
```  
  
 기본 AJAX 서비스 샘플에서와 마찬가지로, <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>를 사용하여 서비스에 AJAX 끝점을 만듭니다.  
  
 GET 요청과 달리 브라우저에서 POST 서비스를 호출할 수는 없습니다. 예를 들어 http:\/\/localhost\/ServiceModelSamples\/service.svc\/Add?n1\=100&n2\=200으로 이동하면 POST 서비스에서는 URL이 아닌 메시지 본문에 JSON 형식의 `n1` 및 `n2` 매개 변수를 전송해야 하기 때문에 오류가 발생합니다.  
  
 클라이언트 웹 페이지 PostAjaxClientPage.aspx에는 사용자가 페이지에 있는 작업 단추 중 하나를 클릭할 때마다 서비스를 호출하는 ASP.NET 코드가 포함되어 있습니다. 서비스는 GET 요청을 사용하여 [Basic AJAX Service](../../../../docs/framework/wcf/samples/basic-ajax-service.md) 샘플과 동일한 방식으로 응답합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음\(기본\) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [.NET Framework 4용 WCF\(Windows Communication Foundation\) 및 WF\(Windows Workflow Foundation\) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780)로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\PostAjaxService`  
  
#### 샘플을 설치, 빌드 및 실행하려면  
  
1.  [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) 설치 지침을 수행했는지 확인합니다.  
  
2.  [Windows Communication Foundation 샘플 빌드](../../../../docs/framework/wcf/samples/building-the-samples.md)에 설명된 대로 PostAjaxService.sln 솔루션을 빌드합니다.  
  
3.  http:\/\/localhost\/ServiceModelSamples\/PostAjaxClientPage.aspx로 이동합니다. 브라우저의 프로젝트 디렉터리에서 PostAjaxClientPage.aspx를 열지 마십시오.  
  
## 참고 항목