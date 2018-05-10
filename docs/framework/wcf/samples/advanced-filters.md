---
title: 고급 필터
ms.date: 03/30/2017
ms.assetid: 8d81590f-e036-4f96-824a-4a187f462764
ms.openlocfilehash: de8577be2d56ec3c942fd8736e350234daf6a35a
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2018
---
# <a name="advanced-filters"></a>고급 필터
이 샘플 Windows Communication Foundation (WCF) 라우팅 서비스를 보여 줍니다. 라우팅 서비스는 쉽게 응용 프로그램에 내용 기반 라우터를 포함 하는 WCF 구성 요소입니다. 이 샘플이에서는 라우팅 서비스를 사용 하 여 통신 하도록 표준 WCF Calculator 샘플입니다. 이 샘플에서는 메시지 필터 및 메시지 필터 테이블을 사용하여 내용 기반 라우팅 논리를 정의하는 방법을 보여 줍니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\RoutingServices\AdvancedFilters`  
  
## <a name="sample-details"></a>샘플 세부 정보  
 다음 표에서는 라우팅 서비스의 메시지 필터 테이블에 추가되는 메시지 필터를 보여 줍니다.  
  
|필터|규칙|우선 순위|  
|------------|----------|--------------|  
|If(헤더 있음)|반올림|2|  
|If(Ep2에 나타남)|기본|1|  
|If(Address2와 함께 나타남)|반올림|1|  
|If(RoundRobin1)|기본|0|  
|If(RoundRobin2)|반올림|0|  
  
 메시지 필터와 메시지 필터 테이블은 코드 또는 응용 프로그램 구성 파일에서 만들 수 있습니다. 이 샘플의 경우 RoutingService\routing.cs 파일에서는 코드를 통해 정의된 메시지 필터 및 메시지 필터 테이블을 볼 수 있으며, RoutingService\App.config 파일에서는 응용 프로그램 구성 파일에 정의된 메시지 필터 및 메시지 필터 테이블을 볼 수 있습니다. 다음 단락에서는 코드를 통해 이 샘플의 메시지 필터 및 메시지 필터 테이블을 만드는 방법을 설명합니다.  
  
 첫 번째 필터인 <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>는 사용자 지정 헤더를 찾습니다. <xref:System.ServiceModel.WSHttpBinding>의 결과는 SOAP 1.2를 사용하는 봉투 버전이므로 SOAP 1.2 네임스페이스를 사용하기 위해 XPath 문이 정의됩니다. <xref:System.ServiceModel.Dispatcher.XPathMessageFilter>의 기본 네임스페이스 관리자가 SOAP 1.2 네임스페이스의 접두사 /s12를 이미 정의했으므로 이 접두사를 사용할 수 있습니다. 그러나 기본 네임스페이스 관리자에 클라이언트가 실제 헤더 값을 정의하는 데 사용하는 사용자 지정 네임스페이스는 없으므로 해당 접두사를 정의해야 합니다. 이 헤더와 함께 표시되는 모든 메시지는 이 필터와 일치합니다.  
  
```  
XPathMessageContext namespaceManager = new XPathMessageContext();  
namespaceManager.AddNamespace("custom", "http://my.custom.namespace/");  
  
XPathMessageFilter xpathFilter = new XPathMessageFilter("/s12:Envelope/s12:Header/custom:RoundingCalculator = 1", namespaceManager);  
```  
  
 두 번째 필터는 <xref:System.ServiceModel.Dispatcher.EndpointNameMessageFilter>에서 받은 모든 메시지를 일치시키는 `calculatorEndpoint`입니다. 끝점 이름은 서비스 끝점 개체가 만들어질 때 정의됩니다.  
  
```  
EndpointNameMessageFilter endpointNameFilter = new EndpointNameMessageFilter("calculatorEndpoint");  
```  
  
 세 번째 필터는 <xref:System.ServiceModel.Dispatcher.PrefixEndpointAddressMessageFilter>입니다. 이 필터는 제공된 주소 접두사 또는 앞 부분과 일치하는 주소를 가진 끝점에 표시되는 모든 메시지를 일치시킵니다. 이 예에서 주소 접두사를 이루어집니다 "http://localhost/routingservice/router/rounding/"입니다. 즉, 주소가 지정 되는 모든 들어오는 메시지 "http://localhost/routingservice/router/rounding/*"이이 필터와 일치 하 합니다. 이 경우,이 반올림 계산기 끝점에 표시 되는 메시지의 주소에 있는 "http://localhost/routingservice/router/rounding/calculator"입니다.  
  
```  
PrefixEndpointAddressMessageFilter prefixAddressFilter = new PrefixEndpointAddressMessageFilter(new EndpointAddress("http://localhost/routingservice/router/rounding/"));  
```  
  
 마지막 두 메시지 필터는 사용자 지정 <xref:System.ServiceModel.Dispatcher.MessageFilter>입니다. 이 예제에서는 "RoundRobin" 메시지 필터가 사용되었습니다. 이 메시지 필터는 제공된 RoutingService\RoundRobinMessageFilter.cs 파일에 만들어져 있습니다. 이 두 필터는 동일한 그룹으로 설정된 경우 번갈아서 메시지 일치를 보고하다가 메시지 불일치를 보고하므로 한 번에 한 필터만 `true`로 응답합니다.  
  
```  
RoundRobinMessageFilter roundRobinFilter1 = new RoundRobinMessageFilter("group1");  
  
