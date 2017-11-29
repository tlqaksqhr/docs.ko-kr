---
title: "방법: 서비스 버전 관리"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4287b6b3-b207-41cf-aebe-3b1d4363b098
caps.latest.revision: "6"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: 4c4bd28c1a59d422c4ec0c65e133d253cabf16c4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-service-versioning"></a><span data-ttu-id="b8b4b-102">방법: 서비스 버전 관리</span><span class="sxs-lookup"><span data-stu-id="b8b4b-102">How To: Service Versioning</span></span>
<span data-ttu-id="b8b4b-103">이 항목에서는 메시지를 동일한 서비스의 여러 버전에 라우트하는 라우팅 구성을 만드는 데 필요한 기본 단계에 대해 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b8b4b-103">This topic outlines the basic steps required to create a routing configuration that routes messages to different versions of the same service.</span></span> <span data-ttu-id="b8b4b-104">이 예제에서 메시지는 계산기 서비스의 서로 다른 두 버전인 `roundingCalc`(v1)와 `regularCalc`(v2)에 라우트됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8b4b-104">In this example, messages are routed to two different versions of a calculator service, `roundingCalc` (v1) and `regularCalc` (v2).</span></span> <span data-ttu-id="b8b4b-105">두 구현 모두 같은 연산을 지원하지만 이전 버전인 `roundingCalc` 서비스에서는 반환 전에 가장 가까운 정수 값으로 모든 계산을 반올림합니다.</span><span class="sxs-lookup"><span data-stu-id="b8b4b-105">Both implementations support the same operations; however the older service, `roundingCalc`, rounds all calculations to the nearest integer value before returning.</span></span> <span data-ttu-id="b8b4b-106">클라이언트 응용 프로그램에서는 새 버전인 `regularCalc` 서비스를 사용할지 여부를 나타낼 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8b4b-106">A client application must be able to indicate whether to use the newer `regularCalc` service.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="b8b4b-107">메시지를 특정 서비스 버전에 라우트하려면 라우팅 서비스에서 메시지 내용을 기반으로 메시지 대상을 확인할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8b4b-107">In order to route a message to a specific service version, the Routing Service must be able to determine the message destination based on the message content.</span></span> <span data-ttu-id="b8b4b-108">아래에서 설명하는 방법에서는 클라이언트가 메시지 헤더에 정보를 삽입하여 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b8b4b-108">In the method demonstrated below, the client will specify the version by inserting information into a message header.</span></span> <span data-ttu-id="b8b4b-109">그러나 클라이언트가 추가 데이터를 전달하지 않아도 서비스 버전을 관리할 수 있는 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8b4b-109">There are methods of service versioning that do not require clients to pass additional data.</span></span> <span data-ttu-id="b8b4b-110">예를 들어 최신 또는 가장 호환성이 뛰어난 버전의 서비스에 메시지를 라우트할 수 있거나 라우터에서 표준 SOAP 봉투의 일부를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8b4b-110">For example, a message could be routed to the most recent or most compatible version of a service or the router could use a part of the standard SOAP envelope.</span></span>  
  
 <span data-ttu-id="b8b4b-111">두 서비스에 의해 노출되는 연산은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b8b4b-111">The operations exposed by both services are:</span></span>  
  
-   <span data-ttu-id="b8b4b-112">Add</span><span class="sxs-lookup"><span data-stu-id="b8b4b-112">Add</span></span>  
  
-   <span data-ttu-id="b8b4b-113">Subtract</span><span class="sxs-lookup"><span data-stu-id="b8b4b-113">Subtract</span></span>  
  
-   <span data-ttu-id="b8b4b-114">곱하기</span><span class="sxs-lookup"><span data-stu-id="b8b4b-114">Multiply</span></span>  
  
