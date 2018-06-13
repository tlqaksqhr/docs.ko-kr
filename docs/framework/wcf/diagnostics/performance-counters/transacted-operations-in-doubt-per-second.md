---
title: Transacted Operations In Doubt Per Second
ms.date: 03/30/2017
ms.assetid: 7e6b0716-c107-42e5-a21d-31d988e7a691
ms.openlocfilehash: e165e934f17d599a9bb89f2702bb74d1ba0bf633
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33474313"
---
# <a name="transacted-operations-in-doubt-per-second"></a><span data-ttu-id="5dae4-102">Transacted Operations In Doubt Per Second</span><span class="sxs-lookup"><span data-stu-id="5dae4-102">Transacted Operations In Doubt Per Second</span></span>
<span data-ttu-id="5dae4-103">카운터 이름: Transacted Operations In Doubt Per Second</span><span class="sxs-lookup"><span data-stu-id="5dae4-103">Counter Name: Transacted Operations In Doubt Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="5dae4-104">설명</span><span class="sxs-lookup"><span data-stu-id="5dae4-104">Description</span></span>  
 <span data-ttu-id="5dae4-105">초당 이 서비스에서 확실하지 않은 결과가 있는 트랜잭션 작업의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="5dae4-105">Number of transactional operations with an in-doubt outcome in this service in a second.</span></span>  
  
 <span data-ttu-id="5dae4-106">이 카운터는 성능 카운터 형식 [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), 값은 다음과 같은 수식으로 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="5dae4-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="5dae4-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="5dae4-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
