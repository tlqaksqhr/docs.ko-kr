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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 0a56616e97526b2d410d18d97dc1391c6fc32cc3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="channelpoolsettings"></a><span data-ttu-id="9fbf1-102">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="9fbf1-102">ChannelPoolSettings</span></span>
<span data-ttu-id="9fbf1-103">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="9fbf1-103">ChannelPoolSettings</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9fbf1-104">구문</span><span class="sxs-lookup"><span data-stu-id="9fbf1-104">Syntax</span></span>  
  
```  
class ChannelPoolSettings  
{  
  datetime IdleTimeout;  
  datetime LeaseTimeout;  
  sint32 MaxOutboundChannelsPerEndpoint;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="9fbf1-105">메서드</span><span class="sxs-lookup"><span data-stu-id="9fbf1-105">Methods</span></span>  
 <span data-ttu-id="9fbf1-106">ChannelPoolSettings 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9fbf1-106">The ChannelPoolSettings class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="9fbf1-107">속성</span><span class="sxs-lookup"><span data-stu-id="9fbf1-107">Properties</span></span>  
 <span data-ttu-id="9fbf1-108">ChannelPoolSettings 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fbf1-108">The ChannelPoolSettings class has the following properties:</span></span>  
  
### <a name="idletimeout"></a><span data-ttu-id="9fbf1-109">IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="9fbf1-109">IdleTimeout</span></span>  
 <span data-ttu-id="9fbf1-110">데이터 형식: datetime</span><span class="sxs-lookup"><span data-stu-id="9fbf1-110">Data type: datetime</span></span>  
  
 <span data-ttu-id="9fbf1-111">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="9fbf1-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9fbf1-112">연결이 끊어지기 전에 유휴 상태일 수 있는 최대 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="9fbf1-112">The maximum time the connection can be idle before being disconnected.</span></span>  
  
### <a name="leasetimeout"></a><span data-ttu-id="9fbf1-113">LeaseTimeout</span><span class="sxs-lookup"><span data-stu-id="9fbf1-113">LeaseTimeout</span></span>  
 <span data-ttu-id="9fbf1-114">데이터 형식: datetime</span><span class="sxs-lookup"><span data-stu-id="9fbf1-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="9fbf1-115">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="9fbf1-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9fbf1-116">시간 제한을 초과하기 전에 대여 작업을 완료하기 위한 최대 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="9fbf1-116">The maximum time for a lease operation to complete before timing out.</span></span>  
  
### <a name="maxoutboundchannelsperendpoint"></a><span data-ttu-id="9fbf1-117">MaxOutboundChannelsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="9fbf1-117">MaxOutboundChannelsPerEndpoint</span></span>  
 <span data-ttu-id="9fbf1-118">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="9fbf1-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="9fbf1-119">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="9fbf1-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9fbf1-120">각 끝점에 대한 최대 아웃바운드 채널 수입니다.</span><span class="sxs-lookup"><span data-stu-id="9fbf1-120">The maximum number of outbound channels for each endpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9fbf1-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9fbf1-121">Requirements</span></span>  
  
|<span data-ttu-id="9fbf1-122">MOF</span><span class="sxs-lookup"><span data-stu-id="9fbf1-122">MOF</span></span>|<span data-ttu-id="9fbf1-123">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fbf1-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="9fbf1-124">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="9fbf1-124">Namespace</span></span>|<span data-ttu-id="9fbf1-125">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fbf1-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9fbf1-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9fbf1-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.ChannelPoolSettings>