-   <span data-ttu-id="b8b4b-115">Divide</span><span class="sxs-lookup"><span data-stu-id="b8b4b-115">Divide</span></span>  
  
 <span data-ttu-id="b8b4b-116">두 서비스 구현은 모두 같은 연산을 처리하고 반환하는 데이터를 제외하면 본질적으로 동일하므로 클라이언트 응용 프로그램에서 보낸 메시지에 포함된 기본 데이터는 요청을 라우트할 방법을 결정하기에는 고유성이 부족합니다.</span><span class="sxs-lookup"><span data-stu-id="b8b4b-116">Because both service implementations handle the same operations, and are essentially identical other than the data that they return, the base data contained in messages sent from client applications is not unique enough to allow you to determine how to route the request.</span></span> <span data-ttu-id="b8b4b-117">예를 들어 두 서비스의 기본 동작이 같기 때문에 동작 필터를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b8b4b-117">For example, Action filters cannot be used because the default actions for both services are the same.</span></span>  
  
 <span data-ttu-id="b8b4b-118">이 문제는 각 서비스 버전의 라우터에 특정 끝점을 노출하거나 서비스 버전을 나타내는 사용자 지정 헤더 요소를 메시지에 추가하는 등의 여러 가지 방법으로 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8b4b-118">This can be resolved in several ways, such as exposing a specific endpoint on the router for each version of the service or adding a custom header element to the message to indicate service version.</span></span>  <span data-ttu-id="b8b4b-119">이러한 각 방법을 사용하면 들어오는 메시지를 특정 버전의 서비스에 고유하게 라우트할 수 있지만 여러 서비스 버전에 대한 요청을 구별하기 위해서는 고유한 메시지 내용을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b8b4b-119">Each of these approaches allows you to uniquely route incoming messages to a specific version of the service, but utilizing unique message content is the preferred method of differentiating between requests for different service versions.</span></span>  
  
 <span data-ttu-id="b8b4b-120">이 예제에서는 클라이언트 응용 프로그램에서 요청 메시지에 ‘CalcVer’ 사용자 지정 헤더를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b8b4b-120">In this example, the client application adds the ‘CalcVer’ custom header to the request message.</span></span> <span data-ttu-id="b8b4b-121">이 헤더에는 메시지를 라우트해야 하는 대상 서비스의 버전을 나타내는 값이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8b4b-121">This header will contain a value that indicates the version of the service that the message should be routed to.</span></span> <span data-ttu-id="b8b4b-122">값 ‘1’은 roundingCalc 서비스로 메시지를 처리해야 함을 나타내고 값 ‘2’는 regularCalc 서비스로 메시지를 처리해야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b8b4b-122">A value of ‘1’ indicates that the message must be processed by the roundingCalc service, while a value of ‘2’ indicates the regularCalc service.</span></span> <span data-ttu-id="b8b4b-123">이러한 값을 사용하면 클라이언트 응용 프로그램에서 메시지를 처리할 서비스의 버전을 직접 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8b4b-123">This allows the client application to directly control which version of the service will process the message.</span></span>  <span data-ttu-id="b8b4b-124">사용자 지정 헤더가 메시지 내에 포함된 값이므로 한 끝점을 사용하여 두 서비스 버전의 대상이 되는 메시지를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8b4b-124">Since the custom header is a value contained within the message, you can use one endpoint to receive messages destined for both versions of the service.</span></span> <span data-ttu-id="b8b4b-125">다음 코드를 사용하면 클라이언트 응용 프로그램에서 이 사용자 지정 헤더를 메시지에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8b4b-125">The following code can be used in the client application to add this custom header to the message:</span></span>  
  
```csharp  
messageHeadersElement.Add(MessageHeader.CreateHeader("CalcVer", "http://my.custom.namespace/", "2"));  
```  
  
### <a name="implement-service-versioning"></a><span data-ttu-id="b8b4b-126">서비스 버전 관리 구현</span><span class="sxs-lookup"><span data-stu-id="b8b4b-126">Implement Service Versioning</span></span>  
  
