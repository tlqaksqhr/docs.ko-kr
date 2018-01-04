---
title: "CoEEShutDownCOM 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CoEEShutDownCOM
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type: DLLExport
f1_keywords: CoEEShutDownCOM
helpviewer_keywords: CoEEShutDownCOM function [.NET Framework hosting]
ms.assetid: b634cae2-632f-4737-9be4-92d0652844d7
topic_type: apiref
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0ae339310c2bfd186cae798ff603d69735abeefd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="coeeshutdowncom-function"></a><span data-ttu-id="0c6f4-102">CoEEShutDownCOM 함수</span><span class="sxs-lookup"><span data-stu-id="0c6f4-102">CoEEShutDownCOM Function</span></span>
<span data-ttu-id="0c6f4-103">공용 언어 런타임 (CLR) 내부 런타임 호출 가능 래퍼 RCW ()를 보유 하는 모든 인터페이스 포인터를 해제 하기 위해를 강제로 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c6f4-103">Forces the common language runtime (CLR) to release all interface pointers it holds inside runtime callable wrappers (RCW).</span></span> <span data-ttu-id="0c6f4-104">모든 RCW 캐시 해제 것과 효과가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c6f4-104">This has the effect of releasing all RCW caches.</span></span> <span data-ttu-id="0c6f4-105">이 전역 함수에서 사용 되지 않는 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="0c6f4-105">This global function is deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="0c6f4-106">대신, 특정 런타임에 대 한 진입점을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c6f4-106">Instead, use the entry point for a specific runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c6f4-107">구문</span><span class="sxs-lookup"><span data-stu-id="0c6f4-107">Syntax</span></span>  
  
```  
void CoEEShutDownCOM ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="0c6f4-108">설명</span><span class="sxs-lookup"><span data-stu-id="0c6f4-108">Remarks</span></span>  
 <span data-ttu-id="0c6f4-109">`CoEEShutDownCOM` 함수 먼저 모든 컨텍스트 및 모든 캐시에서 모든 Rcw를 해제 한 다음 설치 프로그램에 있는 모든 중지 알림을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c6f4-109">The `CoEEShutDownCOM` function first releases all the RCWs in all contexts and in all caches, and then removes any tear-down notification existing in setup.</span></span> <span data-ttu-id="0c6f4-110">DLL 언로드 없습니다 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="0c6f4-110">No DLL unloading occurs.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="0c6f4-111">이 함수에는 프로세스에 로드 되는 모든 런타임에 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c6f4-111">This function affects all runtimes that are loaded into the process.</span></span>  
  
 <span data-ttu-id="0c6f4-112">부터는 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)], 원하는 특정 런타임에 대해이 함수에 대 한 진입점을 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c6f4-112">Beginning with the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)], call the entry point for this function on the specific runtime you want to affect.</span></span> <span data-ttu-id="0c6f4-113">진입점을 가져오려면 호출는 [iclrruntimeinfo:: Getprocaddress](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getprocaddress-method.md) 메서드 "CoEEShutDownCOM"를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c6f4-113">To get the entry point, call the [ICLRRuntimeInfo::GetProcAddress](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getprocaddress-method.md) method and specify "CoEEShutDownCOM".</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c6f4-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0c6f4-114">Requirements</span></span>  
 <span data-ttu-id="0c6f4-115">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0c6f4-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c6f4-116">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0c6f4-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0c6f4-117">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="0c6f4-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0c6f4-118">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c6f4-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c6f4-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0c6f4-119">See Also</span></span>  
 [<span data-ttu-id="0c6f4-120">메타데이터 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="0c6f4-120">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
