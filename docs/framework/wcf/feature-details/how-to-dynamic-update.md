---
title: "방법: 동적 업데이트"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9b8f6e0d-edab-4a7e-86e3-8c66bebc64bb
caps.latest.revision: "4"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: 70f9bb374405496c62650ee3fb715f059e91cd7c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-dynamic-update"></a><span data-ttu-id="403c0-102">방법: 동적 업데이트</span><span class="sxs-lookup"><span data-stu-id="403c0-102">How To: Dynamic Update</span></span>
<span data-ttu-id="403c0-103">이 항목에서는 라우팅 구성을 만들고 동적으로 업데이트하는 데 필요한 기본 단계에 대해 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="403c0-103">This topic outlines the basic steps required to create and dynamically update the routing configuration.</span></span> <span data-ttu-id="403c0-104">이 예제에서는 구성 파일에서 초기 라우팅 구성을 가져오고 이 구성을 사용하여 모든 메시지를 regularCalc 계산기 서비스에 라우트합니다. 그러나 이 구성은 대상 끝점을 roundingCalc 서비스로 변경하기 위해 이후에 프로그래밍 방식으로 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="403c0-104">In this example, the initial routing configuration is obtained from the configuration file and routes all messages to the regularCalc calculator service; however, it is subsequently updated programmatically in order to change the destination endpoint the roundingCalc service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="403c0-105">다양한 구현에서 구성은 완전히 동적으로 업데이트되며 기본 구성에 의존하지 않지만 서비스를 시작할 때처럼 기본 구성을 사용해야 하는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="403c0-105">In many implementations, configuration will be fully dynamic and will not rely on a default configuration; however, there are some scenarios, such as the one in this topic, where it is desirable to have a default configuration state when the service starts.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="403c0-106">동적 업데이트는 메모리에서만 발생하며 구성 파일을 수정하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="403c0-106">Dynamic updates occur only in memory, and do not result in the modification of configuration files.</span></span>  
  
 <span data-ttu-id="403c0-107">regularCalc와 roundingCalc는 모두 같은 연산(더하기, 빼기, 곱하기, 나누기)을 지원하지만 roundingCalc는 가장 가까운 정수 값으로 모든 계산을 반올림합니다.</span><span class="sxs-lookup"><span data-stu-id="403c0-107">Both regularCalc and roundingCalc support the same operations of add, subtract, multiply and divide; however, roundingCalc rounds all calculations to the nearest integer value before returning.</span></span> <span data-ttu-id="403c0-108">구성 파일은 모든 메시지를 regularCalc 서비스에 라우트하도록 서비스를 구성하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="403c0-108">A configuration file is used to configure the service to route all messages to the regularCalc service.</span></span> <span data-ttu-id="403c0-109">라우팅 서비스가 시작된 후에는 메시지를 roundingCalc 서비스에 라우트하도록 서비스를 다시 구성하는 데 <xref:System.ServiceModel.Routing.RoutingExtension.ApplyConfiguration%2A>이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="403c0-109">After the Routing Service has been started, <xref:System.ServiceModel.Routing.RoutingExtension.ApplyConfiguration%2A> is used to reconfigure the service to route messages to the roundingCalc service.</span></span>  
  
### <a name="implement-initial-configuration"></a><span data-ttu-id="403c0-110">초기 구성 구현</span><span class="sxs-lookup"><span data-stu-id="403c0-110">Implement Initial Configuration</span></span>  
  
