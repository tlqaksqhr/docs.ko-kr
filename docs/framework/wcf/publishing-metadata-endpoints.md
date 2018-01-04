---
title: "메타데이터 끝점 게시"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 29cd8a60-dfb7-460c-bf5a-c2b31b782671
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7f4d7d99304df1622f482a827d67d389760bf76d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="publishing-metadata-endpoints"></a><span data-ttu-id="2f5d9-102">메타데이터 끝점 게시</span><span class="sxs-lookup"><span data-stu-id="2f5d9-102">Publishing Metadata Endpoints</span></span>
[!INCLUDE[indigo1](../../../includes/indigo1-md.md)]<span data-ttu-id="2f5d9-103"> 서비스는 하나 이상의 메타데이터 끝점을 게시하여 메타데이터를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="2f5d9-103"> services publish metadata by publishing one or more metadata endpoints.</span></span> <span data-ttu-id="2f5d9-104">서비스 메타데이터를 게시하면 WS-MetadataExchange(MEX) 및 HTTP/GET 요청과 같이 표준화된 프로토콜을 통해 메타데이터를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f5d9-104">Publishing service metadata makes the metadata available using standardized protocols, such as WS-MetadataExchange (MEX) and HTTP/GET requests.</span></span> <span data-ttu-id="2f5d9-105">메타데이터 끝점은 주소, 바인딩 및 계약에 포함된 다른 서비스 끝점과 유사하며 구성 또는 코드를 통해 서비스 호스트에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f5d9-105">Metadata endpoints are similar to other service endpoints in that they have an address, a binding, and a contract, and they can be added to a service host through configuration or in code.</span></span> <span data-ttu-id="2f5d9-106">메타데이터 끝점 게시를 사용하도록 설정하려면 <xref:System.ServiceModel.Description.ServiceMetadataBehavior> 서비스 동작을 서비스에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f5d9-106">To enable publishing metadata endpoints, you must add the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> service behavior to the service.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2f5d9-107">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="2f5d9-107">In This Section</span></span>  
 [<span data-ttu-id="2f5d9-108">방법: 구성 파일을 사용하여 서비스의 메타데이터 게시</span><span class="sxs-lookup"><span data-stu-id="2f5d9-108">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 <span data-ttu-id="2f5d9-109">[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스가 메타데이터를 게시하여 클라이언트가 WS-MetadataExchange를 사용하는 메타데이터 또는 `?wsdl` 쿼리 문자열을 사용하는 HTTP/GET 요청을 검색할 수 있도록 구성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2f5d9-109">Demonstrates how to configure a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service to publish metadata so that clients can retrieve the metadata using a WS-MetadataExchange or an HTTP/GET request using the `?wsdl` query string.</span></span>  
  
 [<span data-ttu-id="2f5d9-110">방법: 코드를 사용하여 서비스에 대한 메타데이터 게시</span><span class="sxs-lookup"><span data-stu-id="2f5d9-110">How to: Publish Metadata for a Service Using Code</span></span>](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md)  
 <span data-ttu-id="2f5d9-111">클라이언트가 WS-MetadataExchange를 사용하는 메타데이터 또는 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 쿼리 문자열을 사용하는 HTTP/GET 요청을 검색할 수 있도록 메타데이터가 코드에서 `?wsdl` 서비스를 게시할 수 있는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2f5d9-111">Demonstrates how to enable metadata publishing for a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service in code so that clients can retrieve the metadata using a WS-MetadataExchange or an HTTP/GET request using the `?wsdl` query string.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f5d9-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2f5d9-112">See Also</span></span>  
 [<span data-ttu-id="2f5d9-113">메타데이터 게시</span><span class="sxs-lookup"><span data-stu-id="2f5d9-113">Publishing Metadata</span></span>](../../../docs/framework/wcf/feature-details/publishing-metadata.md)
