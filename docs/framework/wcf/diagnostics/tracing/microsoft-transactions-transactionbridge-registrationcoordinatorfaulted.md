---
title: Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFaulted
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8193027e-9db2-4af9-a072-27300cd24330
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8cf9f8a9fba43a915fd71e397c4aed54c8d95197
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="microsofttransactionstransactionbridgeregistrationcoordinatorfaulted"></a><span data-ttu-id="2e7a5-102">Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFaulted</span><span class="sxs-lookup"><span data-stu-id="2e7a5-102">Microsoft.Transactions.TransactionBridge.RegistrationCoordinatorFaulted</span></span>
<span data-ttu-id="2e7a5-103">WS-AT 프로토콜 서비스가 코디네이터로부터 Register 메시지에 대한 오류 응답을 받았습니다.</span><span class="sxs-lookup"><span data-stu-id="2e7a5-103">The WS-AT protocol service received a fault from its coordinator in response to a Register message.</span></span>  
  
## <a name="description"></a><span data-ttu-id="2e7a5-104">설명</span><span class="sxs-lookup"><span data-stu-id="2e7a5-104">Description</span></span>  
 <span data-ttu-id="2e7a5-105">로컬 TransactionManager가 반환되는 오류 때문에 상위 TransactionManager를 등록할 수 없는 경우 추적됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e7a5-105">Traced if the local TransactionManager is not able to Register with its superior TransactionManager due to a fault being returned.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="2e7a5-106">문제 해결</span><span class="sxs-lookup"><span data-stu-id="2e7a5-106">Troubleshooting</span></span>  
 <span data-ttu-id="2e7a5-107">반환된 오류에 대한 추적 메시지를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="2e7a5-107">Inspect the trace message for the fault returned.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e7a5-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2e7a5-108">See Also</span></span>  
 [<span data-ttu-id="2e7a5-109">추적</span><span class="sxs-lookup"><span data-stu-id="2e7a5-109">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="2e7a5-110">추적을 사용하여 응용 프로그램 문제 해결</span><span class="sxs-lookup"><span data-stu-id="2e7a5-110">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="2e7a5-111">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="2e7a5-111">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
