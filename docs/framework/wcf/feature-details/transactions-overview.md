---
title: Windows Communication Foundation 트랜잭션 개요
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- transactions [WCF]
- WCF, transactions
- Windows Communication Foundation, transactions
ms.assetid: c7757854-1207-4019-8b31-552578b7d570
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 76edd7cf30d9da06db6e0c2f4624bf9a6d677eca
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="windows-communication-foundation-transactions-overview"></a><span data-ttu-id="539a8-102">Windows Communication Foundation 트랜잭션 개요</span><span class="sxs-lookup"><span data-stu-id="539a8-102">Windows Communication Foundation Transactions Overview</span></span>
<span data-ttu-id="539a8-103">트랜잭션은 동작 또는 작업 집합을 하나의 개별 실행 단위로 그룹화하는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="539a8-103">Transactions provide a way to group a set of actions or operations into a single indivisible unit of execution.</span></span> <span data-ttu-id="539a8-104">트랜잭션은 다음 속성을 가진 작업 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="539a8-104">A transaction is a collection of operations with the following properties:</span></span>  
  
-   <span data-ttu-id="539a8-105">원자성.</span><span class="sxs-lookup"><span data-stu-id="539a8-105">Atomicity.</span></span> <span data-ttu-id="539a8-106">특정 트랜잭션에서 완료된 모든 업데이트가 커밋되어 영구화되거나 모두 중단되어 이전 상태로 롤백되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="539a8-106">This ensures that either all of the updates completed under a specific transaction are committed and made durable or they are all aborted and rolled back to their previous state.</span></span>  
  
-   <span data-ttu-id="539a8-107">일관성.</span><span class="sxs-lookup"><span data-stu-id="539a8-107">Consistency.</span></span> <span data-ttu-id="539a8-108">트랜잭션에서 변경된 내용이 하나의 일관된 상태에서 다른 일관된 상태로의 변환을 나타내도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="539a8-108">This guarantees that the changes made under a transaction represent a transformation from one consistent state to another.</span></span> <span data-ttu-id="539a8-109">예를 들어 당좌 예금 계좌에서 보통 예금 계좌로 돈을 이체하는 트랜잭션은 전체 은행 계좌의 금액을 변경하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="539a8-109">For example, a transaction that transfers money from a checking account to a savings account does not change the amount of money in the overall bank account.</span></span>  
  
-   <span data-ttu-id="539a8-110">격리성</span><span class="sxs-lookup"><span data-stu-id="539a8-110">Isolation.</span></span> <span data-ttu-id="539a8-111">트랜잭션이 다른 동시 트랜잭션에 속하는 커밋되지 않은 변경 내용을 인식하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="539a8-111">This prevents a transaction from observing uncommitted changes belonging to other concurrent transactions.</span></span> <span data-ttu-id="539a8-112">격리는 한 트랜잭션의 유지가 다른 트랜잭션의 실행에 예기치 않은 영향을 주지 않도록 하는 동시에 추상적인 동시성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="539a8-112">Isolation provides an abstraction of concurrency while ensuring one transaction cannot have an unexpected impact on the execution of another transaction.</span></span>  
  
