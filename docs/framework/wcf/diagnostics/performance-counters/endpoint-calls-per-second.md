---
title: "끝점: Calls Per Second"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ca0fc06d-d68f-4236-bd5f-c7ff6214acdd
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 559bc945cde67a89d7e0fcdcde3f50e8ff51a138
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="endpoint-calls-per-second"></a><span data-ttu-id="445f0-102">끝점: Calls Per Second</span><span class="sxs-lookup"><span data-stu-id="445f0-102">Endpoint: Calls Per Second</span></span>
<span data-ttu-id="445f0-103">카운터 이름: Calls Per Second</span><span class="sxs-lookup"><span data-stu-id="445f0-103">Counter Name: Calls Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="445f0-104">설명</span><span class="sxs-lookup"><span data-stu-id="445f0-104">Description</span></span>  
 <span data-ttu-id="445f0-105">이 끝점에 대한 초당 호출 수입니다.</span><span class="sxs-lookup"><span data-stu-id="445f0-105">Number of calls to this endpoint in a second.</span></span>  
  
 <span data-ttu-id="445f0-106">이 카운터는 성능 카운터 형식 [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), 값은 다음과 같은 수식으로 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="445f0-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="445f0-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span><span class="sxs-lookup"><span data-stu-id="445f0-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>
