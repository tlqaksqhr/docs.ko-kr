---
title: CreateVersionStringFromModule 함수
ms.date: 03/30/2017
api_name:
- CreateVersionStringFromModule
api_location:
- dbgshim.dll
api_type:
- COM
f1_keywords:
- CreateVersionStringFromModule
helpviewer_keywords:
- debugging API [Silverlight]
- Silverlight, debugging
- CreateVersionStringFromModule function
ms.assetid: 3d2fe9bd-75ef-4364-84a6-da1e1994ac1a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0988b2c4471cb5449f7c7fac82c6e94bcd537b7e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33409282"
---
# <a name="createversionstringfrommodule-function"></a><span data-ttu-id="daba9-102">CreateVersionStringFromModule 함수</span><span class="sxs-lookup"><span data-stu-id="daba9-102">CreateVersionStringFromModule Function</span></span>
<span data-ttu-id="daba9-103">대상 프로세스의 CLR(공용 언어 런타임) 경로에서 버전 문자열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="daba9-103">Creates a version string from a common language runtime (CLR) path in a target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="daba9-104">구문</span><span class="sxs-lookup"><span data-stu-id="daba9-104">Syntax</span></span>  
  
```  
HRESULT CreateVersionStringFromModule (  
    [in]  DWORD      pidDebuggee,  
    [in]  LPCWSTR    szModuleName,  
    [out, size_is(cchBuffer),  
          length_is(*pdwLength)] LPWSTR Buffer,  
    [in]  DWORD      cchBuffer,  
    [out] DWORD*     pdwLength  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="daba9-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="daba9-105">Parameters</span></span>  
 `pidDebuggee`  
 <span data-ttu-id="daba9-106">[in] 대상 CLR이 로드되는 프로세스의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="daba9-106">[in] Identifier of the process in which the target CLR is loaded.</span></span>  
  
 `szModuleName`  
 <span data-ttu-id="daba9-107">[in] 프로세스에서 로드된 대상 CLR의 전체 경로 또는 상대 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="daba9-107">[in] Full or relative path to the target CLR that is loaded in the process.</span></span>  
  
 `pBuffer`  
 <span data-ttu-id="daba9-108">[out] 대상 CLR에 대한 버전 문자열을 저장하기 위한 버퍼를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="daba9-108">[out] Return buffer for storing the version string for the target CLR.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="daba9-109">[in] `pBuffer`의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="daba9-109">[in] Size of `pBuffer`.</span></span>  
  
 `pdwLength`  
 <span data-ttu-id="daba9-110">[out] `pBuffer`에서 반환된 버전 문자열의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="daba9-110">[out] Length of the version string returned by `pBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="daba9-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="daba9-111">Return Value</span></span>  
 <span data-ttu-id="daba9-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="daba9-112">S_OK</span></span>  
 <span data-ttu-id="daba9-113">`pBuffer`에 반환된 대상 CLR에 대한 버전 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="daba9-113">The version string for the target CLR was successfully returned in `pBuffer`.</span></span>  
  
 <span data-ttu-id="daba9-114">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="daba9-114">E_INVALIDARG</span></span>  
 <span data-ttu-id="daba9-115">`szModuleName`이 null이거나 `pBuffer` 또는 `cchBuffer`가 null입니다.</span><span class="sxs-lookup"><span data-stu-id="daba9-115">`szModuleName` is null, or either `pBuffer` or `cchBuffer` is null.</span></span> <span data-ttu-id="daba9-116">`pBuffer` 및 `cchBuffer`는 둘 다 null이거나 null이 아니어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="daba9-116">`pBuffer` and `cchBuffer` must both be null or non-null.</span></span>  
  
 <span data-ttu-id="daba9-117">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span><span class="sxs-lookup"><span data-stu-id="daba9-117">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span></span>  
 <span data-ttu-id="daba9-118">`pdwLength`가 `cchBuffer`보다 큰 경우</span><span class="sxs-lookup"><span data-stu-id="daba9-118">`pdwLength` is greater than `cchBuffer`.</span></span> <span data-ttu-id="daba9-119">이는 `pBuffer` 및 `cchBuffer` 둘 다에 대해 null을 전달하고 `pdwLength`를 사용하여 필요한 버퍼 크기를 쿼리한 경우의 예상 결과일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="daba9-119">This may be an expected result if you have passed null for both `pBuffer` and `cchBuffer`, and queried the necessary buffer size by using `pdwLength`.</span></span>  
  
 <span data-ttu-id="daba9-120">HRESULT_FROM_WIN32(ERROR_MOD_NOT_FOUND)</span><span class="sxs-lookup"><span data-stu-id="daba9-120">HRESULT_FROM_WIN32(ERROR_MOD_NOT_FOUND)</span></span>  
 <span data-ttu-id="daba9-121">`szModuleName`이 대상 프로세스의 유효한 CLR에 대한 경로를 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="daba9-121">`szModuleName` does not contain a path to a valid CLR in the target process.</span></span>  
  
 <span data-ttu-id="daba9-122">E_FAIL(또는 다른 E_ 반환 코드)</span><span class="sxs-lookup"><span data-stu-id="daba9-122">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="daba9-123">`pidDebuggee`가 유효한 프로세스 또는 다른 실패를 참조하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="daba9-123">`pidDebuggee` does not refer to a valid process, or other failure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="daba9-124">설명</span><span class="sxs-lookup"><span data-stu-id="daba9-124">Remarks</span></span>  
 <span data-ttu-id="daba9-125">이 함수는 `pidDebuggee`로 식별된 CLR 프로세스 및 `szModuleName`으로 지정된 문자열 경로를 수락합니다.</span><span class="sxs-lookup"><span data-stu-id="daba9-125">This function accepts a CLR process that is identified by `pidDebuggee` and a string path that is specified by `szModuleName`.</span></span> <span data-ttu-id="daba9-126">`pBuffer`가 가리키는 버퍼에 버전 문자열이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="daba9-126">The version string is returned in the buffer that `pBuffer` points to.</span></span> <span data-ttu-id="daba9-127">이 문자열은 함수 사용자에게 불투명합니다. 즉, 버전 문자열 자체에는 내포된 의미가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="daba9-127">This string is opaque to the function user; that is, there is no intrinsic meaning in the version string itself.</span></span> <span data-ttu-id="daba9-128">이 함수의 컨텍스트에서 전적으로 사용 되는 및 [CreateDebuggingInterfaceFromVersion 함수](../../../../docs/framework/unmanaged-api/debugging/createdebugginginterfacefromversion-function-for-silverlight.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="daba9-128">It is used solely in the context of this function and the [CreateDebuggingInterfaceFromVersion function](../../../../docs/framework/unmanaged-api/debugging/createdebugginginterfacefromversion-function-for-silverlight.md).</span></span>  
  
 <span data-ttu-id="daba9-129">이 함수는 두 번 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="daba9-129">This function should be called twice.</span></span> <span data-ttu-id="daba9-130">처음 호출할 때는 `pBuffer` 및 `cchBuffer` 둘 다에 대해 null을 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="daba9-130">When you call it the first time, pass null for both `pBuffer` and `cchBuffer`.</span></span> <span data-ttu-id="daba9-131">이렇게 하면 `pBuffer`에 필요한 버퍼의 크기가 `pdwLength`에 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="daba9-131">When you do this, the size of the buffer necessary for `pBuffer` will be returned in `pdwLength`.</span></span> <span data-ttu-id="daba9-132">그런 다음 두 번째로 함수를 호출하고 버퍼에 `pBuffer`에, 해당 크기를 `cchBuffer`에 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="daba9-132">You can then call the function a second time, and pass the buffer in `pBuffer` and its size in `cchBuffer`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="daba9-133">요구 사항</span><span class="sxs-lookup"><span data-stu-id="daba9-133">Requirements</span></span>  
 <span data-ttu-id="daba9-134">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="daba9-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="daba9-135">**헤더:** dbgshim.h</span><span class="sxs-lookup"><span data-stu-id="daba9-135">**Header:** dbgshim.h</span></span>  
  
 <span data-ttu-id="daba9-136">**라이브러리:** dbgshim.dll</span><span class="sxs-lookup"><span data-stu-id="daba9-136">**Library:** dbgshim.dll</span></span>  
  
 <span data-ttu-id="daba9-137">**.NET framework 버전:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="daba9-137">**.NET Framework Versions:** 3.5 SP1</span></span>
