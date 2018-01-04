---
title: OneWayBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5c7e17c3-39b9-4214-ae08-9e6141734305
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 47de8c2449c46b12b8d10ac2a5269a18d1454f41
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="onewaybindingelement"></a><span data-ttu-id="9d8f7-102">OneWayBindingElement</span><span class="sxs-lookup"><span data-stu-id="9d8f7-102">OneWayBindingElement</span></span>
<span data-ttu-id="9d8f7-103">OneWayBindingElement</span><span class="sxs-lookup"><span data-stu-id="9d8f7-103">OneWayBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d8f7-104">구문</span><span class="sxs-lookup"><span data-stu-id="9d8f7-104">Syntax</span></span>  
  
```  
class OneWayBindingElement : BindingElement  
{  
  ChannelPoolSettings ChannelPoolSettings;  
  sint32 MaxAcceptedChannels;  
  boolean PacketRoutable;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="9d8f7-105">메서드</span><span class="sxs-lookup"><span data-stu-id="9d8f7-105">Methods</span></span>  
 <span data-ttu-id="9d8f7-106">OneWayBindingElement 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9d8f7-106">The OneWayBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="9d8f7-107">속성</span><span class="sxs-lookup"><span data-stu-id="9d8f7-107">Properties</span></span>  
 <span data-ttu-id="9d8f7-108">OneWayBindingElement 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d8f7-108">The OneWayBindingElement class has the following properties:</span></span>  
  
### <a name="channelpoolsettings"></a><span data-ttu-id="9d8f7-109">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="9d8f7-109">ChannelPoolSettings</span></span>  
 <span data-ttu-id="9d8f7-110">데이터 형식: ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="9d8f7-110">Data type: ChannelPoolSettings</span></span>  
  
 <span data-ttu-id="9d8f7-111">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="9d8f7-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9d8f7-112">채널 풀 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="9d8f7-112">The channel pool settings.</span></span>  
  
### <a name="maxacceptedchannels"></a><span data-ttu-id="9d8f7-113">MaxAcceptedChannels</span><span class="sxs-lookup"><span data-stu-id="9d8f7-113">MaxAcceptedChannels</span></span>  
 <span data-ttu-id="9d8f7-114">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="9d8f7-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="9d8f7-115">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="9d8f7-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9d8f7-116">허용되는 최대 채널 수입니다.</span><span class="sxs-lookup"><span data-stu-id="9d8f7-116">The maximum number of accepted channels.</span></span>  
  
### <a name="packetroutable"></a><span data-ttu-id="9d8f7-117">PacketRoutable</span><span class="sxs-lookup"><span data-stu-id="9d8f7-117">PacketRoutable</span></span>  
 <span data-ttu-id="9d8f7-118">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="9d8f7-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="9d8f7-119">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="9d8f7-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9d8f7-120">패킷을 라우팅할 수 있는지 여부를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9d8f7-120">A value that indicates whether the packet is routable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d8f7-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9d8f7-121">Requirements</span></span>  
  
|<span data-ttu-id="9d8f7-122">MOF</span><span class="sxs-lookup"><span data-stu-id="9d8f7-122">MOF</span></span>|<span data-ttu-id="9d8f7-123">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d8f7-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="9d8f7-124">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="9d8f7-124">Namespace</span></span>|<span data-ttu-id="9d8f7-125">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d8f7-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9d8f7-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9d8f7-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.OneWayBindingElement>
