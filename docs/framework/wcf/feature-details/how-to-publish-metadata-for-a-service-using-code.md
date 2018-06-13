---
title: '방법: 코드를 사용하여 서비스에 대한 메타데이터 게시'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 51407e6d-4d87-42d5-be7c-9887b8652006
ms.openlocfilehash: bef5421d377bcae6e8c56b0117ebbe22a861de86
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33496626"
---
# <a name="how-to-publish-metadata-for-a-service-using-code"></a><span data-ttu-id="b5161-102">방법: 코드를 사용하여 서비스에 대한 메타데이터 게시</span><span class="sxs-lookup"><span data-stu-id="b5161-102">How to: Publish Metadata for a Service Using Code</span></span>
<span data-ttu-id="b5161-103">Windows Communication Foundation (WCF) 서비스에 대 한 메타 데이터 게시를 설명 하는 두 방법 항목 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="b5161-103">This is one of two how-to topics that discuss publishing metadata for a Windows Communication Foundation (WCF) service.</span></span> <span data-ttu-id="b5161-104">서비스에서 메타데이터를 게시하는 방법을 지정하는 두 가지 방법은 구성 파일을 사용하는 방법과 코드를 사용하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="b5161-104">There are two ways to specify how a service should publish metadata, using a configuration file and using code.</span></span> <span data-ttu-id="b5161-105">이 항목에서는 코드를 사용하여 서비스에 대해 메타데이터를 게시하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b5161-105">This topic shows how to publish metadata for a service using a code.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="b5161-106">이 항목에서는 보호되지 않은 방식으로 메타데이터를 게시하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b5161-106">This topic shows how to publish metadata in an unsecure manner.</span></span> <span data-ttu-id="b5161-107">즉, 모든 클라이언트가 서비스에서 메타데이터를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5161-107">Any client can retrieve the metadata from the service.</span></span> <span data-ttu-id="b5161-108">서비스에서 보호되는 방식으로 메타데이터를 게시해야 하는 경우에는</span><span class="sxs-lookup"><span data-stu-id="b5161-108">If you require your service to publish metadata in a secure manner.</span></span> <span data-ttu-id="b5161-109">참조 [메타 데이터 끝점을 보호 하는 사용자 지정](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b5161-109">see [Custom Secure Metadata Endpoint](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md).</span></span>  
  
 <span data-ttu-id="b5161-110">구성 파일에서 메타 데이터를 게시 하는 방법에 대 한 자세한 내용은 참조 [하는 방법: 구성 파일을 사용 하 여 서비스에 대 한 메타 데이터 게시](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b5161-110">For more information about publishing metadata in a configuration file, see [How to: Publish Metadata for a Service Using a Configuration File](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md).</span></span> <span data-ttu-id="b5161-111">메타데이터를 게시하면 클라이언트에서 WS-Transfer GET 요청을 사용하는 메타데이터 또는 `?wsdl` 쿼리 문자열을 사용하는 HTTP/GET 요청을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5161-111">Publishing metadata allows clients to retrieve the metadata using a WS-Transfer GET request or an HTTP/GET request using the `?wsdl` query string.</span></span> <span data-ttu-id="b5161-112">코드가 작동 중인지 확인하려면 기본 WCF 서비스를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5161-112">To be sure that the code is working you must create a basic WCF service.</span></span> <span data-ttu-id="b5161-113">다음 코드로 된 기본 자체 호스팅 서비스가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5161-113">A basic self-hosted service is provided in the following code.</span></span>  
  
 [!code-csharp[htPublishMetadataCode#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#0)]
 [!code-vb[htPublishMetadataCode#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#0)]  
  
### <a name="to-publish-metadata-in-code"></a><span data-ttu-id="b5161-114">코드에서 메타데이터를 게시하려면</span><span class="sxs-lookup"><span data-stu-id="b5161-114">To publish metadata in code</span></span>  
  
1.  <span data-ttu-id="b5161-115">콘솔 응용 프로그램의 main 메서드 내에서 서비스 형식 및 기본 주소를 전달하여 <xref:System.ServiceModel.ServiceHost> 개체를 인스턴스화합니다.</span><span class="sxs-lookup"><span data-stu-id="b5161-115">Within the main method of a console application, instantiate a <xref:System.ServiceModel.ServiceHost> object by passing in the service type and the base address.</span></span>  
  
     [!code-csharp[htPublishMetadataCode#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#1)]
     [!code-vb[htPublishMetadataCode#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#1)]  
  
2.  <span data-ttu-id="b5161-116">1단계의 코드 바로 아래에 try 블록을 만듭니다. 이렇게 하면 서비스가 실행되는 동안 throw된 예외가 catch됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5161-116">Create a try block immediately below the code for step 1, this catches any exceptions that get thrown while the service is running.</span></span>  
  
     [!code-csharp[htPublishMetadataCode#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#2)]
     [!code-vb[htPublishMetadataCode#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#2)]  
  
     [!code-csharp[htPublishMetadataCode#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#3)]
     [!code-vb[htPublishMetadataCode#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#3)]  
  
3.  <span data-ttu-id="b5161-117">서비스 호스트에 <xref:System.ServiceModel.Description.ServiceMetadataBehavior>가 포함되어 있는지 여부를 확인합니다. 포함되지 않은 경우에는 새 <xref:System.ServiceModel.Description.ServiceMetadataBehavior> 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b5161-117">Check to see whether the service host already contains a <xref:System.ServiceModel.Description.ServiceMetadataBehavior>, if not, create a new <xref:System.ServiceModel.Description.ServiceMetadataBehavior> instance.</span></span>  
  
     [!code-csharp[htPublishMetadataCode#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#4)]
     [!code-vb[htPublishMetadataCode#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#4)]  
  
4.  <span data-ttu-id="b5161-118"><xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> 속성을 `true.`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b5161-118">Set the <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> property to `true.`</span></span>  
  
     [!code-csharp[htPublishMetadataCode#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#5)]
     [!code-vb[htPublishMetadataCode#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#5)]  
  
5.  <span data-ttu-id="b5161-119"><xref:System.ServiceModel.Description.ServiceMetadataBehavior>에 <xref:System.ServiceModel.Description.MetadataExporter> 속성이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5161-119">The <xref:System.ServiceModel.Description.ServiceMetadataBehavior> contains a <xref:System.ServiceModel.Description.MetadataExporter> property.</span></span> <span data-ttu-id="b5161-120"><xref:System.ServiceModel.Description.MetadataExporter>에 <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A> 속성이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5161-120">The <xref:System.ServiceModel.Description.MetadataExporter> contains a <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A> property.</span></span> <span data-ttu-id="b5161-121"><xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A> 속성 값을 <xref:System.ServiceModel.Description.PolicyVersion.Policy15%2A>로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b5161-121">Set the value of the <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A> property to <xref:System.ServiceModel.Description.PolicyVersion.Policy15%2A>.</span></span> <span data-ttu-id="b5161-122"><xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A> 속성을 <xref:System.ServiceModel.Description.PolicyVersion.Policy12%2A>로 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5161-122">The <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A> property can also be set to <xref:System.ServiceModel.Description.PolicyVersion.Policy12%2A>.</span></span> <span data-ttu-id="b5161-123">로 설정 하면 <xref:System.ServiceModel.Description.PolicyVersion.Policy15%2A> 메타 데이터 내보내기 메타 데이터와 정책 정보를 생성 하는 "Ws-policy 1.5를 준수 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5161-123">When set to <xref:System.ServiceModel.Description.PolicyVersion.Policy15%2A> the metadata exporter generates policy information with the metadata that" conforms to WS-Policy 1.5.</span></span> <span data-ttu-id="b5161-124"><xref:System.ServiceModel.Description.PolicyVersion.Policy12%2A>로 설정된 경우, 메타데이터 내보내기는 WS-Policy 1.2를 준수하는 정책 정보를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="b5161-124">When set to <xref:System.ServiceModel.Description.PolicyVersion.Policy12%2A> the metadata exporter generates policy information that conforms to WS-Policy 1.2.</span></span>  
  
     [!code-csharp[htPublishMetadataCode#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#6)]
     [!code-vb[htPublishMetadataCode#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#6)]  
  
6.  <span data-ttu-id="b5161-125">서비스 호스트의 동작 컬렉션에 <xref:System.ServiceModel.Description.ServiceMetadataBehavior> 인스턴스를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b5161-125">Add the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> instance to the service host's behaviors collection.</span></span>  
  
     [!code-csharp[htPublishMetadataCode#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#7)]
     [!code-vb[htPublishMetadataCode#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#7)]  
  
7.  <span data-ttu-id="b5161-126">서비스 호스트에 메타데이터 교환 끝점을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b5161-126">Add the metadata exchange endpoint to the service host.</span></span>  
  
     [!code-csharp[htPublishMetadataCode#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#8)]
     [!code-vb[htPublishMetadataCode#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#8)]  
  
8.  <span data-ttu-id="b5161-127">서비스 호스트에 응용 프로그램 끝점을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b5161-127">Add an application endpoint to the service host.</span></span>  
  
     [!code-csharp[htPublishMetadataCode#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#9)]
     [!code-vb[htPublishMetadataCode#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#9)]  
  
    > [!NOTE]
    >  <span data-ttu-id="b5161-128">서비스에 끝점을 추가하지 않으면 런타임에서 기본 끝점을 자동으로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b5161-128">If you do not add any endpoints to the service, the runtime adds default endpoints for you.</span></span> <span data-ttu-id="b5161-129">이 예제에서는 서비스의 <xref:System.ServiceModel.Description.ServiceMetadataBehavior>가 `true`로 설정되어 있으므로 서비스의 메타데이터 게시 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b5161-129">In this example, because the service has a <xref:System.ServiceModel.Description.ServiceMetadataBehavior> set to `true`, the service has publishing metadata enabled.</span></span> <span data-ttu-id="b5161-130">기본 끝점에 대 한 자세한 내용은 참조 [단순화 된 구성](../../../../docs/framework/wcf/simplified-configuration.md) 및 [WCF 서비스에 대 한 구성을 단순화](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b5161-130">For more information about default endpoints, see [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
9. <span data-ttu-id="b5161-131">서비스 호스트를 열고 들어오는 호출을 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="b5161-131">Open the service host and wait for incoming calls.</span></span> <span data-ttu-id="b5161-132">사용자가 Enter 키를 누르면 서비스 호스트가 닫힙니다.</span><span class="sxs-lookup"><span data-stu-id="b5161-132">When the user presses ENTER, close the service host.</span></span>  
  
     [!code-csharp[htPublishMetadataCode#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#10)]
     [!code-vb[htPublishMetadataCode#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#10)]  
  
10. <span data-ttu-id="b5161-133">콘솔 응용 프로그램을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b5161-133">Build and run the console application.</span></span>  
  
11. <span data-ttu-id="b5161-134">Internet Explorer를 사용 하 여 서비스의 기본 주소를 찾습니다 (http://localhost:8001/MetadataSample 이 샘플의) 메타 데이터 게시가 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b5161-134">Use Internet Explorer to browse to the base address of the service (http://localhost:8001/MetadataSample in this sample) and verify that the metadata publishing is turned on.</span></span> <span data-ttu-id="b5161-135">웹 페이지의 맨 위에 "간단한 서비스"라는 메시지가 표시되고 바로 아래에 "서비스를 만들었습니다."라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5161-135">You should see a Web page displayed that says "Simple Service" at the top and immediately below "You have created a service."</span></span> <span data-ttu-id="b5161-136">그렇지 않으면 "이 서비스에 대한 메타데이터 게시는 현재 사용할 수 없습니다."라는 메시지가 결과 페이지의 맨 위에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b5161-136">If not, a message at the top of the resulting page displays: "Metadata publishing for this service is currently disabled."</span></span>  
  
## <a name="example"></a><span data-ttu-id="b5161-137">예제</span><span class="sxs-lookup"><span data-stu-id="b5161-137">Example</span></span>  
 <span data-ttu-id="b5161-138">다음 코드 예제에서는 코드에서 서비스에 대 한 메타 데이터를 게시 하는 기본 WCF 서비스의 구현을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b5161-138">The following code example shows the implementation of a basic WCF service that publishes metadata for the service in code.</span></span>  
  
 [!code-csharp[htPublishMetadataCode#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#11)]
 [!code-vb[htPublishMetadataCode#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="b5161-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b5161-139">See Also</span></span>  
 [<span data-ttu-id="b5161-140">방법: 관리되는 응용 프로그램에서 WCF 서비스 호스트</span><span class="sxs-lookup"><span data-stu-id="b5161-140">How to: Host a WCF Service in a Managed Application</span></span>](../../../../docs/framework/wcf/how-to-host-a-wcf-service-in-a-managed-application.md)  
 [<span data-ttu-id="b5161-141">자체 호스팅</span><span class="sxs-lookup"><span data-stu-id="b5161-141">Self-Host</span></span>](../../../../docs/framework/wcf/samples/self-host.md)  
 [<span data-ttu-id="b5161-142">메타데이터 아키텍처 개요</span><span class="sxs-lookup"><span data-stu-id="b5161-142">Metadata Architecture Overview</span></span>](../../../../docs/framework/wcf/feature-details/metadata-architecture-overview.md)  
 [<span data-ttu-id="b5161-143">메타데이터 사용</span><span class="sxs-lookup"><span data-stu-id="b5161-143">Using Metadata</span></span>](../../../../docs/framework/wcf/feature-details/using-metadata.md)  
 [<span data-ttu-id="b5161-144">방법: 구성 파일을 사용하여 서비스의 메타데이터 게시</span><span class="sxs-lookup"><span data-stu-id="b5161-144">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