1.  <span data-ttu-id="b8b4b-127">서비스에서 노출하는 서비스 끝점을 지정하여 기본 라우팅 서비스 구성을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b8b4b-127">Create the basic Routing Service configuration by specifying the service endpoint exposed by the service.</span></span> <span data-ttu-id="b8b4b-128">다음 예제에서는 메시지를 받는 데 사용할 하나의 서비스 끝점과</span><span class="sxs-lookup"><span data-stu-id="b8b4b-128">The following example defines a single service endpoint, which will be used to receive messages.</span></span> <span data-ttu-id="b8b4b-129">`roundingCalc`(v1) 및 `regularCalc`(v2) 서비스에 메시지를 보내는 데 사용할 클라이언트 끝점을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b8b4b-129">It also defines the client endpoints which will be used to send messages to the `roundingCalc` (v1) and the `regularCalc` (v2) services.</span></span>  
  
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
    <!--set up the destination endpoints-->  
          <endpoint name="regularCalcEndpoint"  
                    address="net.tcp://localhost:9090/servicemodelsamples/service/"  
                    binding="netTcpBinding"  
                    contract="*" />  
  
          <endpoint name="roundingCalcEndpoint"  
                    address="http://localhost:8080/servicemodelsamples/service/"  
                    binding="wsHttpBinding"  
                    contract="*" />  
        </client>  
    ```  
  
2.  <span data-ttu-id="b8b4b-130">대상 끝점에 메시지를 라우트하는 데 사용되는 필터를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b8b4b-130">Define the filters used to route messages to the destination endpoints.</span></span>  <span data-ttu-id="b8b4b-131">이 예에서는 XPath 필터는 메시지를 라우트해야 하는 버전을 결정 하는 "CalcVer" 사용자 지정 헤더의 값을 감지 하 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8b4b-131">For this example, the XPath filter is used to detect the value of the "CalcVer" custom header to determine which version the message should be routed to.</span></span> <span data-ttu-id="b8b4b-132">"CalcVer" 헤더가 포함 되지 않은 메시지 검색 하는 XPath 필터도 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8b4b-132">An XPath filter is also used to detect messages that do not contain the "CalcVer" header.</span></span> <span data-ttu-id="b8b4b-133">다음 예제에서는 필요한 필터 및 네임스페이스 테이블을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b8b4b-133">The following example defines the required filters and namespace table.</span></span>  
  
    ```xml  
    <!-- use the namespace table element to define a prefix for our custom namespace-->  
    <namespaceTable>  
      <add prefix="custom" namespace="http://my.custom.namespace/"/>  
    </namespaceTable>  
    <filters>  
      <!--define the different message filters-->  
      <!--define an xpath message filter to look for the  
          custom header containing a value of 2-->  
      <filter name="XPathFilterRegular" filterType="XPath"  
              filterData="sm:header()/custom:CalcVer = '2'"/>  
      <!--define an xpath message filter to look for the  
          custom header containing a value of 1-->  
      <filter name="XPathFilterRounding" filterType="XPath"  
              filterData="sm:header()/custom:CalcVer = '1'"/>  
       <!--define an xpath message filter to look for  
           messages that do not contain the custom header-->  
       <filter name="XPathFilterNoHeader" filterType="XPath"  
               filterData="count(sm:header()/custom:CalcVer)=0"/>  
    </filters  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="b8b4b-134">S12 네임 스페이스 접두사는 기본적으로 네임 스페이스 테이블에 정의 된 하 고 "http://www.w3.org/2003/05/soap-envelope" 네임 스페이스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b8b4b-134">The s12 namespace prefix is defined by default in the namespace table, and represents the namespace "http://www.w3.org/2003/05/soap-envelope".</span></span>  
  
3.  <span data-ttu-id="b8b4b-135">각 끝점을 클라이언트 끝점과 연결하는 필터 테이블을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b8b4b-135">Define the filter table, which associates each filter with a client endpoint.</span></span> <span data-ttu-id="b8b4b-136">값이 1 인는 "CalcVer" 헤더를 포함 하는 메시지를 regularCalc 서비스로 보내집니다.</span><span class="sxs-lookup"><span data-stu-id="b8b4b-136">If the message contains the "CalcVer" header with a value of 1, it will be sent to the regularCalc service.</span></span> <span data-ttu-id="b8b4b-137">값이 2이면 메시지가 roundingCalc 서비스에 보내집니다.</span><span class="sxs-lookup"><span data-stu-id="b8b4b-137">If the header contains a value of 2, it will be sent to the roundingCalc service.</span></span> <span data-ttu-id="b8b4b-138">헤더가 없으면 메시지가 regularCalc에 라우트됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8b4b-138">If no header is present, the message will be routed to the regularCalc.</span></span>  
  
     <span data-ttu-id="b8b4b-139">다음 예제에서는 필터 테이블을 정의하고 앞에서 정의한 필터를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b8b4b-139">The following defines the filter table and adds the filters defined earlier.</span></span>  
  
    ```xml  
    <filterTables>  
      <filterTable name="filterTable1">  
          <!--add the filters to the message filter table-->  
          <!--look for the custom header = 1, and if we find it,  
              send the message to the rounding calc endpoint-->  
          <add filterName="XPathFilterRounding" endpointName="roundingCalcEndpoint"/>  
          <!--look for the custom header = 2, and if we find it,  
              send the message to the rounding calc endpoint-->  
          <add filterName="XPathFilterRegular" endpointName="regularCalcEndpoint"/>  
          <!--look for the absence of the custom header, and if  
              it is not present, assume the v1 endpoint-->  
          <add filterName="XPathFilterNoHeader" endpointName="roundingCalcEndpoint"/>  
      </filterTable>  
    </filterTables>  
    ```  
  
