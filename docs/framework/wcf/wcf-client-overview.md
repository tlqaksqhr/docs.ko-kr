---
title: "WCF 클라이언트 개요"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: clients [WCF], architecture
ms.assetid: f60d9bc5-8ade-4471-8ecf-5a07a936c82d
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6333db92d010eab7765cfc62a9f64601d5b82d55
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="wcf-client-overview"></a><span data-ttu-id="7226a-102">WCF 클라이언트 개요</span><span class="sxs-lookup"><span data-stu-id="7226a-102">WCF Client Overview</span></span>
<span data-ttu-id="7226a-103">이 단원에서는 클라이언트 응용 프로그램이 수행하는 작업, [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 클라이언트를 구성, 생성 및 사용하는 방법, 그리고 클라이언트 응용 프로그램의 보안을 유지하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-103">This section describes what client applications do, how to configure, create, and use a [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] client, and how to secure client applications.</span></span>  
  
## <a name="using-wcf-client-objects"></a><span data-ttu-id="7226a-104">WCF 클라이언트 개체 사용</span><span class="sxs-lookup"><span data-stu-id="7226a-104">Using WCF Client Objects</span></span>  
 <span data-ttu-id="7226a-105">클라이언트 응용 프로그램은 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 클라이언트를 사용하여 다른 응용 프로그램과 통신하는, 관리되는 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-105">A client application is a managed application that uses a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client to communicate with another application.</span></span> <span data-ttu-id="7226a-106">[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스에 대한 클라이언트 응용 프로그램을 만들려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-106">To create a client application for a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service requires the following steps:</span></span>  
  
1.  <span data-ttu-id="7226a-107">서비스 끝점에 대한 서비스 계약, 바인딩 및 주소 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-107">Obtain the service contract, bindings, and address information for a service endpoint.</span></span>  
  
2.  <span data-ttu-id="7226a-108">이 정보를 사용하여 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 클라이언트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-108">Create a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client using that information.</span></span>  
  
3.  <span data-ttu-id="7226a-109">작업을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-109">Call operations.</span></span>  
  
4.  <span data-ttu-id="7226a-110">[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 클라이언트 개체를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-110">Close the [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client object.</span></span>  
  
 <span data-ttu-id="7226a-111">다음 단원에서는 이러한 단계에 대해 설명하고 다음과 같은 문제를 간략하게 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-111">The following sections discuss these steps and provide brief introductions to the following issues:</span></span>  
  
-   <span data-ttu-id="7226a-112">오류 처리</span><span class="sxs-lookup"><span data-stu-id="7226a-112">Handling errors.</span></span>  
  
-   <span data-ttu-id="7226a-113">클라이언트 구성 및 보안</span><span class="sxs-lookup"><span data-stu-id="7226a-113">Configuring and securing clients.</span></span>  
  
-   <span data-ttu-id="7226a-114">이중 서비스에 대한 콜백 개체 만들기</span><span class="sxs-lookup"><span data-stu-id="7226a-114">Creating callback objects for duplex services.</span></span>  
  
-   <span data-ttu-id="7226a-115">비동기적으로 서비스 호출</span><span class="sxs-lookup"><span data-stu-id="7226a-115">Calling services asynchronously.</span></span>  
  
-   <span data-ttu-id="7226a-116">클라이언트 채널을 사용하여 서비스 호출</span><span class="sxs-lookup"><span data-stu-id="7226a-116">Calling services using client channels.</span></span>  
  
## <a name="obtain-the-service-contract-bindings-and-addresses"></a><span data-ttu-id="7226a-117">서비스 계약, 바인딩 및 주소 가져오기</span><span class="sxs-lookup"><span data-stu-id="7226a-117">Obtain the Service Contract, Bindings, and Addresses</span></span>  
 <span data-ttu-id="7226a-118">[!INCLUDE[indigo2](../../../includes/indigo2-md.md)]에서 서비스 및 클라이언트는 관리되는 특성, 인터페이스 및 메서드를 사용하여 계약을 모델링합니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-118">In [!INCLUDE[indigo2](../../../includes/indigo2-md.md)], services and clients model contracts using managed attributes, interfaces, and methods.</span></span> <span data-ttu-id="7226a-119">클라이언트 응용 프로그램에서 서비스에 연결하려면 서비스 계약에 대한 형식 정보를 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-119">To connect to a service in a client application, you need to obtain the type information for the service contract.</span></span> <span data-ttu-id="7226a-120">일반적으로 이렇게 하면 사용 하 여는 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md), 서비스에서 메타 데이터를 다운로드 하는 사용자가 선택한 언어의 관리 되는 소스 코드 파일을 변환 및 클라이언트를 만듭니다 구성 하는 데 사용할 수 있는 응용 프로그램 구성 파일에 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 클라이언트 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-120">Typically, you do this by using the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md), which downloads metadata from the service, converts it to a managed source code file in the language of your choice, and creates a client application configuration file that you can use to configure your [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client object.</span></span> <span data-ttu-id="7226a-121">예를 들어, [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 클라이언트 개체를 만들어 `MyCalculatorService`를 호출하려는 경우에 해당 서비스에 대한 메타데이터가 `http://computerName/MyCalculatorService/Service.svc?wsdl`에 게시된다면, 다음 코드 예제에서는 Svcutil.exe를 사용하여 관리되는 코드에 서비스 계약이 들어 있는 `ClientCode.vb` 파일을 가져오는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-121">For example, if you are going to create an [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client object to invoke a `MyCalculatorService`, and you know that the metadata for that service is published at `http://computerName/MyCalculatorService/Service.svc?wsdl`, then the following code example shows how to use Svcutil.exe to obtain a `ClientCode.vb` file that contains the service contract in managed code.</span></span>  
  
```  
svcutil /language:vb /out:ClientCode.vb /config:app.config http://computerName/MyCalculatorService/Service.svc?wsdl  
```  
  
 <span data-ttu-id="7226a-122">클라이언트 응용 프로그램에서 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 클라이언트 개체를 만드는 데 사용할 수 있는 다른 어셈블리나 클라이언트 응용 프로그램으로 이 계약 코드를 컴파일할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-122">You can either compile this contract code into the client application or into another assembly that the client application can then use to create an [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client object.</span></span> <span data-ttu-id="7226a-123">구성 파일을 사용하여 클라이언트 개체가 서비스에 제대로 연결하도록 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-123">You can use the configuration file to configure the client object to properly connect to the service .</span></span>  
  
 <span data-ttu-id="7226a-124">이 프로세스의 예제를 보려면 [하는 방법: 클라이언트 만들기](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-124">For an example of this process, see [How to: Create a Client](../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span></span> <span data-ttu-id="7226a-125">계약에 대 한 자세한 정보를 참조 하십시오. [계약](../../../docs/framework/wcf/feature-details/contracts.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-125">For more complete information about contracts, see [Contracts](../../../docs/framework/wcf/feature-details/contracts.md).</span></span>  
  
## <a name="create-a-wcf-client-object"></a><span data-ttu-id="7226a-126">WCF 클라이언트 개체 만들기</span><span class="sxs-lookup"><span data-stu-id="7226a-126">Create a WCF Client Object</span></span>  
 <span data-ttu-id="7226a-127">[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 클라이언트는 클라이언트가 원격 서비스와 통신하는 데 사용할 수 있는 형식으로 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스를 나타내는 로컬 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-127">A [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client is a local object that represents a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service in a form that the client can use to communicate with the remote service.</span></span> [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]<span data-ttu-id="7226a-128"> 클라이언트 형식은 대상 서비스 계약을 구현하기 때문에 대상 서비스 계약을 만들어 구성할 경우 클라이언트 개체를 사용하여 서비스 작업을 직접 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-128"> client types implement the target service contract, so when you create one and configure it, you can then use the client object directly to invoke service operations.</span></span> <span data-ttu-id="7226a-129">[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 메서드 호출을 메시지로, 서비스에 보내, 회신을 수신 대기 및 해당 값을 반환 하는 런타임은 변환는 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 반환 값으로 클라이언트 개체 또는 `out` 또는 `ref` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-129">The [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] run time converts the method calls into messages, sends them to the service, listens for the reply, and returns those values to the [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client object as return values or `out` or `ref` parameters.</span></span>  
  
 <span data-ttu-id="7226a-130">[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 클라이언트 채널 개체를 사용하여 서비스를 연결한 후 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-130">You can also use [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client channel objects to connect with and use services.</span></span> <span data-ttu-id="7226a-131">자세한 내용은 참조 [WCF 클라이언트 아키텍처](../../../docs/framework/wcf/feature-details/client-architecture.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-131">For details, see [WCF Client Architecture](../../../docs/framework/wcf/feature-details/client-architecture.md).</span></span>  
  
#### <a name="creating-a-new-wcf-object"></a><span data-ttu-id="7226a-132">새 WCF 개체 만들기</span><span class="sxs-lookup"><span data-stu-id="7226a-132">Creating a New WCF Object</span></span>  
 <span data-ttu-id="7226a-133"><xref:System.ServiceModel.ClientBase%601> 클래스 사용을 설명하기 위해 다음 서비스 계약이 생성되어 있는 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-133">To illustrate the use of a <xref:System.ServiceModel.ClientBase%601> class, assume the following simple service contract has been generated from a service application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7226a-134">[!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]를 사용하여 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 클라이언트를 만들 경우 프로젝트에 대한 서비스 참조를 추가하면 개체가 개체 브라우저에 자동으로 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-134">If you are using [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] to create your [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client, objects are loaded automatically into the object browser when you add a service reference to your project.</span></span>  
  
 [!code-csharp[C_GeneratedCodeFiles#12](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#12)]  
  
 <span data-ttu-id="7226a-135">[!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]를 사용하지 않는 경우 생성된 계약 코드를 조사하여 <xref:System.ServiceModel.ClientBase%601> 및 서비스 계약 인터페이스 `ISampleService`를 확장하는 형식을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-135">If you are not using [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], examine the generated contract code to find the type that extends <xref:System.ServiceModel.ClientBase%601> and the service contract interface `ISampleService`.</span></span> <span data-ttu-id="7226a-136">이 경우 형식은 다음 코드와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-136">In this case, that type looks like the following code:</span></span>  
  
 [!code-csharp[C_GeneratedCodeFiles#14](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#14)]  
  
 <span data-ttu-id="7226a-137">생성자 중 하나를 사용하여 이 클래스를 로컬 개체로 만든 다음 구성하여 `ISampleService` 형식 서비스에 연결하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-137">This class can be created as a local object using one of the constructors, configured, and then used to connect to a service of the type `ISampleService`.</span></span>  
  
 <span data-ttu-id="7226a-138">[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 클라이언트 개체를 먼저 만든 다음 단일 try/catch 블록에서 해당 개체를 사용하고 닫는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-138">It is recommended that you create your [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client object first, and then use it and close it inside a single try/catch block.</span></span> <span data-ttu-id="7226a-139">`using` 문(`Using`의 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)])은 특정 예외 모드에서 예외를 마스킹할 수 있으므로 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="7226a-139">You should not use the `using` statement (`Using` in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) because it may mask exceptions in certain failure modes.</span></span> [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="7226a-140">다음 섹션 및 같이 [Using 문과 문제 방지](../../../docs/framework/wcf/samples/avoiding-problems-with-the-using-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-140"> the following sections as well as [Avoiding Problems with the Using Statement](../../../docs/framework/wcf/samples/avoiding-problems-with-the-using-statement.md).</span></span>  
  
### <a name="contracts-bindings-and-addresses"></a><span data-ttu-id="7226a-141">계약, 바인딩 및 주소</span><span class="sxs-lookup"><span data-stu-id="7226a-141">Contracts, Bindings, and Addresses</span></span>  
 <span data-ttu-id="7226a-142">[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 클라이언트 개체를 만들려면 클라이언트 개체를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-142">Before you can create a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client object, you must configure the client object.</span></span> <span data-ttu-id="7226a-143">특히 서비스 있어야 *끝점* 사용 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-143">Specifically, it must have a service *endpoint* to use.</span></span> <span data-ttu-id="7226a-144">끝점은 서비스 계약, 바인딩 및 주소의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-144">An endpoint is the combination of a service contract, a binding, and an address.</span></span> <span data-ttu-id="7226a-145">([!INCLUDE[crabout](../../../includes/crabout-md.md)] 끝점, 참조 [끝점: 주소, 바인딩 및 계약](../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md).) 이 정보에 일반적으로 [ \<끝점 >](../../../docs/framework/configure-apps/file-schema/wcf/endpoint-of-client.md) Svcutil.exe 도구를 생성 하 고 클라이언트를 만들 때 자동으로 로드 되는 것과 같은 클라이언트 응용 프로그램 구성 파일의 요소 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-145">([!INCLUDE[crabout](../../../includes/crabout-md.md)] endpoints, see [Endpoints: Addresses, Bindings, and Contracts](../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md).) Typically, this information is located in the [\<endpoint>](../../../docs/framework/configure-apps/file-schema/wcf/endpoint-of-client.md) element in a client application configuration file, such as the one the Svcutil.exe tool generates, and is loaded automatically when you create your client object.</span></span> <span data-ttu-id="7226a-146">두 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 클라이언트 형식에는 이 정보를 프로그래밍 방식으로 지정할 수 있게 해주는 오버로드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-146">Both [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client types also have overloads that enable you to programmatically specify this information.</span></span>  
  
 <span data-ttu-id="7226a-147">예를 들어, 이전 예제에 사용된 `ISampleService`에 대해 생성된 구성 파일에는 다음과 같은 끝점 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-147">For example, a generated configuration file for an `ISampleService` used in the preceding examples contains the following endpoint information.</span></span>  
  
 [!code-xml[C_GeneratedCodeFiles#19](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/common/client.exe.config#19)]  
  
 <span data-ttu-id="7226a-148">이 구성 파일은 `<client>` 요소에서 대상 끝점을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-148">This configuration file specifies a target endpoint in the `<client>` element.</span></span> <span data-ttu-id="7226a-149">여러 대상 끝점을 사용하는 방법에 대한 [!INCLUDE[crabout](../../../includes/crabout-md.md)]는 <xref:System.ServiceModel.ClientBase%601.%23ctor%2A?displayProperty=nameWithType> 또는 <xref:System.ServiceModel.ChannelFactory%601.%23ctor%2A?displayProperty=nameWithType> 생성자를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7226a-149">[!INCLUDE[crabout](../../../includes/crabout-md.md)] using multiple target endpoints, see the <xref:System.ServiceModel.ClientBase%601.%23ctor%2A?displayProperty=nameWithType> or the <xref:System.ServiceModel.ChannelFactory%601.%23ctor%2A?displayProperty=nameWithType> constructors.</span></span>  
  
## <a name="calling-operations"></a><span data-ttu-id="7226a-150">작업 호출</span><span class="sxs-lookup"><span data-stu-id="7226a-150">Calling Operations</span></span>  
 <span data-ttu-id="7226a-151">클라이언트 개체를 만들어 구성한 후 try/catch 블록을 만들고 로컬 개체에 대해서와 같은 방법으로 작업을 호출한 다음 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 클라이언트 개체를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-151">Once you have a client object created and configured, create a try/catch block, call operations in the same way that you would if the object were local, and close the [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client object.</span></span> <span data-ttu-id="7226a-152">클라이언트 응용 프로그램이 첫 번째 작업을 호출하면 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]에서 기본 채널을 자동으로 엽니다. 개체가 재생되면 기본 채널이 닫힙니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-152">When the client application calls the first operation, [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] automatically opens the underlying channel, and the underlying channel is closed when the object is recycled.</span></span> <span data-ttu-id="7226a-153">또는 다른 작업을 호출하기 이전 또는 이후에 채널을 명시적으로 열었다가 닫을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-153">(Alternatively, you can also explicitly open and close the channel prior to or subsequent to calling other operations.)</span></span>  
  
 <span data-ttu-id="7226a-154">예를 들어, 다음과 같은 서비스 계약을 가정해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-154">For example, if you have the following service contract:</span></span>  
  
```csharp  
namespace Microsoft.ServiceModel.Samples  
{  
    using System;  
    using System.ServiceModel;  
  
    [ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples")]  
    public interface ICalculator  
   {  
        [OperationContract]  
        double Add(double n1, double n2);  
        [OperationContract]  
        double Subtract(double n1, double n2);  
        [OperationContract]  
        double Multiply(double n1, double n2);  
        [OperationContract]  
        double Divide(double n1, double n2);  
    }  
}  
```  
  
```vb  
Namespace Microsoft.ServiceModel.Samples  
  
    Imports System  
    Imports System.ServiceModel  
  
    <ServiceContract(Namespace:= _  
    "http://Microsoft.ServiceModel.Samples")> _   
   Public Interface ICalculator  
        <OperationContract> _   
        Function Add(n1 As Double, n2 As Double) As Double  
        <OperationContract> _   
        Function Subtract(n1 As Double, n2 As Double) As Double  
        <OperationContract> _   
        Function Multiply(n1 As Double, n2 As Double) As Double  
        <OperationContract> _   
     Function Divide(n1 As Double, n2 As Double) As Double  
End Interface  
```  
  
 <span data-ttu-id="7226a-155">다음 코드 예제에 설명된 것처럼 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 클라이언트 개체를 만든 다음 해당 메서드를 호출하여 작업을 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-155">You can call operations by creating a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client object and calling its methods, as the following code example demonstrates.</span></span> <span data-ttu-id="7226a-156">[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 클라이언트 개체 열기, 호출 및 닫기는 단일 try/catch 블록 내에서 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-156">Note that the opening, calling, and closing of the [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client object occurs within a single try/catch block.</span></span> [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="7226a-157">[WCF 클라이언트를 사용 하 여 서비스에 액세스](../../../docs/framework/wcf/feature-details/accessing-services-using-a-client.md) 및 [Using 문과 문제 방지](../../../docs/framework/wcf/samples/avoiding-problems-with-the-using-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-157"> [Accessing Services Using a WCF Client](../../../docs/framework/wcf/feature-details/accessing-services-using-a-client.md) and [Avoiding Problems with the Using Statement](../../../docs/framework/wcf/samples/avoiding-problems-with-the-using-statement.md).</span></span>  
  
 [!code-csharp[C_GeneratedCodeFiles#20](../../../samples/snippets/csharp/VS_Snippets_CFX/c_generatedcodefiles/cs/proxycode.cs#20)]  
  
## <a name="handling-errors"></a><span data-ttu-id="7226a-158">오류 처리</span><span class="sxs-lookup"><span data-stu-id="7226a-158">Handling Errors</span></span>  
 <span data-ttu-id="7226a-159">기본 클라이언트 채널을 명시적으로 열거나 작업을 호출하여 자동으로 열 때, 클라이언트 또는 채널 개체를 사용하여 작업을 호출할 경우 또는 기본 클라이언트 채널을 닫을 때 클라이언트 응용 프로그램에서 예외가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-159">Exceptions can occur in a client application when opening the underlying client channel (whether explicitly or automatically by calling an operation), using the client or channel object to call operations, or when closing the underlying client channel.</span></span> <span data-ttu-id="7226a-160">적어도 응용 프로그램에서 가능한 <xref:System.TimeoutException?displayProperty=nameWithType> 및 <xref:System.ServiceModel.CommunicationException?displayProperty=nameWithType> 예외를 비롯하여 작업에서 반환되는 SOAP 오류로 인해 throw되는 <xref:System.ServiceModel.FaultException?displayProperty=nameWithType> 개체를 처리하도록 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-160">It is recommended at a minimum that applications expect to handle possible <xref:System.TimeoutException?displayProperty=nameWithType> and <xref:System.ServiceModel.CommunicationException?displayProperty=nameWithType> exceptions in addition to any <xref:System.ServiceModel.FaultException?displayProperty=nameWithType> objects thrown as a result of SOAP faults returned by operations.</span></span> <span data-ttu-id="7226a-161">작업 계약에 지정된 SOAP 오류는 형식 매개 변수가 SOAP 오류의 세부 유형인 <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType>으로, 클라이언트 응용 프로그램에서 발생됩니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-161">SOAP faults specified in the operation contract are raised to client applications as a <xref:System.ServiceModel.FaultException%601?displayProperty=nameWithType> where the type parameter is the detail type of the SOAP fault.</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="7226a-162">클라이언트 응용 프로그램에서 오류 조건을 처리, 참조 [송신 및 수신 오류](../../../docs/framework/wcf/sending-and-receiving-faults.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-162"> handling error conditions in a client application, see [Sending and Receiving Faults](../../../docs/framework/wcf/sending-and-receiving-faults.md).</span></span> <span data-ttu-id="7226a-163">전체 샘플은 클라이언트에서 오류를 처리 하는 방법, 참조 [예상 예외](../../../docs/framework/wcf/samples/expected-exceptions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-163">For a complete sample the shows how to handle errors in a client, see [Expected Exceptions](../../../docs/framework/wcf/samples/expected-exceptions.md).</span></span>  
  
## <a name="configuring-and-securing-clients"></a><span data-ttu-id="7226a-164">클라이언트 구성 및 보안</span><span class="sxs-lookup"><span data-stu-id="7226a-164">Configuring and Securing Clients</span></span>  
 <span data-ttu-id="7226a-165">클라이언트를 구성하려면 클라이언트 생성자와 속성을 사용하여 클라이언트 또는 채널 개체에 대한 대상 끝점 정보를 프로그래밍 방식으로 로드할 수도 있지만, 일반적으로 구성 파일에서 이 정보를 로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-165">Configuring a client starts with the required loading of target endpoint information for the client or channel object, usually from a configuration file, although you can also load this information programmatically using the client constructors and properties.</span></span> <span data-ttu-id="7226a-166">그러나 다양한 보안 시나리오에 대해 특정 클라이언트 동작을 활성화하는 추가 구성 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-166">However, additional configuration steps are required to enable certain client behavior and for many security scenarios.</span></span>  
  
 <span data-ttu-id="7226a-167">예를 들어, 서비스 계약에 대한 보안 요구 사항이 서비스 계약 인터페이스에 선언되어 있고, Svcutil.exe에서 구성 파일을 만든 경우 해당 파일에는 일반적으로 서비스의 보안 요구 사항을 지원할 수 있는 바인딩이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-167">For example, security requirements for service contracts are declared in the service contract interface, and if Svcutil.exe created a configuration file, that file usually contains a binding that is capable of supporting the security requirements of the service.</span></span> <span data-ttu-id="7226a-168">그러나, 클라이언트 자격 증명 구성처럼 추가 보안 구성이 필요한 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-168">In some cases, however, more security configuration may be required, such as configuring client credentials.</span></span> <span data-ttu-id="7226a-169">에 대 한 보안 구성에 대 한 자세한 내용은 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 클라이언트 참조 [클라이언트 보안](../../../docs/framework/wcf/securing-clients.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-169">For complete information about the configuration of security for [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] clients, see [Securing Clients](../../../docs/framework/wcf/securing-clients.md).</span></span>  
  
 <span data-ttu-id="7226a-170">또한 클라이언트 응용 프로그램에서 사용자 지정 런타임 동작과 같은 사용자 지정 수정을 사용할 수 있는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-170">In addition, some custom modifications can be enabled in client applications, such as custom run-time behaviors.</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="7226a-171">사용자 지정 클라이언트 동작을 구성을 참조 하는 방법 [클라이언트 동작 구성](../../../docs/framework/wcf/configuring-client-behaviors.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-171"> how to configure a custom client behavior, see [Configuring Client Behaviors](../../../docs/framework/wcf/configuring-client-behaviors.md).</span></span>  
  
## <a name="creating-callback-objects-for-duplex-services"></a><span data-ttu-id="7226a-172">이중 서비스에 대한 콜백 개체 만들기</span><span class="sxs-lookup"><span data-stu-id="7226a-172">Creating Callback Objects for Duplex Services</span></span>  
 <span data-ttu-id="7226a-173">이중 서비스는 계약 요구 사항에 따라 서비스를 호출하도록 콜백 개체를 제공하기 위해 클라이언트 응용 프로그램에서 구현해야 하는 콜백 계약을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-173">Duplex services specify a callback contract that the client application must implement in order to provide a callback object for the service to call according to the requirements of the contract.</span></span> <span data-ttu-id="7226a-174">콜백 개체는 정식 서비스가 아니지만(예를 들어, 콜백 개체를 사용하여 채널을 시작할 수 없음) 구현 및 구성을 위해 일종의 서비스로 간주될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-174">Although callback objects are not full services (for example, you cannot initiate a channel with a callback object), for the purposes of implementation and configuration they can be thought of as a kind of service.</span></span>  
  
 <span data-ttu-id="7226a-175">이중 서비스의 클라이언트는 다음을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-175">Clients of duplex services must:</span></span>  
  
-   <span data-ttu-id="7226a-176">콜백 계약 클래스 구현</span><span class="sxs-lookup"><span data-stu-id="7226a-176">Implement a callback contract class.</span></span>  
  
-   <span data-ttu-id="7226a-177">콜백 계약 구현 클래스의 인스턴스를 만든 다음 해당 인스턴스를 사용하여 <xref:System.ServiceModel.InstanceContext?displayProperty=nameWithType> 클라이언트 생성자에 전달할 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 개체 만들기</span><span class="sxs-lookup"><span data-stu-id="7226a-177">Create an instance of the callback contract implementation class and use it to create the <xref:System.ServiceModel.InstanceContext?displayProperty=nameWithType> object that you pass to the [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client constructor.</span></span>  
  
-   <span data-ttu-id="7226a-178">작업 호출 및 작업 콜백 처리</span><span class="sxs-lookup"><span data-stu-id="7226a-178">Invoke operations and handle operation callbacks.</span></span>  
  
 <span data-ttu-id="7226a-179">이중 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 클라이언트 개체는 콜백 서비스 구성을 포함하여 콜백을 지원하는 데 필요한 기능을 노출한다는 점만 제외하고 비이중 클라이언트 개체와 같은 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-179">Duplex [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] client objects function like their nonduplex counterparts, with the exception that they expose the functionality necessary to support callbacks, including the configuration of the callback service.</span></span>  
  
 <span data-ttu-id="7226a-180">예를 들어, 콜백 클래스에서 <xref:System.ServiceModel.CallbackBehaviorAttribute?displayProperty=nameWithType> 특성의 속성을 사용하여 콜백 개체 런타임 동작을 다양하게 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-180">For example, you can control various aspects of callback object runtime behavior by using properties of the <xref:System.ServiceModel.CallbackBehaviorAttribute?displayProperty=nameWithType> attribute on the callback class.</span></span> <span data-ttu-id="7226a-181">또 다른 예로, <xref:System.ServiceModel.Description.CallbackDebugBehavior?displayProperty=nameWithType> 클래스를 사용하여 콜백 개체를 호출하는 서비스에 예외 정보를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-181">Another example is the use of the <xref:System.ServiceModel.Description.CallbackDebugBehavior?displayProperty=nameWithType> class to enable the return of exception information to services that call the callback object.</span></span> [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="7226a-182">[이중 서비스](../../../docs/framework/wcf/feature-details/duplex-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-182"> [Duplex Services](../../../docs/framework/wcf/feature-details/duplex-services.md).</span></span> <span data-ttu-id="7226a-183">전체 샘플을 참조 하십시오. [이중](../../../docs/framework/wcf/samples/duplex.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-183">For a complete sample, see [Duplex](../../../docs/framework/wcf/samples/duplex.md).</span></span>  
  
 <span data-ttu-id="7226a-184">IIS(인터넷 정보 서비스) 5.1을 실행하는 Windows XP 컴퓨터에서 이중 클라이언트는 <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType> 클래스를 사용하여 클라이언트 기본 주소를 지정해야 합니다. 그렇지 않으면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-184">On Windows XP computers running Internet Information Services (IIS) 5.1, duplex clients must specify a client base address using the <xref:System.ServiceModel.WSDualHttpBinding?displayProperty=nameWithType> class or an exception is thrown.</span></span> <span data-ttu-id="7226a-185">다음 코드 예제에서는 코드에서 이 작업을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-185">The following code example shows how to do this in code.</span></span>  
  
 [!code-csharp[S_DualHttp#8](../../../samples/snippets/csharp/VS_Snippets_CFX/s_dualhttp/cs/program.cs#8)]
 [!code-vb[S_DualHttp#8](../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_dualhttp/vb/module1.vb#8)]  
  
 <span data-ttu-id="7226a-186">다음 코드에서는 구성 파일에서 이 작업을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-186">The following code shows how to do this in a configuration file</span></span>  
  
 [!code-csharp[S_DualHttp#134](../../../samples/snippets/csharp/VS_Snippets_CFX/s_dualhttp/cs/program.cs#134)]  
  
## <a name="calling-services-asynchronously"></a><span data-ttu-id="7226a-187">비동기적으로 서비스 호출</span><span class="sxs-lookup"><span data-stu-id="7226a-187">Calling Services Asynchronously</span></span>  
 <span data-ttu-id="7226a-188">작업이 호출되는 방법은 클라이언트 개발자에 의해 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-188">How operations are called is entirely up to the client developer.</span></span> <span data-ttu-id="7226a-189">작업을 구성하는 메시지는 관리되는 코드에 표시될 때 동기 메서드나 비동기 메서드에 매핑될 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-189">This is because the messages that make up an operation can be mapped to either synchronous or asynchronous methods when expressed in managed code.</span></span> <span data-ttu-id="7226a-190">따라서 작업을 비동기적으로 호출하는 클라이언트를 빌드하려면 Svcutil.exe에서 `/async` 옵션을 사용하여 비동기 클라이언트 코드를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-190">Therefore, if you want to build a client that calls operations asynchronously, you can use Svcutil.exe to generate asynchronous client code using the `/async` option.</span></span> [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="7226a-191">[하는 방법: 서비스 작업을 비동기적으로 호출](../../../docs/framework/wcf/feature-details/how-to-call-wcf-service-operations-asynchronously.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-191"> [How to: Call Service Operations Asynchronously](../../../docs/framework/wcf/feature-details/how-to-call-wcf-service-operations-asynchronously.md).</span></span>  
  
## <a name="calling-services-using-wcf-client-channels"></a><span data-ttu-id="7226a-192">WCF 클라이언트 채널을 사용하여 서비스 호출</span><span class="sxs-lookup"><span data-stu-id="7226a-192">Calling Services Using WCF Client Channels</span></span>  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]<span data-ttu-id="7226a-193"> 클라이언트 형식은 <xref:System.ServiceModel.ClientBase%601>를 확장합니다. 이 형식은 <xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType> 인터페이스에서 직접 파생되어 기본 채널 시스템을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-193"> client types extend <xref:System.ServiceModel.ClientBase%601>, which itself derives from <xref:System.ServiceModel.IClientChannel?displayProperty=nameWithType> interface to expose the underlying channel system.</span></span> <span data-ttu-id="7226a-194"><xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType> 클래스와의 대상 서비스 계약을 사용하여 서비스를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-194">You can invoke services by using the target service contract with the <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="7226a-195">자세한 내용은 참조 [WCF 클라이언트 아키텍처](../../../docs/framework/wcf/feature-details/client-architecture.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7226a-195">For details, see [WCF Client Architecture](../../../docs/framework/wcf/feature-details/client-architecture.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7226a-196">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7226a-196">See Also</span></span>  
 <xref:System.ServiceModel.ClientBase%601?displayProperty=nameWithType>  
 <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType>
