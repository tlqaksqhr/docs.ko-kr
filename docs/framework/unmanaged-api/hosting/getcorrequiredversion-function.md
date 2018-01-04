---
title: "GetCORRequiredVersion 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetCORRequiredVersion
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: GetCORRequiredVersion
helpviewer_keywords: GetCORRequiredVersion function [.NET Framework hosting]
ms.assetid: 1588fe7b-c378-4f4b-9c4b-48647f1119cc
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 65505243d7d1691f0458d614fd878b054916f113
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="getcorrequiredversion-function"></a><span data-ttu-id="bfbdf-102">GetCORRequiredVersion 함수</span><span class="sxs-lookup"><span data-stu-id="bfbdf-102">GetCORRequiredVersion Function</span></span>
<span data-ttu-id="bfbdf-103">필요한 공용 언어 런타임 (CLR) 버전 번호를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="bfbdf-103">Gets the required common language runtime (CLR) version number.</span></span>  
  
 <span data-ttu-id="bfbdf-104">이 함수에 더 이상 사용 되지는 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="bfbdf-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfbdf-105">구문</span><span class="sxs-lookup"><span data-stu-id="bfbdf-105">Syntax</span></span>  
  
```  
HRESULT GetCORRequiredVersion (  
    [out] LPWSTR   pbuffer,  
    [in]  DWORD    cchBuffer,  
    [out] DWORD   *dwLength  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bfbdf-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bfbdf-106">Parameters</span></span>  
 `pbuffer`  
 <span data-ttu-id="bfbdf-107">[out] 버전 번호를 지정 하는 문자열을 포함 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="bfbdf-107">[out] A buffer containing a string that specifies the version number.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="bfbdf-108">[in] 버퍼의 바이트 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="bfbdf-108">[in] The size, in bytes, of the buffer.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="bfbdf-109">[out] 버퍼에 반환 된 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="bfbdf-109">[out] The number of bytes returned in the buffer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bfbdf-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bfbdf-110">Requirements</span></span>  
 <span data-ttu-id="bfbdf-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bfbdf-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bfbdf-112">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="bfbdf-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bfbdf-113">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bfbdf-113">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bfbdf-114">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bfbdf-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfbdf-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bfbdf-115">See Also</span></span>  
 [<span data-ttu-id="bfbdf-116">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="bfbdf-116">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
