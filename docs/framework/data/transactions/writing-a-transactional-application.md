---
title: "트랜잭션 응용 프로그램 작성"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a4d891f2-6fc8-4395-93c6-6819492406e0
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c988f5ab5a342ad3282414634ca3bfc21f481ea5
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="writing-a-transactional-application"></a><span data-ttu-id="27466-102">트랜잭션 응용 프로그램 작성</span><span class="sxs-lookup"><span data-stu-id="27466-102">Writing a Transactional Application</span></span>
<span data-ttu-id="27466-103">트랜잭션 응용 프로그램 프로그래머는 <xref:System.Transactions> 네임스페이스가 제공하는 두 가지 프로그래밍 모델을 활용하여 트랜잭션을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27466-103">As a transactional application programmer, you can take advantage of the two programming models provided by the <xref:System.Transactions> namespace to create a transaction.</span></span> <span data-ttu-id="27466-104">사용 하 여 명시적 프로그래밍 모델을 사용할 수 있습니다는 <xref:System.Transactions.Transaction> 클래스 또는 트랜잭션을 관리 하는 자동으로 인프라에서 사용 하 여 암시적 프로그래밍 모델은 <xref:System.Transactions.TransactionScope> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="27466-104">You can utilize the explicit programming model by using the <xref:System.Transactions.Transaction> class, or the implicit programming model in which transactions are automatically managed by the infrastructure, by using the <xref:System.Transactions.TransactionScope> class.</span></span> <span data-ttu-id="27466-105">개발에 대 한 암시적 트랜잭션 모델을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="27466-105">We recommend that you use the implicit transaction model for development.</span></span> <span data-ttu-id="27466-106">에 트랜잭션 범위를 사용 하는 방법에 자세한 정보를 확인할 수는 [암시적 트랜잭션은 트랜잭션 범위를 사용 하 여 구현](../../../../docs/framework/data/transactions/implementing-an-implicit-transaction-using-transaction-scope.md) 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="27466-106">You can find more information on how to use a transaction scope in the [Implementing an Implicit Transaction using Transaction Scope](../../../../docs/framework/data/transactions/implementing-an-implicit-transaction-using-transaction-scope.md) topic.</span></span>  
  
 <span data-ttu-id="27466-107">두 모델은 모두 프로그램이 일관된 상태에 도달할 때 트랜잭션을 커밋하는 기능을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="27466-107">Both models support committing a transaction when the program reaches a consistent state.</span></span> <span data-ttu-id="27466-108">커밋이 성공하면 트랜잭션이 영구적으로 커밋됩니다.</span><span class="sxs-lookup"><span data-stu-id="27466-108">If the commit succeeds, the transaction is durably committed.</span></span> <span data-ttu-id="27466-109">커밋이 실패하면 트랜잭션이 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="27466-109">If the commit fails, the transaction aborts.</span></span> <span data-ttu-id="27466-110">응용 프로그램에서 트랜잭션을 성공적으로 완료할 수 없는 경우 트랜잭션을 중단하고 그 결과를 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="27466-110">If the application program cannot successfully complete the transaction, it attempts to abort and undo the transaction's effects.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="27466-111">단원 내용</span><span class="sxs-lookup"><span data-stu-id="27466-111">In This Section</span></span>  
  
### <a name="creating-a-transaction"></a><span data-ttu-id="27466-112">트랜잭션 만들기</span><span class="sxs-lookup"><span data-stu-id="27466-112">Creating a Transaction</span></span>  
 <span data-ttu-id="27466-113"><xref:System.Transactions> 네임스페이스에서는 트랜잭션을 만드는 두 가지 모델을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="27466-113">The <xref:System.Transactions> namespace provides two models for creating a transaction.</span></span> <span data-ttu-id="27466-114">이 모델에 대해서는 다음 항목에서 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="27466-114">These models are covered in the following topics.</span></span>  
  
 [<span data-ttu-id="27466-115">트랜잭션 범위를 사용 하 여 암시적 트랜잭션을 구현</span><span class="sxs-lookup"><span data-stu-id="27466-115">Implementing an Implicit Transaction using Transaction Scope</span></span>](../../../../docs/framework/data/transactions/implementing-an-implicit-transaction-using-transaction-scope.md)  
  
 <span data-ttu-id="27466-116"><xref:System.Transactions> 네임스페이스가 <xref:System.Transactions.TransactionScope> 클래스를 사용하여 암시적 트랜잭션을 만드는 기능을 지원하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="27466-116">Describes how the <xref:System.Transactions> namespace supports creating implicit transactions using the <xref:System.Transactions.TransactionScope> class.</span></span>  
  
 [<span data-ttu-id="27466-117">CommittableTransaction를 사용 하 여 명시적 트랜잭션을 구현</span><span class="sxs-lookup"><span data-stu-id="27466-117">Implementing an Explicit Transaction using CommittableTransaction</span></span>](../../../../docs/framework/data/transactions/implementing-an-explicit-transaction-using-committabletransaction.md)  
  
 <span data-ttu-id="27466-118"><xref:System.Transactions> 네임스페이스가 <xref:System.Transactions.CommittableTransaction> 클래스를 사용하여 명시적 트랜잭션을 만드는 기능을 지원하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="27466-118">Describes how the <xref:System.Transactions> namespace supports creating explicit transactions using the <xref:System.Transactions.CommittableTransaction> class.</span></span>  
  
