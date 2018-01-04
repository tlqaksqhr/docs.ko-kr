---
title: "동작 ID 전파"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cd1c1ae5-cc8a-4f51-90c9-f7b476bcfe70
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1f7543a79f351cf1f1e9c6d8c316684d9bfc3155
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="activity-id-propagation"></a><span data-ttu-id="03a29-102">동작 ID 전파</span><span class="sxs-lookup"><span data-stu-id="03a29-102">Activity ID Propagation</span></span>
<span data-ttu-id="03a29-103">ServiceModel 동작 추적을 사용하면 ServiceModel 동작을 통해 전파가 발생하고, ServiceModel 동작 추적을 사용하지 않으면 사용자 간에 전파가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="03a29-103">Propagation happens when ServiceModel activity tracing is enabled (ServiceModel propagation) or disabled (User-to-User activity propagation).</span></span>  
  
## <a name="servicemodel-activity-tracing-is-enabled"></a><span data-ttu-id="03a29-104">ServiceModel 동작 추적 사용</span><span class="sxs-lookup"><span data-stu-id="03a29-104">ServiceModel Activity Tracing is Enabled</span></span>  
 <span data-ttu-id="03a29-105">ServiceModel ActivityTracing을 사용하면 ProcessAction 동작 간에 전파가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="03a29-105">If ServiceModel ActivityTracing is enabled, propagation happens between ProcessAction activities.</span></span>  
  
### <a name="server"></a><span data-ttu-id="03a29-106">서버</span><span class="sxs-lookup"><span data-stu-id="03a29-106">Server</span></span>  
 <span data-ttu-id="03a29-107">때는 `propagateActivity` 특성이로 설정 된 `true` 클라이언트와 서버의 ID에는 `ProcessAction` 활동 서버에는 id는 전파에 동일 `ActivityId` 메시지 헤더입니다.</span><span class="sxs-lookup"><span data-stu-id="03a29-107">When the `propagateActivity` attribute is set to `true` on both the client and server, the ID of the `ProcessAction` activity in the server is identical to the ID in the propagated `ActivityId` message header.</span></span>  
  
 <span data-ttu-id="03a29-108">하지 않으면 `ActivityId` 헤더는 메시지에 (즉, `propagateActivity` = `false` 클라이언트), 또는 때 `propagateActivity` = `false` 서버에서 서버 생성 하는 새 활동 ID</span><span class="sxs-lookup"><span data-stu-id="03a29-108">When no `ActivityId` header is present in the message (that is, `propagateActivity`=`false` on the client), or when `propagateActivity`=`false` on the server, the server generates a new activity ID.</span></span>  
  
### <a name="client"></a><span data-ttu-id="03a29-109">클라이언트</span><span class="sxs-lookup"><span data-stu-id="03a29-109">Client</span></span>  
 <span data-ttu-id="03a29-110">클라이언트가 동기 단일 스레드인 경우 클라이언트는 클라이언트나 서버의 `propagateActivity` 설정을 모두 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="03a29-110">If the client is synchronously single threaded, the client disregards any settings of `propagateActivity` at the client or server.</span></span> <span data-ttu-id="03a29-111">대신 요청 동작에서 응답이 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="03a29-111">Instead, the response is handled in the request activity.</span></span> <span data-ttu-id="03a29-112">클라이언트가 비동기 또는 동기 경우 다중 스레드, `propagateActivity` = `true` 클라이언트에서 및 서버에서 보낸 메시지에 동작 ID 헤더는, 클라이언트는 메시지에서 동작 ID를 검색 한 전송는 전파 된 활동 ID를 포함 하는 프로세스 Action 동작</span><span class="sxs-lookup"><span data-stu-id="03a29-112">If the client is asynchronous or synchronous multithreaded, `propagateActivity`=`true` in the client, and there is an activity ID header in the message sent by the server, the client retrieves the activity ID from the message, and transfers to the Process Action activity that contains the propagated activity ID.</span></span> <span data-ttu-id="03a29-113">그렇지 않으면 클라이언트는 Process Message 동작에서 새 Process Action 동작으로 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="03a29-113">Otherwise, the client transfers from Process Message activity to a new Process Action activity.</span></span> <span data-ttu-id="03a29-114">새 Process Action 동작으로의 이 추가 전송은 일관성을 위해 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="03a29-114">This extra transfer to a new Process Action activity is done for consistency.</span></span> <span data-ttu-id="03a29-115">이 동작 내에서 클라이언트는 응답 메시지 처리를 위해 스레드가 할당될 때 로컬 스레드 컨텍스트에서 BeginCall 동작의 동작 ID를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="03a29-115">Inside this activity, the client retrieves the activity ID of the BeginCall activity from the local thread context, when the thread is allocated for response message processing.</span></span> <span data-ttu-id="03a29-116">그런 다음 초기 Process Action 동작으로 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="03a29-116">It then transfers to the initial Process Action activity.</span></span>  
  
 <span data-ttu-id="03a29-117">클라이언트가 이중이면 메시지를 수신할 때 클라이언트가 서버 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="03a29-117">If the client is duplex, the client acts as server on receiving the message.</span></span>  
  
### <a name="propagation-in-fault-messages"></a><span data-ttu-id="03a29-118">오류 메시지의 전파</span><span class="sxs-lookup"><span data-stu-id="03a29-118">Propagation in Fault Messages</span></span>  
 <span data-ttu-id="03a29-119">올바른 메시지와 오류 메시지의 처리에는 차이가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="03a29-119">There is no difference in handling valid and fault messages.</span></span> <span data-ttu-id="03a29-120">경우 `propagateActivity` = `true`, SOAP 오류 메시지 헤더에 추가 된 활동 ID가 앰비언트 동작과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="03a29-120">If `propagateActivity`=`true`, the activity ID added to the SOAP fault message headers is identical to the ambient activity.</span></span>  
  
