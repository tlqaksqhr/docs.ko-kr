---
title: '방법: 사용자 지정 WS-Metadata Exchange 바인딩 구성'
ms.date: 03/30/2017
helpviewer_keywords:
- WS-Metadata Exchange [WCF]
- WS-Metadata Exchange [WCF], configuring a custom binding
ms.assetid: cdba4d73-da64-4805-bc56-9822becfd1e4
ms.openlocfilehash: 0596e91204a2a9dbaed2fdbe85387ec3785fd3db
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33488701"
---
# <a name="how-to-configure-a-custom-ws-metadata-exchange-binding"></a><span data-ttu-id="965fe-102">방법: 사용자 지정 WS-Metadata Exchange 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="965fe-102">How to: Configure a Custom WS-Metadata Exchange Binding</span></span>
<span data-ttu-id="965fe-103">이 항목에서는 사용자 지정 WS-Metadata 교환 바인딩을 구성하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="965fe-103">This topic will explain how to configure a custom WS-Metadata exchange binding.</span></span> <span data-ttu-id="965fe-104">Windows Communication Foundation (WCF) 시스템 정의 메타 데이터 바인딩이 포함 되어 있지만 원하는 모든 바인딩을 사용 하 여 메타 데이터를 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="965fe-104">Windows Communication Foundation (WCF) includes four system-defined metadata bindings, but you can publish metadata using any binding you want.</span></span> <span data-ttu-id="965fe-105">이 항목에서는 `wsHttpBinding`을 사용하여 메타데이터를 게시하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="965fe-105">This topic will show you how to publish metadata using the `wsHttpBinding`.</span></span> <span data-ttu-id="965fe-106">이 바인딩은 메타데이터를 보안 방법으로 노출하는 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="965fe-106">This binding gives you the option of exposing metadata in a secure way.</span></span> <span data-ttu-id="965fe-107">이 문서의 코드 기반는 [시작](../../../../docs/framework/wcf/samples/getting-started-sample.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="965fe-107">The code in this article is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span>  
  
### <a name="using-a-configuration-file"></a><span data-ttu-id="965fe-108">구성 파일 사용</span><span class="sxs-lookup"><span data-stu-id="965fe-108">Using a configuration file</span></span>  
  
1.  <span data-ttu-id="965fe-109">서비스의 구성 파일에서 `serviceMetadata` 태그를 포함하는 서비스 동작을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="965fe-109">In the service's configuration file, add a service behavior that contains the `serviceMetadata` tag:</span></span>  
  
    ```xml  
    <behaviors>  
       <serviceBehaviors>  
         <behavior name="CalculatorServiceBehavior">  
           <serviceMetadata httpGetEnabled="True"/>  
         </behavior>  
       </serviceBehaviors>  
    </behaviors>  
    ```  
  
2.  <span data-ttu-id="965fe-110">이 새 동작을 참조하는 서비스 태그에 `behaviorConfiguration` 특성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="965fe-110">Add a `behaviorConfiguration` attribute to the service tag that references this new behavior:</span></span>  
  
    ```xml  
    <service        name="Microsoft.ServiceModel.Samples.CalculatorService"  
    behaviorConfiguration="CalculatorServiceBehavior">   
    ```  
  
3.  <span data-ttu-id="965fe-111">mex를 지정하는 메타데이터 끝점을 주소로, `wsHttpBinding`을 바인딩으로, <xref:System.ServiceModel.Description.IMetadataExchange>를 계약으로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="965fe-111">Add a metadata endpoint specifying mex as the address, `wsHttpBinding` as the binding, and <xref:System.ServiceModel.Description.IMetadataExchange> as the contract:</span></span>  
  
    ```xml  
    <endpoint address="mex"  
              binding="wsHttpBinding"  
              contract="IMetadataExchange" />  
    ```  
  
4.  <span data-ttu-id="965fe-112">메타데이터 교환 끝점이 올바로 작동하고 있는지 확인하려면 클라이언트 구성 파일에 끝점 태그를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="965fe-112">To verify the metadata exchange endpoint is working correctly add an endpoint tag in the client configuration file:</span></span>  
  
    ```xml  
    <endpoint name="MyMexEndpoint"               address="http://localhost:8000/servicemodelsamples/service/mex"  
              binding="wsHttpBinding"  
              contract="IMetadataExchange"/>  
    ```  
  
5.  <span data-ttu-id="965fe-113">클라이언트의 Main() 메서드에서 새 <xref:System.ServiceModel.Description.MetadataExchangeClient> 인스턴스를 만들고, 해당 <xref:System.ServiceModel.Description.MetadataExchangeClient.ResolveMetadataReferences%2A> 속성을 `true`로 설정하고, <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A>를 호출한 다음 반환된 메타데이터 컬렉션을 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="965fe-113">In the client's Main() method, create a new <xref:System.ServiceModel.Description.MetadataExchangeClient> instance, set its <xref:System.ServiceModel.Description.MetadataExchangeClient.ResolveMetadataReferences%2A> property to `true`, call <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A> and then iterate through the collection of metadata returned:</span></span>  
  
    ```  
    string mexAddress = "http://localhost:8000/servicemodelsamples/service/mex";  
  
    MetadataExchangeClient mexClient = new MetadataExchangeClient("MyMexEndpoint");  
    mexClient.ResolveMetadataReferences = true;  
    MetadataSet mdSet = mexClient.GetMetadata(new EndpointAddress(mexAddress));  
    foreach (MetadataSection section in mdSet.MetadataSections)  
    Console.WriteLine("Metadata section: " + section.Dialect.ToString());  
    ```  
  
### <a name="configuring-by-code"></a><span data-ttu-id="965fe-114">코드로 구성</span><span class="sxs-lookup"><span data-stu-id="965fe-114">Configuring by code</span></span>  
  
1.  <span data-ttu-id="965fe-115">만들기는 <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> 바인딩 인스턴스:</span><span class="sxs-lookup"><span data-stu-id="965fe-115">Create a <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> binding instance:</span></span>  
  
    ```  
    WSHttpBinding binding = new WSHttpBinding();  
    ```  
  
2.  <span data-ttu-id="965fe-116"><xref:System.ServiceModel.ServiceHost> 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="965fe-116">Create a <xref:System.ServiceModel.ServiceHost> instance:</span></span>  
  
    ```  
    ServiceHost serviceHost = new ServiceHost(typeof(CalculatorService), baseAddress);  
    ```  
  
3.  <span data-ttu-id="965fe-117">서비스 끝점을 추가하고 <xref:System.ServiceModel.Description.ServiceMetadataBehavior> 인스턴스를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="965fe-117">Add a service endpoint and add a <xref:System.ServiceModel.Description.ServiceMetadataBehavior> instance:</span></span>  
  
    ```  
    serviceHost.AddServiceEndpoint(typeof(ICalculator), binding, baseAddress);  
    ServiceMetadataBehavior smb = new ServiceMetadataBehavior();  
    smb.HttpGetEnabled = true;  
    serviceHost.Description.Behaviors.Add(smb);  
    ```  
  
4.  <span data-ttu-id="965fe-118">추가 메타 데이터 교환 끝점을 지정 하는 <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> 이전에 만든:</span><span class="sxs-lookup"><span data-stu-id="965fe-118">Add a metadata exchange endpoint, specifying the <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> created earlier:</span></span>  
  
    ```  
    serviceHost.AddServiceEndpoint(typeof(IMetadataExchange), binding, mexAddress);  
    ```  
  
5.  <span data-ttu-id="965fe-119">메타데이터 교환 끝점이 올바로 작동하고 있는지 확인하려면 클라이언트 구성 파일에 끝점 태그를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="965fe-119">To verify that the metadata exchange endpoint is working correctly, add an endpoint tag in the client configuration file:</span></span>  
  
    ```xml  
    <endpoint name="MyMexEndpoint"               address="http://localhost:8000/servicemodelsamples/service/mex"  
              binding="wsHttpBinding"  
              contract="IMetadataExchange"/>  
    ```  
  
6.  <span data-ttu-id="965fe-120">클라이언트의 Main() 메서드에서 새 <xref:System.ServiceModel.Description.MetadataExchangeClient> 인스턴스를 만들고, 해당 <xref:System.ServiceModel.Description.MetadataExchangeClient.ResolveMetadataReferences%2A> 속성을 `true`로 설정하고, <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A>를 호출한 다음 반환된 메타데이터 컬렉션을 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="965fe-120">In the client's Main() method, create a new <xref:System.ServiceModel.Description.MetadataExchangeClient> instance, set the <xref:System.ServiceModel.Description.MetadataExchangeClient.ResolveMetadataReferences%2A> property to `true`, call <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A> and then iterate through the collection of metadata returned:</span></span>  
  
    ```  
    string mexAddress = "http://localhost:8000/servicemodelsamples/service/mex";  
  
    MetadataExchangeClient mexClient = new MetadataExchangeClient("MyMexEndpoint");  
    mexClient.ResolveMetadataReferences = true;  
    MetadataSet mdSet = mexClient.GetMetadata(new EndpointAddress(mexAddress));  
    foreach (MetadataSection section in mdSet.MetadataSections)  
    Console.WriteLine("Metadata section: " + section.Dialect.ToString());  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="965fe-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="965fe-121">See Also</span></span>  
 [<span data-ttu-id="965fe-122">메타데이터 게시 동작</span><span class="sxs-lookup"><span data-stu-id="965fe-122">Metadata Publishing Behavior</span></span>](../../../../docs/framework/wcf/samples/metadata-publishing-behavior.md)  
 [<span data-ttu-id="965fe-123">메타데이터 검색</span><span class="sxs-lookup"><span data-stu-id="965fe-123">Retrieve Metadata</span></span>](../../../../docs/framework/wcf/samples/retrieve-metadata.md)  
 [<span data-ttu-id="965fe-124">메타데이터</span><span class="sxs-lookup"><span data-stu-id="965fe-124">Metadata</span></span>](../../../../docs/framework/wcf/feature-details/metadata.md)  
 [<span data-ttu-id="965fe-125">메타데이터 게시</span><span class="sxs-lookup"><span data-stu-id="965fe-125">Publishing Metadata</span></span>](../../../../docs/framework/wcf/feature-details/publishing-metadata.md)  
 [<span data-ttu-id="965fe-126">메타데이터 끝점 게시</span><span class="sxs-lookup"><span data-stu-id="965fe-126">Publishing Metadata Endpoints</span></span>](../../../../docs/framework/wcf/publishing-metadata-endpoints.md)
