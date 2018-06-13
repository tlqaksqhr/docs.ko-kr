---
title: '방법: 검색 프록시를 사용하여 서비스를 찾는 클라이언트 응용 프로그램 구현'
ms.date: 03/30/2017
ms.assetid: 62b41a75-cf40-4c52-a842-a5f1c70e247f
ms.openlocfilehash: 82b38d684d6a8de66d569c6fe09813f8ee1bea6a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33489699"
---
# <a name="how-to-implement-a-client-application-that-uses-the-discovery-proxy-to-find-a-service"></a><span data-ttu-id="6808e-102">방법: 검색 프록시를 사용하여 서비스를 찾는 클라이언트 응용 프로그램 구현</span><span class="sxs-lookup"><span data-stu-id="6808e-102">How to: Implement a Client Application that Uses the Discovery Proxy to Find a Service</span></span>
<span data-ttu-id="6808e-103">이 항목은 검색 프록시를 구현하는 방법에 대해 설명하는 세 항목 중 세 번째 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="6808e-103">This topic is the third of three topics that discusses how to implement a discovery proxy.</span></span> <span data-ttu-id="6808e-104">이전 항목에서 [하는 방법: 검색 프록시에 등록 하는 검색 가능한 서비스 구현](../../../../docs/framework/wcf/feature-details/discoverable-service-that-registers-with-the-discovery-proxy.md), 검색 프록시에 자체를 등록 하는 WCF 서비스를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="6808e-104">In the previous topic, [How to: Implement a Discoverable Service that Registers with the Discovery Proxy](../../../../docs/framework/wcf/feature-details/discoverable-service-that-registers-with-the-discovery-proxy.md), you implemented a WCF service that registers itself with the discovery proxy.</span></span> <span data-ttu-id="6808e-105">이 항목에서는 검색 프록시를 사용 하 여 WCF 서비스를 검색 하는 WCF 클라이언트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6808e-105">In this topic you create a WCF client that uses the discovery proxy to find the WCF service.</span></span>  
  
### <a name="implement-the-client"></a><span data-ttu-id="6808e-106">클라이언트 구현</span><span class="sxs-lookup"><span data-stu-id="6808e-106">Implement the client</span></span>  
  
1.  <span data-ttu-id="6808e-107">`DiscoveryProxyExample` 솔루션에 `Client`라는 새 콘솔 응용 프로그램 프로젝트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6808e-107">Add a new console application project to the `DiscoveryProxyExample` solution called `Client`.</span></span>  
  
2.  <span data-ttu-id="6808e-108">다음 어셈블리에 대한 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6808e-108">Add references to the following assemblies:</span></span>  
  
    1.  <span data-ttu-id="6808e-109">System.ServiceModel</span><span class="sxs-lookup"><span data-stu-id="6808e-109">System.ServiceModel</span></span>  
  
    2.  <span data-ttu-id="6808e-110">System.ServiceModel.Discovery</span><span class="sxs-lookup"><span data-stu-id="6808e-110">System.ServiceModel.Discovery</span></span>  
  
3.  <span data-ttu-id="6808e-111">이 항목 아래쪽의 GeneratedClient.cs를 이 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6808e-111">Add the GeneratedClient.cs found at the bottom of this topic to the project.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6808e-112">일반적으로 이 파일은 Svcutil.exe와 같은 도구를 사용하여 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="6808e-112">This file is usually generated using a tool such as Svcutil.exe.</span></span> <span data-ttu-id="6808e-113">이 파일은 작업을 단순화하기 위해 이 항목에 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="6808e-113">It is provided in this topic to simplify the task.</span></span>  
  
4.  <span data-ttu-id="6808e-114">Program.cs 파일을 열고 다음 메서드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6808e-114">Open the Program.cs file and add the following method.</span></span> <span data-ttu-id="6808e-115">이 메서드는 끝점 주소를 받고 이를 사용하여 서비스 클라이언트(프록시)를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="6808e-115">This method takes an endpoint address and uses it to initialize the service client (proxy).</span></span>  
  
    ```  
    static void InvokeCalculatorService(EndpointAddress endpointAddress)  
            {  
                // Create a client  
                CalculatorServiceClient client = new CalculatorServiceClient(new NetTcpBinding(), endpointAddress);  
                Console.WriteLine("Invoking CalculatorService at {0}", endpointAddress.Uri);  
                Console.WriteLine();  
  
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
  
                // Closing the client gracefully closes the connection and cleans up resources  
                client.Close();  
            }  
    ```  
  