1.  <span data-ttu-id="403c0-111">서비스에서 노출하는 서비스 끝점을 지정하여 기본 라우팅 서비스 구성을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="403c0-111">Create the basic Routing Service Configuration by specifying the service endpoints exposed by the service.</span></span> <span data-ttu-id="403c0-112">다음 예제에서는 메시지를 받는 데 사용할 하나의 서비스 끝점과</span><span class="sxs-lookup"><span data-stu-id="403c0-112">The following example defines a single service endpoint, which will be used to receive messages.</span></span> <span data-ttu-id="403c0-113">regularCalc에 메시지를 보내는 데 사용할 클라이언트 끝점을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="403c0-113">It also defines a client endpoint that will be used to send messages to the regularCalc.</span></span>  
  
    ```xml  
    <services>  
      <service behaviorConfiguration="routingConfiguration"  
               name="System.ServiceModel.Routing.RoutingService">  
        <host>  
          <baseAddresses>  
            <add baseAddress="http://localhost/routingservice/router" />  
          </baseAddresses>  
        </host>  
        <!--Set up the inbound endpoint for the Routing Service-->  
        <endpoint address="calculator"  
                  binding="wsHttpBinding"  
                  name="routerEndpoint"  
                  contract="System.ServiceModel.Routing.IRequestReplyRouter" />  
      </service>  
    </services>  
    <client>  
    <!--set up the destination endpoint-->  
      <endpoint name="regularCalcEndpoint"  
                address="net.tcp://localhost:9090/servicemodelsamples/service/"  
                binding="netTcpBinding"  
                contract="*" />  
    </client>  
    ```  
  
2.  <span data-ttu-id="403c0-114">대상 끝점에 메시지를 라우트하는 데 사용되는 필터를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="403c0-114">Define the filter used to route messages to the destination endpoints.</span></span> <span data-ttu-id="403c0-115">이 예제에서는 MatchAll 필터를 사용하여 모든 메시지를 앞에서 정의한 regularCalcEndpoint에 라우트합니다.</span><span class="sxs-lookup"><span data-stu-id="403c0-115">For this example, the MatchAll filter is used to route all messages to the regularCalcEndpoint defined previously.</span></span> <span data-ttu-id="403c0-116">다음 예제에서는 필터와 필터 테이블을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="403c0-116">The following example defines the filter and filter table.</span></span>  
  
    ```xml  
    <filters>  
      <!--define the message filter-->  
      <filter name="MatchAllFilter" filterType="MatchAll"/>  
    </filters>  
    <filterTables>  
      <filterTable name="filterTable1">  
          <!--add the filter to the message filter table-->  
          <add filterName="MatchAllFilter" endpointName="regularCalcEndpoint"/>  
      </filterTable>  
    </filterTables>  
    ```  
  
3.  <span data-ttu-id="403c0-117">필터 테이블에 포함된 필터에 대해 들어오는 메시지를 평가하려면 라우팅 동작을 사용하여 필터 테이블을 서비스 끝점과 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="403c0-117">To evaluate incoming messages against the filters contained in the filter table, you must associate the filter table with the service endpoints by using the routing behavior.</span></span> <span data-ttu-id="403c0-118">다음 예제에서는 "filterTable1"을 연결 된 서비스 끝점을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="403c0-118">The following example demonstrates associating "filterTable1" with the service endpoint.</span></span>  
  
    ```xml  
    <behaviors>  
      <!--default routing service behavior definition-->  
      <serviceBehaviors>  
        <behavior name="routingConfiguration">  
          <routing filterTableName="filterTable1" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    ```  
  
## <a name="implement-dynamic-configuration"></a><span data-ttu-id="403c0-119">동적 구성 구현</span><span class="sxs-lookup"><span data-stu-id="403c0-119">Implement Dynamic Configuration</span></span>  
 <span data-ttu-id="403c0-120">라우팅 서비스의 동적 구성은 새 <xref:System.ServiceModel.Routing.RoutingConfiguration>을 만들고 <xref:System.ServiceModel.Routing.RoutingExtension.ApplyConfiguration%2A>을 사용하여 현재 구성을 대체하는 방식으로 코드에서만 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="403c0-120">Dynamic configuration of the Routing Service can only be performed in code by creating a new <xref:System.ServiceModel.Routing.RoutingConfiguration> and using <xref:System.ServiceModel.Routing.RoutingExtension.ApplyConfiguration%2A> to replace the current configuration.</span></span>  <span data-ttu-id="403c0-121">이 예제에서는 라우팅 서비스가 콘솔 응용 프로그램 내에서 자체 호스팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="403c0-121">For this example, the Routing Service is self-hosted within a console application.</span></span> <span data-ttu-id="403c0-122">응용 프로그램이 시작되면 콘솔 창에 ‘regular’ 또는 ‘rounding’을 입력하여 메시지가 라우트되는 대상 끝점을 구성하는 방식으로 라우팅 구성을 수정할 수 있습니다. ‘regular’를 입력하면 대상 끝점이 regularCalc가 되고 ‘rounding’을 입력하면 대상 끝점이 roundingCalc가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="403c0-122">After the application has started, you can modify the routing configuration by entering ‘regular’ or ‘rounding’ at the console window to configure the destination endpoint that messages are routed to; regularCalc when ‘regular’ is entered, otherwise roundingCalc when ‘rounding’ is entered.</span></span>  
  
