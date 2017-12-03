---
title: "방법: 서비스 끝점으로 메타데이터 가져오기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b69dbe20-92a1-4911-89d8-ffbc3dad4663
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: afc08d08a8843460972daf259027475cbbc10b66
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-import-metadata-into-service-endpoints"></a><span data-ttu-id="7376e-102">방법: 서비스 끝점으로 메타데이터 가져오기</span><span class="sxs-lookup"><span data-stu-id="7376e-102">How to: Import Metadata into Service Endpoints</span></span>
<span data-ttu-id="7376e-103">이 항목에 정의 된 서비스를 사용 하 여 서비스 끝점의 컬렉션으로 메타 데이터를 가져오는 방법에 설명 된 [시작](../../../../docs/framework/wcf/samples/getting-started-sample.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7376e-103">This topic explains how to import metadata into a collection of service endpoints and use the service defined in the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span> <span data-ttu-id="7376e-104">이 항목에서는 서비스에서 메타데이터를 가져온 다음 서비스에 `Add` 메서드를 호출하는 클라이언트 응용 프로그램을 만든 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7376e-104">This topic show how to create a client application that imports metadata from the service and then calls the `Add` method on the service.</span></span>  
  
### <a name="to-import-metadata-into-service-endpoints"></a><span data-ttu-id="7376e-105">서비스 끝점으로 메타데이터를 가져오려면</span><span class="sxs-lookup"><span data-stu-id="7376e-105">To import metadata into service endpoints</span></span>  
  
1.  <span data-ttu-id="7376e-106"><xref:System.ServiceModel.EndpointAddress> 개체를 선언하고 URI(Uniform Resource Identifier)를 사용하여 서비스의 MEX(메타데이터 교환) 주소에 대해 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="7376e-106">Declare an <xref:System.ServiceModel.EndpointAddress> object and initialize it with the Uniform Resource Identifier (URI) for the metadata exchange (MEX) address of the service.</span></span>  
  
     [!code-csharp[UE_ImportMetadata#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/ue_importmetadata/cs/client.cs#0)]  
  
2.  <span data-ttu-id="7376e-107">MEX 주소를 전달하여 <xref:System.ServiceModel.Description.MetadataExchangeClient>를 만들고 <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A>를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="7376e-107">Create a <xref:System.ServiceModel.Description.MetadataExchangeClient>, passing in the MEX address, and call <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A>.</span></span> <span data-ttu-id="7376e-108">그러면 서비스에서 메타데이터가 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="7376e-108">This retrieves the metadata from the service.</span></span>  
  
     [!code-csharp[UE_ImportMetadata#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/ue_importmetadata/cs/client.cs#1)]  
  
3.  <span data-ttu-id="7376e-109">이전에 검색한 메타데이터를 전달하여 <xref:System.ServiceModel.Description.WsdlImporter>를 만들고 <xref:System.ServiceModel.Description.WsdlImporter.ImportAllContracts%2A>를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="7376e-109">Create a <xref:System.ServiceModel.Description.WsdlImporter>, passing in the metadata previously retrieved, and call <xref:System.ServiceModel.Description.WsdlImporter.ImportAllContracts%2A>.</span></span> <span data-ttu-id="7376e-110">그러면 <xref:System.ServiceModel.Description.ContractDescription> 개체 컬렉션이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="7376e-110">This generates a collection of <xref:System.ServiceModel.Description.ContractDescription> objects.</span></span> <span data-ttu-id="7376e-111">필요에 따라 <xref:System.ServiceModel.Description.WsdlImporter.ImportAllEndpoints%2A> 또는 <xref:System.ServiceModel.Description.WsdlImporter.ImportAllBindings%2A>를 호출할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7376e-111">You could also call <xref:System.ServiceModel.Description.WsdlImporter.ImportAllEndpoints%2A> or <xref:System.ServiceModel.Description.WsdlImporter.ImportAllBindings%2A>, depending upon your needs.</span></span>  
  
     [!code-csharp[UE_ImportMetadata#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/ue_importmetadata/cs/client.cs#2)]  
  
    > [!NOTE]
    >  <span data-ttu-id="7376e-112">메타데이터를 가져온 후에는 클라이언트 채널을 만들거나 메타데이터를 내보낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7376e-112">After you have imported the metadata, you will not be able to create a client channel or export the metadata.</span></span> <span data-ttu-id="7376e-113">이 시점에는 형식 정보를 사용할 수 없기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="7376e-113">This is because no type information is available at this point.</span></span> <span data-ttu-id="7376e-114">실제로 서비스와 상호 작용하거나 메타데이터를 내보내려면 형식 정보가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7376e-114">Type information is required to actually interact with the service or export metadata.</span></span> <span data-ttu-id="7376e-115">형식 정보를 생성하려면 4단계와 5단계에 표시된 코드를 생성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7376e-115">To generate the type information, you need to generate code, shown in steps 4 and 5.</span></span> <span data-ttu-id="7376e-116">또는 <xref:System.ServiceModel.Description.MetadataResolver> 도우미 클래스를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7376e-116">Alternatively, you could use the <xref:System.ServiceModel.Description.MetadataResolver> helper class.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="7376e-117">[하는 방법: MetadataResolver를 사용 하 여 동적으로 바인딩 메타 데이터 가져오기](../../../../docs/framework/wcf/feature-details/how-to-use-metadataresolver-to-obtain-binding-metadata-dynamically.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7376e-117"> [How to: Use MetadataResolver to Obtain Binding Metadata Dynamically](../../../../docs/framework/wcf/feature-details/how-to-use-metadataresolver-to-obtain-binding-metadata-dynamically.md).</span></span>  
  
4.  <span data-ttu-id="7376e-118">각 계약에 대해 형식 정보를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="7376e-118">Generate type information for each contract.</span></span>  
  
     [!code-csharp[UE_ImportMetadata#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/ue_importmetadata/cs/client.cs#3)]  
  
5.  <span data-ttu-id="7376e-119">이제 이 정보를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7376e-119">Now you can use this information.</span></span> <span data-ttu-id="7376e-120">다음 샘플에서는 C# 소스 코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="7376e-120">The following sample generates C# source code.</span></span>  
  
     [!code-csharp[UE_ImportMetadata#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/ue_importmetadata/cs/client.cs#4)]  
  
## <a name="see-also"></a><span data-ttu-id="7376e-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7376e-121">See Also</span></span>  
 [<span data-ttu-id="7376e-122">메타 데이터</span><span class="sxs-lookup"><span data-stu-id="7376e-122">Metadata</span></span>](../../../../docs/framework/wcf/feature-details/metadata.md)  
 [<span data-ttu-id="7376e-123">시작</span><span class="sxs-lookup"><span data-stu-id="7376e-123">Getting Started</span></span>](../../../../docs/framework/wcf/samples/getting-started-sample.md)
