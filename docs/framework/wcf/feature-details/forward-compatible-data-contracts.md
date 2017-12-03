---
title: "이후 버전과 호환되는 데이터 계약"
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
helpviewer_keywords: data contracts [WCF], forward compatibility
ms.assetid: 413c9044-26f8-4ecb-968c-18495ea52cd9
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ef25e349ca6245ff3247f3a136d9a950d03d81d5
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="forward-compatible-data-contracts"></a><span data-ttu-id="94a2f-102">이후 버전과 호환되는 데이터 계약</span><span class="sxs-lookup"><span data-stu-id="94a2f-102">Forward-Compatible Data Contracts</span></span>
<span data-ttu-id="94a2f-103">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 데이터 계약 시스템의 특징은 시간에 따라 변경되지 않는 방법으로 계약을 개발할 수 있다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="94a2f-103">A feature of the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] data contract system is that contracts can evolve over time in nonbreaking ways.</span></span> <span data-ttu-id="94a2f-104">즉, 이전 버전의 데이터 계약을 가진 클라이언트가 새 버전의 동일한 데이터 계약을 가진 서비스와 통신할 수 있거나, 새 버전의 데이터 계약을 가진 클라이언트가 이전 버전의 동일한 데이터 계약과 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94a2f-104">That is, a client with an older version of a data contract can communicate with a service with a newer version of the same data contract, or a client with a newer version of a data contract can communicate with an older version of the same data contract.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="94a2f-105">[모범 사례: 데이터 계약 버전 관리](../../../../docs/framework/wcf/best-practices-data-contract-versioning.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="94a2f-105"> [Best Practices: Data Contract Versioning](../../../../docs/framework/wcf/best-practices-data-contract-versioning.md).</span></span>  
  
 <span data-ttu-id="94a2f-106">새 버전의 기존 데이터 계약을 작성하는 경우 필요한 기준에 따라 대부분의 버전 관리 기능을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94a2f-106">You can apply most of the versioning features on an as-needed basis when new versions of an existing data contract are created.</span></span> <span data-ttu-id="94a2f-107">그러나 버전 관리 기능, *라운드트립*, 제대로 작동 하려면 첫 번째 버전의 형식으로 빌드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="94a2f-107">However, one versioning feature, *round-tripping*, must be built into the type from the first version in order to work properly.</span></span>  
  
## <a name="round-tripping"></a><span data-ttu-id="94a2f-108">라운드트립</span><span class="sxs-lookup"><span data-stu-id="94a2f-108">Round-Tripping</span></span>  
 <span data-ttu-id="94a2f-109">라운드트립은 데이터를 새 버전에서 기존 버전으로 전달한 후 다시 새 버전의 데이터 계약으로 전달할 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="94a2f-109">Round-tripping occurs when data passes from a new version to an old version and back to the new version of a data contract.</span></span> <span data-ttu-id="94a2f-110">라운드트립을 사용해도 데이터는 손실되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="94a2f-110">Round-tripping guarantees that no data is lost.</span></span> <span data-ttu-id="94a2f-111">라운드트립을 사용하면 데이터 계약 버전 관리 모델에서 지원하는 이후 모든 변경 사항에 대해 이후 버전과 호환되는 형식으로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94a2f-111">Enabling round-tripping makes the type forward-compatible with any future changes supported by the data contract versioning model.</span></span>  
  
 <span data-ttu-id="94a2f-112">특정 형식의 라운드트립을 사용하려면 형식이 <xref:System.Runtime.Serialization.IExtensibleDataObject> 인터페이스를 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="94a2f-112">To enable round-tripping for a particular type, the type must implement the <xref:System.Runtime.Serialization.IExtensibleDataObject> interface.</span></span> <span data-ttu-id="94a2f-113">인터페이스에는 속성 중 하나인 <xref:System.Runtime.Serialization.IExtensibleDataObject.ExtensionData%2A>가 포함되어 있습니다(<xref:System.Runtime.Serialization.ExtensionDataObject> 형식 반환).</span><span class="sxs-lookup"><span data-stu-id="94a2f-113">The interface contains one property, <xref:System.Runtime.Serialization.IExtensibleDataObject.ExtensionData%2A> (returning the <xref:System.Runtime.Serialization.ExtensionDataObject> type).</span></span> <span data-ttu-id="94a2f-114">속성은 현재 버전에서는 알 수 없는 이후 버전 데이터 계약의 모든 데이터를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="94a2f-114">The property stores any data from future versions of the data contract that is unknown to the current version.</span></span>  
  
