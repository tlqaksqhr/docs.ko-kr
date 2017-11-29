---
title: "방법: 서비스 데이터 분할"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1ccff72e-d76b-4e36-93a2-e51f7b32dc83
caps.latest.revision: "3"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: 7104aa2fee49a21dab7fcc8392a9d4bb291203fe
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-service-data-partitioning"></a><span data-ttu-id="bde87-102">방법: 서비스 데이터 분할</span><span class="sxs-lookup"><span data-stu-id="bde87-102">How To: Service Data Partitioning</span></span>
<span data-ttu-id="bde87-103">이 항목에서는 동일한 대상 서비스의 여러 인스턴스에서 메시지를 분할하는 데 필요한 기본 단계에 대해 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bde87-103">This topic outlines the basic steps required to partition messages across multiple instances of the same destination service.</span></span> <span data-ttu-id="bde87-104">일반적으로 서비스 데이터 분할은 더 좋은 품질의 서비스를 제공하기 위해 서비스의 크기를 조정해야 하는 경우나 다양한 고객의 요청을 특정 방식으로 처리해야 하는 경우에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bde87-104">Service data partitioning is typically used when you need to scale a service in order to provide better quality of service, or when you need to handle requests from different customers in a specific way.</span></span> <span data-ttu-id="bde87-105">예를 들어 우수 또는 "골드" 고객의 메시지는 일반 고객의 메시지 보다 더 높은 우선 순위로 처리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bde87-105">For example, messages from high value or "Gold" customers may need to be processed at a higher priority than messages from a standard customer.</span></span>  
  
 <span data-ttu-id="bde87-106">이 예제에서는 메시지가 regularCalc 서비스의 두 인스턴스 중 하나로 라우트됩니다.</span><span class="sxs-lookup"><span data-stu-id="bde87-106">In this example, messages are routed to one of two instances of the regularCalc service.</span></span> <span data-ttu-id="bde87-107">이 서비스의 두 인스턴스는 동일합니다. 단, calculator1 끝점으로 표시된 서비스는 우수 고객으로부터 받은 메시지를 처리하고 calculator2 끝점으로 표시된 서비스는 기타 고객으로부터 받은 메시지를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="bde87-107">Both instances of the service are identical; however the service represented by the calculator1 endpoint processes messages received from high value customers, the calculator 2 endpoint processes messages from other customers</span></span>  
  
 <span data-ttu-id="bde87-108">클라이언트가 보낸 메시지에는 메시지를 라우트해야 하는 대상 서비스를 식별하는 데 사용할 수 있는 고유한 데이터가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bde87-108">The message sent from the client does not have any unique data that can be used to identify which service instance the message should be routed to.</span></span> <span data-ttu-id="bde87-109">각 클라이언트가 데이터를 특정 대상 서비스로 라우트할 수 있도록 하려면 메시지를 받는 데 사용할 두 개의 서비스 끝점을 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bde87-109">To allow each client to route data to a specific destination service we will implement two service endpoints that will be used to receive messages.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bde87-110">이 예제에서는 특정 끝점을 사용하여 데이터를 분할하지만 헤더나 본문 데이터 같은 메시지 자체 내에 포함된 정보를 사용하여 데이터를 분할할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bde87-110">While this example uses specific endpoints to partition data, this could also be accomplished using information contained within the message itself such as header or body data.</span></span>  
  
### <a name="implement-service-data-partitioning"></a><span data-ttu-id="bde87-111">서비스 데이터 분할 구현</span><span class="sxs-lookup"><span data-stu-id="bde87-111">Implement Service Data Partitioning</span></span>  
  
1.  <span data-ttu-id="bde87-112">서비스에서 노출하는 서비스 끝점을 지정하여 기본 라우팅 서비스 구성을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bde87-112">Create the basic Routing Service configuration by specifying the service endpoints exposed by the service.</span></span> <span data-ttu-id="bde87-113">다음 예제에서는 메시지를 받는 데 사용되는 두 개의 끝점과</span><span class="sxs-lookup"><span data-stu-id="bde87-113">The following example defines two endpoints, which will be used to receive messages.</span></span> <span data-ttu-id="bde87-114">regularCalc 서비스 인스턴스에 메시지를 보내는 데 사용되는 클라이언트 끝점을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="bde87-114">It also defines the client endpoints, which are used to send messages to the regularCalc service instances.</span></span>  
  
    ```xml  
    <services>  
      <service behaviorConfiguration="routingConfiguration"  
               name="System.ServiceModel.Routing.RoutingService">  
        <host>  
          <baseAddresses>  
            <add baseAddress="http://localhost/routingservice/router" />  
          </baseAddresses>  
        </host>  
        <!--Set up the inbound endpoints for the Routing Service-->  
        <!--create the endpoints for the calculator service-->  
        <endpoint address="calculator1"  
                  binding="wsHttpBinding"  
                  name="calculator1Endpoint"  
                  contract="System.ServiceModel.Routing.IRequestReplyRouter" />  
        <endpoint address="calculator2"  
                  binding="wsHttpBinding"  
                  name="calculator2Endpoint"  
                  contract="System.ServiceModel.Routing.IRequestReplyRouter" />  
       </service>  
    </services>  
    <client>  
    <!--set up the destination endpoints-->  
        <endpoint name="CalcEndpoint1"  
                  address="net.tcp://localhost:9090/servicemodelsamples/service/"  
                  binding="netTcpBinding"  
                  contract="*" />  
  
        <endpoint name="CalcEndpoint2"  
                  address="net.tcp://localhost:8080/servicemodelsamples/service/"  
                  binding="netTcpBinding"  
                  contract="*" />  
     </client>  
    ```  
  
