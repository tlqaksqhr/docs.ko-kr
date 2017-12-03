---
title: "ETW 추적"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ac99a063-e2d2-40cc-b659-d23c2f783f92
caps.latest.revision: "42"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5ebffd082f5d1b07ab016c0e5e72d6ad23542147
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="etw-tracing"></a>ETW 추적
이 샘플에서는 ETW(Windows용 이벤트 추적) 및 이 샘플과 함께 제공된 `ETWTraceListener`를 사용하여 E2E(종단 간) 추적을 구현하는 방법을 보여 줍니다. 이 샘플에 따라는 [시작](../../../../docs/framework/wcf/samples/getting-started-sample.md) ETW 추적을 포함 합니다.  
  
> [!NOTE]
>  이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.  
  
 이 샘플에 익숙한 것으로 가정 [Tracing and Message Logging](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md)합니다.  
  
 <xref:System.Diagnostics> 추적 모델의 추적 소스마다 데이터가 추적되는 위치와 방법을 결정하는 추적 수신기가 여러 개씩 있을 수 있습니다. 수신기의 형식에 따라 추적 데이터가 기록되는 형식이 정의됩니다. 다음 코드 샘플에서는 수신기를 구성에 추가하는 방법을 보여 줍니다.  
  
```xml  
<system.diagnostics>  
    <sources>  
        <source name="System.ServiceModel"   
             switchValue="Verbose,ActivityTracing"  
             propagateActivity="true">  
            <listeners>  
                <add type=  
                   "System.Diagnostics.DefaultTraceListener"  
                   name="Default">  
                   <filter type="" />  
                </add>  
                <add name="ETW">  
                    <filter type="" />  
                </add>  
            </listeners>  
        </source>  
    </sources>  
    <sharedListeners>  
        <add type=  
            "Microsoft.ServiceModel.Samples.EtwTraceListener, ETWTraceListener"  
            name="ETW" traceOutputOptions="Timestamp">  
            <filter type="" />  
       </add>  
    </sharedListeners>  
</system.diagnostics>  
```  
  
 이 수신기를 사용하기 전에 ETW 추적 세션이 시작되어야 합니다. 이 세션은 Logman.exe 또는 Tracelog.exe를 사용하여 시작할 수 있습니다. SetupETW.bat 파일이 이 샘플에 포함되어 있으므로 ETW 추적 세션을 닫고 로그 파일을 완료하는 CleanupETW.bat 파일과 함께 세션을 설정할 수 있습니다.  
  
> [!NOTE]
>  이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다. 이러한 도구에 대 한 자세한 내용은 참조 하십시오. [http://go.microsoft.com/fwlink/?LinkId=56580](http://go.microsoft.com/fwlink/?LinkId=56580)  
  
 ETWTraceListener를 사용할 경우 추적은 이진 .etl 파일에 기록됩니다. ServiceModel 추적이 설정된 상태에서 생성된 모든 추적은 동일한 파일에 표시됩니다. 사용 하 여 [Service Trace Viewer 도구 (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) .etl 및.svclog 로그 파일 보기에 대 한 합니다. 이 뷰어는 해당 소스에서 해당 대상 및 소비 지점까지 메시지를 추적하는 데 사용할 수 있는 시스템의 종단 간 보기를 만듭니다.  
  
 ETW 추적 수신기는 순환 로깅을 지원합니다. 이 기능을 사용 하려면로 이동 **시작**, **실행** 유형과 `cmd` 명령 콘솔을 시작 합니다. 다음 명령에서 `<logfilename>` 매개 변수를 로그 파일의 이름으로 바꿉니다.  
  
```  
logman create trace Wcf -o <logfilename> -p "{411a0819-c24b-428c-83e2-26b41091702e}" -f bincirc -max 1000  
```  
  
 `-f` 및 `-max` 스위치는 선택 사항입니다. 이러한 스위치는 각각 이진 순환 형식과 1000MB의 최대 로그 크기를 지정합니다. `-p` 스위치는 추적 공급자를 지정하는 데 사용됩니다. 위 예제에서 `"{411a0819-c24b-428c-83e2-26b41091702e}"`는 "XML ETW 샘플 공급자"의 GUID입니다.  
  
 세션을 시작하려면 다음 명령을 입력합니다.  
  
```  
Logman start Wcf  
```  
  
 로깅을 완료한 후 다음 명령을 사용하여 세션을 중지할 수 있습니다.  
  
```  
Logman stop Wcf  
```  
  
 이 이렇게 하면 선택한 도구와 처리할 수 있는 이진 순환 로그 포함 하 여 [Service Trace Viewer 도구 (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md) 또는 tracerpt를 사용 합니다.  
  
 또한 검토할 수 있습니다는 [순환 추적](../../../../docs/framework/wcf/samples/circular-tracing.md) 순환 로깅을 수행 하는 다른 수신기에 대 한 자세한 내용은 샘플입니다.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1.  수행한 반드시는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.  
  
2.  지침에 따라 솔루션을 빌드하려면 [Windows Communication Foundation 샘플 빌드](../../../../docs/framework/wcf/samples/building-the-samples.md)합니다.  
  
    > [!NOTE]
    >  RegisterProvider.bat, SetupETW.bat 및 CleanupETW.bat 명령을 사용하려면 로컬 관리자 계정으로 실행해야 합니다. 또한 [!INCLUDE[wv](../../../../includes/wv-md.md)] 이상을 사용하는 경우에는 명령 프롬프트를 높은 권한으로 실행해야 합니다. 이렇게 하려면 명령 프롬프트 아이콘을 마우스 오른쪽 단추로 클릭 하 여 **관리자 권한으로 실행**합니다.  
  
3.  샘플을 실행하기 전에 RegisterProvider.bat를 클라이언트와 서버에서 실행합니다. 이렇게 하면 Service Trace Viewer에서 읽을 수 있는 추적을 생성하도록 결과 ETWTracingSampleLog.etl 파일이 설정됩니다. 이 파일은 C:\logs 폴더에 있습니다. 이 폴더가 없을 경우 만들어야 하며 그렇지 않으면 추적이 생성되지 않습니다. 그런 다음 클라이언트 및 서버 컴퓨터에서 SetupETW.bat를 실행하여 ETW 추적 세션을 시작합니다. SetupETW.bat 파일은 CS\Client 폴더에 있습니다.  
  
4.  지침에 따라 단일 컴퓨터 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.  
  
5.  샘플이 완료되면 CleanupETW.bat를 실행하여 ETWTracingSampleLog.etl 파일 만들기를 완료합니다.  
  
6.  Service Trace Viewer 내에서 ETWTracingSampleLog.etl 파일을 엽니다. 이진 형식 파일을 .svclog 파일로 저장하라는 메시지가 표시됩니다.  
  
7.  서비스 추적 뷰어 내에서 새로 만든 .svclog 파일을 열어 ETW 및 ServiceModel 추적을 봅니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\AnalyticTrace`  
  
## <a name="see-also"></a>참고 항목  
 [AppFabric 모니터링 샘플](http://go.microsoft.com/fwlink/?LinkId=193959)
