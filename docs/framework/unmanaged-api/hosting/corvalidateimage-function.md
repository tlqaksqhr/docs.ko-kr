---
title: "_CorValidateImage 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: _CorValidateImage
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: _CorValidateImage
helpviewer_keywords: _CorValidateImage function [.NET Framework hosting]
ms.assetid: 0117e080-05f9-4772-885d-e1847230947c
topic_type: apiref
caps.latest.revision: "22"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 03deb62a84a1e9c6cee898fe0023c34b8c538ece
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="corvalidateimage-function"></a><span data-ttu-id="77d7b-102">_CorValidateImage 함수</span><span class="sxs-lookup"><span data-stu-id="77d7b-102">_CorValidateImage Function</span></span>
<span data-ttu-id="77d7b-103">관리 모듈 이미지가 유효성을 검사 하 고 로드 된 후에 운영 체제 로더를에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="77d7b-103">Validates managed module images, and notifies the operating system loader after they have been loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77d7b-104">구문</span><span class="sxs-lookup"><span data-stu-id="77d7b-104">Syntax</span></span>  
  
```  
STDAPI _CorValidateImage (   
   [in] PVOID* ImageBase,  
   [in] LPCWSTR FileName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="77d7b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="77d7b-105">Parameters</span></span>  
 `ImageBase`  
 <span data-ttu-id="77d7b-106">[in] 관리 되는 코드 유효성을 검사할 이미지의 시작 위치에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="77d7b-106">[in] A pointer to the starting location of the image to validate as managed code.</span></span> <span data-ttu-id="77d7b-107">이미 이미지를 메모리에 로드 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77d7b-107">The image must already be loaded into memory.</span></span>  
  
 `FileName`  
 <span data-ttu-id="77d7b-108">[in] 이미지의 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="77d7b-108">[in] The file name of the image.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="77d7b-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="77d7b-109">Return Value</span></span>  
 <span data-ttu-id="77d7b-110">이 함수는 표준 값 반환 `E_INVALIDARG`, `E_OUTOFMEMORY`, `E_UNEXPECTED`, 및 `E_FAIL`, 다음 값 뿐만 아니라 합니다.</span><span class="sxs-lookup"><span data-stu-id="77d7b-110">This function returns the standard values `E_INVALIDARG`, `E_OUTOFMEMORY`, `E_UNEXPECTED`, and `E_FAIL`, as well as the following values.</span></span>  
  
|<span data-ttu-id="77d7b-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="77d7b-111">Return value</span></span>|<span data-ttu-id="77d7b-112">설명</span><span class="sxs-lookup"><span data-stu-id="77d7b-112">Description</span></span>|  
|------------------|-----------------|  
|`STATUS_INVALID_IMAGE_FORMAT`|<span data-ttu-id="77d7b-113">이미지가 올바르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="77d7b-113">The image is invalid.</span></span> <span data-ttu-id="77d7b-114">이 값은 HRESULT 0xC000007BL.</span><span class="sxs-lookup"><span data-stu-id="77d7b-114">This value has the HRESULT 0xC000007BL.</span></span>|  
|`STATUS_SUCCESS`|<span data-ttu-id="77d7b-115">이미지 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="77d7b-115">The image is valid.</span></span> <span data-ttu-id="77d7b-116">이 값은 HRESULT 0x00000000L.</span><span class="sxs-lookup"><span data-stu-id="77d7b-116">This value has the HRESULT 0x00000000L.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="77d7b-117">설명</span><span class="sxs-lookup"><span data-stu-id="77d7b-117">Remarks</span></span>  
 <span data-ttu-id="77d7b-118">Windows XP 이상 버전에서 운영 체제 로더는 공용 개체 파일 형식 (COFF) 헤더에 COM 설명자 디렉터리 비트를 검사 하 여 관리 모듈을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="77d7b-118">In Windows XP and later versions, the operating system loader checks for managed modules by examining the COM Descriptor Directory bit in the common object file format (COFF) header.</span></span> <span data-ttu-id="77d7b-119">설정 비트는 관리 모듈을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="77d7b-119">A set bit indicates a managed module.</span></span> <span data-ttu-id="77d7b-120">MsCorEE.dll 및 호출 로더는 관리 모듈을 감지 하면 로드 `_CorValidateImage`, 다음 작업을 수행 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="77d7b-120">If the loader detects a managed module, it loads MsCorEE.dll and calls `_CorValidateImage`, which performs the following actions:</span></span>  
  
-   <span data-ttu-id="77d7b-121">이미지 유효한 관리 되는 모듈 인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="77d7b-121">Confirms that the image is a valid managed module.</span></span>  
  
-   <span data-ttu-id="77d7b-122">공용 언어 런타임 (CLR)의 진입점으로 이미지의 진입점을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="77d7b-122">Changes the entry point in the image to an entry point in the common language runtime (CLR).</span></span>  
  
-   <span data-ttu-id="77d7b-123">64 비트 버전의 Windows에서는 이미지를 p e 32에서 PE32 + 형식으로 변환 하 여 메모리에 있는 이미지를 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="77d7b-123">For 64-bit versions of Windows, modifies the image that is in memory by transforming it from PE32 to PE32+ format.</span></span>  
  
-   <span data-ttu-id="77d7b-124">관리 모듈 이미지가 로드 될 때 로더를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="77d7b-124">Returns to the loader when the managed module images are loaded.</span></span>  
  
 <span data-ttu-id="77d7b-125">실행 가능 이미지에 대 한 운영 체제 로더에 다음 호출에서 [_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) 실행 파일에 지정 된 진입점에 관계 없이 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="77d7b-125">For executable images, the operating system loader then calls the [_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) function, regardless of the entry point specified in the executable.</span></span> <span data-ttu-id="77d7b-126">로더가 DLL 어셈블리 이미지에 대 한 호출에서 [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="77d7b-126">For DLL assembly images, the loader calls the [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) function.</span></span>  
  
 <span data-ttu-id="77d7b-127">`_CorExeMain`또는 `_CorDllMain` 다음 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="77d7b-127">`_CorExeMain` or `_CorDllMain` performs the following actions:</span></span>  
  
-   <span data-ttu-id="77d7b-128">CLR을 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="77d7b-128">Initializes the CLR.</span></span>  
  
-   <span data-ttu-id="77d7b-129">어셈블리의 CLR 헤더에서 관리 되는 진입점을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="77d7b-129">Locates the managed entry point from the assembly's CLR header.</span></span>  
  
-   <span data-ttu-id="77d7b-130">실행을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="77d7b-130">Begins execution.</span></span>  
  
 <span data-ttu-id="77d7b-131">로더 호출은 [_CorImageUnloading](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md) 관리 되는 경우에 작동 모듈 이미지가 로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="77d7b-131">The loader calls the [_CorImageUnloading](../../../../docs/framework/unmanaged-api/hosting/corimageunloading-function.md) function when managed module images are unloaded.</span></span> <span data-ttu-id="77d7b-132">그러나이 함수 조치; 수행 하지 않습니다. 만 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="77d7b-132">However, this function does not perform any action; it just returns.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77d7b-133">요구 사항</span><span class="sxs-lookup"><span data-stu-id="77d7b-133">Requirements</span></span>  
 <span data-ttu-id="77d7b-134">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="77d7b-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77d7b-135">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="77d7b-135">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="77d7b-136">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="77d7b-136">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="77d7b-137">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77d7b-137">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77d7b-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="77d7b-138">See Also</span></span>  
 [<span data-ttu-id="77d7b-139">메타데이터 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="77d7b-139">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
