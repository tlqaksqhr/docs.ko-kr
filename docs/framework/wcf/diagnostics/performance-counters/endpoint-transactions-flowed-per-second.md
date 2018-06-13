---
title: '끝점: Transactions Flowed Per Second'
ms.date: 03/30/2017
ms.assetid: 0f370ff1-a913-450b-bccb-c279ad165b3d
ms.openlocfilehash: ff3d76025bbae0759dba005adbd62609701c5a7a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33471284"
---
# <a name="endpoint-transactions-flowed-per-second"></a><span data-ttu-id="27204-102">끝점: Transactions Flowed Per Second</span><span class="sxs-lookup"><span data-stu-id="27204-102">Endpoint: Transactions Flowed Per Second</span></span>
<span data-ttu-id="27204-103">카운터 이름: Transactions Flowed Per Second</span><span class="sxs-lookup"><span data-stu-id="27204-103">Counter Name: Transactions Flowed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="27204-104">설명</span><span class="sxs-lookup"><span data-stu-id="27204-104">Description</span></span>  
 <span data-ttu-id="27204-105">이 끝점에서 작업에 적용된 초당 트랜잭션의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="27204-105">Number of transactions flowed to operations at this endpoint in a second.</span></span> <span data-ttu-id="27204-106">끝점에 전송된 메시지에 트랜잭션 ID가 있을 때마다 이 카운터가 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="27204-106">This counter is incremented any time a transaction ID is present in a message sent to the endpoint.</span></span>  
  
 <span data-ttu-id="27204-107">이 카운터는 성능 카운터 형식 [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), 값은 다음과 같은 수식으로 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="27204-107">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="27204-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="27204-108">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
