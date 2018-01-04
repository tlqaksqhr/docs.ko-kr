---
title: Transacted Operations Committed Per Second
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7318921b-47c4-4c8c-9fdd-41a92061c53f
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 96a17d99329248dff4a29f3c68649c67622c45d8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="transacted-operations-committed-per-second"></a><span data-ttu-id="089bd-102">Transacted Operations Committed Per Second</span><span class="sxs-lookup"><span data-stu-id="089bd-102">Transacted Operations Committed Per Second</span></span>
<span data-ttu-id="089bd-103">카운터 이름: Transacted Operations Committed Per Second</span><span class="sxs-lookup"><span data-stu-id="089bd-103">Counter Name: Transacted Operations Committed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="089bd-104">설명</span><span class="sxs-lookup"><span data-stu-id="089bd-104">Description</span></span>  
 <span data-ttu-id="089bd-105">초당 이 서비스에서 커밋된 트랜잭션 작업 수입니다.</span><span class="sxs-lookup"><span data-stu-id="089bd-105">Number of transactional operations that have been committed in this service in a second.</span></span>  
  
 <span data-ttu-id="089bd-106">이 카운터는 성능 카운터 형식 [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), 값은 다음과 같은 수식으로 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="089bd-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="089bd-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="089bd-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