RoundRobinMessageFilter roundRobinFilter2 = new RoundRobinMessageFilter("group1");  
```  
  
 그런 다음에는 이러한 모든 메시지가 <xref:System.ServiceModel.Dispatcher.MessageFilterTable%601>에 추가됩니다. 이때 메시지 필터 테이블에서 필터가 실행되는 순서에 영향을 주도록 우선 순위가 지정됩니다. 우선 순위가 높을수록 일찍 실행되고 우선 순위가 낮을수록 나중에 실행됩니다. 따라서 우선 순위가 2인 필터는 우선 순위가 1인 필터보다 먼저 실행됩니다. 우선 순위가 지정되지 않은 경우 기본 우선 순위는 0입니다. 메시지 필터 테이블에서는 지정된 우선 순위의 필터를 모두 실행한 후에 다음으로 낮은 우선 순위로 이동합니다. 특정 우선 순위에서 일치 항목을 찾은 경우 메시지 필터 테이블에서는 다음으로 낮은 우선 순위에서 일치 항목을 계속 찾으려고 시도하지 않습니다.  
  
> [!NOTE]
>  이 예제에서는 메시지 필터 우선 순위를 사용하는 방법을 보여 주지만, 일반적으로는 우선 순위 없이도 제대로 작동하도록 필터를 디자인하고 구성하는 것이 성능과 디자인 면에서 보다 뛰어납니다.  
  
 첫 번째로 추가되는 필터는 XPath 필터이며 해당 우선 순위는 2로 설정됩니다. 이 필터가 첫 번째로 실행되는 메시지 필터입니다. 이 필터로 사용자 지정 헤더를 찾은 경우 다른 필터의 결과에 상관없이 해당 메시지가 반올림 계산기 끝점으로 라우트됩니다.  
  
 우선 순위 1에서는 두 개의 필터가 추가됩니다. 이 두 필터는 우선 순위가 2인 XPath 필터로 일치하는 메시지를 찾지 못한 경우에만 실행됩니다. 이 두 필터는 메시지가 표시될 때 메시지 주소로 지정된 위치를 확인하는 두 가지 방법을 보여 줍니다. 두 필터는 메시지가 두 끝점 중 하나에 도착했는지 여부를 효율적으로 확인하며 동시에 둘 모두가 `true`를 반환하지는 않으므로 동일한 우선 순위에서 실행될 수 있습니다.  
  
 마지막으로, 최하위 우선 순위인 우선 순위 0에서는 RoundRobin 메시지 필터가 실행됩니다. 이러한 필터는 동일한 그룹 이름으로 구성되므로 한 번에 하나만 일치합니다. 사용자 지정 헤더가 있는 모든 메시지는 라우트되고 모두 가상화된 특정 끝점으로 주소가 지정되었으므로 RoundRobin 메시지 필터로 처리되는 메시지는 사용자 지정 헤더 없이 기본 라우터 끝점으로 주소가 지정된 메시지뿐입니다. 이러한 메시지는 각 호출마다 하나씩 전환되므로 작업 중 절반은 일반 계산기 끝점으로 이동하고 나머지 절반은 반올림 계산기 끝점으로 이동합니다.  
  
#### <a name="to-use-this-sample"></a>이 샘플을 사용하려면  
  
1.  [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]에서 AdvancedFilters.sln을 엽니다.  
  
2.  열려는 **솔루션 탐색기**선택, **솔루션 탐색기** 에서 **보기** 메뉴.  
  
3.  Visual Studio에서 F5 또는 CTRL + SHIFT + B를 누릅니다.  
  
    1.  F5 키를 누를 때 필요한 프로젝트가 자동 시작 하려는 경우 솔루션을 마우스 오른쪽 단추로 클릭 하 고 선택 **속성**합니다. 선택 된 **시작 프로젝트** 노드 아래의 **공용 속성** 왼쪽된 창에서. 선택은 **여러 개의 시작 프로젝트** 라디오 단추 및 모든 프로젝트에 설정 된 **시작** 작업 합니다.  
  
    2.  Ctrl+Shift+B를 사용하여 프로젝트를 빌드할 경우에는 다음 응용 프로그램을 시작해야 합니다.  
  
        1.  계산기 클라이언트(./CalculatorClient/bin/client.exe)  
  
        2.  계산기 서비스(./CalculatorService/bin/service.exe)  
  
        3.  반올림 계산기 서비스(./RoundingCalcService/bin/service.exe)  
  
        4.  라우팅 서비스(./RoutingService/bin/RoutingService.exe)  
  
4.  계산기 클라이언트의 콘솔 창에서 Enter 키를 눌러 클라이언트를 시작합니다. 그러면 클라이언트에서는 선택 가능한 대상 끝점 목록을 반환합니다.  
  
5.  해당하는 문자를 입력하여 대상 끝점을 선택하고 Enter 키를 누릅니다.  
  
6.  그런 다음 클라이언트에서는 사용자 지정 헤더를 추가할지 여부를 묻습니다. 예의 경우 Y 키, 아니요의 경우 N 키를 누른 다음 Enter 키를 누릅니다.  
  
7.  선택에 따라 서로 다른 출력이 나타납니다.  
  
    1.  다음은 메시지에 사용자 지정 헤더를 추가한 경우 반환되는 출력입니다.  
  
        ```Output  
        Add(100,15.99) = 116  
        Subtract(145,76.54) = 68.5  
        Multiply(9,81.25) = 731.3  
        Divide(22,7) = 3.1  
        ```  
  
    2.  다음은 사용자 지정 헤더가 없는 반올림 계산기 끝점을 선택한 경우 반환되는 출력입니다.  
  
        ```Output  
        Add(100,15.99) = 116  
        Subtract(145,76.54) = 68.5  
        Multiply(9,81.25) = 731.3  
        Divide(22,7) = 3.1  
        ```  
  
    3.  다음은 사용자 지정 헤더가 없는 일반 계산기 끝점을 선택한 경우 반환되는 출력입니다.  
  
        ```Output  
        Add(100,15.99) = 115.99  
        Subtract(145,76.54) = 68. 46  
        Multiply(9,81.25) = 731.25  
        Divide(22,7) = 3.14285714285714  
        ```  
  
    4.  다음은 사용자 지정 헤더가 없는 기본 라우터 끝점을 선택한 경우 반환되는 출력입니다.  
  
        ```Output  
        Add(100,15.99) = 116  
        Subtract(145,76.54) = 68.46  
        Multiply(9,81.25) = 731.3  
        Divide(22,7) = 3.14285714285714  
        ```  
  
8.  계산기 서비스 및 반올림 계산기 서비스에서도 호출된 작업의 로그를 각 해당 콘솔 창에 출력합니다.  
  
9. 클라이언트 콘솔 창에 입력 `quit` 종료 하려면 ENTER 키를 누릅니다.  
  
10. 서비스 콘솔 창에서 Enter 키를 눌러 서비스를 종료합니다.  
  
## <a name="configurable-via-code-or-appconfig"></a>코드 또는 App.config를 통해 구성 가능  
 이 샘플은 App.config 파일을 사용하여 라우터 동작을 정의하도록 구성되어 있습니다. RoutingService\App.config 파일이 인식되지 않도록 이 파일의 이름을 다른 이름으로 바꾸고, RoutingService\routing.cs에서 `ConfigureRouterViaCode()` 메서드 호출의 주석 처리를 제거할 수도 있습니다. 어떤 방법을 사용하든 라우터 동작은 동일합니다.  
  
### <a name="scenario"></a>시나리오  
 이 샘플에서는 한 끝점을 통해 노출되는 서비스의 여러 형식 또는 구현을 허용하는 내용 기반 라우터의 역할을 하는 라우터를 보여 줍니다.  
  
### <a name="real-world-scenario"></a>실제 시나리오  
 Contoso에서는 모든 서비스를 가상화하여 서로 다른 여러 형식의 서비스에 액세스할 수 있게 해 주는 하나의 끝점만 공개하려고 합니다. 이 경우 라우팅 서비스의 내용 기반 라우팅 기능을 사용하여 들어오는 요청을 보낼 위치를 확인합니다.  
  
## <a name="see-also"></a>참고 항목  
 [AppFabric 호스팅 및 지 속성 샘플](http://go.microsoft.com/fwlink/?LinkId=193961)
