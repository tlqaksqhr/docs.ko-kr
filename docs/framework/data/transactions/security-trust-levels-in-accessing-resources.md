---
title: "리소스 액세스의 보안 신뢰 수준"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fb5be924-317d-4d69-b33a-3d18ecfb9d6e
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d6fe8902021d6585434c2dcdfa42784d59818157
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="security-trust-levels-in-accessing-resources"></a><span data-ttu-id="f1ab3-102">리소스 액세스의 보안 신뢰 수준</span><span class="sxs-lookup"><span data-stu-id="f1ab3-102">Security Trust Levels in Accessing Resources</span></span>
<span data-ttu-id="f1ab3-103">이 항목에서는 <xref:System.Transactions>에서 노출하는 리소스 형식에 따라 액세스가 제한되는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f1ab3-103">This topic discusses how access is restricted on the types of resources that <xref:System.Transactions> exposes.</span></span>  
  
 <span data-ttu-id="f1ab3-104"><xref:System.Transactions>에 대한 세 가지 기본 신뢰 수준이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1ab3-104">There are three main levels of trust for <xref:System.Transactions>.</span></span> <span data-ttu-id="f1ab3-105">신뢰 수준은 <xref:System.Transactions>에서 노출하는 리소스 형식과 이러한 리소스에 액세스하는 데 필요한 신뢰 수준을 기반으로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1ab3-105">The trust levels are defined based on the types of resources that <xref:System.Transactions> exposes, and the level of trust that should be required to access those resources.</span></span> <span data-ttu-id="f1ab3-106"><xref:System.Transactions>에서 액세스를 제공하는 리소스는 시스템 메모리, 공유 프로세스 범위 리소스 및 시스템 범위 리소스입니다.</span><span class="sxs-lookup"><span data-stu-id="f1ab3-106">The resources that <xref:System.Transactions> provides access to are system memory, shared process wide resources, and system wide resources.</span></span> <span data-ttu-id="f1ab3-107">수준은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f1ab3-107">The levels are:</span></span>  
  
-   <span data-ttu-id="f1ab3-108">**AllowPartiallyTrustedCallers** (APTCA) 트랜잭션을 사용 하 여 단일 응용 프로그램 도메인 내에서 응용 프로그램에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1ab3-108">**AllowPartiallyTrustedCallers** (APTCA) for applications using transactions within a single application domain.</span></span>  
  
-   <span data-ttu-id="f1ab3-109">**DistributedTransactionPermission** DTP 분산된 트랜잭션을 사용 하 여 응용 프로그램에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1ab3-109">**DistributedTransactionPermission** (DTP) for applications using distributed transactions.</span></span>  
  
-   <span data-ttu-id="f1ab3-110">지속적인 리소스, 구성 관리 응용 프로그램 및 레거시 interop 응용 프로그램에 대한 완전 신뢰</span><span class="sxs-lookup"><span data-stu-id="f1ab3-110">Full trust for durable resources, configuration management applications, and legacy interop applications.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f1ab3-111">가장된 컨텍스트를 사용하여 인리스트먼트 인터페이스를 호출하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1ab3-111">You should not call any of the enlistment interfaces with impersonated contexts.</span></span>  
  
## <a name="trust-levels"></a><span data-ttu-id="f1ab3-112">신뢰 수준</span><span class="sxs-lookup"><span data-stu-id="f1ab3-112">Trust Levels</span></span>  
  
