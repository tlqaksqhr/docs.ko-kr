---
title: "ICLRMetaHost::GetVersionFromFile 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRMetaHost.GetVersionFromFile
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRMetaHost::GetVersionFromFile
helpviewer_keywords:
- ICLRMetaHost::GetVersionFromFile method [.NET Framework hosting]
- GetVersionFromFile method [.NET Framework hosting]
ms.assetid: 55bb3eb4-f665-42fc-973c-465567570e82
topic_type: apiref
caps.latest.revision: "20"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 61e6cd1c83cc369e06099c72a6012eb448d6d37a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="iclrmetahostgetversionfromfile-method"></a><span data-ttu-id="7e769-102">ICLRMetaHost::GetVersionFromFile 메서드</span><span class="sxs-lookup"><span data-stu-id="7e769-102">ICLRMetaHost::GetVersionFromFile Method</span></span>
<span data-ttu-id="7e769-103">어셈블리의.NET Framework 컴파일 원본이 (메타 데이터에 저장 됨)을 지정 된 파일 경로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7e769-103">Gets an assembly's original .NET Framework compilation version (stored in the metadata), given its file path.</span></span> <span data-ttu-id="7e769-104">이 메서드를 대체는 [GetFileVersion](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md) 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="7e769-104">This method supersedes the [GetFileVersion](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e769-105">구문</span><span class="sxs-lookup"><span data-stu-id="7e769-105">Syntax</span></span>  
  
```  
HRESULT GetVersionFromFile (  
    [in] LPCWSTR pwzFilePath,  
    [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBuffer);  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7e769-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7e769-106">Parameters</span></span>  
 `pwzFilePath`  
 <span data-ttu-id="7e769-107">[in] 완전 한 어셈블리 파일 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="7e769-107">[in] The complete assembly file path.</span></span>  
  
 `pwzbuffer`  
 <span data-ttu-id="7e769-108">[out] .NET Framework 컴파일 버전 형식에서 메타 데이터에 "v*A*. *B*[. *X*] "입니다.</span><span class="sxs-lookup"><span data-stu-id="7e769-108">[out] The .NET Framework compilation version stored in the metadata, in the format "v*A*.*B*[.*X*]".</span></span> <span data-ttu-id="7e769-109">*A*, *B*, 및 *X* 는 주 버전, 부 버전 및 빌드 번호에 해당 하는 10 진수입니다.</span><span class="sxs-lookup"><span data-stu-id="7e769-109">*A*, *B*, and *X* are decimal numbers that correspond to the major version, the minor version, and the build number.</span></span> <span data-ttu-id="7e769-110">이 문자열의 길이 MAX_PATH 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e769-110">The length of this string is limited to MAX_PATH.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7e769-111">이 출력 C:\Windows\Microsoft.NET\Framework 아래 표시 된 대로.NET Framework 버전에 대 한 디렉터리 이름을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="7e769-111">This output matches the directory name for the .NET Framework version, as it appears under C:\Windows\Microsoft.NET\Framework.</span></span>  
  
 <span data-ttu-id="7e769-112">예제 값은 "v1.0.3705", "v1.1.4322", "v2.0.50727" 및 "v4.0 합니다. *X*"여기서 *X* 설치 된 빌드 번호에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="7e769-112">Example values are "v1.0.3705", "v1.1.4322", "v2.0.50727", and "v4.0.*X*", where *X* depends on the build number installed.</span></span> <span data-ttu-id="7e769-113">"V" 앞에 나오는 참고가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e769-113">Note that the "v" prefix is required.</span></span>  
  
 `pcchBuffer`  
 <span data-ttu-id="7e769-114">[out에서] 크기 `pwzbuffer` 버퍼 오버런을 방지 하기.</span><span class="sxs-lookup"><span data-stu-id="7e769-114">[in, out] The size of `pwzbuffer` to avoid buffer overruns.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7e769-115">반환 값</span><span class="sxs-lookup"><span data-stu-id="7e769-115">Return Value</span></span>  
 <span data-ttu-id="7e769-116">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7e769-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="7e769-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7e769-117">HRESULT</span></span>|<span data-ttu-id="7e769-118">설명</span><span class="sxs-lookup"><span data-stu-id="7e769-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7e769-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="7e769-119">S_OK</span></span>|<span data-ttu-id="7e769-120">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7e769-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="7e769-121">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="7e769-121">E_POINTER</span></span>|<span data-ttu-id="7e769-122">`pwzbuffer` 또는 `pcchBuffer`이 null입니다.</span><span class="sxs-lookup"><span data-stu-id="7e769-122">`pwzbuffer` or `pcchBuffer` is null.</span></span>|  
|<span data-ttu-id="7e769-123">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span><span class="sxs-lookup"><span data-stu-id="7e769-123">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span></span>|<span data-ttu-id="7e769-124">버퍼가 너무 작습니다.</span><span class="sxs-lookup"><span data-stu-id="7e769-124">The buffer is too small.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7e769-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7e769-125">Requirements</span></span>  
 <span data-ttu-id="7e769-126">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7e769-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e769-127">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="7e769-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="7e769-128">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="7e769-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7e769-129">**.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e769-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e769-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7e769-130">See Also</span></span>  
 [<span data-ttu-id="7e769-131">ICLRMetaHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7e769-131">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)  
 [<span data-ttu-id="7e769-132">호스팅</span><span class="sxs-lookup"><span data-stu-id="7e769-132">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
