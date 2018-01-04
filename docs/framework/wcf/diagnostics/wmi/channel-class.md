---
title: "Channel 클래스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d9fae2ca-209c-4341-a0f5-6b79d1a67776
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 073f0a2a2731a08acd914a7dd85cb2b419d98128
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="channel-class"></a><span data-ttu-id="c9ce8-102">Channel 클래스</span><span class="sxs-lookup"><span data-stu-id="c9ce8-102">Channel class</span></span>
<span data-ttu-id="c9ce8-103">채널</span><span class="sxs-lookup"><span data-stu-id="c9ce8-103">Channel</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9ce8-104">구문</span><span class="sxs-lookup"><span data-stu-id="c9ce8-104">Syntax</span></span>  
  
```  
class Channel  
{  
  string LocalAddress;  
  Endpoint ref;  
  string RemoteAddress;  
  string SessionId;  
  string Type;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="c9ce8-105">메서드</span><span class="sxs-lookup"><span data-stu-id="c9ce8-105">Methods</span></span>  
 <span data-ttu-id="c9ce8-106">Channel 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c9ce8-106">The Channel class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="c9ce8-107">속성</span><span class="sxs-lookup"><span data-stu-id="c9ce8-107">Properties</span></span>  
 <span data-ttu-id="c9ce8-108">Channel 클래스에는 다음 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9ce8-108">The Channel class has the following properties.</span></span>  
  
### <a name="localaddress"></a><span data-ttu-id="c9ce8-109">LocalAddress</span><span class="sxs-lookup"><span data-stu-id="c9ce8-109">LocalAddress</span></span>  
 <span data-ttu-id="c9ce8-110">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="c9ce8-110">Data type: string</span></span>  
  
 <span data-ttu-id="c9ce8-111">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="c9ce8-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c9ce8-112">채널에 대한 로컬 끝점입니다.</span><span class="sxs-lookup"><span data-stu-id="c9ce8-112">The local endpoint for the channel.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="c9ce8-113">ref</span><span class="sxs-lookup"><span data-stu-id="c9ce8-113">ref</span></span>  
 <span data-ttu-id="c9ce8-114">데이터 형식: Endpoint</span><span class="sxs-lookup"><span data-stu-id="c9ce8-114">Data type: Endpoint</span></span>  
  
 <span data-ttu-id="c9ce8-115">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="c9ce8-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c9ce8-116">채널이 연결되는 끝점에 대한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="c9ce8-116">A reference to the endpoint the channel connects to.</span></span>  
  
### <a name="remoteaddress"></a><span data-ttu-id="c9ce8-117">RemoteAddress</span><span class="sxs-lookup"><span data-stu-id="c9ce8-117">RemoteAddress</span></span>  
 <span data-ttu-id="c9ce8-118">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="c9ce8-118">Data type: string</span></span>  
  
 <span data-ttu-id="c9ce8-119">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="c9ce8-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c9ce8-120">채널과 연결된 원격 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="c9ce8-120">The remote address associated with the channel.</span></span>  
  
### <a name="sessionid"></a><span data-ttu-id="c9ce8-121">SessionId</span><span class="sxs-lookup"><span data-stu-id="c9ce8-121">SessionId</span></span>  
 <span data-ttu-id="c9ce8-122">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="c9ce8-122">Data type: string</span></span>  
  
 <span data-ttu-id="c9ce8-123">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="c9ce8-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c9ce8-124">현재 세션 ID(있는 경우)입니다.</span><span class="sxs-lookup"><span data-stu-id="c9ce8-124">The current session Id, if any.</span></span>  
  
### <a name="type"></a><span data-ttu-id="c9ce8-125">형식</span><span class="sxs-lookup"><span data-stu-id="c9ce8-125">Type</span></span>  
 <span data-ttu-id="c9ce8-126">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="c9ce8-126">Data type: string</span></span>  
  
 <span data-ttu-id="c9ce8-127">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="c9ce8-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c9ce8-128">채널 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="c9ce8-128">The type of the channel.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9ce8-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c9ce8-129">Requirements</span></span>  
  
|<span data-ttu-id="c9ce8-130">MOF</span><span class="sxs-lookup"><span data-stu-id="c9ce8-130">MOF</span></span>|<span data-ttu-id="c9ce8-131">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9ce8-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="c9ce8-132">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="c9ce8-132">Namespace</span></span>|<span data-ttu-id="c9ce8-133">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9ce8-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c9ce8-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c9ce8-134">See Also</span></span>  
 <xref:System.ServiceModel.Channels.ChannelBase>
