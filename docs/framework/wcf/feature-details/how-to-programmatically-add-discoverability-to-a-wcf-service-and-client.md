---
title: "방법: 프로그래밍 방식으로 WCF 서비스 및 클라이언트에 검색 기능 추가 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4f7ae7ab-6fc8-4769-9730-c14d43f7b9b1
caps.latest.revision: 13
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 13
---
# 방법: 프로그래밍 방식으로 WCF 서비스 및 클라이언트에 검색 기능 추가
이 항목에서는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 서비스를 검색 가능하게 만드는 방법에 대해 설명하며, 기반으로 [Self-host](http://go.microsoft.com/fwlink/?LinkId=145523) 샘플입니다.  
  
### <a name="to-configure-the-existing-self-host-service-sample-for-discovery"></a>기존 자체 호스팅 서비스 샘플을 검색용으로 구성하려면  
  
1.  [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]에서 자체 호스트 솔루션을 엽니다. 샘플은 TechnologySamples\Basic\Service\Hosting\SelfHost 디렉터리에 있습니다.  
  
2.  서비스 프로젝트에 `System.ServiceModel.Discovery.dll`에 대한 참조를 추가합니다. “System.ServiceModel.Discovery.dll 또는 항목 또는 해당 종속성 중 하나를 하려면 최신 버전의는 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] ... 프로젝트에 지정 된 것 " 이 메시지를 표시 하는 경우 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 선택 **속성**합니다. 에 **프로젝트 속성** 창에서 다음 사항을 확인는 **대상 프레임 워크** 는 [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].  
  
3.  Service.cs 파일을 열고 다음 `using` 문을 추가합니다.  
  
    ```  
    using System.ServiceModel.Discovery;  
    ```  
  
4.  에 `Main()` 메서드, 내부는 `using` 문, 추가 <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> 인스턴스를 서비스 호스트입니다.  
  
    ```  
    public static void Main()  
    {  
        // Create a ServiceHost for the CalculatorService type.  
        using (ServiceHost serviceHost = new ServiceHost(typeof(CalculatorService)))  
        {  
            // Add a ServiceDiscoveryBehavior  
            serviceHost.Description.Behaviors.Add(new ServiceDiscoveryBehavior());                  
  
            // ...  
        }  
    }  
    ```  
  
     <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> 에 적용 되는 서비스가 검색 가능 임을 지정 합니다.  
  
5.  추가 <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> 서비스 호스트를 추가 하는 코드 바로 뒤에 <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>합니다.  
  
    ```  
    // Add ServiceDiscoveryBehavior  
    serviceHost.Description.Behaviors.Add(new ServiceDiscoveryBehavior());  
  
    // Add a UdpDiscoveryEndpoint  
    serviceHost.AddServiceEndpoint(new UdpDiscoveryEndpoint());  
    ```  
  
     이 코드는 검색 메시지를 표준 UDP 검색 끝점에 보내도록 지정합니다.  
  
### <a name="to-create-a-client-application-that-uses-discovery-to-call-the-service"></a>검색을 사용하는 클라이언트 응용 프로그램을 만들어 서비스를 호출하려면  
  
1.  `DiscoveryClientApp`라는 솔루션에 새 콘솔 응용 프로그램을 추가합니다.  
  
2.  `System.ServiceModel.dll` 및 `System.ServiceModel.Discovery.dll`에 대한 참조를 추가합니다.  
  
3.  GeneratedClient.cs 및 App.config 파일을 기본 클라이언트 프로젝트에서 새 DiscoveryClientApp 프로젝트로 복사합니다. 이 위해 파일을 마우스 오른쪽 단추로 **솔루션 탐색기**선택, **복사**를 선택한 다음는 **DiscoveryClientApp** 프로젝트 마우스 오른쪽 단추로 클릭 한 다음 선택 **붙여넣기**합니다.  
  
4.  Program.cs를 엽니다.  
  
5.  다음 `using` 문을 추가합니다.  
  
    ```  
    using System.ServiceModel;  
    using System.ServiceModel.Discovery;  
    using Microsoft.ServiceModel.Samples;  
  
    ```  
  
6.  `FindCalculatorServiceAddress()`라는 정적 메서드를 `Program` 클래스에 추가합니다.  
  
    ```  
    static EndpointAddress FindCalculatorServiceAddress()  
    {  
    }  
    ```  
  
     이 메서드는 검색을 사용하여 `CalculatorService` 서비스를 찾습니다.  
  
