---
title: Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorResponseInvalidMetadata
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a174bbf5-0ffe-4fda-969d-e7fbd1996123
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e5bc467c7854dd787b0fff5d4a1da24d72c01c80
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="microsofttransactionstransactionbridgeregistrationcoordinatorresponseinvalidmetadata"></a><span data-ttu-id="3ee4d-102">Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorResponseInvalidMetadata</span><span class="sxs-lookup"><span data-stu-id="3ee4d-102">Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorResponseInvalidMetadata</span></span>
<span data-ttu-id="3ee4d-103">WS-Atomic Transaction 프로토콜 서비스에서 잘못되었거나 호환되지 않는 메타데이터가 있는 끝점 참조를 포함한 RegisterResponse 메시지를 코디네이터로부터 받았습니다.</span><span class="sxs-lookup"><span data-stu-id="3ee4d-103">The WS-Atomic Transaction protocol service received a RegisterResponse message from its coordinator that contains an endpoint reference with invalid or incompatible metadata.</span></span>  
  
## <a name="description"></a><span data-ttu-id="3ee4d-104">설명</span><span class="sxs-lookup"><span data-stu-id="3ee4d-104">Description</span></span>  
 <span data-ttu-id="3ee4d-105">로컬 트랜잭션 관리자에서 상위 트랜잭션 관리자에 등록하려고 하는 경우 상위에서 RegisterResponse 메시지에 잘못된 주소를 반환하면 추적됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ee4d-105">Traced when the local Transaction Manager tries to register with its superior Transaction Manager and the superior returns an invalid address within the RegisterResponse message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ee4d-106">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3ee4d-106">See Also</span></span>  
 [<span data-ttu-id="3ee4d-107">추적</span><span class="sxs-lookup"><span data-stu-id="3ee4d-107">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="3ee4d-108">추적을 사용 하 여 응용 프로그램 문제를 해결 하려면</span><span class="sxs-lookup"><span data-stu-id="3ee4d-108">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="3ee4d-109">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="3ee4d-109">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