4.  <span data-ttu-id="b8b4b-140">필터 테이블에 포함된 필터에 대해 들어오는 메시지를 평가하려면 라우팅 동작을 사용하여 필터 테이블을 서비스 끝점과 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8b4b-140">To evaluate incoming messages against the filters contained in the filter table, you must associate the filter table with the service endpoints by using the routing behavior.</span></span>  <span data-ttu-id="b8b4b-141">다음 예제에서는 "filterTable1" 연결 된 서비스 끝점을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b8b4b-141">The following example demonstrates associating "filterTable1" with the service endpoints:</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="b8b4b-142">예제</span><span class="sxs-lookup"><span data-stu-id="b8b4b-142">Example</span></span>  
 <span data-ttu-id="b8b4b-143">다음은 구성 파일의 전체 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="b8b4b-143">The following is a complete listing of the configuration file.</span></span>  
  
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
<!--set up the destination endpoints-->  
      <endpoint name="regularCalcEndpoint"  
                address="net.tcp://localhost:9090/servicemodelsamples/service/"  
                binding="netTcpBinding"  
                contract="*" />  
  
      <endpoint name="roundingCalcEndpoint"  
                address="http://localhost:8080/servicemodelsamples/service/"  
                binding="wsHttpBinding"  
                contract="*" />  
    </client>  
    <routing>  
      <!-- use the namespace table element to define a prefix for our custom namespace-->  
      <namespaceTable>  
        <add prefix="custom" namespace="http://my.custom.namespace/"/>  
      </namespaceTable>  
      <filters>  
        <!--define the different message filters-->  
        <!--define an xpath message filter to look for the  
            custom header containing a value of 2-->  
        <filter name="XPathFilterRegular" filterType="XPath"  
                filterData="sm:header()/custom:CalcVer = '2'"/>  
        <!--define an xpath message filter to look for the  
            custom header containing a value of 1-->  
        <filter name="XPathFilterRounding" filterType="XPath"  
                filterData="sm:header()/custom:CalcVer = '1'"/>  
        <!--define an xpath message filter to look for  
            messages that do not contain the custom header-->  
        <filter name="XPathFilterNoHeader" filterType="XPath"  
                filterData="count(sm:header()/custom:CalcVer)=0"/>  
      </filters>  
      <filterTables>  
        <filterTable name="filterTable1">  
            <!--add the filters to the message filter table-->  
            <!--look for the custom header = 1, and if we find it,  
                send the message to the rounding calc endpoint-->  
            <add filterName="XPathFilterRounding" endpointName="roundingCalcEndpoint"/>  
            <!--look for the custom header = 2, and if we find it,  
                send the message to the rounding calc endpoint-->  
            <add filterName="XPathFilterRegular" endpointName="regularCalcEndpoint"/>  
            <!--look for the absence of the custom header, and if  
                it is not present, assume the v1 endpoint-->  
            <add filterName="XPathFilterNoHeader" endpointName="roundingCalcEndpoint"/>  
        </filterTable>  
      </filterTables>  
    </routing>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="example"></a><span data-ttu-id="b8b4b-144">예제</span><span class="sxs-lookup"><span data-stu-id="b8b4b-144">Example</span></span>  
 <span data-ttu-id="b8b4b-145">다음은 클라이언트 응용 프로그램의 전체 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="b8b4b-145">The following is a complete listing of the client application.</span></span>  
  