1.  <span data-ttu-id="403c0-123">라우팅 서비스를 지원하려면 다음 using 문을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="403c0-123">The following using statements must be added in order to support the Routing Service.</span></span>  
  
    ```csharp  
    using System;  
    using System.Collections.Generic;  
    using System.ServiceModel;  
    using System.ServiceModel.Channels;  
    using System.ServiceModel.Description;  
    using System.ServiceModel.Dispatcher;  
    using System.ServiceModel.Routing;  
    ```  
  
2.  <span data-ttu-id="403c0-124">다음 코드는 라우팅 서비스를 콘솔 응용 프로그램으로 자체 호스팅하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="403c0-124">The following code is used to self-host the Routing Service as a console application.</span></span> <span data-ttu-id="403c0-125">이 코드는 이전 단계에서 설명한 구성을 사용하여 라우팅 서비스를 초기화합니다. 이 구성은 응용 프로그램 구성 파일에 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="403c0-125">This initializes the Routing Service using the configuration described in the previous step, which is contained within the application configuration file.</span></span> <span data-ttu-id="403c0-126">while 루프에는 라우팅 구성을 변경하는 데 사용되는 코드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="403c0-126">The while loop contains the code used to change the routing configuration.</span></span>  
  
    ```csharp  
    // Host the service within this EXE console application.  
    public static void Main()  
    {  
        // Create a ServiceHost for the CalculatorService type.  
        using (ServiceHost serviceHost =  
            new ServiceHost(typeof(RoutingService)))  
        {  
            // Open the ServiceHost to create listeners           
            // and start listening for messages.  
            Console.WriteLine("The Routing Service configured, opening....");  
            serviceHost.Open();  
            Console.WriteLine("The Routing Service is now running.");  
             Console.WriteLine("Type 'quit' to terminate router.");  
             Console.WriteLine("<ENTER> to change routing configuration.");  
             while (Console.ReadLine() != "quit")  
             {  
            ....  
            }  
        }  
    }  
    ```  
  
