---
title: "추적 형식 요약"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e639410b-d1d1-479c-b78e-a4701d4e4085
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fe4222ac124174341a28035c955a2a9bef4a167c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="trace-type-summary"></a><span data-ttu-id="ca8a5-102">추적 형식 요약</span><span class="sxs-lookup"><span data-stu-id="ca8a5-102">Trace Type Summary</span></span>
<span data-ttu-id="ca8a5-103">[Source Levels](http://go.microsoft.com/fwlink/?LinkID=94943) 다양 한 추적 수준을 정의: 중요, 오류, 경고, 정보 및 Verbose에 대 한 설명 제공는 `ActivityTracing` 플래그의 출력을 토글하 경계와 동작 전송 이벤트를 추적 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca8a5-103">[Source Levels](http://go.microsoft.com/fwlink/?LinkID=94943) defines various trace levels: Critical, Error, Warning, Information, and Verbose, as well as provides description of the `ActivityTracing` flag, which toggles the output of trace boundary and activity transfer events.</span></span>  
  
 <span data-ttu-id="ca8a5-104">또한 검토할 수 있습니다 [TraceEventType](http://go.microsoft.com/fwlink/?LinkId=95169) 에서 내보낼 수 있는 추적 형식에 대 한 <xref:System.Diagnostics>합니다.</span><span class="sxs-lookup"><span data-stu-id="ca8a5-104">You can also review [TraceEventType](http://go.microsoft.com/fwlink/?LinkId=95169) for the types of traces which can be emitted from <xref:System.Diagnostics>.</span></span>  
  
 <span data-ttu-id="ca8a5-105">다음 표에서는 가장 중요한 항목을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ca8a5-105">The following table lists the most important ones.</span></span>  
  
|<span data-ttu-id="ca8a5-106">추적 형식</span><span class="sxs-lookup"><span data-stu-id="ca8a5-106">Trace Type</span></span>|<span data-ttu-id="ca8a5-107">설명</span><span class="sxs-lookup"><span data-stu-id="ca8a5-107">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="ca8a5-108">중요</span><span class="sxs-lookup"><span data-stu-id="ca8a5-108">Critical</span></span>|<span data-ttu-id="ca8a5-109">오류 또는 응용 프로그램 충돌</span><span class="sxs-lookup"><span data-stu-id="ca8a5-109">Fatal error or application crash.</span></span>|  
|<span data-ttu-id="ca8a5-110">오류</span><span class="sxs-lookup"><span data-stu-id="ca8a5-110">Error</span></span>|<span data-ttu-id="ca8a5-111">복구할 수 있는 오류</span><span class="sxs-lookup"><span data-stu-id="ca8a5-111">Recoverable error.</span></span>|  
|<span data-ttu-id="ca8a5-112">경고</span><span class="sxs-lookup"><span data-stu-id="ca8a5-112">Warning</span></span>|<span data-ttu-id="ca8a5-113">알림 메시지</span><span class="sxs-lookup"><span data-stu-id="ca8a5-113">Informational message.</span></span>|  
|<span data-ttu-id="ca8a5-114">정보</span><span class="sxs-lookup"><span data-stu-id="ca8a5-114">Information</span></span>|<span data-ttu-id="ca8a5-115">중요하지 않은 문제</span><span class="sxs-lookup"><span data-stu-id="ca8a5-115">Non-critical problem.</span></span>|  
|<span data-ttu-id="ca8a5-116">자세히</span><span class="sxs-lookup"><span data-stu-id="ca8a5-116">Verbose</span></span>|<span data-ttu-id="ca8a5-117">추적 디버깅</span><span class="sxs-lookup"><span data-stu-id="ca8a5-117">Debugging trace.</span></span>|  
|<span data-ttu-id="ca8a5-118">시작</span><span class="sxs-lookup"><span data-stu-id="ca8a5-118">Start</span></span>|<span data-ttu-id="ca8a5-119">처리의 논리 단위 시작</span><span class="sxs-lookup"><span data-stu-id="ca8a5-119">Starting of a logical unit of processing.</span></span>|  
|<span data-ttu-id="ca8a5-120">일시 중단</span><span class="sxs-lookup"><span data-stu-id="ca8a5-120">Suspend</span></span>|<span data-ttu-id="ca8a5-121">처리의 논리 단위 일시 중단</span><span class="sxs-lookup"><span data-stu-id="ca8a5-121">Suspension of a logical unit of processing.</span></span>|  
|<span data-ttu-id="ca8a5-122">다시 시작</span><span class="sxs-lookup"><span data-stu-id="ca8a5-122">Resume</span></span>|<span data-ttu-id="ca8a5-123">처리의 논리 단위 다시 시작</span><span class="sxs-lookup"><span data-stu-id="ca8a5-123">Resumption of a logical unit of processing.</span></span>|  
|<span data-ttu-id="ca8a5-124">Stop</span><span class="sxs-lookup"><span data-stu-id="ca8a5-124">Stop</span></span>|<span data-ttu-id="ca8a5-125">처리의 논리 단위 중지</span><span class="sxs-lookup"><span data-stu-id="ca8a5-125">Stopping of a logical unit of processing.</span></span>|  
|<span data-ttu-id="ca8a5-126">전송</span><span class="sxs-lookup"><span data-stu-id="ca8a5-126">Transfer</span></span>|<span data-ttu-id="ca8a5-127">상관 관계 ID의 변경</span><span class="sxs-lookup"><span data-stu-id="ca8a5-127">Changing of correlation identity.</span></span>|  
  
 <span data-ttu-id="ca8a5-128">동작은 위의 추적 형식의 조합으로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca8a5-128">An activity is defined as a combination of the trace types above.</span></span>  
  
 <span data-ttu-id="ca8a5-129">다음은 로컬(추적 소스) 범위에서 이상적인 동작을 정의하는 정규식입니다.</span><span class="sxs-lookup"><span data-stu-id="ca8a5-129">The following is a regular expression that defines an ideal activity in a local (trace source) scope,</span></span>  
  
 `R = Start (Critical | Error | Warning | Information | Verbose | Transfer | (Transfer Suspend Transfer Resume) )* Stop`  
  
 <span data-ttu-id="ca8a5-130">이는 동작이 다음 조건을 만족해야 함을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="ca8a5-130">This means that an activity must satisfy the following conditions.</span></span>  
  
-   <span data-ttu-id="ca8a5-131">Start 및 Stop 추적에 의해 각각 시작되고 중지되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca8a5-131">It must start and stop respectively by a Start and Stop traces</span></span>  
  
-   <span data-ttu-id="ca8a5-132">Suspend 추적 또는 Resume 추적의 바로 앞에 Transfer 추적이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca8a5-132">It must have a Transfer trace immediately preceding a Suspend or Resume trace</span></span>  
  
-   <span data-ttu-id="ca8a5-133">Suspend 추적 및 Resume 추적이 존재할 경우 이 사이에 추적이 있으면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca8a5-133">It must not have any traces between the Suspend and Resume traces if such traces exist</span></span>  
  
-   <span data-ttu-id="ca8a5-134">위와 같은 조건이 충족되는 한 Critical/Error/Warning/Information/Verbose/Transfer 추적은 여러 개가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca8a5-134">It can have any and as many of critical/Error/Warning/Information/Verbose/Transfer traces as long as the previous conditions are observed</span></span>  
  
 <span data-ttu-id="ca8a5-135">다음은 전역 범위에서 이상적인 동작을 정의하는 정규식입니다.</span><span class="sxs-lookup"><span data-stu-id="ca8a5-135">The following is a regular expression that defines an ideal activity in the global scope,</span></span>  
  
```  
R+   
```  
  
 <span data-ttu-id="ca8a5-136">로컬 범위에서 동작에 대한 정규식인 R을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="ca8a5-136">with R being the regular expression for an activity in the local scope.</span></span> <span data-ttu-id="ca8a5-137">이는 다음으로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca8a5-137">This translates to,</span></span>  
  
```  
[R+ = Start ( Critical | Error | Warning | Information | Verbose | Transfer | (Transfer Suspend Transfer Resume) )* Stop]+  
```
