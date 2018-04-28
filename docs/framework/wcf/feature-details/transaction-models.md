---
title: 트랜잭션 모델
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 48a8bc1b-128b-4cf1-a421-8cc73223c340
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ab3baf8cc0bb6af951f6f3e6396b7545d0c6b301
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="transaction-models"></a><span data-ttu-id="0bb24-102">트랜잭션 모델</span><span class="sxs-lookup"><span data-stu-id="0bb24-102">Transaction Models</span></span>
<span data-ttu-id="0bb24-103">이 항목에서는 트랜잭션 프로그래밍 모델 및 Microsoft가 제공하는 인프라 구성 요소 간의 관계에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0bb24-103">This topic describes the relationship between the transaction programming models and the infrastructure components Microsoft provides.</span></span>  
  
 <span data-ttu-id="0bb24-104">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]에서 트랜잭션을 사용하는 경우 서로 다른 트랜잭션 모델 사이에서 선택하지 않고 통합되고 일관된 모델의 다른 계층에서 작업하는 것임을 이해하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="0bb24-104">When using transactions in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], it is important to understand that you are not selecting between different transactional models, but rather operating at different layers of an integrated and consistent model.</span></span>  
  
 <span data-ttu-id="0bb24-105">다음 단원에서는 세 가지 기본 트랜잭션 구성 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0bb24-105">The following sections describe the three primary transaction components.</span></span>  
  
## <a name="windows-communication-foundation-transactions"></a><span data-ttu-id="0bb24-106">Windows Communication Foundation 트랜잭션</span><span class="sxs-lookup"><span data-stu-id="0bb24-106">Windows Communication Foundation Transactions</span></span>  
 <span data-ttu-id="0bb24-107">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]의 트랜잭션 지원을 사용하여 트랜잭션 서비스를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bb24-107">The transaction support in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] allows you write transactional services.</span></span> <span data-ttu-id="0bb24-108">또한 WS-AT(WS-AtomicTransaction) 프로토콜에 대한 지원을 통해 응용 프로그램은 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 또는 타사 기술 중 하나를 사용하여 빌드된 웹 서비스에 트랜잭션을 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bb24-108">In addition, with its support for the WS-AtomicTransaction (WS-AT) protocol, applications can flow transactions to Web services built using either [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] or third-party technology.</span></span>  
  
 <span data-ttu-id="0bb24-109">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스 또는 응용 프로그램에서 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 트랜잭션 기능은 인프라가 트랜잭션을 생성, 전달 및 동기화 하는 방법 및 시점을 선언적으로 지정하기 위한 특성 및 구성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0bb24-109">In a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service or application, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] transaction features provide attributes and configuration for declaratively specifying how and when the infrastructure should create, flow, and synchronize transactions.</span></span>  
  
## <a name="systemtransactions-transactions"></a><span data-ttu-id="0bb24-110">System.Transactions 트랜잭션</span><span class="sxs-lookup"><span data-stu-id="0bb24-110">System.Transactions Transactions</span></span>  
 <span data-ttu-id="0bb24-111"><xref:System.Transactions> 네임스페이스는 <xref:System.Transactions.Transaction> 클래스 기반의 명시적 프로그래밍 모델과 <xref:System.Transactions.TransactionScope> 클래스를 사용하는 암시적 프로그래밍 모델을 모두 제공합니다. 후자의 경우 인프라에서 자동으로 트랜잭션을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="0bb24-111">The <xref:System.Transactions> namespace provides both an explicit programming model based on the <xref:System.Transactions.Transaction> class, as well as an implicit programming model using the <xref:System.Transactions.TransactionScope> class, in which the infrastructure automatically manages transactions.</span></span>  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="0bb24-112"> 이러한 두 가지 모델을 사용 하 여 트랜잭션 응용 프로그램 만들기를 참조 하는 방법 [트랜잭션 응용 프로그램을 작성](http://go.microsoft.com/fwlink/?LinkId=94947)합니다.</span><span class="sxs-lookup"><span data-stu-id="0bb24-112"> how to create a transactional application using these two models, see [Writing a Transactional Application](http://go.microsoft.com/fwlink/?LinkId=94947).</span></span>  
  
 <span data-ttu-id="0bb24-113">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스 또는 응용 프로그램의 경우 <xref:System.Transactions>은 클라이언트 응용 프로그램 내에서 트랜잭션을 만들고 필요한 경우 서비스 내에서 트랜잭션과 명시적으로 상호 작용하기 위한 프로그래밍 모델을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0bb24-113">In a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service or application, <xref:System.Transactions> provides the programming model for creating transactions within a client application and for explicitly interacting with a transaction, when required, within a service.</span></span>  
  
## <a name="msdtc-transactions"></a><span data-ttu-id="0bb24-114">MSDTC 트랜잭션</span><span class="sxs-lookup"><span data-stu-id="0bb24-114">MSDTC Transactions</span></span>  
 <span data-ttu-id="0bb24-115">MSDTC(Microsoft Distributed Transaction Coordinator)는 분산 트랜잭션을 지원하는 트랜잭션 관리자입니다.</span><span class="sxs-lookup"><span data-stu-id="0bb24-115">The Microsoft Distributed Transaction Coordinator (MSDTC) is a transaction manager that provides support for distributed transactions.</span></span>  
  
 <span data-ttu-id="0bb24-116">자세한 내용은 참조는 [DTC 프로그래머 참조](http://go.microsoft.com/fwlink/?LinkId=94948)합니다.</span><span class="sxs-lookup"><span data-stu-id="0bb24-116">For more information, see the [DTC Programmer's Reference](http://go.microsoft.com/fwlink/?LinkId=94948).</span></span>  
  
 <span data-ttu-id="0bb24-117">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스 또는 응용 프로그램의 경우 MSDTC는 클라이언트 또는 서비스 내에서 만든 트랜잭션의 코디네이션을 위한 인프라를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0bb24-117">In a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service or application, MSDTC provides the infrastructure for the coordination of transactions created within a client or service.</span></span>
