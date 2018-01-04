---
title: "GetAssemblyIdentityFromFile 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetAssemblyIdentityFromFile
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type: COM
f1_keywords: GetAssemblyIdentityFromFile
helpviewer_keywords: GetAssemblyIdentityFromFile function [.NET Framework fusion]
ms.assetid: 2c32da53-76c7-4048-84d0-d05207333004
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 56d7fb4ee74e40ecd29ee276665ff43ab9fd56be
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="getassemblyidentityfromfile-function"></a><span data-ttu-id="726ee-102">GetAssemblyIdentityFromFile 함수</span><span class="sxs-lookup"><span data-stu-id="726ee-102">GetAssemblyIdentityFromFile Function</span></span>
<span data-ttu-id="726ee-103">에 대 한 포인터를 가져옵니다는 `IUnknown` 개체와 지정한 `IID` 지정 된 파일 경로에 있는 어셈블리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="726ee-103">Gets a pointer to an `IUnknown` object with the specified `IID` in the assembly at the specified file path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="726ee-104">구문</span><span class="sxs-lookup"><span data-stu-id="726ee-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyIdentityFromFile (  
    [in]  LPCWSTR   pwzFilePath,  
    [in]  REFIID    riid,  
    [out] IUnknown  **ppIdentity  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="726ee-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="726ee-105">Parameters</span></span>  
 `pwzFilePath`  
 <span data-ttu-id="726ee-106">[in] 유효한 경로 요청된 된 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="726ee-106">[in] A valid path to the requested assembly.</span></span>  
  
 `riid`  
 <span data-ttu-id="726ee-107">[in] `IID` 반환할 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="726ee-107">[in] The `IID` of the interface to return.</span></span>  
  
 `ppIdentity`  
 <span data-ttu-id="726ee-108">[out] 반환 된 인터페이스 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="726ee-108">[out] The returned interface pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="726ee-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="726ee-109">Requirements</span></span>  
 <span data-ttu-id="726ee-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="726ee-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="726ee-111">**헤더:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="726ee-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="726ee-112">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="726ee-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="726ee-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="726ee-113">See Also</span></span>  
 <span data-ttu-id="726ee-114"><<!--zzxref:IUnknown --> `IUnknown`></span><span class="sxs-lookup"><span data-stu-id="726ee-114"><<!--zzxref:IUnknown --> `IUnknown`></span></span>  
 [<span data-ttu-id="726ee-115">Fusion 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="726ee-115">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