### <a name="escalating-transaction-management"></a><span data-ttu-id="27466-119">트랜잭션 관리 에스컬레이션</span><span class="sxs-lookup"><span data-stu-id="27466-119">Escalating Transaction Management</span></span>  
 <span data-ttu-id="27466-120">트랜잭션이 다른 응용 프로그램 도메인의 리소스에 액세스해야 하는 경우 또는 다른 지속적인 리소스 관리자를 참여시키려는 경우 트랜잭션이 MSDTC에 의해 관리되도록 자동으로 에스컬레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="27466-120">When a transaction needs to access a resource in another application domain, or if you want to enlist in another durable resource manager, the transaction is automatically escalated to be managed by the MSDTC.</span></span> <span data-ttu-id="27466-121">트랜잭션 에스컬레이션을 다룹니다는 [트랜잭션 관리 에스컬레이션](../../../../docs/framework/data/transactions/transaction-management-escalation.md) 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="27466-121">Transaction escalation is covered in the [Transaction Management Escalation](../../../../docs/framework/data/transactions/transaction-management-escalation.md) topic.</span></span>  
  
### <a name="concurrency"></a><span data-ttu-id="27466-122">동시성</span><span class="sxs-lookup"><span data-stu-id="27466-122">Concurrency</span></span>  
 <span data-ttu-id="27466-123">항목 [DependentTransaction 사용 하 여 동시성 관리](../../../../docs/framework/data/transactions/managing-concurrency-with-dependenttransaction.md) 사용 하 여 비동기 작업 사이의 동시성 가능 방법을 보여 줍니다.는 <xref:System.Transactions.DependentTransaction> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="27466-123">The topic [Managing Concurrency with DependentTransaction](../../../../docs/framework/data/transactions/managing-concurrency-with-dependenttransaction.md) demonstrates how concurrency can be achieved between asynchronous tasks by using the <xref:System.Transactions.DependentTransaction> class.</span></span>  
  
### <a name="com-interop"></a><span data-ttu-id="27466-124">COM+ Interop</span><span class="sxs-lookup"><span data-stu-id="27466-124">COM+ Interop</span></span>  
 <span data-ttu-id="27466-125">항목 [엔터프라이즈 서비스와 COM + 트랜잭션을와 상호 운용성](../../../../docs/framework/data/transactions/interoperability-with-enterprise-services-and-com-transactions.md) COM + 트랜잭션을와 상호 작용 하면 분산된 트랜잭션도 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="27466-125">The topic [Interoperability with Enterprise Services and COM+ Transactions](../../../../docs/framework/data/transactions/interoperability-with-enterprise-services-and-com-transactions.md) illustrates how you can make your distributed transactions interact with COM+ transactions.</span></span>  
  
### <a name="diagnostics"></a><span data-ttu-id="27466-126">진단</span><span class="sxs-lookup"><span data-stu-id="27466-126">Diagnostics</span></span>  
 <span data-ttu-id="27466-127">[진단 추적](../../../../docs/framework/data/transactions/diagnostic-traces.md) 의해 생성 되는 추적 코드를 사용 하는 방법에 대해 설명 된 <xref:System.Transactions> 응용 프로그램에서 오류를 해결 하는 인프라입니다.</span><span class="sxs-lookup"><span data-stu-id="27466-127">[Diagnostic Traces](../../../../docs/framework/data/transactions/diagnostic-traces.md) describes how you can use the trace codes that are generated by the <xref:System.Transactions> infrastructure to troubleshoot errors in your applications.</span></span>  
  
### <a name="working-within-aspnet"></a><span data-ttu-id="27466-128">ASP.NET 작업</span><span class="sxs-lookup"><span data-stu-id="27466-128">Working within ASP.NET</span></span>  
 <span data-ttu-id="27466-129">[ASP.NET에서 System.Transactions를 사용 하 여](../../../../docs/framework/data/transactions/using-system-transactions-in-aspnet.md) 성공적으로 사용 하는 방법에 대해 설명 <xref:System.Transactions> 내 ASP.NET 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="27466-129">The [Using System.Transactions in ASP.NET](../../../../docs/framework/data/transactions/using-system-transactions-in-aspnet.md) topic describes how you can successfully use <xref:System.Transactions> inside an ASP.NET application.</span></span>
