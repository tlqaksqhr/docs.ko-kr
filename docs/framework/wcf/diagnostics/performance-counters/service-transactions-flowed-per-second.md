---
title: "서비스: Transactions Flowed Per Second"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ec72eb49-2942-4811-91df-d6e5dad81fd8
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 9172075294de8431216540b06aec542753c94621
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="service-transactions-flowed-per-second"></a><span data-ttu-id="18f68-102">서비스: Transactions Flowed Per Second</span><span class="sxs-lookup"><span data-stu-id="18f68-102">Service: Transactions Flowed Per Second</span></span>
<span data-ttu-id="18f68-103">카운터 이름: Transactions Flowed Per Second</span><span class="sxs-lookup"><span data-stu-id="18f68-103">Counter Name: Transactions Flowed Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="18f68-104">설명</span><span class="sxs-lookup"><span data-stu-id="18f68-104">Description</span></span>  
 <span data-ttu-id="18f68-105">이 서비스에서 작업에 적용된 초당 트랜잭션 수입니다.</span><span class="sxs-lookup"><span data-stu-id="18f68-105">Number of transactions flowed to operations in this service in a second.</span></span>  
  
 <span data-ttu-id="18f68-106">이 카운터는 성능 카운터 형식 [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), 값은 다음과 같은 수식으로 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="18f68-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="18f68-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="18f68-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