## <a name="servicemodel-activity-tracing-is-disabled"></a><span data-ttu-id="03a29-121">ServiceModel 동작 추적 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="03a29-121">ServiceModel Activity Tracing is Disabled</span></span>  
 <span data-ttu-id="03a29-122">ServiceModel ActivityTracing을 사용하지 않으면 ServiceModel 동작을 거치지 않고 직접 사용자 코드 동작 간에 전파가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="03a29-122">If ServiceModel ActivityTracing is disabled, propagation occurs between user code activities directly without going through ServiceModel activities.</span></span> <span data-ttu-id="03a29-123">사용자 정의 동작 ID도 메시지 동작 ID 헤더를 통해 전파됩니다.</span><span class="sxs-lookup"><span data-stu-id="03a29-123">A user-defined activity ID is also propagated through the message activity ID header.</span></span>  
  
 <span data-ttu-id="03a29-124">경우 `propagateActivity` = `true` 및 `ActivityTracing` = `off` (에 관계 없이 여부 ServiceModel 추적을 활성화)는 ServiceModel 추적 수신기에 대 한 다음 클라이언트 또는 서버에서 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="03a29-124">If `propagateActivity`=`true` and `ActivityTracing`=`off` for a ServiceModel trace listener (regardless of whether tracing is enabled on ServiceModel), the following happen on either the client or server:</span></span>  
  
-   <span data-ttu-id="03a29-125">작업 요청 또는 응답 전송 시 메시지가 구성될 때까지 TLS의 동작 ID가 사용자 코드에서 전파됩니다.</span><span class="sxs-lookup"><span data-stu-id="03a29-125">On operation request or sending response, the activity ID in TLS is propagated out of user code until a message is formed.</span></span> <span data-ttu-id="03a29-126">메시지가 전송되기 전에 동작 ID 헤더도 메시지에 삽입됩니다.</span><span class="sxs-lookup"><span data-stu-id="03a29-126">An activity ID header is also inserted into the message before it is sent.</span></span>  
  
-   <span data-ttu-id="03a29-127">요청이나 응답을 받을 때 수신된 메시지 개체를 만드는 즉시 메시지 헤더에서 동작 ID가 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="03a29-127">On receiving request or receiving response, the activity ID is retrieved from the message header as soon as the received message object is created.</span></span> <span data-ttu-id="03a29-128">TLS의 동작 ID는 사용자 코드에 도달할 때까지 메시지가 범위에서 사라지는 즉시 전파됩니다.</span><span class="sxs-lookup"><span data-stu-id="03a29-128">The activity ID in TLS is propagated as soon as the message disappears from scope until user code is reached.</span></span>  
  
 <span data-ttu-id="03a29-129">이러한 작업은 전파가 설정된 경우 사용자 추적이 동일한 동작에 나타나도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="03a29-129">These actions guarantee that user traces will appear in the same activity if propagation is on.</span></span> <span data-ttu-id="03a29-130">그러나 ServiceModel 추적의 경우는 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="03a29-130">However, it makes no guarantee on ServiceModel traces.</span></span> <span data-ttu-id="03a29-131">ServiceModel 추적은 사용자 코드 동작이 설정된 스레드와 동일한 스레드에서 추적 처리가 실행되는 경우에만 사용자 코드 동작에서 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="03a29-131">ServiceModel traces occur in a user code activity only if the processing of those traces is executed on the same thread where the user code activity was set.</span></span>  
  
 <span data-ttu-id="03a29-132">일반적으로 ServiceModel 추적은 다음 위치에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03a29-132">In general, ServiceModel traces can be observed in the following places:</span></span>  
  
-   <span data-ttu-id="03a29-133">ServiceModel 추적을 사용하지 않으면 내보낸 모든 추적이 사용자 동작에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="03a29-133">If ServiceModel tracing is disabled, all emitted traces appear in user activities.</span></span> <span data-ttu-id="03a29-134">서버와 클라이언트에서 모두 전파를 사용하는 경우 이러한 추적이 동일한 동작에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03a29-134">If propagation is enabled at both the server and client, these traces will be in the same activity.</span></span>  
  
-   <span data-ttu-id="03a29-135">ServiceModel 추적을 사용하지만 ActivityTracing을 사용하지 않으면 양쪽에서 모두 전파를 사용하는 경우 사용자 추적이 동일한 동작에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="03a29-135">If ServiceModel tracing is enabled, but ActivityTracing is disabled, user traces appear in the same activity if propagation is enabled on both ends.</span></span> <span data-ttu-id="03a29-136">ServiceModel 추적은 동작이 처음에 설정된 사용자 코드 처리와 동일한 스레드에서 발생하지 않는 한 기본 0000 동작에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="03a29-136">ServiceModel traces appear in the default 0000 activity, unless they occur in the same thread as the user code processing where the activity is initially set.</span></span>  
  
-   <span data-ttu-id="03a29-137">ServiceModel 추적과 ActivityTracing을 모두 사용하면 사용자 추적이 사용자 정의 동작에 나타나고 ServiceModel 추적은 ServiceModel에서 정의된 동작에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="03a29-137">If both ServiceModel tracing and ActivityTracing are enabled, user traces appear in user-defined activities, and ServiceModel traces appear in ServiceModel-defined activities.</span></span> <span data-ttu-id="03a29-138">전파는 ServiceModel 수준에서 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="03a29-138">Propagation happens at ServiceModel level.</span></span>
