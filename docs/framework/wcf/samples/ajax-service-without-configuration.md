---
title: 구성을 사용하지 않고 AJAX 서비스 만들기
ms.date: 03/30/2017
ms.assetid: e6db7acd-5679-45d4-b98a-8449c6873838
ms.openlocfilehash: 53a0de88d08fbc12cb8861042a50da6503fa5def
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="ajax-service-without-configuration"></a>구성을 사용하지 않고 AJAX 서비스 만들기
이 샘플에서는 구성을 사용 하지 않고 기본 ASP.NET Asynchronous JavaScript and XML (AJAX) 서비스 (웹 브라우저 클라이언트에서 JavaScript 코드를 사용 하 여 액세스할 수 있는 서비스)를 만들려면 Windows Communication Foundation (WCF)를 사용 하는 방법을 보여 줍니다. 설정. 이 서비스는 .svc 파일의 특수한 구문을 사용하여 AJAX 끝점을 사용하도록 자동으로 설정합니다.  
  
 Wcf에서 AJAX 지원을 통해 ASP.NET AJAX와 함께 사용 되도록 최적화 되었습니다는 `ScriptManager` 제어 합니다. ASP.NET AJAX와 함께 WCF를 사용 하는 예제를 참조 하십시오.는 [Ajax 샘플과](http://msdn.microsoft.com/library/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e)합니다.  
  
> [!NOTE]
>  이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.  
  
 이 샘플은 AJAX Service Using HTTP POST를 기반으로 합니다. 에 설명 된 대로 [기본 AJAX 서비스](../../../../docs/framework/wcf/samples/basic-ajax-service.md) 샘플에서 <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> 서비스를 호스트 하는 데 사용 됩니다.  

```svc
<%ServiceHost  
    language=c#  
    Debug="true"  
    Service="Microsoft.Ajax.Samples.CalculatorService  
    Factory="System.ServiceModel.Activation.WebScriptServiceHostFactory"  
%>  
```

 <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>가 자동으로 <xref:System.ServiceModel.Description.WebScriptEndpoint>를 서비스에 추가합니다. 끝점에 대한 구성 변경이 필요하지 않은 경우 서비스에 대한 Web.config 파일에서 `<system.ServiceModel>` 섹션을 완전히 제거할 수 있습니다. Web.config 파일에는 ConfigFreeClientPage.aspx에 사용되는 몇 가지 ASP.NET 설정이 포함되어 있습니다. 그렇지 않은 경우 전체 Web.config 파일을 제거할 수 있습니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\ConfigFreeAjaxService`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1.  설치 지침을 수행 하도록 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.  
  
2.  에 설명 된 대로 ConfigFreeAjaxService.sln 솔루션을 구축 [Windows Communication Foundation 샘플 빌드](../../../../docs/framework/wcf/samples/building-the-samples.md)합니다.  
  
3.  로 이동 http://localhost/ServiceModelSamples/ConfigFreeClientPage.aspx (열지 마세요 프로젝트 디렉터리 내에서 브라우저에서).  
  
> [!NOTE]
>  이 샘플을 실행할 때 IIS의 ServiceModelSamples 폴더에 대해 익명 인증 및 Windows 인증을 동시에 사용하도록 설정되지 않았는지 확인하세요. 두 인증이 동시에 사용하도록 설정되어 있는 경우에는 Windows 인증을 비활성화하세요. 샘플을 실행한 다음 Windows 인증을 사용하도록 설정하고 "iisreset"를 실행합니다.  
  
## <a name="see-also"></a>참고 항목  
 [기본 AJAX 서비스](../../../../docs/framework/wcf/samples/basic-ajax-service.md)