5.  <span data-ttu-id="6808e-116">`Main` 메서드에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6808e-116">Add the following code to the `Main` method.</span></span>  
  
    ```  
    public static void Main()  
            {  
                // Create a DiscoveryEndpoint that points to the DiscoveryProxy  
                Uri probeEndpointAddress = new Uri("net.tcp://localhost:8001/Probe");  
                DiscoveryEndpoint discoveryEndpoint = new DiscoveryEndpoint(new NetTcpBinding(), new EndpointAddress(probeEndpointAddress));  
  
                // Create a DiscoveryClient passing in the discovery endpoint  
                DiscoveryClient discoveryClient = new DiscoveryClient(discoveryEndpoint);  
  
                Console.WriteLine("Finding ICalculatorService endpoints using the proxy at {0}", probeEndpointAddress);  
                Console.WriteLine();  
  
                try  
                {  
                    // Search for services that implement ICalculatorService              
                    FindResponse findResponse = discoveryClient.Find(new FindCriteria(typeof(ICalculatorService)));  
  
                    Console.WriteLine("Found {0} ICalculatorService endpoint(s).", findResponse.Endpoints.Count);  
                    Console.WriteLine();  
  
                    // Check to see if endpoints were found, if so then invoke the service.  
                    if (findResponse.Endpoints.Count > 0)  
                    {  
                        InvokeCalculatorService(findResponse.Endpoints[0].Address);  
                    }  
                }  
                catch (TargetInvocationException)  
                {  
                    Console.WriteLine("This client was unable to connect to and query the proxy. Ensure that the proxy is up and running.");  
                }  
  
                Console.WriteLine("Press <ENTER> to exit.");  
                Console.ReadLine();  
            }  
    ```  
  
 <span data-ttu-id="6808e-117">클라이언트 응용 프로그램의 구현을 완료했습니다.</span><span class="sxs-lookup"><span data-stu-id="6808e-117">You have completed implementing the client application.</span></span> <span data-ttu-id="6808e-118">계속 진행 하 [하는 방법: 검색 프록시 테스트](../../../../docs/framework/wcf/feature-details/how-to-test-the-discovery-proxy.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6808e-118">Continue on to [How to: Test the Discovery Proxy](../../../../docs/framework/wcf/feature-details/how-to-test-the-discovery-proxy.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6808e-119">예제</span><span class="sxs-lookup"><span data-stu-id="6808e-119">Example</span></span>  
 <span data-ttu-id="6808e-120">다음은 이 항목에서 사용되는 전체 코드 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="6808e-120">This is the full code listing for this topic.</span></span>  
  
```  
// GeneratedClient.cs  
//----------------------------------------------------------------  
// Copyright (c) Microsoft Corporation.  All rights reserved.  
//----------------------------------------------------------------  
//------------------------------------------------------------------------------  
// <auto-generated>  
//     This code was generated by a tool.  
//     Runtime Version:2.0.50727.1434  
//  
//     Changes to this file may cause incorrect behavior and will be lost if  
//     the code is regenerated.  
// </auto-generated>  
//------------------------------------------------------------------------------  
  
namespace Microsoft.Samples.Discovery  
{  
    [System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "4.0.0.0")]  
    [System.ServiceModel.ServiceContractAttribute(Namespace = "http://Microsoft.Samples.Discovery", ConfigurationName = "ICalculatorService")]  
    public interface ICalculatorService  
    {  
  
        [System.ServiceModel.OperationContractAttribute(ProtectionLevel = System.Net.Security.ProtectionLevel.EncryptAndSign, Action = "http://Microsoft.Samples.Discovery/ICalculatorService/Add", ReplyAction = "http://Microsoft.Samples.Discovery/ICalculatorService/AddResponse")]  
        double Add(double n1, double n2);  
  
        [System.ServiceModel.OperationContractAttribute(ProtectionLevel = System.Net.Security.ProtectionLevel.EncryptAndSign, Action = "http://Microsoft.Samples.Discovery/ICalculatorService/Subtract", ReplyAction = "http://Microsoft.Samples.Discovery/ICalculatorService/SubtractResponse")]  
        double Subtract(double n1, double n2);  
  
        [System.ServiceModel.OperationContractAttribute(ProtectionLevel = System.Net.Security.ProtectionLevel.EncryptAndSign, Action = "http://Microsoft.Samples.Discovery/ICalculatorService/Multiply", ReplyAction = "http://Microsoft.Samples.Discovery/ICalculatorService/MultiplyResponse")]  
        double Multiply(double n1, double n2);  
  
        [System.ServiceModel.OperationContractAttribute(ProtectionLevel = System.Net.Security.ProtectionLevel.EncryptAndSign, Action = "http://Microsoft.Samples.Discovery/ICalculatorService/Divide", ReplyAction = "http://Microsoft.Samples.Discovery/ICalculatorService/DivideResponse")]  
        double Divide(double n1, double n2);  
    }  
  
    [System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "4.0.0.0")]  
    public interface ICalculatorServiceChannel : ICalculatorService, System.ServiceModel.IClientChannel  
    {  
    }  
  
    [System.Diagnostics.DebuggerStepThroughAttribute()]  
    [System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "4.0.0.0")]  
    public partial class CalculatorServiceClient : System.ServiceModel.ClientBase<ICalculatorService>, ICalculatorService  
    {  
  
        public CalculatorServiceClient()  
        {  
        }  
  
        public CalculatorServiceClient(string endpointConfigurationName) :  
            base(endpointConfigurationName)  
        {  
        }  
  
        public CalculatorServiceClient(string endpointConfigurationName, string remoteAddress) :  
            base(endpointConfigurationName, remoteAddress)  
        {  
        }  
  
        public CalculatorServiceClient(string endpointConfigurationName, System.ServiceModel.EndpointAddress remoteAddress) :  
            base(endpointConfigurationName, remoteAddress)  
        {  
        }  
  
        public CalculatorServiceClient(System.ServiceModel.Channels.Binding binding, System.ServiceModel.EndpointAddress remoteAddress) :  
            base(binding, remoteAddress)  
        {  
        }  
  
        public double Add(double n1, double n2)  
        {  
            return base.Channel.Add(n1, n2);  
        }  
  
        public double Subtract(double n1, double n2)  
        {  
            return base.Channel.Subtract(n1, n2);  
        }  
  
        public double Multiply(double n1, double n2)  
        {  
            return base.Channel.Multiply(n1, n2);  
        }  
  
        public double Divide(double n1, double n2)  
        {  
            return base.Channel.Divide(n1, n2);  
        }  
    }  
}  
```  
  
```  
// Program.cs  
//----------------------------------------------------------------  
// Copyright (c) Microsoft Corporation.  All rights reserved.  
//----------------------------------------------------------------  
  
using System;  
using System.Reflection;  
using System.ServiceModel;  
using System.ServiceModel.Discovery;  
  
namespace Microsoft.Samples.Discovery  
{  
    class Client  
    {  
        public static void Main()  
        {  
            // Create a DiscoveryEndpoint that points to the DiscoveryProxy  
            Uri probeEndpointAddress = new Uri("net.tcp://localhost:8001/Probe");  
            DiscoveryEndpoint discoveryEndpoint = new DiscoveryEndpoint(new NetTcpBinding(), new EndpointAddress(probeEndpointAddress));  
  
            DiscoveryClient discoveryClient = new DiscoveryClient(discoveryEndpoint);  
  
            Console.WriteLine("Finding ICalculatorService endpoints using the proxy at {0}", probeEndpointAddress);  
            Console.WriteLine();  
  
            try  
            {  
                // Find ICalculatorService endpoints              
                FindResponse findResponse = discoveryClient.Find(new FindCriteria(typeof(ICalculatorService)));  
  
                Console.WriteLine("Found {0} ICalculatorService endpoint(s).", findResponse.Endpoints.Count);  
                Console.WriteLine();  
  
                // Check to see if endpoints were found, if so then invoke the service.  
                if (findResponse.Endpoints.Count > 0)  
                {  
                    InvokeCalculatorService(findResponse.Endpoints[0].Address);  
                }  
            }  
            catch (TargetInvocationException)  
            {  
                Console.WriteLine("This client was unable to connect to and query the proxy. Ensure that the proxy is up and running.");  
            }  
  
            Console.WriteLine("Press <ENTER> to exit.");  
            Console.ReadLine();  
        }  
  
        static void InvokeCalculatorService(EndpointAddress endpointAddress)  
        {  
            // Create a client  
            CalculatorServiceClient client = new CalculatorServiceClient(new NetTcpBinding(), endpointAddress);  
            Console.WriteLine("Invoking CalculatorService at {0}", endpointAddress.Uri);  
            Console.WriteLine();  
  
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
  
            // Closing the client gracefully closes the connection and cleans up resources  
            client.Close();  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="6808e-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6808e-121">See Also</span></span>  
 [<span data-ttu-id="6808e-122">WCF 검색 개요</span><span class="sxs-lookup"><span data-stu-id="6808e-122">WCF Discovery Overview</span></span>](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)  
 [<span data-ttu-id="6808e-123">방법: 검색 프록시 구현</span><span class="sxs-lookup"><span data-stu-id="6808e-123">How to: Implement a Discovery Proxy</span></span>](../../../../docs/framework/wcf/feature-details/how-to-implement-a-discovery-proxy.md)  
 [<span data-ttu-id="6808e-124">방법: 검색 프록시에 등록할 검색 가능한 서비스 구현</span><span class="sxs-lookup"><span data-stu-id="6808e-124">How to: Implement a Discoverable Service that Registers with the Discovery Proxy</span></span>](../../../../docs/framework/wcf/feature-details/discoverable-service-that-registers-with-the-discovery-proxy.md)
