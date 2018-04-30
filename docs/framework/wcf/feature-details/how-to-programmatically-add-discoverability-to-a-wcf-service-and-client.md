---
title: '방법: 프로그래밍 방식으로 WCF 서비스 및 클라이언트에 검색 기능 추가'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4f7ae7ab-6fc8-4769-9730-c14d43f7b9b1
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3c0da3598b115df4f135ac3fab516447df85e258
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/30/2018
---
# <a name="how-to-programmatically-add-discoverability-to-a-wcf-service-and-client"></a><span data-ttu-id="909df-102">방법: 프로그래밍 방식으로 WCF 서비스 및 클라이언트에 검색 기능 추가</span><span class="sxs-lookup"><span data-stu-id="909df-102">How to: Programmatically Add Discoverability to a WCF Service and Client</span></span>
<span data-ttu-id="909df-103">이 항목에서는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 서비스를 검색 가능하게 만드는 방법에 대해 설명하며,</span><span class="sxs-lookup"><span data-stu-id="909df-103">This topic explains how to make a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service discoverable.</span></span> <span data-ttu-id="909df-104">에 기반 하는 고 [자체 호스트](http://go.microsoft.com/fwlink/?LinkId=145523) 샘플.</span><span class="sxs-lookup"><span data-stu-id="909df-104">It is based on the [Self-Host](http://go.microsoft.com/fwlink/?LinkId=145523) sample.</span></span>  
  
### <a name="to-configure-the-existing-self-host-service-sample-for-discovery"></a><span data-ttu-id="909df-105">기존 자체 호스팅 서비스 샘플을 검색용으로 구성하려면</span><span class="sxs-lookup"><span data-stu-id="909df-105">To configure the existing Self-Host service sample for Discovery</span></span>  
  
1.  <span data-ttu-id="909df-106">[!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]에서 자체 호스트 솔루션을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="909df-106">Open the Self-Host solution in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span></span> <span data-ttu-id="909df-107">샘플은 TechnologySamples\Basic\Service\Hosting\SelfHost 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="909df-107">The sample is located in the TechnologySamples\Basic\Service\Hosting\SelfHost directory.</span></span>  
  
2.  <span data-ttu-id="909df-108">서비스 프로젝트에 `System.ServiceModel.Discovery.dll`에 대한 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="909df-108">Add a reference to `System.ServiceModel.Discovery.dll` to the service project.</span></span> <span data-ttu-id="909df-109">"시스템 라는 오류 메시지가 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="909df-109">You may see an error message saying "System.</span></span> <span data-ttu-id="909df-110">라는 또는 해당 종속성 중 하나를 하려면 최신 버전의는 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] ... 프로젝트에 지정 된 "</span><span class="sxs-lookup"><span data-stu-id="909df-110">ServiceModel.Discovery.dll or one of its dependencies requires a later version of the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] than the one specified in the project …"</span></span> <span data-ttu-id="909df-111">이 메시지가 나타나는 경우 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 선택 **속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="909df-111">If you see this message, right-click the project in the Solution Explorer and choose **Properties**.</span></span> <span data-ttu-id="909df-112">에 **프로젝트 속성** 창 있는지 확인은 **대상 프레임 워크** 은 [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="909df-112">In the **Project Properties** window, make sure that the **Target Framework** is [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].</span></span>  
  
3.  <span data-ttu-id="909df-113">Service.cs 파일을 열고 다음 `using` 문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="909df-113">Open the Service.cs file and add the following `using` statement.</span></span>  
  
    ```csharp  
    using System.ServiceModel.Discovery;  
    ```  
  
4.  <span data-ttu-id="909df-114">`Main()` 메서드의 `using` 문 안에서 서비스 호스트에 <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> 인스턴스를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="909df-114">In the `Main()` method, inside the `using` statement, add a <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> instance to the service host.</span></span>  
  
    ```csharp  
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
  
     <span data-ttu-id="909df-115"><xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>는 자신이 적용되는 서비스가 검색 가능하게 되도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="909df-115">The <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> specifies that the service it is applied to is discoverable.</span></span>  
  
5.  <span data-ttu-id="909df-116"><xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint>를 추가하는 코드 바로 뒤에 있는 서비스 호스트에 <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="909df-116">Add a <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> to the service host right after the code that adds the <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>.</span></span>  
  
    ```csharp  
    // Add ServiceDiscoveryBehavior  
    serviceHost.Description.Behaviors.Add(new ServiceDiscoveryBehavior());  
  
    // Add a UdpDiscoveryEndpoint  
    serviceHost.AddServiceEndpoint(new UdpDiscoveryEndpoint());  
    ```  
  
     <span data-ttu-id="909df-117">이 코드는 검색 메시지를 표준 UDP 검색 끝점에 보내도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="909df-117">This code specifies that discovery messages should be sent to the standard UDP discovery endpoint.</span></span>  
  
### <a name="to-create-a-client-application-that-uses-discovery-to-call-the-service"></a><span data-ttu-id="909df-118">검색을 사용하는 클라이언트 응용 프로그램을 만들어 서비스를 호출하려면</span><span class="sxs-lookup"><span data-stu-id="909df-118">To create a client application that uses discovery to call the service</span></span>  
  
1.  <span data-ttu-id="909df-119">`DiscoveryClientApp`라는 솔루션에 새 콘솔 응용 프로그램을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="909df-119">Add a new console application to the solution called `DiscoveryClientApp`.</span></span>  
  
2.  <span data-ttu-id="909df-120">`System.ServiceModel.dll` 및 `System.ServiceModel.Discovery.dll`에 대한 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="909df-120">Add a reference to `System.ServiceModel.dll` and `System.ServiceModel.Discovery.dll`</span></span>  
  
3.  <span data-ttu-id="909df-121">GeneratedClient.cs 및 App.config 파일을 기본 클라이언트 프로젝트에서 새 DiscoveryClientApp 프로젝트로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="909df-121">Copy the GeneratedClient.cs and App.config files from the existing client project to the new DiscoveryClientApp project.</span></span> <span data-ttu-id="909df-122">이 수행 하려면에 있는 파일을 마우스 오른쪽 단추로 **솔루션 탐색기**선택, **복사**를 선택한 후는 **DiscoveryClientApp** 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 마우스 선택**붙여넣기**합니다.</span><span class="sxs-lookup"><span data-stu-id="909df-122">To do this, right-click the files in the **Solution Explorer**, select **Copy**, and then select the **DiscoveryClientApp** project, right-click and select **Paste**.</span></span>  
  
4.  <span data-ttu-id="909df-123">Program.cs를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="909df-123">Open Program.cs.</span></span>  
  
5.  <span data-ttu-id="909df-124">다음 `using` 문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="909df-124">Add the following `using` statements.</span></span>  
  
    ```csharp  
    using System.ServiceModel;  
    using System.ServiceModel.Discovery;  
    using Microsoft.ServiceModel.Samples;  
    ```  
  
6.  <span data-ttu-id="909df-125">`FindCalculatorServiceAddress()`라는 정적 메서드를 `Program` 클래스에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="909df-125">Add a static method called `FindCalculatorServiceAddress()` to the `Program` class.</span></span>  
  
    ```csharp  
    static EndpointAddress FindCalculatorServiceAddress()  
    {  
    }  
    ```  
  
     <span data-ttu-id="909df-126">이 메서드는 검색을 사용하여 `CalculatorService` 서비스를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="909df-126">This method uses discovery to search for the `CalculatorService` service.</span></span>  
  
7.  <span data-ttu-id="909df-127">`FindCalculatorServiceAddress` 메서드 안에서 생성자에 <xref:System.ServiceModel.Discovery.DiscoveryClient>를 전달하여 새 <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="909df-127">Inside the `FindCalculatorServiceAddress` method, create a new <xref:System.ServiceModel.Discovery.DiscoveryClient> instance, passing in a <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> to the constructor.</span></span>  
  
    ```csharp  
    static EndpointAddress FindCalculatorServiceAddress()  
    {  
        // Create DiscoveryClient  
        DiscoveryClient discoveryClient = new DiscoveryClient(new UdpDiscoveryEndpoint());  
    }  
    ```  
  
     <span data-ttu-id="909df-128">이렇게 하면 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클래스에서 표준 UDP 검색 끝점을 사용하여 검색 메시지를 보내고 받아야 한다는 내용이 <xref:System.ServiceModel.Discovery.DiscoveryClient>에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="909df-128">This tells [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] that the <xref:System.ServiceModel.Discovery.DiscoveryClient> class should use the standard UDP discovery endpoint to send and receive discovery messages.</span></span>  
  
8.  <span data-ttu-id="909df-129">다음 줄에서 <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> 메서드를 호출하고 검색하려는 서비스 계약이 포함된 <xref:System.ServiceModel.Discovery.FindCriteria> 인스턴스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="909df-129">On the next line, call the <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> method and specify a <xref:System.ServiceModel.Discovery.FindCriteria> instance that contains the service contract you want to search for.</span></span> <span data-ttu-id="909df-130">이 경우 `ICalculator`를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="909df-130">In this case, specify `ICalculator`.</span></span>  
  
    ```csharp  
    // Find ICalculatorService endpoints              
    FindResponse findResponse = discoveryClient.Find(new FindCriteria(typeof(ICalculator)));  
    ```  
  
9. <span data-ttu-id="909df-131"><xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A>를 호출한 후 일치하는 서비스가 하나 이상 있는지 확인하고 첫 번째 일치하는 서비스의 <xref:System.ServiceModel.EndpointAddress>를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="909df-131">After the call to <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A>, check to see if there is at least one matching service and return the <xref:System.ServiceModel.EndpointAddress> of the first matching service.</span></span> <span data-ttu-id="909df-132">그렇지 않으면 `null`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="909df-132">Otherwise return `null`.</span></span>  
  
    ```csharp  
    if (findResponse.Endpoints.Count > 0)  
    {  
        return findResponse.Endpoints[0].Address;  
    }  
    else  
    {  
        return null;  
    }  
    ```  
  
10. <span data-ttu-id="909df-133">`InvokeCalculatorService`라는 정적 메서드를 `Program` 클래스에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="909df-133">Add a static method named `InvokeCalculatorService` to the `Program` class.</span></span>  
  
    ```csharp  
    static void InvokeCalculatorService(EndpointAddress endpointAddress)  
    {  
    }  
    ```  
  
     <span data-ttu-id="909df-134">이 메서드는 `FindCalculatorServiceAddress`에서 반환되는 끝점 주소를 사용하여 계산기 서비스를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="909df-134">This method uses the endpoint address returned from `FindCalculatorServiceAddress` to call the calculator service.</span></span>  
  
11. <span data-ttu-id="909df-135">`InvokeCalculatorService` 메서드 안에서 `CalculatorServiceClient` 클래스의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="909df-135">Inside the `InvokeCalculatorService` method, create an instance of the `CalculatorServiceClient` class.</span></span> <span data-ttu-id="909df-136">이 클래스는 여 정의 되는 [자체 호스트](http://go.microsoft.com/fwlink/?LinkId=145523) 샘플.</span><span class="sxs-lookup"><span data-stu-id="909df-136">This class is defined by the [Self-Host](http://go.microsoft.com/fwlink/?LinkId=145523) sample.</span></span> <span data-ttu-id="909df-137">이 클래스는 Svcutil.exe를 사용하여 생성되었습니다.</span><span class="sxs-lookup"><span data-stu-id="909df-137">It was generated using Svcutil.exe.</span></span>  
  
    ```csharp  
    // Create a client  
    CalculatorClient client = new CalculatorClient();  
    ```  
  
12. <span data-ttu-id="909df-138">다음 줄에서 클라이언트의 끝점 주소를 `FindCalculatorServiceAddress()`에서 반환되는 끝점 주소로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="909df-138">On the next line, set the endpoint address of the client to the endpoint address returned from `FindCalculatorServiceAddress()`.</span></span>  
  
    ```csharp  
    // Connect to the discovered service endpoint  
    client.Endpoint.Address = endpointAddress;  
    ```  
  
13. <span data-ttu-id="909df-139">이전 단계의 코드 바로 뒤에서 계산기 서비스에 의해 노출되는 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="909df-139">Immediately after the code for the previous step, call the methods exposed by the calculator service.</span></span>  
  
    ```csharp  
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
  
14. <span data-ttu-id="909df-140">`Main()` 클래스의 `Program` 메서드에 `FindCalculatorServiceAddress`를 호출하는 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="909df-140">Add code to the `Main()` method in the `Program` class to call `FindCalculatorServiceAddress`.</span></span>  
  
    ```csharp  
    public static void Main()  
    {  
        EndpointAddress endpointAddress = FindCalculatorServiceAddress();  
    }  
    ```  
  
15. <span data-ttu-id="909df-141">다음 줄에서 `InvokeCalculatorService()`를 호출하고 `FindCalculatorServiceAddress()`에서 반환되는 끝점 주소를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="909df-141">On the next line, call the `InvokeCalculatorService()` and pass in the endpoint address returned from `FindCalculatorServiceAddress()`.</span></span>  
  
    ```csharp  
    if (endpointAddress != null)  
    {  
        InvokeCalculatorService(endpointAddress);  
    }  
  
    Console.WriteLine("Press <ENTER> to exit.");  
    Console.ReadLine();  
    ```  
  
### <a name="to-test-the-application"></a><span data-ttu-id="909df-142">응용 프로그램을 테스트하려면</span><span class="sxs-lookup"><span data-stu-id="909df-142">To test the application</span></span>  
  
1.  <span data-ttu-id="909df-143">권한이 높은 명령 프롬프트를 열고 Service.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="909df-143">Open an elevated command prompt and run Service.exe.</span></span>  
  
2.  <span data-ttu-id="909df-144">명령 프롬프트를 열고 Discoveryclientapp.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="909df-144">Open a command prompt and run Discoveryclientapp.exe.</span></span>  
  
3.  <span data-ttu-id="909df-145">service.exe의 출력이 다음과 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="909df-145">The output from service.exe should look like the following output.</span></span>  
  
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
  
4.  <span data-ttu-id="909df-146">Discoveryclientapp.exe의 출력이 다음과 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="909df-146">The output from Discoveryclientapp.exe should look like the following output.</span></span>  
  
    ```Output  
    Invoking CalculatorService at http://localhost:8000/ServiceModelSamples/service  
    Add(100,15.99) = 115.99  
    Subtract(100,15.99) = 84.01  
    Multiply(100,15.99) = 1599  
    Divide(100,15.99) = 6.25390869293308  
  
    Press <ENTER> to exit.  
    ```  
  
## <a name="example"></a><span data-ttu-id="909df-147">예제</span><span class="sxs-lookup"><span data-stu-id="909df-147">Example</span></span>  
 <span data-ttu-id="909df-148">다음은 이 샘플의 코드 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="909df-148">The following is a listing of the code for this sample.</span></span> <span data-ttu-id="909df-149">이 코드에 기반 하므로 [자체 호스트](http://go.microsoft.com/fwlink/?LinkId=145523) 샘플에 변경 된 파일이 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="909df-149">Because this code is based on the [Self-Host](http://go.microsoft.com/fwlink/?LinkId=145523) sample, only those files that are changed are listed.</span></span> <span data-ttu-id="909df-150">자체 호스팅 샘플에 대 한 자세한 내용은 참조 [설치 지침은](http://go.microsoft.com/fwlink/?LinkId=145522)합니다.</span><span class="sxs-lookup"><span data-stu-id="909df-150">For more information about the Self-Host sample, see [Setup Instructions](http://go.microsoft.com/fwlink/?LinkId=145522).</span></span>  
  
```csharp  
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
  
```csharp  
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

## <a name="see-also"></a><span data-ttu-id="909df-151">참고 항목</span><span class="sxs-lookup"><span data-stu-id="909df-151">See Also</span></span>  
 [<span data-ttu-id="909df-152">WCF 검색 개요</span><span class="sxs-lookup"><span data-stu-id="909df-152">WCF Discovery Overview</span></span>](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)  
 [<span data-ttu-id="909df-153">WCF 검색 개체 모델</span><span class="sxs-lookup"><span data-stu-id="909df-153">WCF Discovery Object Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-discovery-object-model.md)
