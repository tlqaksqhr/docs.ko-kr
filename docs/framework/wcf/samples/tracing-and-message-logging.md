---
title: "추적 및 메시지 로깅"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Tracing and logging
ms.assetid: a4f39bfc-3c5e-4d51-a312-71c5c3ce0afd
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: cae7d806ce68f6804f97195c9bf2571328af6dff
ms.sourcegitcommit: f28752eab00d2bd97e971542c0f49ce63cfbc239
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2018
---
# <a name="tracing-and-message-logging"></a>추적 및 메시지 로깅
이 샘플에서는 추적 및 메시지 로깅을 사용하도록 설정하는 방법을 보여 줍니다. 결과 추적 및 메시지 로그를 사용 하 여 표시 되는 [Service Trace Viewer 도구 (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)합니다. 이 샘플에 따라는 [시작](../../../../docs/framework/wcf/samples/getting-started-sample.md)합니다.  
  
> [!NOTE]
>  이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.  
  
## <a name="tracing"></a>추적  
 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]는 <xref:System.Diagnostics> 네임스페이스에 정의된 추적 메커니즘을 사용합니다. 이 추적 모델에서 추적 데이터는 응용 프로그램이 구현하는 추적 소스에 의해 생성됩니다. 각 소스는 이름으로 식별됩니다. 추적 소비자는 정보를 검색하려는 추적 소스에 대한 추적 수신기를 만듭니다. 추적 데이터를 수신하려면 추적 소스에 대한 수신기를 만들어야 합니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 이 작업을 수행하려면 서비스 모델 추적 소스를 `switchValue`로 설정하여 서비스나 클라이언트의 구성 파일에 다음 코드를 추가합니다.  
  
```xml  
<system.diagnostics>  
    <sources>  
      <source name="System.ServiceModel" switchValue="Information,ActivityTracing"  
        propagateActivity="true">  
        <listeners>  
          <add name="xml" />  
        </listeners>  
      </source>  
      <source name="System.ServiceModel.MessageLogging">  
        <listeners>  
          <add name="xml" />  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add initializeData="C:\logs\TracingAndLogging-service.svclog" type="System.Diagnostics.XmlWriterTraceListener"  
        name="xml" />  
    </sharedListeners>  
    <trace autoflush="true" />  
</system.diagnostics>  
```  
  
 추적 소스에 대 한 자세한 내용은 참조 추적 소스는 [추적 구성](../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md) 항목입니다.  
  
## <a name="activity-tracing-and-propagation"></a>동작 추적 및 전파  
 필요 `ActivityTracing` 사용 하도록 설정 하 고 `propagateActivity` 로 설정 `true` 에 `system.ServiceModel` (끝점 내의 동작 사이 (활동), 처리의 논리 단위에서 추적의 상관 관계를 제공 하는 클라이언트와 서비스 모두에 대 한 추적 소스 동작 전송을 통해), 부분과 (동작 ID 전파)를 통해 여러 끝점에 걸쳐 있는 동작입니다.  
  
 이러한 세 가지 메커니즘(동작, 전송 및 전파)은 Service Trace Viewer 도구를 사용하여 오류의 근본 원인을 더 신속하게 찾을 수 있도록 도와줍니다. 자세한 내용은 참조 [상관 관계가 지정 된 추적 보기 및 문제 해결에 대 한 Service Trace Viewer를 사용 하 여](../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)합니다.  
  
 사용자 정의 동작 추적을 만들어 ServiceModel이 제공되는 추적을 확장할 수 있습니다. 사용자 정의 동작 추적을 통해 사용자는 추적 동작을 만들어 다음을 수행할 수 있습니다.  
  
-   추적을 작업의 논리 단위로 그룹화합니다.  
  
-   전송과 전파를 통해 동작을 상호 연결합니다.  
  