```csharp  
using System;  
using System.ServiceModel;  
using System.ServiceModel.Channels;  
  
namespace Microsoft.Samples.AdvancedFilters  
{  
    //The service contract is defined in generatedClient.cs, generated from the service by the svcutil tool.  
  
    //Client implementation code.  
    class Client  
    {  
        static void Main()  
        {  
            //Print out the welcome text  
            Console.WriteLine("This sample routes the Calculator Sample through the new WCF RoutingService");  
            Console.WriteLine("Wait for all the services to indicate that they've started, then press");  
            Console.WriteLine("<ENTER> to start the client.");  
  
            while (Console.ReadLine() != "quit")  
            {  
                //Offer the Address configuration for the client  
                Console.WriteLine("");  
                Console.WriteLine("Welcome to the Calculator Client!");  
  
                EndpointAddress epa;  
                //set the default address as the general router endpoint  
                epa = new EndpointAddress("http://localhost/routingservice/router/calculator");  
  
                //set up the CalculatorClient with the EndpointAddress, the WSHttpBinding, and the ICalculator contract  
                //We use the WSHttpBinding so that the outgoing has a message envelope, which we'll manipulate in a minute  
                CalculatorClient client = new CalculatorClient(new WSHttpBinding(), epa);  
                //client.Endpoint.Contract = ContractDescription.GetContract(typeof(ICalculator));  
  
                //Ask the customer if they want to add a custom header to the outgoing message.  
                //The Router will look for this header, and if so ignore the endpoint the message was  
                //received on, and instead direct the message to the RoundingCalcService.  
                Console.WriteLine("");  
                Console.WriteLine("Which calculator service should be used?");  
                Console.WriteLine("Enter 1 for the rounding calculator, 2 for the regular calculator.");  
                Console.WriteLine("[1] or [2]?");  
  
                string header = Console.ReadLine();  
  
                //get the current operationContextScope from the client's inner channel  
                using (OperationContextScope ocs = new OperationContextScope((client.InnerChannel)))  
                {  
                    //get the outgoing message headers element (collection) from the context  
                    MessageHeaders messageHeadersElement = OperationContext.Current.OutgoingMessageHeaders;  
  
                    //if they wanted to create the header, go ahead and add it to the outgoing message  
                    if (header != null && (header=="1" || header=="2"))  
                    {  
                        //create a new header "RoundingCalculator", no specific namespace, and set the value to   
                        //the value of header.  
                        //the Routing Service will look for this header in order to determine if the message  
                        //should be routed to the RoundingCalculator  
                        messageHeadersElement.Add(MessageHeader.CreateHeader("CalcVer", "http://my.custom.namespace/", header));  
                    }  
                    else //incorrect choice, no header added  
                    {  
                        Console.WriteLine("Incorrect value entered, not adding a header");  
                    }  
  
                        //call the client operations  
                        CallClient(client);  
                }  
  
                //close the client to clean it up  
                client.Close();  
                Console.WriteLine();  
                Console.WriteLine("Press <ENTER> to run the client again or type 'quit' to quit.");  
            }  
        }  
  
        private static void CallClient(CalculatorClient client)  
        {  
            Console.WriteLine("");  
            Console.WriteLine("Sending!");  
            // Call the Add service operation.  
            double value1 = 100.00D;  
            double value2 = 15.99D;  
            double result = client.Add(value1, value2);  
            Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
  
            // Call the Subtract service operation.  
            value1 = 145.00D;  
            value2 = 76.54D;  
            result = client.Subtract(value1, value2);  
            Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result);  
  
            // Call the Multiply service operation.  
            value1 = 9.00D;  
            value2 = 81.25D;  
            result = client.Multiply(value1, value2);  
            Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result);  
  
            // Call the Divide service operation.  
            value1 = 22.00D;  
            value2 = 7.00D;  
            result = client.Divide(value1, value2);  
            Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result);  
  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="b8b4b-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b8b4b-146">See Also</span></span>  
 [<span data-ttu-id="b8b4b-147">라우팅 서비스</span><span class="sxs-lookup"><span data-stu-id="b8b4b-147">Routing Services</span></span>](../../../../docs/framework/wcf/samples/routing-services.md)
