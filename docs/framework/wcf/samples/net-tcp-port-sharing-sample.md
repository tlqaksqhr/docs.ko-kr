---
title: Net.TCP Port Sharing 샘플
ms.date: 03/30/2017
ms.assetid: 03da5959-0574-4e91-8a53-05854b6c55dc
ms.openlocfilehash: cfd87868a5ecc557ccca1003f54f3a896b2f9fcc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="nettcp-port-sharing-sample"></a>Net.TCP Port Sharing 샘플
TCP/IP 프로토콜은 포트라는 16비트 숫자를 사용하여 동일한 컴퓨터에서 실행되는 여러 네트워크 응용 프로그램에 대한 연결을 구분합니다. 응용 프로그램이 포트에서 수신 대기 중이면 이 포트의 모든 TCP 트래픽이 해당 응용 프로그램으로 이동합니다. 다른 응용 프로그램이 동시에 이 포트에서 수신 대기할 수는 없습니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\TCP\PortSharing`  
  
 대부분의 프로토콜은 표준 또는 기본 포트 번호를 사용합니다. 예를 들어 HTTP 프로토콜은 보통 TCP 포트 80을 사용합니다. IIS(인터넷 정보 서비스)에는 여러 HTTP 응용 프로그램 간에 포트를 공유하는 수신기가 있습니다. IIS는 직접 포트에서 수신 대기하고 메시지 스트림에 있는 정보에 따라 적절한 응용 프로그램으로 메시지를 전달합니다. 이렇게 하면 여러 HTTP 응용 프로그램이 메시지 수신 포트를 확보하기 위해 경쟁하지 않고 같은 포트 번호를 사용할 수 있습니다.  
  
 NetTcp 포트 공유는 이와 비슷하게 여러 네트워크 응용 프로그램이 하나의 포트를 공유할 수 있는 Windows Communication Foundation (WCF) 기능입니다. NetTcp 포트 공유 서비스는 net.tcp 프로토콜을 사용하여 연결을 받은 다음 대상 주소를 기준으로 메시지를 전달합니다.  
  
 NetTcp 포트 공유 서비스는 기본적으로 사용되지 않습니다. 이 샘플을 실행하기 전에 수동으로 이 서비스를 사용하도록 설정해야 합니다. 자세한 내용은 참조 [하는 방법: Net.TCP Port Sharing Service를 사용 하도록 설정](../../../../docs/framework/wcf/feature-details/how-to-enable-the-net-tcp-port-sharing-service.md)합니다. 서비스를 사용하지 않으면 서버 응용 프로그램이 시작될 때 예외가 throw됩니다.  
  
```  
Unhandled Exception: System.ServiceModel.CommunicationException: The TransportManager failed to listen on the supplied URI using the NetTcpPortSharing service: failed to start the service because it is disabled. An administrator can enable it by running 'sc.exe config NetTcpPortSharing start= demand'.. ---> System.InvalidOperationException: Cannot start service NetTcpPortSharing on computer '.'. ---> System.ComponentModel.Win32Exception: The service cannot be started, either because it is disabled or because it has no enabled devices associated with it  
```  
  
 포트 공유는 <xref:System.ServiceModel.NetTcpBinding.PortSharingEnabled%2A> 바인딩 또는 <xref:System.ServiceModel.NetTcpBinding> 바인딩 요소의 <xref:System.ServiceModel.Channels.TcpTransportBindingElement> 속성을 설정하여 서버에서 사용하도록 설정합니다. 클라이언트는 서버에서 포트 공유를 사용하도록 구성된 방식에 대해 몰라도 관계 없습니다.  
  
## <a name="enabling-port-sharing"></a>포트 공유 사용  
 다음 코드에서는 서버에서 포트 공유를 사용하는 방법을 보여 줍니다. 여기서는 임의의 URI 경로가 있는 고정 포트에서 `ICalculator` 서비스의 인스턴스를 시작합니다. 두 서비스에서 같은 포트를 공유할 수 있더라도, NetTcp 포트 공유 서비스에서 올바른 응용 프로그램에 메시지를 라우트할 수 있도록 전체 끝점 주소가 고유해야 합니다.  

```csharp
// Configure a binding with TCP port sharing enabled  
NetTcpBinding binding = new NetTcpBinding();  
binding.PortSharingEnabled = true;  
  
