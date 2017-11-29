---
title: "방법: 기본 Windows Communication Foundation 클라이언트 구성"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: WCF clients [WCF], configuring
ms.assetid: d067b86d-afb0-47bf-94f6-45180a3d8d78
caps.latest.revision: "47"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1f4d6b5386e82a2052182ba3f4a929de13b27c22
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-configure-a-basic-windows-communication-foundation-client"></a><span data-ttu-id="40f16-102">방법: 기본 Windows Communication Foundation 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="40f16-102">How to: Configure a Basic Windows Communication Foundation Client</span></span>
<span data-ttu-id="40f16-103">이 작업은 기본 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 응용 프로그램을 만드는 데 필요한 6가지 작업 중 다섯 번째 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="40f16-103">This is the fifth of six tasks required to create a basic [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] application.</span></span> <span data-ttu-id="40f16-104">모든 6 가지 작업의 개요를 참조 하십시오.는 [초보자를 위한 자습서](../../../docs/framework/wcf/getting-started-tutorial.md) 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="40f16-104">For an overview of all six of the tasks, see the [Getting Started Tutorial](../../../docs/framework/wcf/getting-started-tutorial.md) topic.</span></span>  
  
 <span data-ttu-id="40f16-105">이 항목 disuccess 클라이언트 구성 파일의 서비스 참조 추가 기능을 사용 하 여 생성 된 [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] 또는 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="40f16-105">This topic disuccess the client configuration file that was generated using the Add Service Reference functionality of [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] or the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span> <span data-ttu-id="40f16-106">클라이언트를 구성하려면 클라이언트에서 서비스에 액세스하는 데 사용하는 끝점을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="40f16-106">Configuring the client consists of specifying the endpoint that the client uses to access the service.</span></span> <span data-ttu-id="40f16-107">끝점에는 주소, 바인딩 및 계약이 포함되어 있으며 이러한 각 항목은 클라이언트 구성 프로세스에서 지정되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="40f16-107">An endpoint has an address, a binding and a contract, and each of these must be specified in the process of configuring the client.</span></span>  
  
### <a name="to-configure-a-windows-communication-foundation-client"></a><span data-ttu-id="40f16-108">Windows Communication Foundation 클라이언트를 구성하려면</span><span class="sxs-lookup"><span data-stu-id="40f16-108">To configure a Windows Communication Foundation client</span></span>  
  
1.  <span data-ttu-id="40f16-109">GettingStartedClient 프로젝트에서 생성된 구성 파일(App.config)을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="40f16-109">Open the generated configuration file (App.config) from the GettingStartedClient project.</span></span> <span data-ttu-id="40f16-110">다음 예제에서는 생성된 구성 파일을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="40f16-110">The following example is a view of the generated configuration file.</span></span> <span data-ttu-id="40f16-111">아래는 [ \<system.serviceModel >](../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) 섹션에서 찾을 [ \<끝점 >](http://msdn.microsoft.com/en-us/13aa23b7-2f08-4add-8dbf-a99f8127c017) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="40f16-111">Under the [\<system.serviceModel>](../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) section, find the [\<endpoint>](http://msdn.microsoft.com/en-us/13aa23b7-2f08-4add-8dbf-a99f8127c017) element.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
        <startup>   
          <!-- specifies the version of WCF to use-->  
            <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.5,Profile=Client" />  
        </startup>  
        <system.serviceModel>  
            <bindings>  
                <!-- Uses wsHttpBinding-->  
                <wsHttpBinding>  
                    <binding name="WSHttpBinding_ICalculator" />  
                </wsHttpBinding>  
            </bindings>  
            <client>  
                <!-- specifies the endpoint to use when calling the service -->  
                <endpoint address="http://localhost:8000/ServiceModelSamples/Service/CalculatorService"  
                    binding="wsHttpBinding" bindingConfiguration="WSHttpBinding_ICalculator"  
                    contract="ServiceReference1.ICalculator" name="WSHttpBinding_ICalculator">  
                    <identity>  
                        <userPrincipalName value="migree@redmond.corp.microsoft.com" />  
                    </identity>  
                </endpoint>  
            </client>  
        </system.serviceModel>  
    </configuration>   
    ```  
  
     <span data-ttu-id="40f16-112">이 예제에서는 다음 주소에 위치한 서비스에 액세스하도록 클라이언트가 사용하는 끝점을 구성합니다. http://localhost:8000/ServiceModelSamples/Service/CalculatorService</span><span class="sxs-lookup"><span data-stu-id="40f16-112">This example configures the endpoint that the client uses to access the service that is located at the following address: http://localhost:8000/ServiceModelSamples/Service/CalculatorService</span></span>  
  
     <span data-ttu-id="40f16-113">끝점 요소는 WCF 클라이언트와 서비스 사이의 통신에 `ServiceReference1.ICalculator` 서비스 계약을 사용하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="40f16-113">The endpoint element specifies that the `ServiceReference1.ICalculator` service contract is used for communication between the WCF client and service.</span></span> <span data-ttu-id="40f16-114">WCF 채널 구성 시스템에서 제공 된 <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> 합니다.</span><span class="sxs-lookup"><span data-stu-id="40f16-114">The WCF channel is configured with the system-provided <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`>.</span></span> <span data-ttu-id="40f16-115">이 계약은 Visual Studio의 서비스 참조 추가를 사용하여 생성한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="40f16-115">This contract was generated by using Add Service Reference in Visual Studio.</span></span> <span data-ttu-id="40f16-116">실질적으로 GettingStartedLib 프로젝트에 정의된 계약의 사본입니다.</span><span class="sxs-lookup"><span data-stu-id="40f16-116">It is essentially a copy of the contract that was defined in the GettingStartedLib project.</span></span> <span data-ttu-id="40f16-117"><<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> 바인딩은 HTTP를 전송, 상호 운용 가능한 보안 및 기타 구성 세부 사항으로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="40f16-117">The <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> binding specifies HTTP as the transport, interoperable security, and other configuration details.</span></span>  
  
2.  [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="40f16-118">생성된 된 클라이언트를 사용 하 여이 구성을 사용 하 여, 참조 하는 방법 [하는 방법: 클라이언트를 사용 하 여](../../../docs/framework/wcf/how-to-use-a-wcf-client.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="40f16-118"> how to use the generated client with this configuration, see [How to: Use a Client](../../../docs/framework/wcf/how-to-use-a-wcf-client.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40f16-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="40f16-119">See Also</span></span>  
 [<span data-ttu-id="40f16-120">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="40f16-120">Using Bindings to Configure Services and Clients</span></span>](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="40f16-121">ServiceModel Metadata 유틸리티 도구(Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="40f16-121">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)  
 [<span data-ttu-id="40f16-122">방법: 클라이언트 만들기</span><span class="sxs-lookup"><span data-stu-id="40f16-122">How to: Create a Client</span></span>](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)  
 [<span data-ttu-id="40f16-123">시작</span><span class="sxs-lookup"><span data-stu-id="40f16-123">Getting Started</span></span>](../../../docs/framework/wcf/samples/getting-started-sample.md)  
 [<span data-ttu-id="40f16-124">자체 호스팅</span><span class="sxs-lookup"><span data-stu-id="40f16-124">Self-Host</span></span>](../../../docs/framework/wcf/samples/self-host.md)