### <a name="aptca-partial-trust"></a><span data-ttu-id="f1ab3-113">APTCA(부분 신뢰)</span><span class="sxs-lookup"><span data-stu-id="f1ab3-113">APTCA (Partial Trust)</span></span>  
 <span data-ttu-id="f1ab3-114"><xref:System.Transactions> 으로 표시 되어 있으므로 부분적으로 신뢰할 수 있는 코드에서 어셈블리를 호출할 수 있습니다는 **AllowPartiallyTrustedCallers** 특성 (APTCA).</span><span class="sxs-lookup"><span data-stu-id="f1ab3-114">The <xref:System.Transactions> assembly can be called by partially trusted code because it has been marked with the **AllowPartiallyTrustedCallers** attribute (APTCA).</span></span> <span data-ttu-id="f1ab3-115">이 특성을 기본적으로 암시적 제거 <xref:System.Security.Permissions.SecurityAction.LinkDemand> 에 대 한는 **FullTrust** 사용 권한 집합을 이외 각 형식의 공개적으로 액세스 가능한 각 메서드에 자동으로 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1ab3-115">This attribute essentially removes the implicit <xref:System.Security.Permissions.SecurityAction.LinkDemand> for the **FullTrust** permission set that is otherwise automatically placed on each publicly accessible method in each type.</span></span> <span data-ttu-id="f1ab3-116">그러나 일부 형식과 멤버에는 더 강력한 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f1ab3-116">However, some types and members still require stronger permissions.</span></span>  
  
 <span data-ttu-id="f1ab3-117">APTCA 특성을 통해 응용 프로그램은 단일 응용 프로그램 도메인 내에서 부분 신뢰 트랜잭션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1ab3-117">The APTCA attribute enables applications to use transactions in partial trust within a single application domain.</span></span> <span data-ttu-id="f1ab3-118">이 경우 일시적인 인리스트먼트와 에스컬레이션되지 않는 트랜잭션을 오류 처리에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1ab3-118">This enables non-escalated transactions and volatile enlistments that can be used for error handling.</span></span> <span data-ttu-id="f1ab3-119">이러한 예로 트랜잭션된 해시 테이블과 이를 사용하는 응용 프로그램이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1ab3-119">One example of this is a transacted hash table and an application that uses it.</span></span> <span data-ttu-id="f1ab3-120">단일 트랜잭션으로 해시 테이블에 데이터를 추가하고 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1ab3-120">Data can be added to and removed from the hash table under a single transaction.</span></span> <span data-ttu-id="f1ab3-121">나중에 트랜잭션을 롤백하는 경우 해당 트랜잭션에서 수행된 해시 테이블의 모든 변경 내용을 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1ab3-121">If the transaction is later rolled back, all of the changes made to the hash table under that transaction can be undone.</span></span>  
  
### <a name="distributedtransactionpermission-dtp"></a><span data-ttu-id="f1ab3-122">DistributedTransactionPermission(DTP)</span><span class="sxs-lookup"><span data-stu-id="f1ab3-122">DistributedTransactionPermission (DTP)</span></span>  
 <span data-ttu-id="f1ab3-123">MSDTC에서 관리하도록 <xref:System.Transactions> 트랜잭션을 에스컬레이션하는 경우 <xref:System.Transactions>에서 분산 트랜잭션을 만들려면 <xref:System.Transactions.DistributedTransactionPermission>(DTP)이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f1ab3-123">When a <xref:System.Transactions> transaction is escalated to be managed by MSDTC, <xref:System.Transactions> demands the <xref:System.Transactions.DistributedTransactionPermission> (DTP) to create the distributed transaction.</span></span> <span data-ttu-id="f1ab3-124">따라서 serialization 또는 지속적인 추가 인리스트먼트를 통해 트랜잭션이 에스컬레이션되게 하는 코드에 DTP를 부여해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1ab3-124">This means that the code that causes the transaction to be escalated (such as through serialization or additional durable enlistments) would need to be granted DTP.</span></span> <span data-ttu-id="f1ab3-125">원래 <xref:System.Transactions> 트랜잭션을 만든 코드에는 이 권한이 없어도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1ab3-125">The code that originally created the <xref:System.Transactions> transaction does not necessarily need to possess this permission.</span></span>  
  