### <a name="example"></a><span data-ttu-id="94a2f-115">예제</span><span class="sxs-lookup"><span data-stu-id="94a2f-115">Example</span></span>  
 <span data-ttu-id="94a2f-116">다음 데이터 계약은 이후 변경 사항에 대해 이후 버전과 호환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="94a2f-116">The following data contract is not forward-compatible with future changes.</span></span>  
  
 [!code-csharp[C_DataContract#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontract/cs/source.cs#7)]
 [!code-vb[C_DataContract#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontract/vb/source.vb#7)]  
  
 <span data-ttu-id="94a2f-117">예를 들어, "phoneNumber"라는 새 데이터 멤버와 같은 이후 변경 사항과 호환되는 형식을 만들려면 <xref:System.Runtime.Serialization.IExtensibleDataObject> 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="94a2f-117">To make the type compatible with future changes (such as adding a new data member named "phoneNumber"), implement the <xref:System.Runtime.Serialization.IExtensibleDataObject> interface.</span></span>  
  
 [!code-csharp[C_DataContract#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontract/cs/source.cs#8)]
 [!code-vb[C_DataContract#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontract/vb/source.vb#8)]  
  
 <span data-ttu-id="94a2f-118">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 인프라에서 원래 데이터 계약의 일부가 아닌 데이터가 있는 경우 해당 데이터는 속성에 저장되어 보관됩니다.</span><span class="sxs-lookup"><span data-stu-id="94a2f-118">When the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] infrastructure encounters data that is not part of the original data contract, the data is stored in the property and preserved.</span></span> <span data-ttu-id="94a2f-119">임시 저장소를 제외한 다른 방법으로는 처리되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="94a2f-119">It is not processed in any other way except for temporary storage.</span></span> <span data-ttu-id="94a2f-120">개체가 최초 위치로 다시 돌아오는 경우, 원래 데이터(알 수 없는 데이터)도 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="94a2f-120">If the object is returned back to where it originated, the original (unknown) data is also returned.</span></span> <span data-ttu-id="94a2f-121">따라서 데이터가 손실 없이 원래 끝점 간을 라운드트립합니다.</span><span class="sxs-lookup"><span data-stu-id="94a2f-121">Therefore, the data has made a round trip to and from the originating endpoint without loss.</span></span> <span data-ttu-id="94a2f-122">그러나 원래 끝점에서 데이터를 처리해야 하는 경우 예상했던 작업은 수행되지 않고 해당 끝점은 변경 사항을 감지하고 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="94a2f-122">Note, however, that if the originating endpoint required the data to be processed, that expectation is unmet, and the endpoint must somehow detect and accommodate the change.</span></span>  
  
 <span data-ttu-id="94a2f-123"><xref:System.Runtime.Serialization.ExtensionDataObject> 형식에는 public 메서드 또는 속성이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="94a2f-123">The <xref:System.Runtime.Serialization.ExtensionDataObject> type contains no public methods or properties.</span></span> <span data-ttu-id="94a2f-124">따라서 <xref:System.Runtime.Serialization.IExtensibleDataObject.ExtensionData%2A> 속성 내에 저장된 데이터에 직접 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="94a2f-124">Thus, it is impossible to get direct access to the data stored inside the <xref:System.Runtime.Serialization.IExtensibleDataObject.ExtensionData%2A> property.</span></span>  
  
 <span data-ttu-id="94a2f-125">라운드트립 기능은 `ignoreExtensionDataObject` 생성자에서 `true`를 <xref:System.Runtime.Serialization.DataContractSerializer>로 설정하거나 <xref:System.ServiceModel.ServiceBehaviorAttribute.IgnoreExtensionDataObject%2A>에서 `true` 속성을 <xref:System.ServiceModel.ServiceBehaviorAttribute>로 설정하여 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94a2f-125">The round-tripping feature may be turned off, either by setting `ignoreExtensionDataObject` to `true` in the <xref:System.Runtime.Serialization.DataContractSerializer> constructor or by setting the <xref:System.ServiceModel.ServiceBehaviorAttribute.IgnoreExtensionDataObject%2A> property to `true` on the <xref:System.ServiceModel.ServiceBehaviorAttribute>.</span></span> <span data-ttu-id="94a2f-126">이 기능을 해제하면 deserializer가 <xref:System.Runtime.Serialization.IExtensibleDataObject.ExtensionData%2A> 속성을 채우지 않고, serializer가 속성의 콘텐츠를 내보내지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="94a2f-126">When this feature is off, the deserializer will not populate the <xref:System.Runtime.Serialization.IExtensibleDataObject.ExtensionData%2A> property, and the serializer will not emit the contents of the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94a2f-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="94a2f-127">See Also</span></span>  
 <xref:System.Runtime.Serialization.IExtensibleDataObject>  
 <xref:System.Runtime.Serialization.ExtensionDataObject>  
 [<span data-ttu-id="94a2f-128">데이터 계약 버전 관리</span><span class="sxs-lookup"><span data-stu-id="94a2f-128">Data Contract Versioning</span></span>](../../../../docs/framework/wcf/feature-details/data-contract-versioning.md)  
 [<span data-ttu-id="94a2f-129">모범 사례: 데이터 계약 버전 관리</span><span class="sxs-lookup"><span data-stu-id="94a2f-129">Best Practices: Data Contract Versioning</span></span>](../../../../docs/framework/wcf/best-practices-data-contract-versioning.md)
