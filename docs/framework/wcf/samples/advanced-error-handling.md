---
title: 고급 오류 처리
ms.date: 03/30/2017
ms.assetid: ed54b687-78af-4eda-8507-9fd081bdea1a
ms.openlocfilehash: 723b1ca9c2fa771d8bc3f337d9c4fde8c9632c68
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33810085"
---
# <a name="advanced-error-handling"></a>고급 오류 처리
이 샘플 Windows Communication Foundation (WCF) 라우팅 서비스를 보여 줍니다. 라우팅 서비스는 쉽게 응용 프로그램에 내용 기반 라우터를 포함 하는 WCF 구성 요소입니다. 이 샘플에서는 라우팅 서비스가 트랜잭션과 멀티캐스트 같은 보다 복잡한 다른 메시징 개념을 사용하여 오류에서 적절하게 복구하는 방법을 보여 줍니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\RoutingServices\AdvancedErrorHandling`  
  
## <a name="sample-details"></a>샘플 세부 정보  
 이 샘플에서 라우팅 서비스는 MSMQ 큐에서 메시지를 읽고 이 메시지를 두 개의 큐 목록에 멀티캐스트하도록 구성되어 있습니다. 한 목록은 서비스 큐에 사용되고 다른 목록은 로깅 큐에 사용됩니다.  
  
 기본적으로 라우팅 서비스에서 사용하도록 구성된 MSMQ 바인딩은 트랜잭션 사용을 지원하므로 라우팅 서비스에서는 메시지가 성공적으로 라우트되었음을 인바운드 큐(`InQ`)에 보고하기 전에 메시지가 트랜잭션 메시지이며 각 목록의 하나 이상의 큐에서 받은 메시지인지를 확인합니다. 따라서 서비스 큐 또는 로깅 큐를 모두 사용할 수 없는 경우 라우팅 서비스에서는 메시지를 라우트할 수 없으므로 인바운드 큐에서 적절한 작업을 수행해야 함을 보고합니다. 이 작업에는 메시지를 배달 못한 시스템 큐로 이동하는 작업이 포함됩니다.  
  
#### <a name="to-use-this-sample"></a>이 샘플을 사용하려면  
  
1.  > [!IMPORTANT]
    >  이 샘플을 실행하기 전에 MSMQ를 설치합니다. MSMQ가 설치되어 있지 않은 경우 이 샘플을 실행하면 예외 메시지가 반환됩니다. MSMQ를 설치 하기 위한 지침을 찾을 수 있습니다 [설치 메시지 큐 (MSMQ)](http://go.microsoft.com/fwlink/?LinkId=166437)합니다.  
  
     [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]에서 AdvancedErrorHandling.sln을 엽니다.  
  
2.  키를 눌러 **F5** 또는 **CTRL + SHIFT + B** Visual Studio에서.  
  
    1.  Ctrl+Shift+B를 사용하여 응용 프로그램을 빌드하는 경우에는 ./RoutingService/bin/debug/RoutingService.exe에서 응용 프로그램을 시작해야 합니다.  
  
3.  콘솔 창에서 Enter 키를 눌러 클라이언트를 시작합니다.  
  
4.  클라이언트는 각 사례마다 큐에 대한 통계를 다르게 반환합니다.  
  
    1.  다음은 사례 1(오류 없음)에 대해 반환되는 출력입니다.  
  
        ```Output  
        The inbound queue has 0 messages.  
        The primary service queue has 1 messages.   
        The backup service queue has 0 messages.   
        The primary logging queue has 1 messages.   
        The backup logging queue has 0 messages.   
        Press <Enter> to continue  
        ```  
  
    2.  다음은 사례 3(기본 서비스 및 로깅 큐 오류)에 대해 반환되는 출력입니다.  
  
        ```Output  
        The inbound queue has 0 messages.   
        The primary service queue does not exist.   
        The backup service queue has 1 messages.   
        The primary logging queue does not exist.   
        The backup logging queue has 1 messages.   
        Press <ENTER> to continue.  
        ```  
  
    3.  다음은 사례 4(기본 서비스 큐와 기본 및 백업 로깅 큐 오류)에 대해 반환되는 출력입니다.  
  
        ```Output  
        The inbound queue has 0 messages.   
        The primary service queue does not exist.  
        The backup service queue has 0 messages.   
        The primary logging queue does not exist.   
        The backup logging queue does not exist.   
        The System Dead Letter queue has 1 messages.   
        Press <ENTER> to Quit.  
        ```  
  
    4.  다음은 사례 2(기본 서비스 큐 오류)에 대해 반환되는 출력입니다.  
  
        ```Output  
        The inbound queue has 0 messages.   
        The primary service queue does not exist.  
        The backup service queue has 1 messages.   
        The primary logging queue has 1 messages.   
        The backup logging queue has 0 messages.   
        Press <ENTER> to continue.  
        ```  
  
## <a name="configurable-via-code-or-appconfig"></a>코드 또는 App.config를 통해 구성 가능  
 이 샘플은 App.config 파일을 사용하여 라우터 동작을 정의하도록 구성되어 있습니다. RoutingService\App.config 파일이 인식되지 않도록 이 파일의 이름을 다른 이름으로 바꾸고 RoutingService\Program.cs의 `configDriven` 필드 값을 `false`로 변경하여 코드에 정의된 구성을 사용할 수도 있습니다. 어떤 방법을 사용하든 라우터 동작은 동일합니다.  
  
### <a name="scenario"></a>시나리오  
 이 샘플에서는 라우팅 서비스에서 트랜잭션 및 받기 컨텍스트와 같은 고급 메시징 기능을 처리하고 이러한 기능을 올바른 처리 오류 처리 시나리오의 일부로 사용하는 방법을 보여 줍니다.  
  
### <a name="real-world-scenario"></a>실제 시나리오  
 Contoso에서는 라우팅 서비스를 통한 트랜잭션 수신을 사용하여 오류가 발생하더라도 필요한 모든 서비스에서 정보를 받을 수 있도록 하려고 합니다. 또한 메시지를 배달할 수 없으면 오류 처리 논리가 사용되는 경우라도 오류가 올바르게 자동 처리되고 보고되도록 하려고 합니다. 이를 위해 필요한 경우 라우팅 서비스가 특정 끝점으로 장애 조치되도록 구성하며, 라우팅 서비스에서는 트랜잭션/수신 컨텍스트의 작성, 완료 및 롤백/중단을 포함하여 오류 상황을 처리합니다.  
  
## <a name="see-also"></a>참고 항목  
 [AppFabric 호스팅 및 지 속성 샘플](http://go.microsoft.com/fwlink/?LinkId=193961)
