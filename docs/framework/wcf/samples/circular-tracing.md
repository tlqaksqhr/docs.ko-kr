---
title: "순환 추적"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5ff139f9-8806-47bc-8f33-47fe6c436b92
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a4942e7e23b3cddd0f1c5bd3be8195ceeb190ca3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="circular-tracing"></a>순환 추적
이 샘플에서는 순환 버퍼 추적 수신기의 구현 방법을 보여 줍니다. 프로덕션 서비스의 대표적인 시나리오는 장기간 사용 가능한 서비스가 있고 낮은 수준으로 추적 로깅을 사용하도록 설정한 경우입니다. 이러한 서비스는 많은 디스크 공간을 사용합니다. 서비스의 문제를 해결할 때는 추적 로그에서 가장 최근의 데이터가 문제 해결과 직접적인 관련이 있습니다. 이 샘플에서는 구성 가능한 최대 데이터 크기에 맞게 디스크에 가장 최근의 추적만 유지하는 순환 버퍼 추적 수신기를 구현하는 방법을 보여 줍니다. 이 샘플에 따라는 [시작](../../../../docs/framework/wcf/samples/getting-started-sample.md) 및 사용자 지정 추적 수신기를 포함 합니다.  
  
> [!NOTE]
>  이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.  
  
 이 샘플에 익숙한 것으로 가정은 [Tracing and Message Logging](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md) 읽기에 대해 제공 되는 설명서 및 샘플의 [Tracing and Message Logging](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md) 샘플.  
  
## <a name="circular-buffer-trace-listener"></a>순환 버퍼 추적 수신기  
 순환 버퍼 추적 수신기의 구현은 각각 필요한 전체 추적 로그 데이터 크기의 최대 절반까지 저장할 수 있는 두 개의 파일이 있는 것을 전제로 합니다. 수신기는 파일 하나를 만든 다음 데이터 크기의 절반에 도달할 때까지 이 파일에 기록하고 그런 다음 두 번째 파일로 전환합니다. 수신기가 두 번째 파일에서도 크기 제한에 도달하면 새 추적으로 첫 번째 파일을 덮어씁니다.  
  
 이 수신기에서 파생 되는 `XmlWriteTraceListener` 로그를 볼 수를 허용 하 고는 [Service Trace Viewer 도구 (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)합니다. 로그를 볼 때는 Service Trace Viewer 도구에서 두 개의 로그 파일을 동시에 열어 쉽게 다시 결합할 수 있습니다. Service Trace Viewer 도구는 추적이 올바른 순서대로 표시되도록 자동으로 정렬합니다.  
  
## <a name="configuration"></a>구성  
 수신기 및 소스 요소에 대한 다음 코드를 추가하여 순환 버퍼 추적 수신기를 사용하도록 서비스를 구성할 수 있습니다. 순환 추적 수신기의 구성에서 `maxFileSizeKB` 특성을 설정하여 최대 파일 크기를 지정합니다. 다음 코드는 이 설정을 보여 줍니다.  
  
```xml  
<system.diagnostics>  
  <sources>  
    <source name="System.ServiceModel" switchValue="Information,ActivityTracing" propagateActivity="true">  
      <listeners>  
        <add name="CircularTraceListener" />  
      </listeners>  
    </source>  
  </sources>  
  <sharedListeners>  
    <add name="CircularTraceListener" type="Microsoft. Samples.ServiceModel.CircularTraceListener,CircularTraceListener"   
         initializeData="c:\logs\CircularTracing-service.svclog" maxFileSizeKB="100" />  
  </sharedListeners>  
  <trace autoflush="true" />  
</system.diagnostics>  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1.  수행한 반드시는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.  
  
2.  C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.  
  
3.  지침에 따라 단일 컴퓨터 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\CircularTracing`  
  
## <a name="see-also"></a>참고 항목  
 [AppFabric 모니터링 샘플](http://go.microsoft.com/fwlink/?LinkId=193959)