3.  <span data-ttu-id="403c0-127">라우팅 구성을 동적으로 업데이트하려면 새 라우팅 구성을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="403c0-127">To dynamically update the routing configuration, a new routing configuration must be created.</span></span> <span data-ttu-id="403c0-128">기존 라우팅 구성을 완전히 대체하므로 여기에는 새 라우팅 구성에 필요한 모든 끝점, 필터 및 필터 테이블이 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="403c0-128">This must contain all endpoints, filters and filter tables that are required for the new routing configuration, as it will completely replace the existing routing configuration.</span></span> <span data-ttu-id="403c0-129">새 라우팅 구성을 사용하려면 <xref:System.ServiceModel.Routing.RoutingExtension.ApplyConfiguration%2A>을 호출하고 새 구성을 전달해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="403c0-129">In order to use the new routing configuration, you must invoke <xref:System.ServiceModel.Routing.RoutingExtension.ApplyConfiguration%2A> and pass the new configuration.</span></span>  
  
     <span data-ttu-id="403c0-130">앞에서 정의한 while 루프에 다음 코드를 추가하여 사용자 입력을 기반으로 서비스를 다시 구성할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="403c0-130">Add the following code to the while loop defined previously to allow the service to be reconfigured based on user input.</span></span>  
  
    ```csharp  
    Console.WriteLine("Enter 'regular' or 'rounding' to set the destination endpoint:");  
    string destEndpoint = Console.ReadLine();  
    // Create a new RoutingConfiguration  
    RoutingConfiguration rc = new RoutingConfiguration();  
    // Determine the endpoint to configure for  
    switch (destEndpoint)  
    {  
        case "regular":  
            // Define the destination endpoint  
            ServiceEndpoint regularCalc = new ServiceEndpoint(  
               ContractDescription.GetContract(typeof(IRequestReplyRouter)),  
               new NetTcpBinding(),  
               new EndpointAddress("net.tcp://localhost:9090/servicemodelsamples/service/"));  
            // Create a MatchAll filter and add to the filter table  
            rc.FilterTable.Add(new MatchAllMessageFilter(), new List<ServiceEndpoint> { regularCalc });  
            // Use ApplyConfiguration to update the Routing Service  
            serviceHost.Extensions.Find<RoutingExtension>().ApplyConfiguration(rc);  
            Console.WriteLine("Applied new routing configuration.");  
            break;  
        case "rounding":  
            // Define the destination endpoint  
            ServiceEndpoint roundingCalc = new ServiceEndpoint(  
               ContractDescription.GetContract(typeof(IRequestReplyRouter)),  
               new NetTcpBinding(),  
               new EndpointAddress("net.tcp://localhost:8080/servicemodelsamples/service/"));  
            // Create a MatchAll filter and add to the filter table  
            rc.FilterTable.Add(new MatchAllMessageFilter(), new List<ServiceEndpoint> { roundingCalc });  
            // Use ApplyConfiguration to update the Routing Service  
            serviceHost.Extensions.Find<RoutingExtension>().ApplyConfiguration(rc);  
            Console.WriteLine("Applied new routing configuration.");  
            break;  
        default:  
            Console.WriteLine("Incorrect value entered, no change.");  
            break;  
    }  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="403c0-131">새 RoutingConfiguration을 제공하는 메서드가 RoutingExtension 서비스 확장에 포함되어 있으므로 새 RoutingConfiguration 개체는 ServiceHost 또는 ServiceExtensions에 대한 참조를 가지고 있거나 가져올 수 있는 WCF 확장성 모델의 아무 위치에나 제공될 수 있습니다. 예를 들면 다른 ServiceExtension에 제공될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="403c0-131">Since the method for providing a new RoutingConfiguration is contained in the RoutingExtension service extension, new RoutingConfiguration objects can be provided anywhere in the WCF extensibility model that has or can obtain a reference to the ServiceHost or ServiceExtensions (such as in another ServiceExtension).</span></span> <span data-ttu-id="403c0-132">이런이 방식으로 RoutingConfiguration을 동적으로 업데이트 하는 예제를 보려면 [동적 재구성](../../../../docs/framework/wcf/samples/dynamic-reconfiguration.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="403c0-132">For an example of dynamically updating the RoutingConfiguration in this manner, see [Dynamic Reconfiguration](../../../../docs/framework/wcf/samples/dynamic-reconfiguration.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="403c0-133">예제</span><span class="sxs-lookup"><span data-stu-id="403c0-133">Example</span></span>  
 <span data-ttu-id="403c0-134">다음은 이 예제에 사용되는 콘솔 응용 프로그램의 전체 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="403c0-134">Following is a complete listing of the console application used in this example.</span></span>  
  
```  
//-----------------------------------------------------------------  
//  Copyright (c) Microsoft Corporation.  All Rights Reserved.  
//-----------------------------------------------------------------  
  
using System;  
using System.Collections.Generic;  
using System.ServiceModel;  
using System.ServiceModel.Channels;  
using System.ServiceModel.Description;  
using System.ServiceModel.Dispatcher;  
using System.ServiceModel.Routing;  
  
