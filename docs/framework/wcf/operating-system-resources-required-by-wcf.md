---
title: "WCF에 필요한 운영 체제 리소스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cdd9a331-53fe-4e0d-bdfe-782264aec5c9
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 31006331f5e8a71bf3f4fb9a68c31cb32d0b6f2b
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="operating-system-resources-required-by-wcf"></a><span data-ttu-id="c33e6-102">WCF에 필요한 운영 체제 리소스</span><span class="sxs-lookup"><span data-stu-id="c33e6-102">Operating System Resources Required by WCF</span></span>
[!INCLUDE[indigo1](../../../includes/indigo1-md.md)]<span data-ttu-id="c33e6-103">는 운영 체제에서 제공하는 여러 리소스를 사용하여 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="c33e6-103"> depends on several resources that are provided by the operating system to function.</span></span> <span data-ttu-id="c33e6-104">다음 표에서는 이러한 리소스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c33e6-104">The following table lists those resources.</span></span>  
  
|<span data-ttu-id="c33e6-105">리소스</span><span class="sxs-lookup"><span data-stu-id="c33e6-105">Resource</span></span>|<span data-ttu-id="c33e6-106">설명</span><span class="sxs-lookup"><span data-stu-id="c33e6-106">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="c33e6-107">MSDTC(Microsoft Distributed Transaction Coordinator)</span><span class="sxs-lookup"><span data-stu-id="c33e6-107">Microsoft Distributed Transaction Coordinator (MSDTC)</span></span>|<span data-ttu-id="c33e6-108">OleTx 트랜잭션을 지원하는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c33e6-108">Required to support OleTx transactions.</span></span>|  
|<span data-ttu-id="c33e6-109">IIS(인터넷 정보 서비스)</span><span class="sxs-lookup"><span data-stu-id="c33e6-109">Internet Information Services (IIS)</span></span>|<span data-ttu-id="c33e6-110">IIS를 사용하여 응용 프로그램을 호스트하려는 경우에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c33e6-110">Required if you want to use IIS to host your application.</span></span>|  
|<span data-ttu-id="c33e6-111">WAS(Windows Process Activation Service)</span><span class="sxs-lookup"><span data-stu-id="c33e6-111">Windows Process Activation Service (WAS)</span></span>|<span data-ttu-id="c33e6-112">WAS를 사용하여 응용 프로그램을 호스트하려는 경우에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c33e6-112">Required if you want to use WAS to host your application.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c33e6-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c33e6-113">See Also</span></span>  
 [<span data-ttu-id="c33e6-114">시스템 요구 사항</span><span class="sxs-lookup"><span data-stu-id="c33e6-114">System Requirements</span></span>](../../../docs/framework/wcf/wcf-system-requirements.md)
