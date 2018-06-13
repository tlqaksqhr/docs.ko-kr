---
title: NukeDownloadedCache 함수
ms.date: 03/30/2017
api_name:
- NukeDownloadedCache
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- NukeDownloadedCache
helpviewer_keywords:
- NukeDownloadedCache function [.NET Framework fusion]
ms.assetid: fac2b1c6-6fa3-4818-805b-b63972024c86
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f0436991512713c05e60a3c10d6fbdaa17bb378c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429829"
---
# <a name="nukedownloadedcache-function"></a><span data-ttu-id="ce0b2-102">NukeDownloadedCache 함수</span><span class="sxs-lookup"><span data-stu-id="ce0b2-102">NukeDownloadedCache Function</span></span>
<span data-ttu-id="ce0b2-103">공용 언어 런타임 (CLR) 다운로드 캐시를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="ce0b2-103">Deletes the common language runtime (CLR) download cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce0b2-104">구문</span><span class="sxs-lookup"><span data-stu-id="ce0b2-104">Syntax</span></span>  
  
```  
HRESULT NukeDownloadedCache();  
```  
  
## <a name="return-value"></a><span data-ttu-id="ce0b2-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="ce0b2-105">Return Value</span></span>  
 <span data-ttu-id="ce0b2-106">이 메서드는 WinError.h에 정의 된 대로 표준 COM 오류 코드를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce0b2-106">This method returns standard COM error codes, as defined in WinError.h.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ce0b2-107">설명</span><span class="sxs-lookup"><span data-stu-id="ce0b2-107">Remarks</span></span>  
 <span data-ttu-id="ce0b2-108">CLR 다운로드 캐시는 다시 사용할 수 있도록 URL에서 다운로드 하는 강력한 이름의 어셈블리를 저장 하는 영역입니다.</span><span class="sxs-lookup"><span data-stu-id="ce0b2-108">The CLR download cache is the area where strong-named assemblies that are downloaded from a URL are stored for possible reuse.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce0b2-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ce0b2-109">Requirements</span></span>  
 <span data-ttu-id="ce0b2-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ce0b2-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce0b2-111">**헤더:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="ce0b2-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="ce0b2-112">**라이브러리:** Fusion.dll 및 Mscorwks.dll 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce0b2-112">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="ce0b2-113">올바른 버전의.NET Framework를 대상 하는 데 Mscorwks.dll 대신 Fusion.dll를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce0b2-113">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="ce0b2-114">**.NET framework 버전:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce0b2-114">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce0b2-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ce0b2-115">See Also</span></span>  
 [<span data-ttu-id="ce0b2-116">CreateHistoryReader 함수</span><span class="sxs-lookup"><span data-stu-id="ce0b2-116">CreateHistoryReader Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/createhistoryreader-function.md)  
 [<span data-ttu-id="ce0b2-117">GetHistoryFileDirectory 함수</span><span class="sxs-lookup"><span data-stu-id="ce0b2-117">GetHistoryFileDirectory Function</span></span>](../../../../docs/framework/unmanaged-api/fusion/gethistoryfiledirectory-function.md)  
 [<span data-ttu-id="ce0b2-118">Fusion 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="ce0b2-118">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