7.  내부는 `FindCalculatorServiceAddress` 메서드를 새 <xref:System.ServiceModel.Discovery.DiscoveryClient> 전달 인스턴스는 <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> 생성자에 있습니다.  
  
    ```  
    static EndpointAddress FindCalculatorServiceAddress()  
    {  
        // Create DiscoveryClient  
        DiscoveryClient discoveryClient = new DiscoveryClient(new UdpDiscoveryEndpoint());  
    }  
    ```  
  
     이 코드를 통해 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 하는 <xref:System.ServiceModel.Discovery.DiscoveryClient> 클래스 검색 메시지를 받거나 보내기 위해 표준 UDP 검색 끝점을 사용 해야 합니다.  
  
8.  다음 줄에서 호출는 <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> 메서드를 지정 하 고는 <xref:System.ServiceModel.Discovery.FindCriteria> 인스턴스를 검색 하려는 서비스 계약이 포함 된 합니다. 이 경우 `ICalculator`를 지정합니다.  
  
    ```  
    // Find ICalculatorService endpoints              
    FindResponse findResponse = discoveryClient.Find(new FindCriteria(typeof(ICalculator)));  
    ```  
  
9. 호출한 후 <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A>에 일치 하는 서비스가 하나 이상 있는지 확인 하 고 반환 된 <xref:System.ServiceModel.EndpointAddress> 첫 번째 일치 하는 서비스의 합니다. 그렇지 않으면 `null`을 반환합니다.  
  
    ```  
    if (findResponse.Endpoints.Count > 0)  
    {  
        return findResponse.Endpoints[0].Address;  
    }  
    else  
    {  
        return null;  
    }  
    ```  
  
10. `InvokeCalculatorService`라는 정적 메서드를 `Program` 클래스에 추가합니다.  
  
    ```  
    static void InvokeCalculatorService(EndpointAddress endpointAddress)  
    {  
    }  
    ```  
  
     이 메서드는 `FindCalculatorServiceAddress`에서 반환되는 끝점 주소를 사용하여 계산기 서비스를 호출합니다.  
  
