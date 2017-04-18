---
title: "Windows Communication Foundation과 함께 사용하도록 Windows Process Activation Service 구성 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1d50712e-53cd-4773-b8bc-a1e1aad66b78
caps.latest.revision: 12
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 12
---
# Windows Communication Foundation과 함께 사용하도록 Windows Process Activation Service 구성
이 항목에서는 [!INCLUDE[wv](../../../../includes/wv-md.md)]에서 HTTP 네트워크 프로토콜을 통해 통신하지 않는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 서비스를 호스팅하도록 WAS라고도 하는 Windows Process Activation Service를 설정하는 데 필요한 단계에 대해 설명합니다.다음 단원에서는 이 구성 단계에 대해 간략히 설명합니다.  
  
-   필요한 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 활성화 구성 요소를 설치하거나 설치를 확인합니다.  
  
-   사용할 네트워크 프로토콜 바인딩으로 WAS 사이트를 만들거나 새 프로토콜 바인딩을 기존 사이트에 추가합니다.  
  
-   서비스를 호스팅할 응용 프로그램을 만들고 이 응용 프로그램에서 필요한 네트워크 프로토콜을 사용하도록 설정합니다.  
  
-   HTTP가 아닌 끝점을 노출하는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스를 빌드합니다.  
  
## HTTP가 아닌 바인딩을 사용하여 사이트 구성  
 WAS에 HTTP가 아닌 바인딩을 사용하려면 사이트 바인딩을 WAS 구성에 추가해야 합니다.WAS에 대한 구성 저장소는 %windir%\\system32\\inetsrv\\config 디렉터리에 있는 applicationHost.config 파일입니다.WAS와 IIS 7.0에서 이 구성 저장소를 공유합니다.  
  
 applicationHost.config는 메모장과 같은 표준 텍스트 편집기에서 열 수 있는 XML 텍스트 파일입니다.그러나 주로 [!INCLUDE[iisver](../../../../includes/iisver-md.md)] 명령줄 구성 도구\(appcmd.exe\)를 사용하여 HTTP가 아닌 사이트 바인딩을 추가합니다.  
  
 다음 명령은 appcmd.exe\(이 명령은 한 줄로 입력됨\)를 사용하여 net.tcp 사이트 바인딩을 기본 웹 사이트에 추가합니다.  
  
```  
appcmd.exe set site "Default Web Site" -+bindings.[protocol='net.tcp',bindingInformation='808:*']  
```  
  
 이 명령은 applicationHost.config 파일에 아래 표시된 줄을 추가하여 새 net.tcp 바인딩을 기본 웹 사이트에 추가합니다.  
  
```  
<sites>  
    <site name="Default Web Site" id="1">  
        <bindings>  
            <binding protocol="HTTP" bindingInformation="*:80:" />  
            //The following line is added by the command.  
            <binding protocol="net.tcp" bindingInformation="808:*" />  
        </bindings>  
    </site>  
</sites>  
```  
  
## HTTP가 아닌 프로토콜을 사용하도록 응용 프로그램 설정  
 응용 프로그램 수준에서 개별 네트워크 프로토콜을 사용하거나 사용하지 않도록 설정할 수 있습니다.다음 명령은 `Default Web Site`에서 실행되는 응용 프로그램에 대한 HTTP 및 net.tcp 프로토콜을 모두 사용하도록 설정하는 방법을 보여 줍니다.  
  
```  
appcmd.exe set app "Default Web Site/appOne" /enabledProtocols:net.tcp  
```  
  
 설정된 프로토콜의 목록은 ApplicationHost.config에 저장된 사이트의 XML 구성에 있는 \<applicationDefaults\> 요소에서도 설정할 수 있습니다.  
  
 applicationHost.config의 다음과 같은 XML 코드는 HTTP 프로토콜 및 HTTP가 아닌 프로토콜에 모두 바인딩되는 사이트를 보여 줍니다.HTTP가 아닌 프로토콜을 지원하는 데 필요한 추가 구성은 주석으로 호출됩니다.  
  
```  
<sites>  
    <site name="Default Web Site" id="1">  
    <application path="/">  
        <virtualDirectory path="/" physicalPath="D:\inetpub\wwwroot" />  
    </application>  
       <bindings>  
            //The following two lines are added by the command.  
            <binding protocol="HTTP" bindingInformation="*:80:" />  
            <binding protocol="net.tcp" bindingInformation="808:*" />  
       </bindings>  
    </site>  
    <siteDefaults>  
        <logFile   
        customLogPluginClsid="{FF160663-DE82-11CF-BC0A-00AA006111E0}"  
          directory="D:\inetpub\logs\LogFiles" />  
        <traceFailedRequestsLogging   
          directory="D:\inetpub\logs\FailedReqLogFiles" />  
    </siteDefaults>  
    <applicationDefaults   
      applicationPool="DefaultAppPool"   
      //The following line is inserted by the command.  
      enabledProtocols="http, net.tcp" />  
    <virtualDirectoryDefaults allowSubDirConfig="true" />  
</sites>  
```  
  
 WAS를 설치 및 구성하지 않은 상태에서 WAS for Non\-HTTP Activation을 사용하여 서비스를 활성화하려고 하면 다음 오류가 나타날 수 있습니다.  
  
```Output  
[InvalidOperationException: 'net.tcp' 프로토콜에 HostedTransportConfiguration 형식이 등록된 구현이 없습니다.]   System.ServiceModel.AsyncResult.End(IAsyncResult result) +15778592   System.ServiceModel.Activation.HostedHttpRequestAsyncResult.End(IAsyncResult 결과) +15698937   System.ServiceModel.Activation.HostedHttpRequestAsyncResult.ExecuteSynchronous(HttpApplication context, Boolean flowContext) +265   System.ServiceModel.Activation.HttpModule.ProcessRequest(Object sender, EventArgs e) +227   System.Web.SyncEventExecutionStep.System.Web.HttpApplication.IExecutionStep.Execute() +80   System.Web.HttpApplication.ExecuteStep(IExecutionStep step, Boolean& completedSynchronously) +171  
```  
  
 이 오류가 표시되는 경우 WAS for Non\-HTTP Activation을 올바르게 설치하고 구성하십시오.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][방법: WCF Activation 구성 요소 설치 및 구성](../../../../docs/framework/wcf/feature-details/how-to-install-and-configure-wcf-activation-components.md).  
  
## 비 HTTP 활성화에 WAS를 사용하는 WCF 서비스 빌드  
 WAS를 설치 및 구성하는 단계를 수행한 후\([방법: WCF Activation 구성 요소 설치 및 구성](../../../../docs/framework/wcf/feature-details/how-to-install-and-configure-wcf-activation-components.md) 참조\) 활성화에 WAS를 사용하도록 서비스를 구성하는 것은 IIS에서 호스팅되는 서비스를 구성하는 것과 유사합니다.  
  
 WAS가 활성화된 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스 빌드에 대한 자세한 내용은 [방법: WAS에서 WCF 서비스 호스팅](../../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-was.md)을 참조하십시오.  
  
## 참고 항목  
 [Windows Process Activation Service에서의 호스팅](../../../../docs/framework/wcf/feature-details/hosting-in-windows-process-activation-service.md)   
 [Windows Server AppFabric 호스팅 기능](http://go.microsoft.com/fwlink/?LinkId=201276)