2.  <span data-ttu-id="bde87-115">대상 끝점에 메시지를 라우트하는 데 사용되는 필터를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="bde87-115">Define the filters used to route messages to the destination endpoints.</span></span>  <span data-ttu-id="bde87-116">이 예제에서는 EndpointName 필터를 사용하여 메시지를 받은 서비스 끝점을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="bde87-116">For this example, the EndpointName filter is used to determine which service endpoint received the message.</span></span> <span data-ttu-id="bde87-117">다음 예제에서는 필요한 라우팅 섹션과 필터를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="bde87-117">The following example defines the necessary routing section and filters.</span></span>  
  
    ```xml  
    <filters>  
      <!--define the different message filters-->  
      <!--define endpoint name filters looking for messages that show up on the virtual endpoints-->  
      <filter name="HighPriority" filterType="EndpointName"  
              filterData="calculator1Endpoint"/>  
      <filter name="NormalPriority" filterType="EndpointName"  
              filterData="calculator2Endpoint"/>  
    </filters>  
    ```  
  
3.  <span data-ttu-id="bde87-118">각 끝점을 클라이언트 끝점과 연결하는 필터 테이블을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="bde87-118">Define the filter table, which associates each filter with a client endpoint.</span></span> <span data-ttu-id="bde87-119">이 예제에서는 메시지를 받는 데 사용된 특정 끝점을 기반으로 메시지가 라우트됩니다.</span><span class="sxs-lookup"><span data-stu-id="bde87-119">In this example, the message will be routed based on the specific endpoint it was received over.</span></span> <span data-ttu-id="bde87-120">메시지가 두 개의 가능한 필터 중 하나와만 일치할 수 있으므로 필터 우선 순위를 사용하여 필터가 평가되는 순서를 제어하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bde87-120">Since the message can only match one of the two possible filters, there is no need for using filter priority to control to the order in which filters are evaluated.</span></span>  
  
     <span data-ttu-id="bde87-121">다음 예제에서는 필터 테이블을 정의하고 앞에서 정의한 필터를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="bde87-121">The following defines the filter table and adds the filters defined earlier.</span></span>  
  
    ```xml  
    <filterTables>  
       <filterTable name="filterTable1">  
         <!--add the filters to the message filter table-->  
         <add filterName="HighPriority" endpointName="CalcEndpoint1"/>  
         <add filterName="NormalPriority" endpointName="CalcEndpoint2"/>  
       </filterTable>  
    </filterTables>  
    ```  
  
4.  <span data-ttu-id="bde87-122">테이블에 포함된 필터에 대해 들어오는 메시지를 평가하려면 라우팅 동작을 사용하여 필터 테이블을 서비스 끝점과 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bde87-122">To evaluate incoming messages against the filters contained in the table, you must associate the filter table with the service endpoints by using the routing behavior.</span></span> <span data-ttu-id="bde87-123">다음 예제에서는 "filterTable1" 연결 된 서비스 끝점을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bde87-123">The following example demonstrates associating "filterTable1" with the service endpoints:</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="bde87-124">예제</span><span class="sxs-lookup"><span data-stu-id="bde87-124">Example</span></span>  
 <span data-ttu-id="bde87-125">다음은 구성 파일의 전체 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="bde87-125">The following is a complete listing of the configuration file.</span></span>  
  
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
        <!--Set up the inbound endpoints for the Routing Service-->  
        <!--create the endpoints for the calculator service-->  
        <endpoint address="calculator1"  
                  binding="wsHttpBinding"  
                  name="calculator1Endpoint"  
                  contract="System.ServiceModel.Routing.IRequestReplyRouter" />  
        <endpoint address="calculator2"  
                  binding="wsHttpBinding"  
                  name="calculator2Endpoint"  
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
      <endpoint name="CalcEndpoint1"  
                address="net.tcp://localhost:9090/servicemodelsamples/service/"  
                binding="netTcpBinding"  
                contract="*" />  
  
      <endpoint name="CalcEndpoint2"  
                address="net.tcp://localhost:8080/servicemodelsamples/service/"  
                binding="netTcpBinding"  
                contract="*" />  
    </client>  
    <routing>  
      <!-- use the namespace table element to define a prefix for our custom namespace-->  
  
      <filters>  
        <!--define the different message filters-->  
        <!--define endpoint name filters looking for messages that show up on the virtual endpoints-->  
        <filter name="HighPriority" filterType="EndpointName"  
                filterData="calculator1Endpoint"/>  
        <filter name="NormalPriority" filterType="EndpointName"  
                filterData="calculator2Endpoint"/>  
      </filters>  
  
      <filterTables>  
        <filterTable name="filterTable1">  
          <!--add the filters to the message filter table-->  
          <add filterName="HighPriority" endpointName="CalcEndpoint1"/>  
          <add filterName="NormalPriority" endpointName="CalcEndpoint2"/>  
        </filterTable>  
      </filterTables>  
  
    </routing>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="bde87-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bde87-126">See Also</span></span>  
 [<span data-ttu-id="bde87-127">라우팅 서비스</span><span class="sxs-lookup"><span data-stu-id="bde87-127">Routing Services</span></span>](../../../../docs/framework/wcf/samples/routing-services.md)
