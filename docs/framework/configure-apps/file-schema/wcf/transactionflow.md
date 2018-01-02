---
title: '&lt;transactionFlow&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8c7b4c5b-ace3-4fe3-89ff-7b13c9aacd13
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3720294ac937c6aa7ce99ab687efa76b2e860abb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="lttransactionflowgt"></a><span data-ttu-id="bbdc9-102">&lt;transactionFlow&gt;</span><span class="sxs-lookup"><span data-stu-id="bbdc9-102">&lt;transactionFlow&gt;</span></span>
<span data-ttu-id="bbdc9-103">사용자 지정 바인딩에 대한 트랜잭션 흐름 지원을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bbdc9-103">Specifies transaction flow support for the custom binding.</span></span>  
  
 <span data-ttu-id="bbdc9-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="bbdc9-104">\<system.serviceModel></span></span>  
<span data-ttu-id="bbdc9-105">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="bbdc9-105">\<bindings></span></span>  
<span data-ttu-id="bbdc9-106">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="bbdc9-106">\<customBinding></span></span>  
<span data-ttu-id="bbdc9-107">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="bbdc9-107">\<binding></span></span>  
<span data-ttu-id="bbdc9-108">\<transactionFlow ></span><span class="sxs-lookup"><span data-stu-id="bbdc9-108">\<transactionFlow></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bbdc9-109">구문</span><span class="sxs-lookup"><span data-stu-id="bbdc9-109">Syntax</span></span>  
  
```xml  
<transactionFlow transactionProtocol="OleTransactions/WSAtomicTransactionOctober2004"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bbdc9-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="bbdc9-110">Attributes and Elements</span></span>  
 <span data-ttu-id="bbdc9-111">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bbdc9-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bbdc9-112">특성</span><span class="sxs-lookup"><span data-stu-id="bbdc9-112">Attributes</span></span>  
  
|<span data-ttu-id="bbdc9-113">특성</span><span class="sxs-lookup"><span data-stu-id="bbdc9-113">Attribute</span></span>|<span data-ttu-id="bbdc9-114">설명</span><span class="sxs-lookup"><span data-stu-id="bbdc9-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bbdc9-115">transactionProtocol</span><span class="sxs-lookup"><span data-stu-id="bbdc9-115">transactionProtocol</span></span>|<span data-ttu-id="bbdc9-116">사용할 트랜잭션 프로토콜을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bbdc9-116">Specifies the transaction protocol to be used.</span></span> <span data-ttu-id="bbdc9-117">유효한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="bbdc9-117">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="bbdc9-118">-OleTransactions</span><span class="sxs-lookup"><span data-stu-id="bbdc9-118">-   OleTransactions</span></span><br /><span data-ttu-id="bbdc9-119">-WSAtomicTransactionOctober2004</span><span class="sxs-lookup"><span data-stu-id="bbdc9-119">-   WSAtomicTransactionOctober2004</span></span><br /><br /> <span data-ttu-id="bbdc9-120">기본값은 OleTransactions입니다.</span><span class="sxs-lookup"><span data-stu-id="bbdc9-120">The default is OleTransactions.</span></span><br /><br /> <span data-ttu-id="bbdc9-121">이 특성은 <xref:System.ServiceModel.TransactionProtocol> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="bbdc9-121">This attribute is of type <xref:System.ServiceModel.TransactionProtocol>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bbdc9-122">자식 요소</span><span class="sxs-lookup"><span data-stu-id="bbdc9-122">Child Elements</span></span>  
 <span data-ttu-id="bbdc9-123">없음</span><span class="sxs-lookup"><span data-stu-id="bbdc9-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bbdc9-124">부모 요소</span><span class="sxs-lookup"><span data-stu-id="bbdc9-124">Parent Elements</span></span>  
  
|<span data-ttu-id="bbdc9-125">요소</span><span class="sxs-lookup"><span data-stu-id="bbdc9-125">Element</span></span>|<span data-ttu-id="bbdc9-126">설명</span><span class="sxs-lookup"><span data-stu-id="bbdc9-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bbdc9-127">\<바인딩 ></span><span class="sxs-lookup"><span data-stu-id="bbdc9-127">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="bbdc9-128">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="bbdc9-128">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bbdc9-129">설명</span><span class="sxs-lookup"><span data-stu-id="bbdc9-129">Remarks</span></span>  
 <span data-ttu-id="bbdc9-130">이 요소를 사용하면 끝점의 바인딩 설정에 들어오는 트랜잭션 흐름을 사용하거나 사용하지 않도록 설정할 수 있을 뿐 아니라 들어오는 트랜잭션에 대해 원하는 프로토콜 형식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbdc9-130">This element allows you to enable or disable incoming transaction flow in an endpoint’s binding settings, as well as to specify the desired protocol format for incoming transactions.</span></span> <span data-ttu-id="bbdc9-131">이 구성 요소를 사용 하 여에 대 한 자세한 내용은 참조 하십시오. [ServiceModel 트랜잭션 구성](../../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md) 및 [트랜잭션 흐름을 사용 하도록 설정](../../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bbdc9-131">For more information on using this configuration element, see [ServiceModel Transaction Configuration](../../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md) and [Enabling Transaction Flow](../../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md).</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="bbdc9-132">`OleTransactions` 프로토콜을 사용하여 끝점 간에 트랜잭션을 전달할 경우 대상 끝점에서 `OleTransactions` 이외의 프로토콜을 사용하여 트랜잭션을 다시 전달하려고 하면 트랜잭션 시간 제한이 상실될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbdc9-132">When using the `OleTransactions` protocol to flow transactions from endpoint to endpoint, the transaction timeout can be lost if the destination endpoint attempts to flow again using any protocol other than `OleTransactions`.</span></span> <span data-ttu-id="bbdc9-133">따라서 OleTransactions 홉 뒤의 모든 하위 수준 노드가 예상보다 늦게 시간이 초과될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbdc9-133">This can cause all down-level nodes after the OleTransactions hop to timeout later than expected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbdc9-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bbdc9-134">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.TransactionFlowElement>  
 <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="bbdc9-135">ServiceModel 트랜잭션 구성</span><span class="sxs-lookup"><span data-stu-id="bbdc9-135">ServiceModel Transaction Configuration</span></span>](../../../../../docs/framework/wcf/feature-details/servicemodel-transaction-configuration.md)  
 [<span data-ttu-id="bbdc9-136">트랜잭션 흐름 사용</span><span class="sxs-lookup"><span data-stu-id="bbdc9-136">Enabling Transaction Flow</span></span>](../../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md)  
 [<span data-ttu-id="bbdc9-137">바인딩</span><span class="sxs-lookup"><span data-stu-id="bbdc9-137">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="bbdc9-138">바인딩 확장</span><span class="sxs-lookup"><span data-stu-id="bbdc9-138">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="bbdc9-139">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="bbdc9-139">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="bbdc9-140">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="bbdc9-140">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
