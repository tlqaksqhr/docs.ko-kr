---
title: "ICLRRuntimeInfo::LoadLibrary 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeInfo.LoadLibrary
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeInfo::LoadLibrary
helpviewer_keywords:
- ICLRRuntimeInfo::LoadLibrary method [.NET Framework hosting]
- LoadLibrary method [.NET Framework hosting]
ms.assetid: 4517ada3-4417-4ac5-a150-73da7a87c686
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8b688a4f2557c5ab2ef112e13b411e25ad47b8c3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrruntimeinfoloadlibrary-method"></a><span data-ttu-id="ed12a-102">ICLRRuntimeInfo::LoadLibrary 메서드</span><span class="sxs-lookup"><span data-stu-id="ed12a-102">ICLRRuntimeInfo::LoadLibrary Method</span></span>
<span data-ttu-id="ed12a-103">가 나타내는 공용 언어 런타임 (CLR)에서.NET Framework 라이브러리를 로드 한 [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="ed12a-103">Loads a .NET Framework library from the common language runtime (CLR) represented by an [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface.</span></span>  
  
 <span data-ttu-id="ed12a-104">이 메서드를 대체는 [LoadLibraryShim](../../../../docs/framework/unmanaged-api/hosting/loadlibraryshim-function.md) 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="ed12a-104">This method supersedes the [LoadLibraryShim](../../../../docs/framework/unmanaged-api/hosting/loadlibraryshim-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed12a-105">구문</span><span class="sxs-lookup"><span data-stu-id="ed12a-105">Syntax</span></span>  
  
```  
HRESULT LoadLibrary(  
     [in]  LPCWSTR pwzDllName,  
     [out, retval] HMODULE *phndModule);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ed12a-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ed12a-106">Parameters</span></span>  
 `pwzDllName`  
 <span data-ttu-id="ed12a-107">[in] 로드할된 어셈블리의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ed12a-107">[in] The name of the assembly to be loaded.</span></span>  
  
 `phndModule`  
 <span data-ttu-id="ed12a-108">[out] 로드 된 어셈블리에 대 한 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="ed12a-108">[out] A handle to the loaded assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ed12a-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="ed12a-109">Return Value</span></span>  
 <span data-ttu-id="ed12a-110">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ed12a-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="ed12a-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ed12a-111">HRESULT</span></span>|<span data-ttu-id="ed12a-112">설명</span><span class="sxs-lookup"><span data-stu-id="ed12a-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ed12a-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="ed12a-113">S_OK</span></span>|<span data-ttu-id="ed12a-114">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ed12a-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="ed12a-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="ed12a-115">E_POINTER</span></span>|<span data-ttu-id="ed12a-116">`pwzDllName` 또는 `phndModule`이 null입니다.</span><span class="sxs-lookup"><span data-stu-id="ed12a-116">`pwzDllName` or `phndModule` is null.</span></span>|  
|<span data-ttu-id="ed12a-117">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="ed12a-117">E_OUTOFMEMORY</span></span>|<span data-ttu-id="ed12a-118">요청을 처리할 메모리가 부족 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed12a-118">Not enough memory is available to handle the request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ed12a-119">설명</span><span class="sxs-lookup"><span data-stu-id="ed12a-119">Remarks</span></span>  
 <span data-ttu-id="ed12a-120">이 메서드는.NET Framework 재배포 가능 패키지에 포함 된 Dll을 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed12a-120">This method only loads DLLs included in the .NET Framework redistributable package.</span></span> <span data-ttu-id="ed12a-121">사용자가 생성 한 어셈블리를 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed12a-121">It can not load user-generated assemblies.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed12a-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ed12a-122">Requirements</span></span>  
 <span data-ttu-id="ed12a-123">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ed12a-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed12a-124">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="ed12a-124">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="ed12a-125">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="ed12a-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ed12a-126">**.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed12a-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed12a-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ed12a-127">See Also</span></span>  
 [<span data-ttu-id="ed12a-128">ICLRRuntimeInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ed12a-128">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [<span data-ttu-id="ed12a-129">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ed12a-129">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="ed12a-130">호스팅</span><span class="sxs-lookup"><span data-stu-id="ed12a-130">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
