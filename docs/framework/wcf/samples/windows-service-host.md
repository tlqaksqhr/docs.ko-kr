---
title: "Windows Service Host | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "NT 서비스"
  - "NT Service Host 샘플 [Windows Communication Foundation]"
ms.assetid: 1b2f45c5-2bed-4979-b0ee-8f9efcfec028
caps.latest.revision: 40
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 40
---
# Windows Service Host
이 샘플에서는 관리되는 Windows 서비스에서 호스팅되는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 서비스를 보여 줍니다.Windows 서비스는 **제어판**에서 서비스 애플릿을 사용하여 제어하며 시스템을 다시 부팅한 후에 자동으로 시작되도록 구성할 수 있습니다.이 샘플은 클라이언트 프로그램과 Windows 서비스 프로그램으로 구성됩니다.서비스는 .exe 프로그램으로 구현되고 자체 호스팅 코드가 포함됩니다.WAS\(Windows Process Activation Services\) 또는 IIS\(인터넷 정보 서비스\) 등의 다른 호스팅 환경에서는 직접 호스팅 코드를 작성할 필요가 없습니다.  
  
> [!NOTE]
>  이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.계속하기 전에 다음\(기본\) 디렉터리를 확인하십시오.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780)로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하십시오.이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WindowsService`  
  
 이 서비스를 빌드한 후에는 다른 Windows 서비스와 마찬가지로 Installutil.exe 유틸리티로 설치해야 합니다.서비스를 변경하려는 경우에는 먼저 `installutil /u`를 사용하여 제거해야 합니다.이 샘플에 포함된 Setup.bat 및 Cleanup.bat 파일은 Windows 서비스를 설치 및 시작하기 위한 명령과 Windows 서비스를 종료 및 제거하기 위한 명령입니다.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스는 Windows 서비스가 실행 중인 경우에만 클라이언트에 응답할 수 있습니다.**제어판**에서 서비스 애플릿을 사용하여 Windows 서비스를 중지하고 클라이언트를 실행하면 클라이언트에서 서비스에 액세스를 시도할 때 <xref:System.ServiceModel.EndpointNotFoundException> 예외가 발생합니다.Windows 서비스를 다시 시작하고 클라이언트를 다시 실행하면 통신이 성공합니다.  
  
 서비스 코드에는 ICalculator 계약을 구현하는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스 구현 클래스인 설치 관리자 클래스와 런타임 호스트 역할을 하는 Windows 서비스 클래스가 포함됩니다.<xref:System.Configuration.Install.Installer>에서 상속되는 설치 관리자 클래스를 사용하면 프로그램을 Installutil.exe 도구를 통해 NT 서비스로 설치할 수 있습니다.서비스 구현 클래스인 `WcfCalculatorService`는 기본 서비스 계약을 구현하는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스입니다.이 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스는 `WindowsCalculatorService`라는 Windows 서비스 클래스 내에서 호스팅됩니다.Windows 서비스로 정규화하기 위해 클래스가 <xref:System.ServiceProcess.ServiceBase>에서 상속되고 [OnStart\(String\<xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29> 및 <xref:System.ServiceProcess.ServiceBase.OnStop> 메서드를 구현합니다.[OnStart\(String\<xref:System.ServiceProcess.ServiceBase.OnStart%28System.String%5B%5D%29>에서 <xref:System.ServiceModel.ServiceHost> 개체가 `WcfCalculatorService` 형식에 대해 만들어지고 열립니다.<xref:System.ServiceProcess.ServiceBase.OnStop>에서 ServiceHost는 <xref:System.ServiceModel.ServiceHost> 개체의 <xref:System.ServiceModel.Channels.CommunicationObject.Close%28System.TimeSpan%29> 메서드를 호출하여 닫습니다.호스트의 기본 주소는 [\<add\>](../../../../docs/framework/configure-apps/file-schema/wcf/add-of-baseaddresses.md) 요소를 사용하여 구성됩니다. 해당 요소는 [\<service\>](../../../../docs/framework/configure-apps/file-schema/wcf/service.md)의 자식인 [\<host\>](../../../../docs/framework/configure-apps/file-schema/wcf/host.md)의 자식인 [\<baseAddresses\>](../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md)의 자식입니다.  
  
 정의된 끝점에서는 기본 주소와 [\<wsHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)를 사용합니다.다음 샘플에서는 CalculatorService를 노출시키는 끝점과 기본 주소의 구성을 보여 줍니다.  
  
```  
<services>  
  <service name="Microsoft.ServiceModel.Samples.WcfCalculatorService"  
           behaviorConfiguration="CalculatorServiceBehavior">  
    <host>  
      <baseAddresses>  
        <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>  
      </baseAddresses>  
    </host>  
    <!-- This endpoint is exposed at the base address provided by host: http://localhost:8000/ServiceModelSamples/service.  -->  
    <endpoint address=""  
              binding="wsHttpBinding"  
              contract="Microsoft.ServiceModel.Samples.ICalculator" />  
    ...  
  </service>  
</services>  
  
```  
  
 샘플을 실행하면 작업 요청 및 응답이 서비스와 클라이언트 콘솔 창 모두에 표시됩니다.서비스와 클라이언트를 종료하려면 각 콘솔 창에서 Enter 키를 누릅니다.  
  
### 샘플을 설치, 빌드 및 실행하려면  
  
1.  [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)를 수행했는지 확인합니다.  
  
2.  C\# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Windows Communication Foundation 샘플 빌드](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.  
  
3.  솔루션이 빌드되고 나면 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]의 관리자 권한 명령 프롬프트에서 Setup.bat를 실행하여 Installutil.exe 도구로 Windows 서비스를 설치합니다.서비스가 서비스에 표시됩니다.  
  
4.  단일 컴퓨터 또는 다중 컴퓨터 구성에서 샘플을 실행하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)의 지침을 따릅니다.  
  
## 참고 항목  
 [AppFabric 호스팅 및 지속성 샘플](http://go.microsoft.com/fwlink/?LinkId=193961)