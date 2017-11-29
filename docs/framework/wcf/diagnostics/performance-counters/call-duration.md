---
title: Call Duration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e4973ec3-3c66-4c0b-b5d0-294b62c83f7d
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 9bf221115b7919a1ca7facdfe80af2af899b3326
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="call-duration"></a><span data-ttu-id="eb0cc-102">Call Duration</span><span class="sxs-lookup"><span data-stu-id="eb0cc-102">Call Duration</span></span>
<span data-ttu-id="eb0cc-103">카운터 이름: Call Duration</span><span class="sxs-lookup"><span data-stu-id="eb0cc-103">Counter Name: Call Duration</span></span>  
  
## <a name="description"></a><span data-ttu-id="eb0cc-104">설명</span><span class="sxs-lookup"><span data-stu-id="eb0cc-104">Description</span></span>  
 <span data-ttu-id="eb0cc-105">이 작업에 대한 평균 호출 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="eb0cc-105">The average duration of calls to this operation.</span></span> <span data-ttu-id="eb0cc-106">평균 기간은 (N1-N0)/(D1-D0) 공식을 사용해 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb0cc-106">The average duration is calculated based on this equation: (N1-N0)/(D1-D0).</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="eb0cc-107">비동기 WCF 서비스에서 사용되는 경우 Call Duration 카운터는 항상 -1을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="eb0cc-107">When used on an asynchronous WCF service the Call Duration counter will always return -1.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb0cc-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="eb0cc-108">See Also</span></span>  
 [<span data-ttu-id="eb0cc-109">PERF_AVERAGE_TIMER (영문)</span><span class="sxs-lookup"><span data-stu-id="eb0cc-109">PERF_AVERAGE_TIMER</span></span>](http://go.microsoft.com/fwlink/?LinkId=95015)
