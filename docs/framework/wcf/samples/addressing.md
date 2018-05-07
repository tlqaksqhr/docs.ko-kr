---
title: 주소 지정
ms.date: 03/30/2017
ms.assetid: d438e6f2-d0f3-43aa-b259-b51b5bda2e64
ms.openlocfilehash: 94ac903afb27f1b87f0ca8bf05cb891d0d9ee34c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="addressing"></a>주소 지정
Addressing 샘플에서는 끝점 주소의 다양한 측면과 기능을 보여 줍니다. 이 샘플에 따라는 [시작](../../../../docs/framework/wcf/samples/getting-started-sample.md)합니다. 이 샘플에서 서비스는 자체 호스트됩니다. 서비스와 클라이언트는 모두 콘솔 응용 프로그램입니다. 서비스는 상대 및 절대 끝점 주소를 조합하여 여러 끝점을 정의합니다.  
  
> [!NOTE]
>  이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.  
  
 서비스 구성 파일에는 기본 주소와 4개의 끝점이 지정됩니다. 기본 주소는 다음 샘플 구성에서처럼 service/host/baseAddresses 아래 add 요소를 사용하여 지정합니다.  
  
```xml  
<service name="Microsoft.ServiceModel.Samples.CalculatorService"  
         behaviorConfiguration="CalculatorServiceBehavior">  
  <host>  
    <baseAddresses>  
      <add baseAddress="http://localhost:8000/ServiceModelSamples/service" />  
    </baseAddresses>  
  </host>  
</service>  
```  
  
 다음 샘플 구성에서와 같이 첫 번째 끝점 정의는 끝점 주소가 기본 주소와 URI 컴퍼지션 다음에 오는 상대 주소의 조합인 상대 주소를 지정합니다.  
  
```xml
<!-- Empty relative address specified:   
     use the base address provided by the host. -->  
<!-- The endpoint address is  
     http://localhost:8000/ServiceModelSamples/service. -->  
<endpoint address=""  
          binding="wsHttpBinding"  
          contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
 이 경우 상대 주소가 비어 있으므로("") 끝점 주소는 기본 주소와 동일합니다. 실제 끝점 주소는 http://localhost:8000/servicemodelsamples/service합니다.  
  
 두 번째 끝점 정의도 다음 샘플 구성에서처럼 상대 주소를 지정합니다.  
  
```xml  
<!-- The relative address specified: use the base address -->  
<!-- provided by the host + path. The endpoint address is -->  
<!-- http://localhost:8000/servicemodelsamples/service/test. -->  
<endpoint address="/test"  
          binding="wsHttpBinding"  
          contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
 상대 주소 "test"가 기본 주소에 추가됩니다. 실제 끝점 주소는 http://localhost:8000/servicemodelsamples/service/test합니다.  
  
 세 번째 끝점 정의는 다음 샘플 구성에서처럼 절대 주소를 지정합니다.  
  
```xml  
<endpoint address="http://localhost:8001/hello/servicemodelsamples"  
          binding="wsHttpBinding"  
          contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
 주소에서 기본 주소는 아무런 역할도 하지 않습니다. 실제 끝점 주소는 http://localhost:8001/hello/servicemodelsamples합니다.  
  
 네 번째 끝점 주소는 절대 주소 및 다른 전송(TCP)을 지정합니다. 주소에서 기본 주소는 아무런 역할도 하지 않습니다. 실제 끝점 주소는 net.tcp://localhost:9000/servicemodelsamples/service입니다.  
  
```xml  
<!-- The absolute address specified, different transport: -->  
<!-- use the specified address, and ignore the base address. -->  
<!-- The endpoint address is -->  
<!-- net.tcp://localhost:9000/servicemodelsamples/service. -->  
<endpoint address=  
          "net.tcp://localhost:9000/servicemodelsamples/service"  
          binding="netTcpBinding"  
          contract="Microsoft.ServiceModel.Samples.ICalculator" />  
</service>  
```  
  
 클라이언트는 4개의 서비스 끝점 하나에만 액세스하지만 이러한 서비스 끝점이 모두 해당 구성 파일에 정의됩니다. 클라이언트는 `CalculatorProxy` 개체를 만들 때 끝점을 선택합니다. 구성 이름을 `CalculatorEndpoint1`부터 `CalculatorEndpoint4`까지 변경하여 각 끝점을 사용할 수 있습니다.  
  
 샘플을 실행하면 서비스는 각 끝점에 대한 주소, 바인딩 이름 및 계약 이름을 열거합니다. ServiceHost의 관점에서 보면 MEX(메타데이터 교환) 끝점은 또 다른 끝점이므로 목록에 표시됩니다.  
  
```  
Service endpoints:  
Endpoint - address:  http://localhost:8000/ServiceModelSamples/service  
           binding:  WSHttpBinding  
           contract: ICalculator  
Endpoint - address:  http://localhost:8000/ServiceModelSamples/service/test  
           binding:  WSHttpBinding  
           contract: ICalculator  
Endpoint - address:  http://localhost:8001/hello/servicemodelsamples  
           binding:  WSHttpBinding  
           contract: ICalculator  
Endpoint - address:  net.tcp://localhost:9000/servicemodelsamples/service  
           binding:  NetTcpBinding  
           contract: ICalculator  
Endpoint - address:  http://localhost:8000/ServiceModelSamples/service/mex  
           binding:  MetadataExchangeHttpBinding  
           contract: IMetadataExchange  
  
The service is ready.  
Press <ENTER> to terminate service.  
```  
  
 클라이언트를 실행하면 작업 요청 및 응답이 서비스와 클라이언트 콘솔 창 모두에 표시됩니다. 서비스와 클라이언트를 종료하려면 각 콘솔 창에서 Enter 키를 누릅니다.  
  
```  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1.  수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.  
  
2.  C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.  
  
3.  지침에 따라 단일 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.  
  
    > [!NOTE]
    >  Svcutil.exe를 사용하여 이 샘플에 대한 구성을 다시 생성할 경우 클라이언트 구성에서 끝점 이름을 클라이언트 코드와 일치하도록 수정해야 합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Addressing`  
  
## <a name="see-also"></a>참고 항목
