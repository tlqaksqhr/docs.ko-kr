---
title: "AXL_AUTHENTICODE_TIMESTAMPER_INFO 구조"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 89e41a81-0f41-45ad-8f20-a120e4ff24fb
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 46c0646cfff79888db2b6b37184dd97da21e71e3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="axlauthenticodetimestamperinfo-structure"></a><span data-ttu-id="0fab5-102">AXL_AUTHENTICODE_TIMESTAMPER_INFO 구조</span><span class="sxs-lookup"><span data-stu-id="0fab5-102">AXL_AUTHENTICODE_TIMESTAMPER_INFO Structure</span></span>
<span data-ttu-id="0fab5-103">Authenticode 타임스탬퍼 정보를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0fab5-103">Defines the Authenticode time stamper information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0fab5-104">구문</span><span class="sxs-lookup"><span data-stu-id="0fab5-104">Syntax</span></span>  
  
```  
typedef struct _AXL_AUTHENTICODE_SIGNER_INFO {  
    DWORD cbSize;  
    HRESULT dwError;  
    ALG_ID algHash;  
    FILETIME ftTimestamp  
    PCCERT_CHAIN_CONTEXT pChainContext;  
} AXL_AUTHENTICODE_TIMESTAMPER_INFO, * PAXL_AUTHENTICODE_TIMESTAMPER_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="0fab5-105">멤버</span><span class="sxs-lookup"><span data-stu-id="0fab5-105">Members</span></span>  
  
|<span data-ttu-id="0fab5-106">멤버</span><span class="sxs-lookup"><span data-stu-id="0fab5-106">Member</span></span>|<span data-ttu-id="0fab5-107">설명</span><span class="sxs-lookup"><span data-stu-id="0fab5-107">Description</span></span>|  
|------------|-----------------|  
|`cbSize`|<span data-ttu-id="0fab5-108">이 구조체의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="0fab5-108">The size of this structure.</span></span>|  
|`dwError`|<span data-ttu-id="0fab5-109">오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="0fab5-109">The error code.</span></span>|  
|`algHash`|<span data-ttu-id="0fab5-110">해시 알고리즘입니다.</span><span class="sxs-lookup"><span data-stu-id="0fab5-110">The hash algorithm.</span></span>|  
|`ftTimestamp`|<span data-ttu-id="0fab5-111">타임스탬프의 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="0fab5-111">The time of the time stamp.</span></span>|  
|`pChainContext`|<span data-ttu-id="0fab5-112">타임스탬퍼의 체인 컨텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="0fab5-112">The time stamper’s chain context.</span></span>  <span data-ttu-id="0fab5-113">참조는 [CERT_CONTEXT](http://msdn.microsoft.com/library/windows/desktop/aa377189.aspx) 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="0fab5-113">See the [CERT_CONTEXT](http://msdn.microsoft.com/library/windows/desktop/aa377189.aspx) structure.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0fab5-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0fab5-114">See Also</span></span>  
 [<span data-ttu-id="0fab5-115">Authenticode</span><span class="sxs-lookup"><span data-stu-id="0fab5-115">Authenticode</span></span>](../../../../docs/framework/unmanaged-api/authenticode/index.md)
