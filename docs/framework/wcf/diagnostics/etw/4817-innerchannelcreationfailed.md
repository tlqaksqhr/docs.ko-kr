---
title: 4817 - InnerChannelCreationFailed
ms.date: 03/30/2017
ms.assetid: c1a20619-beda-49b9-bb64-76b6a009c32b
ms.openlocfilehash: e9c99281e6abe27a8e59583102a712c9fa5a3854
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33469572"
---
# <a name="4817---innerchannelcreationfailed"></a><span data-ttu-id="56790-102">4817 - InnerChannelCreationFailed</span><span class="sxs-lookup"><span data-stu-id="56790-102">4817 - InnerChannelCreationFailed</span></span>
## <a name="properties"></a><span data-ttu-id="56790-103">속성</span><span class="sxs-lookup"><span data-stu-id="56790-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="56790-104">ID</span><span class="sxs-lookup"><span data-stu-id="56790-104">ID</span></span>|<span data-ttu-id="56790-105">4817</span><span class="sxs-lookup"><span data-stu-id="56790-105">4817</span></span>|  
|<span data-ttu-id="56790-106">키워드</span><span class="sxs-lookup"><span data-stu-id="56790-106">Keywords</span></span>|<span data-ttu-id="56790-107">검색</span><span class="sxs-lookup"><span data-stu-id="56790-107">Discovery</span></span>|  
|<span data-ttu-id="56790-108">수준</span><span class="sxs-lookup"><span data-stu-id="56790-108">Level</span></span>|<span data-ttu-id="56790-109">경고</span><span class="sxs-lookup"><span data-stu-id="56790-109">Warning</span></span>|  
|<span data-ttu-id="56790-110">채널</span><span class="sxs-lookup"><span data-stu-id="56790-110">Channel</span></span>|<span data-ttu-id="56790-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="56790-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="56790-112">설명</span><span class="sxs-lookup"><span data-stu-id="56790-112">Description</span></span>  
 <span data-ttu-id="56790-113">이 이벤트는 DiscoveryClientChannel이 검색된 끝점으로 채널을 만들지 못할 경우 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="56790-113">This event is emitted when the DiscoveryClientChannel failed to create the channel with a discovered endpoint.</span></span> <span data-ttu-id="56790-114">DiscoveryClientChannel은 이제 사용 가능한 다음 끝점으로 검색된 끝점을 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="56790-114">The DiscoveryClientChannel will now attempt to use the next available discovered endpoint.</span></span>  
  
## <a name="message"></a><span data-ttu-id="56790-115">메시지</span><span class="sxs-lookup"><span data-stu-id="56790-115">Message</span></span>  
 <span data-ttu-id="56790-116">DiscoveryClientChannel에서 EndpointAddress='%1' 및 Via='%2'을(를) 사용하는 검색된 끝점으로 채널을 만들지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="56790-116">The DiscoveryClientChannel failed to create the channel with a discovered endpoint with EndpointAddress='%1' and Via='%2'.</span></span> <span data-ttu-id="56790-117">DiscoveryClientChannel은 이제 사용 가능한 다음 끝점으로 검색된 끝점을 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="56790-117">The DiscoveryClientChannel will now attempt to use the next available discovered endpoint.</span></span>  
  
## <a name="details"></a><span data-ttu-id="56790-118">설명</span><span class="sxs-lookup"><span data-stu-id="56790-118">Details</span></span>
