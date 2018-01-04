---
title: ChannelPoolSettings
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d3f475bd-f780-4bbe-b291-339387322964
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3995b517b27a5565f7fcb9c11da27c9e1bb40887
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="channelpoolsettings"></a><span data-ttu-id="8b446-102">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="8b446-102">ChannelPoolSettings</span></span>
<span data-ttu-id="8b446-103">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="8b446-103">ChannelPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b446-104">구문</span><span class="sxs-lookup"><span data-stu-id="8b446-104">Syntax</span></span>  
  
```  
class ChannelPoolSettings  
{  
  datetime IdleTimeout;  
  datetime LeaseTimeout;  
  sint32 MaxOutboundChannelsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="8b446-105">메서드</span><span class="sxs-lookup"><span data-stu-id="8b446-105">Methods</span></span>  
 <span data-ttu-id="8b446-106">ChannelPoolSettings 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8b446-106">The ChannelPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="8b446-107">속성</span><span class="sxs-lookup"><span data-stu-id="8b446-107">Properties</span></span>  
 <span data-ttu-id="8b446-108">ChannelPoolSettings 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b446-108">The ChannelPoolSettings class has the following properties:</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="8b446-109">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="8b446-109">IdleTimeout</span></span>  
 <span data-ttu-id="8b446-110">데이터 형식: datetime</span><span class="sxs-lookup"><span data-stu-id="8b446-110">Data type: datetime</span></span>  
  
 <span data-ttu-id="8b446-111">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="8b446-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8b446-112">연결이 끊어지기 전에 유휴 상태일 수 있는 최대 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="8b446-112">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="leasetimeout"></a><span data-ttu-id="8b446-113">LeaseTimeout</span><span class="sxs-lookup"><span data-stu-id="8b446-113">LeaseTimeout</span></span>  
 <span data-ttu-id="8b446-114">데이터 형식: datetime</span><span class="sxs-lookup"><span data-stu-id="8b446-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="8b446-115">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="8b446-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8b446-116">시간 제한을 초과하기 전에 대여 작업을 완료하기 위한 최대 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="8b446-116">The maximum time for a lease operation to complete before timing out.</span></span>  
  
### <a name="maxoutboundchannelsperendpoint"></a><span data-ttu-id="8b446-117">MaxOutboundChannelsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="8b446-117">MaxOutboundChannelsPerEndpoint</span></span>  
 <span data-ttu-id="8b446-118">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="8b446-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="8b446-119">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="8b446-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="8b446-120">각 끝점에 대한 최대 아웃바운드 채널 수입니다.</span><span class="sxs-lookup"><span data-stu-id="8b446-120">The maximum number of outbound channels for each endpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b446-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8b446-121">Requirements</span></span>  
  
|<span data-ttu-id="8b446-122">MOF</span><span class="sxs-lookup"><span data-stu-id="8b446-122">MOF</span></span>|<span data-ttu-id="8b446-123">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b446-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="8b446-124">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="8b446-124">Namespace</span></span>|<span data-ttu-id="8b446-125">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b446-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8b446-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8b446-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.ChannelPoolSettings>
