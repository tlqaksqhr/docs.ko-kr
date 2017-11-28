---
title: System.ServiceModel.TxFailedToNegotiateOleTx
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3f0f0b4b-a1ad-4704-8329-455daf54892d
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 61360eff4f2c403eea98bbc0a2eae36e516b3d7a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="systemservicemodeltxfailedtonegotiateoletx"></a><span data-ttu-id="fa59f-102">System.ServiceModel.TxFailedToNegotiateOleTx</span><span class="sxs-lookup"><span data-stu-id="fa59f-102">System.ServiceModel.TxFailedToNegotiateOleTx</span></span>
<span data-ttu-id="fa59f-103">지정된 코디네이션 컨텍스트에 대해 OleTransactions 프로토콜 협상을 완료하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="fa59f-103">The OleTransactions protocol negotiation failed to complete for the specified coordination context.</span></span>  
  
## <a name="description"></a><span data-ttu-id="fa59f-104">설명</span><span class="sxs-lookup"><span data-stu-id="fa59f-104">Description</span></span>  
 <span data-ttu-id="fa59f-105">OleTx 정보가 포함된 들어오는 트랜잭션이 첨부된 OleTx 정보를 사용할 수 없고 대신 WS-AT를 사용하는 경우 추적됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa59f-105">Traced when an incoming transaction with OleTx information is unable to use the attached OleTx information, and will fall-back to using WS-AT instead.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="fa59f-106">문제 해결</span><span class="sxs-lookup"><span data-stu-id="fa59f-106">Troubleshooting</span></span>  
 <span data-ttu-id="fa59f-107">시스템 간의 MSDTC RPC 통신 관련 잠재적 문제를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fa59f-107">Indicates a potential problem with MSDTC RPC communication between the machines.</span></span> <span data-ttu-id="fa59f-108">이렇게 많은 추적이 로그에 나타날 경우 성능이 많이 떨어질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa59f-108">If many of these traces appear in the log, a drastic decrease in performance can result.</span></span>  <span data-ttu-id="fa59f-109">OleTx를 사용하지 않는 경우 WS-AT 레지스트리 구성에서 `OleTxUpgradeEnabled`를 0으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="fa59f-109">If OleTx is not desired, set `OleTxUpgradeEnabled` to 0 in the WS-AT registry configuration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa59f-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fa59f-110">See Also</span></span>  
 [<span data-ttu-id="fa59f-111">추적</span><span class="sxs-lookup"><span data-stu-id="fa59f-111">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="fa59f-112">추적을 사용 하 여 응용 프로그램 문제를 해결 하려면</span><span class="sxs-lookup"><span data-stu-id="fa59f-112">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="fa59f-113">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="fa59f-113">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
