---
title: "워크플로에서 계약 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 939c64e9-e7cc-4abc-b41e-27cfce1d7e50
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1c84483b2ca18d63f20e64a62bb757e244db9b24
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="using-contracts-in-workflow"></a><span data-ttu-id="24c4e-102">워크플로에서 계약 사용</span><span class="sxs-lookup"><span data-stu-id="24c4e-102">Using Contracts in Workflow</span></span>
<span data-ttu-id="24c4e-103">서비스를 구현하는 경우 서비스를 설명하는 많은 계약과 서비스가 보내고 받는 데이터를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="24c4e-103">When implementing a service, you define a number of contracts that describe the service and the data that it sends and receives.</span></span> <span data-ttu-id="24c4e-104">이러한 데이터는 데이터 계약 및 메시지 계약 정의로 표현되기 때문에 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 및 워크플로 서비스에서는 데이터 계약과 메시지 계약을 서비스 설명의 일부로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="24c4e-104">The data is represented as data contracts and message contracts; both [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] and workflow services use data contract and message contract definitions as part of service descriptions.</span></span> <span data-ttu-id="24c4e-105">서비스 자체에서는 서비스의 작업을 설명하기 위해 메타데이터(WSDL 형식)를 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="24c4e-105">The service itself exposes metadata (in the form of WSDL) in order to describe the operations of the service.</span></span> <span data-ttu-id="24c4e-106">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 서비스 계약과 작업 계약을 사용하여 서비스와 서비스가 지원하는 작업을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="24c4e-106">In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], service contracts and operation contracts define the service and the operations it supports.</span></span> <span data-ttu-id="24c4e-107">그러나 워크플로 서비스에서는 이러한 계약이 비즈니스 프로세스 자체의 일부이기 때문에 계약 유추라고 하는 프로세스에 의해 메타데이터로 노출됩니다.</span><span class="sxs-lookup"><span data-stu-id="24c4e-107">However, in a workflow service, these contracts are part of the business process itself; they are exposed in metadata by a process called contract inference.</span></span>  
  
## <a name="contract-inference"></a><span data-ttu-id="24c4e-108">계약 유추</span><span class="sxs-lookup"><span data-stu-id="24c4e-108">Contract Inference</span></span>  
 <span data-ttu-id="24c4e-109"><xref:System.ServiceModel.Activities.WorkflowServiceHost>를 사용하여 워크플로 서비스가 호스트되면 워크플로 정의가 검사되고 워크플로에 있는 메시징 작업 집합을 기반으로 계약이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="24c4e-109">When a workflow service is hosted using <xref:System.ServiceModel.Activities.WorkflowServiceHost>, the workflow definition is examined and a contract is generated based on the set of messaging activities found in the workflow.</span></span> <span data-ttu-id="24c4e-110">특히 계약을 생성하는 데는 다음 작업과 속성이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="24c4e-110">In particular the following activities and properties are used to generate the contract:</span></span>  
  
 <span data-ttu-id="24c4e-111"><xref:System.ServiceModel.Activities.Receive> 작업</span><span class="sxs-lookup"><span data-stu-id="24c4e-111"><xref:System.ServiceModel.Activities.Receive> Activity</span></span>  
  
-   <xref:System.ServiceModel.Activities.Receive.ServiceContractName%2A>  
  
-   <!--zz <xref:System.ServiceModel.Activities.Receive.OperationContractName%2A>  --> `System.ServiceModel.Activities.Receive.OperationContractName`
  
-   <xref:System.ServiceModel.Activities.Receive.Action%2A>  
  
-   <!--zz <xref:System.ServiceModel.Activities.Receive.ValueType%2A> --> `System.ServiceModel.Activities.Receive.ValueType`
  
 <span data-ttu-id="24c4e-112"><xref:System.ServiceModel.Activities.SendReply> 작업</span><span class="sxs-lookup"><span data-stu-id="24c4e-112"><xref:System.ServiceModel.Activities.SendReply> Activity</span></span>  
  
-   <xref:System.ServiceModel.Activities.SendReply.Action%2A>  
  
-   <!--zz <xref:System.ServiceModel.Activities.SendReply.ValueType%2A>-->  `System.ServiceModel.Activities.SendReply.ValueType`
  
 <span data-ttu-id="24c4e-113"><xref:System.ServiceModel.Activities.TransactedReceiveScope> 작업</span><span class="sxs-lookup"><span data-stu-id="24c4e-113"><xref:System.ServiceModel.Activities.TransactedReceiveScope> Activity</span></span>  
  
 <span data-ttu-id="24c4e-114">계약 유추의 최종 결과는 WCF 서비스 및 작업 계약과 동일한 데이터 구조를 사용하는 서비스에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="24c4e-114">The end result of contract inference is a description of the service using the same data structures as WCF service and operation contracts.</span></span> <span data-ttu-id="24c4e-115">이 정보는 나중에 워크플로 서비스에 대한 WSDL을 노출하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="24c4e-115">This information is then used to expose WSDL for the workflow service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24c4e-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="24c4e-116">See Also</span></span>  
 [<span data-ttu-id="24c4e-117">워크플로 서비스</span><span class="sxs-lookup"><span data-stu-id="24c4e-117">Workflow Services</span></span>](../../../../docs/framework/wcf/feature-details/workflow-services.md)  
 [<span data-ttu-id="24c4e-118">메시징 활동</span><span class="sxs-lookup"><span data-stu-id="24c4e-118">Messaging Activities</span></span>](../../../../docs/framework/wcf/feature-details/messaging-activities.md)  
 [<span data-ttu-id="24c4e-119">방법: 메시징 작업으로는 워크플로 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="24c4e-119">How to: Create a Workflow Service with Messaging Activities</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-workflow-service-with-messaging-activities.md)  
 [<span data-ttu-id="24c4e-120">방법: 기존 서비스 계약을 사용하는 워크플로 서비스 만들기</span><span class="sxs-lookup"><span data-stu-id="24c4e-120">How to: Create a workflow service that consumes an existing service contract</span></span>](../../../../docs/framework/windows-workflow-foundation/how-to-create-a-workflow-service-that-consumes-an-existing-service-contract.md)
