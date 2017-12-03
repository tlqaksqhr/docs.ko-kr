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
ms.openlocfilehash: 93632d6a178c0f58143fc148a0e1eb51be94ed17
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="channel-class"></a><span data-ttu-id="9f8ca-102">Channel 클래스</span><span class="sxs-lookup"><span data-stu-id="9f8ca-102">Channel class</span></span>
<span data-ttu-id="9f8ca-103">채널</span><span class="sxs-lookup"><span data-stu-id="9f8ca-103">Channel</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f8ca-104">구문</span><span class="sxs-lookup"><span data-stu-id="9f8ca-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="9f8ca-105">메서드</span><span class="sxs-lookup"><span data-stu-id="9f8ca-105">Methods</span></span>  
 <span data-ttu-id="9f8ca-106">Channel 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9f8ca-106">The Channel class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="9f8ca-107">속성</span><span class="sxs-lookup"><span data-stu-id="9f8ca-107">Properties</span></span>  
 <span data-ttu-id="9f8ca-108">Channel 클래스에는 다음 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f8ca-108">The Channel class has the following properties.</span></span>  
  
### <a name="localaddress"></a><span data-ttu-id="9f8ca-109">LocalAddress</span><span class="sxs-lookup"><span data-stu-id="9f8ca-109">LocalAddress</span></span>  
 <span data-ttu-id="9f8ca-110">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="9f8ca-110">Data type: string</span></span>  
  
 <span data-ttu-id="9f8ca-111">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="9f8ca-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9f8ca-112">채널에 대한 로컬 끝점입니다.</span><span class="sxs-lookup"><span data-stu-id="9f8ca-112">The local endpoint for the channel.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="9f8ca-113">ref</span><span class="sxs-lookup"><span data-stu-id="9f8ca-113">ref</span></span>  
 <span data-ttu-id="9f8ca-114">데이터 형식: Endpoint</span><span class="sxs-lookup"><span data-stu-id="9f8ca-114">Data type: Endpoint</span></span>  
  
 <span data-ttu-id="9f8ca-115">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="9f8ca-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9f8ca-116">채널이 연결되는 끝점에 대한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="9f8ca-116">A reference to the endpoint the channel connects to.</span></span>  
  
### <a name="remoteaddress"></a><span data-ttu-id="9f8ca-117">RemoteAddress</span><span class="sxs-lookup"><span data-stu-id="9f8ca-117">RemoteAddress</span></span>  
 <span data-ttu-id="9f8ca-118">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="9f8ca-118">Data type: string</span></span>  
  
 <span data-ttu-id="9f8ca-119">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="9f8ca-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9f8ca-120">채널과 연결된 원격 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="9f8ca-120">The remote address associated with the channel.</span></span>  
  
### <a name="sessionid"></a><span data-ttu-id="9f8ca-121">SessionId</span><span class="sxs-lookup"><span data-stu-id="9f8ca-121">SessionId</span></span>  
 <span data-ttu-id="9f8ca-122">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="9f8ca-122">Data type: string</span></span>  
  
 <span data-ttu-id="9f8ca-123">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="9f8ca-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9f8ca-124">현재 세션 ID(있는 경우)입니다.</span><span class="sxs-lookup"><span data-stu-id="9f8ca-124">The current session Id, if any.</span></span>  
  
### <a name="type"></a><span data-ttu-id="9f8ca-125">형식</span><span class="sxs-lookup"><span data-stu-id="9f8ca-125">Type</span></span>  
 <span data-ttu-id="9f8ca-126">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="9f8ca-126">Data type: string</span></span>  
  
 <span data-ttu-id="9f8ca-127">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="9f8ca-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9f8ca-128">채널 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="9f8ca-128">The type of the channel.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f8ca-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9f8ca-129">Requirements</span></span>  
  
|<span data-ttu-id="9f8ca-130">MOF</span><span class="sxs-lookup"><span data-stu-id="9f8ca-130">MOF</span></span>|<span data-ttu-id="9f8ca-131">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f8ca-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="9f8ca-132">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="9f8ca-132">Namespace</span></span>|<span data-ttu-id="9f8ca-133">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f8ca-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9f8ca-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9f8ca-134">See Also</span></span>  
 <xref:System.ServiceModel.Channels.ChannelBase>
