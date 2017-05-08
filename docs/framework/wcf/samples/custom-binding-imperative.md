---
title: "사용자 지정 바인딩 명령 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6e13bf96-5de0-4476-b646-5f150774418d
caps.latest.revision: 18
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 18
---
# 사용자 지정 바인딩 명령
이 샘플에서는 명령 코드를 작성하여 구성 파일이나 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]에서 생성한 클라이언트를 사용하지 않고 사용자 지정 바인딩을 정의하고 사용하는 방법을 보여 줍니다.이 샘플에서는 HTTP 전송에서 제공하는 기능과 신뢰할 수 있는 세션 채널을 조합하여 신뢰할 수 있는 HTTP 기반 바인딩을 만듭니다.이 샘플은 계산기 서비스를 구현하는 [시작](../../../../docs/framework/wcf/samples/getting-started-sample.md)을 기반으로 합니다.  
  
> [!NOTE]
>  이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.  
  
 클라이언트와 서버에서 모두 두 바인딩 요소\(신뢰할 수 있는 세션 및 HTTP\)를 포함하는 사용자 지정 바인딩을 만듭니다.  
  
```  
  
ReliableSessionBindingElement reliableSession = new ReliableSessionBindingElement();  
reliableSession.Ordered = true;  
  
HttpTransportBindingElement httpTransport = new HttpTransportBindingElement();  
httpTransport.AuthenticationScheme = System.Net.AuthenticationSchemes.Anonymous;  
httpTransport.HostNameComparisonMode = HostNameComparisonMode.StrongWildcard;  
  
CustomBinding binding = new CustomBinding(reliableSession, httpTransport);  
  
```  
  
 서비스에서는 ServiceHost에 끝점을 추가하여 바인딩을 사용합니다.  
  
```  
serviceHost.AddServiceEndpoint(typeof(ICalculator), binding, "");  
```  
  
 클라이언트에서는 <xref:System.ServiceModel.ChannelFactory>에서 서비스에 대해 채널을 만들기 위해 바인딩을 사용합니다.  
  
```  
EndpointAddress address = new EndpointAddress("http://localhost:8000/servicemodelsamples/service");  
ChannelFactory<ICalculator> channelFactory = new ChannelFactory<ICalculator>(binding, address);  
ICalculator channel = channelFactory.CreateChannel();  
```  
  
 그런 다음 이 채널은 서비스와의 상호 작용에 사용됩니다.  
  
```  
  
// Call the Add service operation.  
double value1 = 100.00D;  
double value2 = 15.99D;  
double result = channel.Add(value1, value2);  
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
  
```  
  
 샘플을 실행하면 작업 요청 및 응답이 클라이언트 콘솔 창에 표시됩니다.클라이언트를 종료하려면 클라이언트 창에서 Enter 키를 누릅니다.  
  
```  
  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### 샘플을 설치, 빌드 및 실행하려면  
  
1.  [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)를 수행했는지 확인합니다.  
  
2.  C\# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Windows Communication Foundation 샘플 빌드](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.  
  
3.  단일 컴퓨터 또는 다중 컴퓨터 구성에서 샘플을 실행하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)의 지침을 따릅니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.계속하기 전에 다음\(기본\) 디렉터리를 확인하십시오.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780)로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하십시오.이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Binding\Custom\Imperative`  
  
## 참고 항목  
 [Custom Binding](http://msdn.microsoft.com/ko-kr/657e8143-beb0-472d-9cfe-ed1a19c2ab08)