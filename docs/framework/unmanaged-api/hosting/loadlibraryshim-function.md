---
title: "LoadLibraryShim 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: LoadLibraryShim
api_location:
- mscoree.dll
- mscoreei.dll
api_type: DLLExport
f1_keywords: LoadLibraryShim
helpviewer_keywords: LoadLibraryShim function [.NET Framework hosting]
ms.assetid: 30931874-4d0e-4df1-b3d1-e425b50655d1
topic_type: apiref
caps.latest.revision: "20"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c56f5a3576c505fd7b7d514e3f2d038e7f8f3ecc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="loadlibraryshim-function"></a><span data-ttu-id="4cb43-102">LoadLibraryShim 함수</span><span class="sxs-lookup"><span data-stu-id="4cb43-102">LoadLibraryShim Function</span></span>
<span data-ttu-id="4cb43-103">지정 된 버전의.NET Framework 재배포 가능 패키지에 포함 된 DLL 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cb43-103">Loads a specified version of a DLL that is included in the .NET Framework redistributable package.</span></span>  
  
 <span data-ttu-id="4cb43-104">이 함수에 더 이상 사용 되지는 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="4cb43-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="4cb43-105">사용 하 여 [iclrruntimeinfo:: Loadlibrary](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-loadlibrary-method.md) 메서드 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cb43-105">Use the [ICLRRuntimeInfo::LoadLibrary](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-loadlibrary-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4cb43-106">구문</span><span class="sxs-lookup"><span data-stu-id="4cb43-106">Syntax</span></span>  
  
```  
HRESULT LoadLibraryShim (  
    [in]  LPCWSTR  szDllName,  
    [in]  LPCWSTR  szVersion,  
          LPVOID   pvReserved,  
    [out] HMODULE *phModDll  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4cb43-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4cb43-107">Parameters</span></span>  
 `szDllName`  
 <span data-ttu-id="4cb43-108">[in] .NET Framework 라이브러리를 로드할 수 있는 DLL의 이름을 나타내는 0으로 끝나는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="4cb43-108">[in] A zero-terminated string that represents the name of the DLL to be loaded from the .NET Framework library.</span></span>  
  
 `szVersion`  
 <span data-ttu-id="4cb43-109">[in] DLL 로드의 버전을 나타내는 0으로 끝나는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="4cb43-109">[in] A zero-terminated string that represents the version of the DLL to be loaded.</span></span> <span data-ttu-id="4cb43-110">경우 `szVersion` 가 null 이면 로드를 버전 4 보다 작은 지정된 된 DLL의 최신 버전에 대해 선택한 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="4cb43-110">If `szVersion` is null, the version selected for loading is the latest version of the specified DLL that is less than version 4.</span></span> <span data-ttu-id="4cb43-111">즉, 버전 4 보다 크거나 같은 모든 버전 경우 무시 됩니다 `szVersion` 매개 변수가 null 이면 및 없는 버전 보다 작은 버전 4가 설치 되어 DLL 로드 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4cb43-111">That is, all versions equal to or greater than version 4 are ignored if `szVersion` is null, and if no version less than version 4 is installed, the DLL fails to load.</span></span> <span data-ttu-id="4cb43-112">이의 설치 프로그램을 확인 하기는 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] 기존 응용 프로그램 또는 구성 요소에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4cb43-112">This is to ensure that installation of the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] does not affect pre-existing applications or components.</span></span> <span data-ttu-id="4cb43-113">항목을 참조 [In-proc SxS 및 마이그레이션 빠른 시작](http://go.microsoft.com/fwlink/?LinkId=200329) CLR 팀 블로그에서.</span><span class="sxs-lookup"><span data-stu-id="4cb43-113">See the entry [In-Proc SxS and Migration Quick Start](http://go.microsoft.com/fwlink/?LinkId=200329) in the CLR team blog.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="4cb43-114">나중에 사용하기 위해 예약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cb43-114">Reserved for future use.</span></span>  
  
 `phModDll`  
 <span data-ttu-id="4cb43-115">[out] 모듈의 핸들에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="4cb43-115">[out] A pointer to the handle of the module.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4cb43-116">반환 값</span><span class="sxs-lookup"><span data-stu-id="4cb43-116">Return Value</span></span>  
 <span data-ttu-id="4cb43-117">이 메서드는 다음 값 외에도 WinError.h에 정의 된 대로 표준 구성 요소 개체 모델 (COM) 오류 코드를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cb43-117">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="4cb43-118">반환 코드</span><span class="sxs-lookup"><span data-stu-id="4cb43-118">Return code</span></span>|<span data-ttu-id="4cb43-119">설명</span><span class="sxs-lookup"><span data-stu-id="4cb43-119">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="4cb43-120">S_OK</span><span class="sxs-lookup"><span data-stu-id="4cb43-120">S_OK</span></span>|<span data-ttu-id="4cb43-121">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4cb43-121">The method completed successfully.</span></span>|  
|<span data-ttu-id="4cb43-122">CLR_E_SHIM_RUNTIMELOAD</span><span class="sxs-lookup"><span data-stu-id="4cb43-122">CLR_E_SHIM_RUNTIMELOAD</span></span>|<span data-ttu-id="4cb43-123">로드 `szDllName` 공용 언어 런타임 (CLR) 및 CLR의 필수 버전을 로드할 수 없습니다 로드 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cb43-123">Loading `szDllName` requires loading the common language runtime (CLR), and the necessary version of the CLR cannot be loaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4cb43-124">설명</span><span class="sxs-lookup"><span data-stu-id="4cb43-124">Remarks</span></span>  
 <span data-ttu-id="4cb43-125">이 함수는.NET Framework 재배포 가능 패키지에 포함 된 Dll을 로드 하려고 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4cb43-125">This function is used to load DLLs that are included in the .NET Framework redistributable package.</span></span> <span data-ttu-id="4cb43-126">사용자가 생성 한 Dll은 로드 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4cb43-126">It does not load user-generated DLLs.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4cb43-127">.NET Framework 버전 2.0 부터는 Fusion.dll 로드 하면 CLR이 로드 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="4cb43-127">Beginning with the .NET Framework version 2.0, loading Fusion.dll causes the CLR to be loaded.</span></span> <span data-ttu-id="4cb43-128">Fusion.dll 함수는 런타임에 의해 구현을 제공 하는 래퍼 이지만 이제 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="4cb43-128">This is because the functions in Fusion.dll are now wrappers whose implementations are provided by the runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4cb43-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4cb43-129">Requirements</span></span>  
 <span data-ttu-id="4cb43-130">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4cb43-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4cb43-131">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4cb43-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4cb43-132">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4cb43-132">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cb43-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4cb43-133">See Also</span></span>  
 [<span data-ttu-id="4cb43-134">사용 되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="4cb43-134">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
