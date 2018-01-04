---
title: "Windows Communication Foundation 바인딩"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: bindings [WCF]
ms.assetid: 845df323-be53-4848-92ef-ba67a406484d
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e878aadf1c7df6042323c008ff52a4be8a9d817f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="windows-communication-foundation-bindings"></a><span data-ttu-id="27da0-102">Windows Communication Foundation 바인딩</span><span class="sxs-lookup"><span data-stu-id="27da0-102">Windows Communication Foundation Bindings</span></span>
<span data-ttu-id="27da0-103">바인딩은 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 서비스 끝점이 다른 끝점과 통신하는 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="27da0-103">Bindings specify how a [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] service endpoint communicates with other endpoints.</span></span> <span data-ttu-id="27da0-104">가장 기본적으로 바인딩은 HTTP 또는 TCP와 같은 사용할 전송을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="27da0-104">At its most basic, a binding must specify the transport (for example, HTTP or TCP) to use.</span></span> <span data-ttu-id="27da0-105">바인딩을 통해 보안 및 트랜잭션 지원과 같은 다른 특징을 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27da0-105">You can also set other characteristics, such as security and transaction support, through bindings.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="27da0-106">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="27da0-106">In This Section</span></span>  
 [<span data-ttu-id="27da0-107">WCF 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="27da0-107">WCF Bindings Overview</span></span>](../../../docs/framework/wcf/bindings-overview.md)  
 <span data-ttu-id="27da0-108">[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 바인딩이 수행하는 작업, 시스템에서 제공하는 바인딩 종류 및 이러한 바인딩을 정의하거나 수정하는 방법에 대해 간략히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="27da0-108">Overview of what [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] bindings do, what bindings the system provides, and how you can define or modify them.</span></span>  
  
 [<span data-ttu-id="27da0-109">시스템 제공 바인딩</span><span class="sxs-lookup"><span data-stu-id="27da0-109">System-Provided Bindings</span></span>](../../../docs/framework/wcf/system-provided-bindings.md)  
 <span data-ttu-id="27da0-110">[!INCLUDE[indigo2](../../../includes/indigo2-md.md)]에 포함된 바인딩 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="27da0-110">A list of bindings included with [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].</span></span> <span data-ttu-id="27da0-111">이러한 바인딩은 대부분의 보안 및 메시지 패턴 요구 사항을 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="27da0-111">These bindings cover the majority of security and message pattern requirements.</span></span>  
  
 [<span data-ttu-id="27da0-112">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="27da0-112">Using Bindings to Configure Services and Clients</span></span>](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 <span data-ttu-id="27da0-113">[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 바인딩에는 서비스 끝점에 연결하는 데 클라이언트가 사용해야 하는 중요한 정보가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27da0-113">A [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] binding contains important information that clients must use to connect to service endpoints.</span></span>  
  
 [<span data-ttu-id="27da0-114">서비스에 대한 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="27da0-114">Configuring Bindings for Services</span></span>](../../../docs/framework/wcf/configuring-bindings-for-wcf-services.md)  
 <span data-ttu-id="27da0-115">구성을 통해 관리자와 설치 관리자가 서비스 끝점에 대한 바인딩을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27da0-115">Configuration enables administrators and installers to customize the bindings for service endpoints.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="27da0-116">참조</span><span class="sxs-lookup"><span data-stu-id="27da0-116">Reference</span></span>  
 <xref:System.ServiceModel.Channels>  
  
## <a name="related-sections"></a><span data-ttu-id="27da0-117">관련 단원</span><span class="sxs-lookup"><span data-stu-id="27da0-117">Related Sections</span></span>  
 [<span data-ttu-id="27da0-118">끝점: 주소, 바인딩 및 계약</span><span class="sxs-lookup"><span data-stu-id="27da0-118">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)  
  
 [<span data-ttu-id="27da0-119">바인딩</span><span class="sxs-lookup"><span data-stu-id="27da0-119">Bindings</span></span>](../../../docs/framework/wcf/feature-details/bindings.md)  
  
## <a name="see-also"></a><span data-ttu-id="27da0-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="27da0-120">See Also</span></span>  
 [<span data-ttu-id="27da0-121">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="27da0-121">Custom Bindings</span></span>](../../../docs/framework/wcf/extending/custom-bindings.md)