-   [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 추적의 성능 비용(예: 로그 파일의 디스크 공간 비용)을 줄입니다.  
  
 사용자 정의 동작 추적에 대 한 자세한 내용은 참조 하십시오는 [추적 확장](../../../../docs/framework/wcf/samples/extending-tracing.md) 샘플.  
  
## <a name="message-logging"></a>메시지 로깅  
 모든 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응용 프로그램의 클라이언트 및 서비스 둘 다에서 메시지 로깅을 사용하도록 설정할 수 있습니다. 메시지 로깅을 사용하도록 설정하려면 클라이언트나 서비스에 다음 코드를 추가해야 합니다.  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <diagnostics>  
      <!-- Enable Message Logging here. -->  
      <!-- log all messages received or sent at the transport or service model levels -->  
      <messageLogging logEntireMessage="true"  
                      maxMessagesToLog="300"  
                      logMessagesAtServiceLevel="true"  
                      logMalformedMessages="true"  
                      logMessagesAtTransportLevel="true" />  
    </diagnostics>  
  </system.serviceModel>  
</configuration>  
```  
  
 메시지가 기록될 때 클라이언트에서 추적되는지 아니면 서버에서 추적되는지 여부에 따라 추적 유형이 달라집니다. 예를 들어, 클라이언트에 보내지는 "추가" 메시지는 클라이언트에서는 "TransportWrite" 범주 아래에 추적되지만 서비스에서는 "TransportRead" 범주 아래에 추적됩니다.  
  
 클라이언트의 App.config 파일이나 서비스의 Web.config 파일의 <xref:System.Diagnostics> 섹션에 다음 코드를 추가하여 추적 수신기를 구성합니다.  
  
```xml  
<system.diagnostics>  
    <sources>  
      <source name="System.ServiceModel" switchValue="Information,ActivityTracing"  
        propagateActivity="true">  
        <listeners>  
          <add name="xml" />  
        </listeners>  
      </source>  
      <source name="System.ServiceModel.MessageLogging">  
        <listeners>  
          <add name="xml" />  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add initializeData="C:\logs\TracingAndLogging-client.svclog" type="System.Diagnostics.XmlWriterTraceListener"  
        name="xml" />  
    </sharedListeners>  
    <trace autoflush="true" />  
  </system.diagnostics>  
```  
  
 메시지는 구성 파일에 지정된 대상 디렉터리에 XML 형식으로 기록됩니다.  
  
> [!NOTE]
>  처음에 로그 디렉터리를 만들어야 추적 파일이 만들어집니다. C:\logs\ 디렉터리가 있는지 확인하거나 수신기 구성에서 대체 로깅 디렉터리를 지정합니다. 자세한 내용은 이 문서의 끝에 있는 초기 설정 지침을 참조하십시오.  
  
 메시지 로깅에 대 한 자세한 내용은 참조는 [메시지 로깅 구성](../../../../docs/framework/wcf/diagnostics/configuring-message-logging.md) 항목입니다.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1.  수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.  
  
2.  Tracing and Message Logging 샘플을 실행하기 전에 .svclog 파일을 서비스에서 기록할 수 있도록 C:\logs\ 디렉터리를 만듭니다. 이 디렉터리의 이름은 추적 및 메시지를 기록하기 위한 경로로 구성 파일에 정의되며 변경할 수 있습니다. 로그 디렉터리에 대한 Network Service 쓰기 권한을 사용자에게 제공합니다.  
  
3.  지침에 따라 솔루션의 C#, c + + 또는 Visual Basic.NET 버전을 빌드하려면 [Windows Communication Foundation 샘플 빌드](../../../../docs/framework/wcf/samples/building-the-samples.md)합니다.  
  
4.  지침에 따라 단일 컴퓨터 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\TracingAndLogging`  
  
## <a name="see-also"></a>참고 항목  
 [추적](../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [AppFabric 모니터링 샘플](http://go.microsoft.com/fwlink/?LinkId=193959)