-   <span data-ttu-id="539a8-113">지속성.</span><span class="sxs-lookup"><span data-stu-id="539a8-113">Durability.</span></span> <span data-ttu-id="539a8-114">커밋되고 나면 데이터베이스 레코드 같은 관리되는 리소스에 대한 업데이트가 실패한 경우에도 지속되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="539a8-114">This means that once committed, updates to managed resources (such as a database record) will be persistent in the face of failures.</span></span>  
  
 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="539a8-115">에서는 웹 서비스 응용 프로그램에서 분산 트랜잭션을 만들 수 있는 다양한 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="539a8-115"> provides a rich set of features that enable you to create distributed transactions in your Web service application.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="539a8-116">에서는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응용 프로그램이 타사 기술을 사용하여 작성된 상호 운용 가능한 웹 서비스 같은 상호 운용 가능한 응용 프로그램으로 트랜잭션을 이동할 수 있도록 하는 WS-AT(WS-AtomicTransaction) 프로토콜 지원을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="539a8-116"> implements support for the WS-AtomicTransaction (WS-AT) protocol that enables [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications to flow transactions to interoperable applications, such as interoperable Web services built using third-party technology.</span></span> <span data-ttu-id="539a8-117">또한 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 트랜잭션 흐름을 가능하게 하는 interop 기능이 필요하지 않은 시나리오에서 사용할 수 있는 OLE 트랜잭션 프로토콜 지원을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="539a8-117">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] also implements support for the OLE Transactions protocol, which can be used in scenarios where you do not need interop functionality to enable transaction flow.</span></span>  
  
 <span data-ttu-id="539a8-118">응용 프로그램 구성 파일에서 바인딩을 구성하여 트랜잭션 흐름을 가능하거나 불가능하게 하고 바인딩에 원하는 트랜잭션 프로토콜을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="539a8-118">You can use an application configuration file to configure bindings to enable or disable transaction flow, as well as set the desired transaction protocol on a binding.</span></span> <span data-ttu-id="539a8-119">또한 구성 파일을 사용하여 서비스 수준에서 트랜잭션 시간 초과를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="539a8-119">In addition, you can set transaction time-outs at the service level using the configuration file.</span></span> <span data-ttu-id="539a8-120">자세한 내용은 참조 [트랜잭션 흐름을 사용 하도록 설정](../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="539a8-120">For more information, see [Enabling Transaction Flow](../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md).</span></span>  
  
 <span data-ttu-id="539a8-121"><xref:System.ServiceModel> 네임스페이스의 트랜잭션 특성을 사용하여 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="539a8-121">Transaction attributes in the <xref:System.ServiceModel> namespace allow you to do the following:</span></span>  
  
-   <span data-ttu-id="539a8-122"><xref:System.ServiceModel.ServiceBehaviorAttribute> 특성을 사용하여 트랜잭션 시간 초과와 격리 수준 필터링을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="539a8-122">Configure transaction time-outs and isolation-level filtering using the <xref:System.ServiceModel.ServiceBehaviorAttribute> attribute.</span></span>  
  
-   <span data-ttu-id="539a8-123"><xref:System.ServiceModel.OperationBehaviorAttribute> 특성을 사용하여 트랜잭션 기능을 활성화하고 트랜잭션 완료 동작을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="539a8-123">Enable transactions functionality and configure transaction completion behavior using the <xref:System.ServiceModel.OperationBehaviorAttribute> attribute.</span></span>  
  
-   <span data-ttu-id="539a8-124">계약 메서드의 <xref:System.ServiceModel.ServiceContractAttribute> 및 <xref:System.ServiceModel.OperationContractAttribute> 특성을 사용하여 트랜잭션 흐름을 필요로 하거나 허용 또는 거부합니다.</span><span class="sxs-lookup"><span data-stu-id="539a8-124">Use the <xref:System.ServiceModel.ServiceContractAttribute> and <xref:System.ServiceModel.OperationContractAttribute> attributes on a contract method to require, allow or deny transaction flow.</span></span>  
  
 <span data-ttu-id="539a8-125">자세한 내용은 참조 [ServiceModel 트랜잭션 특성](../../../../docs/framework/wcf/feature-details/servicemodel-transaction-attributes.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="539a8-125">For more information, see [ServiceModel Transaction Attributes](../../../../docs/framework/wcf/feature-details/servicemodel-transaction-attributes.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="539a8-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="539a8-126">See Also</span></span>  
 [<span data-ttu-id="539a8-127">ServiceModel 트랜잭션 특성</span><span class="sxs-lookup"><span data-stu-id="539a8-127">ServiceModel Transaction Attributes</span></span>](../../../../docs/framework/wcf/feature-details/servicemodel-transaction-attributes.md)  
 [<span data-ttu-id="539a8-128">트랜잭션 흐름 사용</span><span class="sxs-lookup"><span data-stu-id="539a8-128">Enabling Transaction Flow</span></span>](../../../../docs/framework/wcf/feature-details/enabling-transaction-flow.md)