// Start a service on a fixed TCP port  
ServiceHost host = new ServiceHost(typeof(CalculatorService));  
ushort salt = (ushort)new Random().Next();  
string address =  
   String.Format("net.tcp://localhost:9000/calculator/{0}", salt);  
host.AddServiceEndpoint(typeof(ICalculator), binding, address);  
host.Open();  
```

 포트 공유가 사용되면 포트 번호 충돌 없이 서비스를 여러 번 실행할 수 있습니다. 코드를 변경하여 포트 공유를 사용하지 않는 경우 서비스의 두 복사본을 시작하면 두 번째 복사본에서 <xref:System.ServiceModel.AddressAlreadyInUseException>이 발생합니다.  
  
```  
Unhandled Exception: System.ServiceModel.AddressAlreadyInUseException: There is already a listener on IP endpoint 0.0.0.0:9000.  Make sure that you are not trying to use this endpoint multiple times in your application and that there are no other applications listening on this endpoint. ---> System.Net.Sockets.SocketException: Only one usage of each socket address (protocol/network address/port) is normally permitted  
```  
  
## <a name="running-the-sample"></a>샘플 실행  
 테스트 클라이언트를 사용하여 메시지가 포트를 공유하는 서비스로 올바르게 라우트되는지 확인할 수 있습니다.  

```csharp
class client  
{  
   static void Main(string[] args)  
   {  
      Console.Write("Enter the service number to test: ");  
      ushort salt = ushort.Parse(Console.ReadLine());  
      string address = String.Format("net.tcp://localhost:9000/calculator/{0}", salt);  
      ChannelFactory<ICalculator> factory = new ChannelFactory<ICalculator>(new NetTcpBinding());  
      ICalculator proxy = factory.CreateChannel(new EndpointAddress(address));  
  
      // Call the Add service operation.  
      double value1 = 100.00D;  
      double value2 = 15.99D;  
      double result = proxy.Add(value1, value2);  
      Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
  
      // Call the Subtract service operation.  
      value1 = 145.00D;  
      value2 = 76.54D;  
      result = proxy.Subtract(value1, value2);  
      Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result);  
  
      // Call the Multiply service operation.  
      value1 = 9.00D;  
      value2 = 81.25D;  
      result = proxy.Multiply(value1, value2);  
      Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result);  
  
      // Call the Divide service operation.  
      value1 = 22.00D;  
      value2 = 7.00D;  
      result = proxy.Divide(value1, value2);  
      Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result);  
  
      Console.WriteLine();  
      Console.WriteLine("Press <ENTER> to terminate client.");  
      Console.ReadLine();  
  
      factory.Close();  
   }  
}  
```

 서비스의 각 인스턴스에서는 고유한 번호와 주소를 인쇄합니다. 예를 들어, service.exe를 실행했을 때 다음 텍스트가 표시될 수 있습니다.  
  
```  
Service #4381 listening on net.tcp://localhost:9000/calculator/4381.  
Press <ENTER> to terminate service.  
```  
  
 client.exe를 실행할 때 여기에 표시된 서비스 번호를 입력합니다.  
  
```  
Enter the service number to test: 4381  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
 클라이언트가 사용하는 생성된 주소를 변경하면 다중 컴퓨터 구성에서도 이 샘플을 실행할 수 있습니다. Client.cs에서 끝점 주소 형식 문자열을 서비스의 새 주소와 일치하도록 변경합니다. "localhost"에 대한 모든 참조를 서버 컴퓨터의 IP 주소로 바꿉니다. 이렇게 변경한 후 샘플을 다시 컴파일해야 합니다.  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1.  다음 명령을 사용하여 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0을 설치합니다.  
  
    ```  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2.  수행 했는지 확인 하십시오.는 [Windows Communication Foundation 샘플의 일회 설치 절차](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)합니다.  
  
3.  소개 단원에서 설명한 것처럼 NetTcp 포트 공유 서비스를 사용합니다.  
  
4.  C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.  
  
5.  지침에 따라 단일 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다. 이 샘플의 실행에 대한 자세한 내용은 앞의 샘플 실행 단원을 참조하십시오.  
  
## <a name="see-also"></a>참고 항목