### <a name="fulltrust-link-demands"></a><span data-ttu-id="f1ab3-126">FullTrust 링크 요청</span><span class="sxs-lookup"><span data-stu-id="f1ab3-126">FullTrust Link Demands</span></span>  
 <span data-ttu-id="f1ab3-127">이 사용 권한 수준은 지속적인 리소스에 쓰는 응용 프로그램을 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="f1ab3-127">This permission level is intended to restrict applications that are writing to durable resources.</span></span> <span data-ttu-id="f1ab3-128">실패 시 응용 프로그램이 복구될 수 있어야 하며 트랜잭션 관리자가 영구 데이터를 업데이트할 수 있도록 트랜잭션의 최종 결과를 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1ab3-128">Upon failure, the application needs to be able to recover with the transaction manager to determine the final outcome of the transaction, so that it can update permanent data.</span></span> <span data-ttu-id="f1ab3-129">이 응용 프로그램 종류를 지속적인 소스 관리자라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1ab3-129">This type of application is known as a durable source manager.</span></span> <span data-ttu-id="f1ab3-130">이 응용 프로그램 종류의 일반적인 예로 SQL이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1ab3-130">A classic example of this type of application is SQL.</span></span>  
  
 <span data-ttu-id="f1ab3-131">복구를 사용하기 위해 이 응용 프로그램 종류에는 시스템 리소스를 영구적으로 사용하는 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1ab3-131">To enable recovery, this type of application has the ability to permanently consume system resources.</span></span> <span data-ttu-id="f1ab3-132">이는 트랜잭션에 참여하는 모든 지속적인 리소스 관리자에서 결과를 받은 것을 확인할 수 있을 때까지 복구할 수 있는 트랜잭션 관리자가 커밋된 트랜잭션을 저장해야 하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="f1ab3-132">This is because the recoverable transaction manager must remember transactions that have committed until it can confirm that all durable resource managers that are participating in the transaction have received the outcome.</span></span> <span data-ttu-id="f1ab3-133">따라서 이 응용 프로그램 종류에는 완전 신뢰가 필요하며 해당 신뢰 수준이 부여되지 않은 경우 실행하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1ab3-133">Therefore, this type of application requires full trust and should not be run unless that level of trust has been granted.</span></span>  
  
 <span data-ttu-id="f1ab3-134">지속적인 인리스트먼트 및 복구에 대 한 자세한 내용은 참조는 [트랜잭션에서 참가자 인 리스트 먼 트 리소스](../../../../docs/framework/data/transactions/enlisting-resources-as-participants-in-a-transaction.md) 및 [복구 수행](../../../../docs/framework/data/transactions/performing-recovery.md) 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="f1ab3-134">For more information on durable enlistments and recovery, see the [Enlisting Resources as Participants in a Transaction](../../../../docs/framework/data/transactions/enlisting-resources-as-participants-in-a-transaction.md) and [Performing Recovery](../../../../docs/framework/data/transactions/performing-recovery.md) topics.</span></span>  
  
 <span data-ttu-id="f1ab3-135">COM+와의 레거시 interop 작업을 수행하는 응용 프로그램에도 완전 신뢰가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1ab3-135">Applications that perform legacy interop work with COM+ are also required to have full trust.</span></span>  
  
 <span data-ttu-id="f1ab3-136">다음은 형식의 목록 및 부분적으로에서 호출할 수 없는 멤버에 신뢰할 수 있는 코드와 데코레이팅되기 때문에 **FullTrust** 선언적 보안 특성:</span><span class="sxs-lookup"><span data-stu-id="f1ab3-136">The following is a list of types and members that are not callable by partially trusted code because they are decorated with the **FullTrust** declarative security attribute:</span></span>  
  
 `PermissionSetAttribute(SecurityAction.LinkDemand, Name := "FullTrust")`  
  
-   <xref:System.Transactions.Transaction.EnlistDurable%2A?displayProperty=nameWithType>  
  
-   <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%2A>  
  
-   <xref:System.Transactions.TransactionInterop>  
  
-   <xref:System.Transactions.TransactionManager.DistributedTransactionStarted>  
  
-   <xref:System.Transactions.HostCurrentTransactionCallback>  
  
-   <xref:System.Transactions.TransactionManager.Reenlist%2A>  
  
-   <xref:System.Transactions.TransactionManager.RecoveryComplete%2A>  
  
-   <xref:System.Transactions.TransactionScope.%23ctor%28System.Transactions.TransactionScopeOption%2CSystem.Transactions.TransactionOptions%2CSystem.Transactions.EnterpriseServicesInteropOption%29>  
  
 <span data-ttu-id="f1ab3-137">만 직접 실행 호출자가 보유 하는 데 필요한는 **FullTrust** 권한 위의 형식이 나 메서드를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1ab3-137">Only the immediate caller is required to possess the **FullTrust** permission set to use the above types or methods.</span></span>