11. `InvokeCalculatorService` 메서드 안에서 `CalculatorServiceClient` 클래스의 인스턴스를 만듭니다. 이 클래스에서 정의 됩니다는 [Self-host](http://go.microsoft.com/fwlink/?LinkId=145523) 샘플입니다. 이 클래스는 Svcutil.exe를 사용하여 생성되었습니다.  
  
    ```  
    // Create a client  
    CalculatorClient client = new CalculatorClient();  
    ```  
  
12. 다음 줄에서 클라이언트의 끝점 주소를 `FindCalculatorServiceAddress()`에서 반환되는 끝점 주소로 설정합니다.  
  
    ```  
    // Connect to the discovered service endpoint  
    client.Endpoint.Address = endpointAddress;  
    ```  
  
13. 이전 단계의 코드 바로 뒤에서 계산기 서비스에 의해 노출되는 메서드를 호출합니다.  
  
    ```  
    Console.WriteLine("Invoking CalculatorService at {0}", endpointAddress);  
  
    double value1 = 100.00D;  
    double value2 = 15.99D;  
  
    // Call the Add service operation.  
    double result = client.Add(value1, value2);  
    Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
  
    // Call the Subtract service operation.  
    result = client.Subtract(value1, value2);  
    Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result);  
  
    // Call the Multiply service operation.  
    result = client.Multiply(value1, value2);  
    Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result);  
  
    // Call the Divide service operation.  
    result = client.Divide(value1, value2);  
    Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result);  
    Console.WriteLine();  
  
    //Closing the client gracefully closes the connection and cleans up resources  
    client.Close();  
    ```  
  
14. `Main()` 클래스의 `Program` 메서드에 `FindCalculatorServiceAddress`를 호출하는 코드를 추가합니다.  
  
    ```  
    public static void Main()  
    {  
        EndpointAddress endpointAddress = FindCalculatorServiceAddress();  
    }  
    ```  
  
15. 다음 줄에서 `InvokeCalculatorService()`를 호출하고 `FindCalculatorServiceAddress()`에서 반환되는 끝점 주소를 전달합니다.  
  
    ```  
    if (endpointAddress != null)  
    {  
        InvokeCalculatorService(endpointAddress);  
    }  
  
    Console.WriteLine("Press <ENTER> to exit.");  
    Console.ReadLine();  
    ```  
  
### <a name="to-test-the-application"></a>응용 프로그램을 테스트하려면  
  
1.  권한이 높은 명령 프롬프트를 열고 Service.exe를 실행합니다.  
  
2.  명령 프롬프트를 열고 Discoveryclientapp.exe를 실행합니다.  
  
3.  service.exe의 출력이 다음과 같이 표시됩니다.  
  
    ```Output  
    Received Add(100,15.99)  
    Return: 115.99  
    Received Subtract(100,15.99)  
    Return: 84.01  
    Received Multiply(100,15.99)  
    Return: 1599  
    Received Divide(100,15.99)  
    Return: 6.25390869293308  
    ```  
  
4.  Discoveryclientapp.exe의 출력이 다음과 같이 표시됩니다.  
  
    ```Output  
    Invoking CalculatorService at http://localhost:8000/ServiceModelSamples/service  
    Add(100,15.99) = 115.99  
    Subtract(100,15.99) = 84.01  
    Multiply(100,15.99) = 1599  
    Divide(100,15.99) = 6.25390869293308  
  
    Press <ENTER> to exit.  
    ```  
  
## <a name="example"></a>예제  
 다음은 이 샘플의 코드 목록입니다. 이 코드는 기반는 [Self-host](http://go.microsoft.com/fwlink/?LinkId=145523) 샘플에 변경 된 파일만 나열 됩니다. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Self-host 샘플 참조 [설치 지침은](http://go.microsoft.com/fwlink/?LinkId=145522)합니다.  
  
```  
  
// Service.cs  
using System;  
using System.Configuration;  
using System.ServiceModel;  
using System.ServiceModel.Discovery;  
  
namespace Microsoft.ServiceModel.Samples  
{  
    // See SelfHost sample for service contract and implementation  
    // ...  
  
        // Host the service within this EXE console application.  
        public static void Main()  
        {  
            // Create a ServiceHost for the CalculatorService type.  
            using (ServiceHost serviceHost = new ServiceHost(typeof(CalculatorService)))  
            {  
                // Add the ServiceDiscoveryBehavior to make the service discoverable  
                serviceHost.Description.Behaviors.Add(new ServiceDiscoveryBehavior());  
                serviceHost.AddServiceEndpoint(new UdpDiscoveryEndpoint());  
  
                // Open the ServiceHost to create listeners and start listening for messages.  
                serviceHost.Open();  
  
                // The service can now be accessed.  
                Console.WriteLine("The service is ready.");  
                Console.WriteLine("Press <ENTER> to terminate service.");  
                Console.WriteLine();  
                Console.ReadLine();  
            }  
        }  
    }  
}  
```  
  
```  
// Program.cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.ServiceModel;  
using System.ServiceModel.Discovery;  
using Microsoft.ServiceModel.Samples;  
using System.Text;  
  
namespace DiscoveryClientApp  
{  
    class Program  
    {  
        static EndpointAddress FindCalculatorServiceAddress()  
        {  
            // Create DiscoveryClient  
            DiscoveryClient discoveryClient = new DiscoveryClient(new UdpDiscoveryEndpoint());  
  
            // Find ICalculatorService endpoints              
            FindResponse findResponse = discoveryClient.Find(new FindCriteria(typeof(ICalculator)));  
  
            if (findResponse.Endpoints.Count > 0)  
            {  
                return findResponse.Endpoints[0].Address;  
            }  
            else  
            {  
                return null;  
            }  
        }  
  
        static void InvokeCalculatorService(EndpointAddress endpointAddress)  
        {  
            // Create a client  
            CalculatorClient client = new CalculatorClient();  
  
            // Connect to the discovered service endpoint  
            client.Endpoint.Address = endpointAddress;  
  
            Console.WriteLine("Invoking CalculatorService at {0}", endpointAddress);  
  
            double value1 = 100.00D;  
            double value2 = 15.99D;  
  
            // Call the Add service operation.  
            double result = client.Add(value1, value2);  
            Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
  
            // Call the Subtract service operation.  
            result = client.Subtract(value1, value2);  
            Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result);  
  
            // Call the Multiply service operation.  
            result = client.Multiply(value1, value2);  
            Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result);  
  
            // Call the Divide service operation.  
            result = client.Divide(value1, value2);  
            Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result);  
            Console.WriteLine();  
  
            //Closing the client gracefully closes the connection and cleans up resources  
            client.Close();  
        }  
        static void Main(string[] args)  
        {  
            EndpointAddress endpointAddress = FindCalculatorServiceAddress();  
  
            if (endpointAddress != null)  
            {  
                InvokeCalculatorService(endpointAddress);  
            }  
  
            Console.WriteLine("Press <ENTER> to exit.");  
            Console.ReadLine();  
  
        }  
    }  
}  
```  
  
<!-- TODO: review snippet reference  [!CODE [Microsoft.Win32.RegistryKey#4](Microsoft.Win32.RegistryKey#4)]  -->  
  
## <a name="see-also"></a>참고 항목  
 [WCF Discovery 개요](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)   
 [WCF Discovery 개체 모델](../../../../docs/framework/wcf/feature-details/wcf-discovery-object-model.md)