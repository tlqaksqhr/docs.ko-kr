---
title: System.ServiceModel.MessageClosedAgain
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 24c274d4-65cd-4c91-9869-bc6eb34ef979
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 57500bf3c66c0aec47150bb21cc8871738d4b72d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="systemservicemodelmessageclosedagain"></a><span data-ttu-id="34f11-102">System.ServiceModel.MessageClosedAgain</span><span class="sxs-lookup"><span data-stu-id="34f11-102">System.ServiceModel.MessageClosedAgain</span></span>
<span data-ttu-id="34f11-103">System.ServiceModel.MessageClosedAgain</span><span class="sxs-lookup"><span data-stu-id="34f11-103">System.ServiceModel.MessageClosedAgain</span></span>  
  
## <a name="description"></a><span data-ttu-id="34f11-104">설명</span><span class="sxs-lookup"><span data-stu-id="34f11-104">Description</span></span>  
 <span data-ttu-id="34f11-105">메시지가 다시 닫혔습니다.</span><span class="sxs-lookup"><span data-stu-id="34f11-105">A message was closed again.</span></span>  
  
 <span data-ttu-id="34f11-106">메시지는 한 번만 닫혀야 합니다.</span><span class="sxs-lookup"><span data-stu-id="34f11-106">A message should be closed only once.</span></span> <span data-ttu-id="34f11-107">사용자 확장 코드에서 이 추적을 내보낸다는 것은 사용자 확장 코드가 이미 닫힌 메시지를 닫고 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="34f11-107">If this trace is being emitted in user extension code, it indicates that the user extension code is closing a message that has already been closed.</span></span> <span data-ttu-id="34f11-108">제품 코드를 통해 이 추적을 내보낸다는 것은 사용자 확장명 코드가 메시지를 너무 일찍 닫을 가능성이 있다는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="34f11-108">If this trace is being emitted through product code, it indicates that the user extension code could potentially be closing a message too early.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34f11-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="34f11-109">See Also</span></span>  
 [<span data-ttu-id="34f11-110">추적</span><span class="sxs-lookup"><span data-stu-id="34f11-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="34f11-111">추적을 사용하여 응용 프로그램 문제 해결</span><span class="sxs-lookup"><span data-stu-id="34f11-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="34f11-112">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="34f11-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