namespace Microsoft.Samples.AdvancedFilters  
{  
    public class Router  
    {  
        // Host the service within this EXE console application.  
        public static void Main()  
        {             
            // Create a ServiceHost for the CalculatorService type.  
            using (ServiceHost serviceHost =  
                new ServiceHost(typeof(RoutingService)))  
            {  
                // Open the ServiceHost to create listeners           
                // and start listening for messages.  
                Console.WriteLine("The Routing Service configured, opening....");  
                serviceHost.Open();  
                Console.WriteLine("The Routing Service is now running.");  
                Console.WriteLine("Type 'quit' to terminate router.");  
                Console.WriteLine("<ENTER> to change routing configuration.");  
                while (Console.ReadLine() != "quit")  
                {  
                    Console.WriteLine("Enter 'regular' or 'rounding' to set the destination endpoint:");  
                    string destEndpoint = Console.ReadLine();  
                    // Create a new RoutingConfiguration  
                    RoutingConfiguration rc = new RoutingConfiguration();  
                    // Determine the endpoint to configure for  
                    switch (destEndpoint)  
                    {  
                        case "regular":  
                            // Define the destination endpoint  
                            ServiceEndpoint regularCalc = new ServiceEndpoint(  
                            ContractDescription.GetContract(typeof(IRequestReplyRouter)),  
                            new NetTcpBinding(),  
                            new EndpointAddress("net.tcp://localhost:9090/servicemodelsamples/service/"));  
                            // Create a MatchAll filter and add to the filter table  
                            rc.FilterTable.Add(new MatchAllMessageFilter(), new List<ServiceEndpoint> { regularCalc });  
                            // Use ApplyConfiguration to update the Routing Service  
                            serviceHost.Extensions.Find<RoutingExtension>().ApplyConfiguration(rc);  
                            Console.WriteLine("Applied new routing configuration.");  
                            break;  
                        case "rounding":  
                            // Define the destination endpoint  
                            ServiceEndpoint roundingCalc = new ServiceEndpoint(  
                                ContractDescription.GetContract(typeof(IRequestReplyRouter)),  
                                new NetTcpBinding(),  
                                new EndpointAddress("net.tcp://localhost:8080/servicemodelsamples/service/"));  
                            // Create a MatchAll filter and add to the filter table  
                            rc.FilterTable.Add(new MatchAllMessageFilter(), new List<ServiceEndpoint> { roundingCalc });  
                            // Use ApplyConfiguration to update the Routing Service  
                            serviceHost.Extensions.Find<RoutingExtension>().ApplyConfiguration(rc);  
                            Console.WriteLine("Applied new routing configuration.");  
                            break;  
                        default:  
                            Console.WriteLine("Incorrect value entered, no change.");  
                            break;  
                    }  
                }  
            }  
        }  
    }  
}  
```  
  
## <a name="example"></a><span data-ttu-id="403c0-135">예제</span><span class="sxs-lookup"><span data-stu-id="403c0-135">Example</span></span>  
 <span data-ttu-id="403c0-136">다음은 이 예제에 사용되는 구성 파일의 전체 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="403c0-136">Following is a complete listing of the configuration file used in this example.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<!-- Copyright (c) Microsoft Corporation. All rights reserved -->  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service behaviorConfiguration="routingConfiguration"  
               name="System.ServiceModel.Routing.RoutingService">  
        <host>  
          <baseAddresses>  
            <add baseAddress="http://localhost/routingservice/router" />  
          </baseAddresses>  
        </host>  
        <!--Set up the inbound endpoint for the Routing Service-->  
        <endpoint address="calculator"  
                  binding="wsHttpBinding"  
                  name="routerEndpoint"  
                  contract="System.ServiceModel.Routing.IRequestReplyRouter" />  
      </service>  
    </services>  
    <behaviors>  
      <!--default routing service behavior definition-->  
      <serviceBehaviors>  
        <behavior name="routingConfiguration">  
          <routing filterTableName="filterTable1" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  
    <client>  
<!--set up the destination endpoint-->  
      <endpoint name="regularCalcEndpoint"  
                address="net.tcp://localhost:9090/servicemodelsamples/service/"  
                binding="netTcpBinding"  
                contract="*" />  
    </client>  
    <routing>  
  
      <filters>  
        <!--define the message filter-->  
        <filter name="MatchAllFilter" filterType="MatchAll"/>  
      </filters>  
      <filterTables>  
        <filterTable name="filterTable1">  
            <!--add the filter to the message filter table-->  
            <add filterName="MatchAllFilter" endpointName="regularCalcEndpoint"/>  
        </filterTable>  
      </filterTables>  
    </routing>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="403c0-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="403c0-137">See Also</span></span>  
 [<span data-ttu-id="403c0-138">라우팅 서비스</span><span class="sxs-lookup"><span data-stu-id="403c0-138">Routing Services</span></span>](../../../../docs/framework/wcf/samples/routing-services.md)
