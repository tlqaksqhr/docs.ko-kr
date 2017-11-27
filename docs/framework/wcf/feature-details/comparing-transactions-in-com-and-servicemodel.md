---
title: "COM+ 및 ServiceModel의 트랜잭션 비교"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e493bcdd-b91a-4486-853f-83dbcd1931b7
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 712f8a7a153d7255275ff7ebaa647d5a624f8ae9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="comparing-transactions-in-com-and-servicemodel"></a><span data-ttu-id="d6ee7-102">COM+ 및 ServiceModel의 트랜잭션 비교</span><span class="sxs-lookup"><span data-stu-id="d6ee7-102">Comparing Transactions in COM+ and ServiceModel</span></span>
<span data-ttu-id="d6ee7-103">이 항목에서는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 네임스페이스가 제공하는 <xref:System.ServiceModel> 특성을 사용하여 트랜잭션 COM+ 서비스의 동작을 시뮬레이션하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d6ee7-103">This topic discusses how to simulate the behavior of a transactional COM+ service using the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] attributes the <xref:System.ServiceModel> namespace provides.</span></span>  
  
## <a name="emulating-com-using-servicemodel-attributes"></a><span data-ttu-id="d6ee7-104">ServiceModel 특성을 사용하여 COM+ 에뮬레이트</span><span class="sxs-lookup"><span data-stu-id="d6ee7-104">Emulating COM+ Using ServiceModel Attributes</span></span>  
 <span data-ttu-id="d6ee7-105">다음 표에서는 <xref:System.EnterpriseServices.TransactionOption> 트랜잭션을 만드는 데 사용되는 `EnterpriseServices` 열거 및 이러한 열거가 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 네임스페이스에서 제공하는 <xref:System.ServiceModel> 특성과 상호 관련된 방식을 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="d6ee7-105">The following table compares the <xref:System.EnterpriseServices.TransactionOption> enumeration used to create an `EnterpriseServices` transaction and how they correlate to the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] attributes the <xref:System.ServiceModel> namespace provides.</span></span>  
  
|<span data-ttu-id="d6ee7-106">COM+ 특성</span><span class="sxs-lookup"><span data-stu-id="d6ee7-106">COM+ attribute</span></span>|[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="d6ee7-107"> 특성</span><span class="sxs-lookup"><span data-stu-id="d6ee7-107"> attributes</span></span>|  
|---------------------|------------------------------------------------------------------------|  
|<span data-ttu-id="d6ee7-108">RequiresNew</span><span class="sxs-lookup"><span data-stu-id="d6ee7-108">RequiresNew</span></span>|<span data-ttu-id="d6ee7-109"><xref:System.ServiceModel.TransactionFlowAttribute>이 <xref:System.ServiceModel.TransactionFlowOption.NotAllowed>로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6ee7-109"><xref:System.ServiceModel.TransactionFlowAttribute> is set to <xref:System.ServiceModel.TransactionFlowOption.NotAllowed>.</span></span><br /><br /> <span data-ttu-id="d6ee7-110"><xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A>가 `true`인 경우</span><span class="sxs-lookup"><span data-stu-id="d6ee7-110"><xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> is `true`.</span></span><br /><br /> <span data-ttu-id="d6ee7-111">바인딩 요소의 `TransactionFlow` 특성이 `false`인 경우</span><span class="sxs-lookup"><span data-stu-id="d6ee7-111">The `TransactionFlow` attribute in the binding element is `false`.</span></span>|  
|<span data-ttu-id="d6ee7-112">필수</span><span class="sxs-lookup"><span data-stu-id="d6ee7-112">Required</span></span>|<span data-ttu-id="d6ee7-113"><xref:System.ServiceModel.TransactionFlowAttribute>이 <xref:System.ServiceModel.TransactionFlowOption.Allowed>로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6ee7-113"><xref:System.ServiceModel.TransactionFlowAttribute> is set to <xref:System.ServiceModel.TransactionFlowOption.Allowed>.</span></span><br /><br /> <span data-ttu-id="d6ee7-114"><xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A>가 `true`인 경우</span><span class="sxs-lookup"><span data-stu-id="d6ee7-114"><xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> is `true`.</span></span><br /><br /> <span data-ttu-id="d6ee7-115">바인딩 요소의 `TransactionFlow` 특성이 `true`인 경우</span><span class="sxs-lookup"><span data-stu-id="d6ee7-115">The `TransactionFlow` attribute in the binding element is `true`.</span></span>|  
|<span data-ttu-id="d6ee7-116">지원함</span><span class="sxs-lookup"><span data-stu-id="d6ee7-116">Supported</span></span>|<span data-ttu-id="d6ee7-117">직접 대응하는 특성이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d6ee7-117">There is no direct equivalent.</span></span> <span data-ttu-id="d6ee7-118">일반적으로 `Required`에 지정된 동작을 대신 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6ee7-118">In general, you should adopt the behavior specified for `Required` instead.</span></span>|  
|<span data-ttu-id="d6ee7-119">NotSupported</span><span class="sxs-lookup"><span data-stu-id="d6ee7-119">NotSupported</span></span>|<span data-ttu-id="d6ee7-120"><xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A>가 `false`인 경우</span><span class="sxs-lookup"><span data-stu-id="d6ee7-120"><xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A> is `false`.</span></span><br /><br /> <span data-ttu-id="d6ee7-121">바인딩 요소의 `TransactionFlow` 특성이 `false`인 경우</span><span class="sxs-lookup"><span data-stu-id="d6ee7-121">The `TransactionFlow` attribute in the binding element is `false`.</span></span>|  
|<span data-ttu-id="d6ee7-122">Disabled</span><span class="sxs-lookup"><span data-stu-id="d6ee7-122">Disabled</span></span>|<span data-ttu-id="d6ee7-123">직접 대응하는 특성이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d6ee7-123">There is no direct equivalent.</span></span> <span data-ttu-id="d6ee7-124">일반적으로 `NotSupported`에 지정된 동작을 대신 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6ee7-124">In general, you should adopt the behavior specified for `NotSupported` instead.</span></span>|
