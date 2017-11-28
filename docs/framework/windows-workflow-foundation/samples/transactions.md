---
title: Transactions2
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 51212219-a39e-448e-bff3-10064ff5de64
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c7611ce26c1a3b9150a60ced7b4931cc1282eecd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="transactions"></a><span data-ttu-id="cc6ef-102">트랜잭션</span><span class="sxs-lookup"><span data-stu-id="cc6ef-102">Transactions</span></span>
<span data-ttu-id="cc6ef-103">이 단원에는 [!INCLUDE[wf](../../../../includes/wf-md.md)]에서 워크플로 트랜잭션을 보여 주는 샘플이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc6ef-103">This section contains samples that demonstrate workflow transactions in [!INCLUDE[wf](../../../../includes/wf-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cc6ef-104">단원 내용</span><span class="sxs-lookup"><span data-stu-id="cc6ef-104">In This Section</span></span>  
 [<span data-ttu-id="cc6ef-105">기본 TransactionScope</span><span class="sxs-lookup"><span data-stu-id="cc6ef-105">Basic TransactionScope</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/basic-transactionscope.md)  
 <span data-ttu-id="cc6ef-106"><xref:System.Activities.Statements.TransactionScope> 인스턴스를 중첩하는 방법을 보여 주는 네 개의 시나리오로 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc6ef-106">Consists of four scenarios that show how to nest <xref:System.Activities.Statements.TransactionScope> instances.</span></span>  
  
 [<span data-ttu-id="cc6ef-107">TransactedReceiveScope 사용</span><span class="sxs-lookup"><span data-stu-id="cc6ef-107">Use of TransactedReceiveScope</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/use-of-transactedreceivescope.md)  
 <span data-ttu-id="cc6ef-108"><xref:System.Activities.Statements.TransactionScope>를 사용하여 클라이언트에 새 트랜잭션을 만들고 <xref:System.ServiceModel.Activities.TransactedReceiveScope>를 사용하여 이동된 트랜잭션과 함께 메시지를 받고 서버에 있는 트랜잭션의 수명 주기 범위를 지정하여 클라이언트에서 서버로 트랜잭션을 이동하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cc6ef-108">Demonstrates how to flow a transaction from a client to a server using <xref:System.Activities.Statements.TransactionScope> to create a new transaction on the client and a <xref:System.ServiceModel.Activities.TransactedReceiveScope> to receive a message with a flowed transaction and scope the lifetime of the transaction on the server.</span></span>  
  
 [<span data-ttu-id="cc6ef-109">서비스 내에 transactionscope 중첩</span><span class="sxs-lookup"><span data-stu-id="cc6ef-109">Nesting of TransactionScope within a service</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/nesting-of-transactionscope-within-a-service.md)  
 <span data-ttu-id="cc6ef-110">한 서비스 내의 <xref:System.Activities.Statements.TransactionScope> 활동 인스턴스를 처리하는 방법을 보여 주는 두 개의 시나리오로 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc6ef-110">Consists of two scenarios that show how to handle <xref:System.Activities.Statements.TransactionScope> activity instances within a service.</span></span>
