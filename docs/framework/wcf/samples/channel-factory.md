---
title: "채널 팩터리 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 09b53aa1-b13c-476c-a461-e82fcacd2a8b
caps.latest.revision: 24
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 24
---
# 채널 팩터리
이 샘플에서는 클라이언트 응용 프로그램에서 생성된 클라이언트 대신 <xref:System.ServiceModel.ChannelFactory> 클래스가 있는 채널을 만드는 방법을 보여 줍니다.이 샘플은 계산기 서비스를 구현하는 [시작](../../../../docs/framework/wcf/samples/getting-started-sample.md)을 기반으로 합니다.  
  
> [!NOTE]
>  이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.  
  
 이 샘플에서는 <xref:System.ServiceModel.ChannelFactory%601> 클래스를 사용하여 서비스 끝점에 채널을 만듭니다.일반적으로 서비스 끝점에 채널을 만들려면 [ServiceModel Metadata 유틸리티 도구\(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)를 사용하여 클라이언트 형식을 생성하고 생성된 형식의 인스턴스를 만듭니다.이 샘플에서와 같이 <xref:System.ServiceModel.ChannelFactory%601> 클래스를 사용하여 채널을 만들 수도 있습니다.다음 샘플 코드에서 만들어지는 서비스는 [시작](../../../../docs/framework/wcf/samples/getting-started-sample.md)에 있는 서비스와 동일합니다.  
  
```  
EndpointAddress address = new EndpointAddress("http://localhost/servicemodelsamples/service.svc");  
WSHttpBinding binding = new WSHttpBinding();  
ChannelFactory<ICalculator> factory = new   
                    ChannelFactory<ICalculator>(binding, address);  
ICalculator channel = factory.CreateChannel();  
```  
  
> [!IMPORTANT]
>  다중 컴퓨터 시나리오에서 이 샘플을 실행하는 경우에는 앞의 코드에서 "localhost"를 서비스를 실행하는 컴퓨터의 정규화된 이름으로 바꿔야 합니다.이 샘플에서는 구성을 사용하여 끝점 주소를 설정하지 않기 때문에 코드에서 설정해야 합니다.  
  
 채널이 만들어지면 생성된 클라이언트의 경우와 마찬가지로 서비스 작업을 호출할 수 있습니다.  
  
```  
// Call the Add service operation.  
double value1 = 100.00D;  
double value2 = 15.99D;  
double result = channel.Add(value1, value2);  
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
  
```  
  
 채널을 닫으려면 먼저 <xref:System.ServiceModel.IClientChannel> 인터페이스로 캐스팅해야 합니다.이는 생성된 채널이 `Add` 및 `Subtract` 등의 메서드가 있지만 `Close`는 없는 `ICalculator` 인터페이스를 사용하여 클라이언트 응용 프로그램에 선언되기 때문입니다.`Close` 메서드는 <xref:System.ServiceModel.ICommunicationObject> 인터페이스에서 시작됩니다.  
  
```  
// Close the channel.  
 ((IClientChannel)client).Close();  
  
```  
  
 샘플을 실행하면 작업 요청 및 응답이 클라이언트 콘솔 창에 표시됩니다.클라이언트 응용 프로그램을 종료하려면 클라이언트 창에서 Enter 키를 누릅니다.  
  
```  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### 샘플을 설치, 빌드 및 실행하려면  
  
1.  [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)를 수행했는지 확인합니다.  
  
2.  C\# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Windows Communication Foundation 샘플 빌드](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.이 샘플에서는 메타데이터 게시를 사용하지 않습니다.먼저 이 샘플의 메타데이터 게시를 사용하여 클라이언트 형식을 다시 생성해야 합니다.  
  
3.  단일 컴퓨터 또는 다중 컴퓨터 구성에서 샘플을 실행하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)의 지침을 따릅니다.  
  
### 다중 컴퓨터 구성에서 샘플을 실행하려면  
  
1.  다음 코드에서 "localhost"를 서비스를 실행하는 컴퓨터의 정규화된 이름으로 바꿉니다.  
  
    ```  
    EndpointAddress address = new EndpointAddress("http://localhost/servicemodelsamples/service.svc");  
    ```  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.계속하기 전에 다음\(기본\) 디렉터리를 확인하십시오.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780)로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하십시오.이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Client\ChannelFactory`  
  
## 참고 항목