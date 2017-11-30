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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7f3963fe28ccaf55b3946254e395b770619c8f22
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="systemservicemodelmessageclosedagain"></a><span data-ttu-id="2b7eb-102">System.ServiceModel.MessageClosedAgain</span><span class="sxs-lookup"><span data-stu-id="2b7eb-102">System.ServiceModel.MessageClosedAgain</span></span>
<span data-ttu-id="2b7eb-103">System.ServiceModel.MessageClosedAgain</span><span class="sxs-lookup"><span data-stu-id="2b7eb-103">System.ServiceModel.MessageClosedAgain</span></span>  
  
## <a name="description"></a><span data-ttu-id="2b7eb-104">설명</span><span class="sxs-lookup"><span data-stu-id="2b7eb-104">Description</span></span>  
 <span data-ttu-id="2b7eb-105">메시지가 다시 닫혔습니다.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-105">A message was closed again.</span></span>  
  
 <span data-ttu-id="2b7eb-106">메시지는 한 번만 닫혀야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-106">A message should be closed only once.</span></span> <span data-ttu-id="2b7eb-107">사용자 확장 코드에서 이 추적을 내보낸다는 것은 사용자 확장 코드가 이미 닫힌 메시지를 닫고 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-107">If this trace is being emitted in user extension code, it indicates that the user extension code is closing a message that has already been closed.</span></span> <span data-ttu-id="2b7eb-108">제품 코드를 통해 이 추적을 내보낸다는 것은 사용자 확장명 코드가 메시지를 너무 일찍 닫을 가능성이 있다는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2b7eb-108">If this trace is being emitted through product code, it indicates that the user extension code could potentially be closing a message too early.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b7eb-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2b7eb-109">See Also</span></span>  
 [<span data-ttu-id="2b7eb-110">추적</span><span class="sxs-lookup"><span data-stu-id="2b7eb-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="2b7eb-111">추적을 사용 하 여 응용 프로그램 문제를 해결 하려면</span><span class="sxs-lookup"><span data-stu-id="2b7eb-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="2b7eb-112">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="2b7eb-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
