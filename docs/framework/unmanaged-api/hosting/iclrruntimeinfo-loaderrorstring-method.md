---
title: ICLRRuntimeInfo::LoadErrorString 메서드
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.LoadErrorString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::LoadErrorString
helpviewer_keywords:
- ICLRRuntimeInfo::LoadErrorString method [.NET Framework hosting]
- LoadErrorString method [.NET Framework hosting]
ms.assetid: 52c543ab-9ef5-4ee7-b836-c0ffc35cd45b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 43a00d687c6a9ec42cb8573e70d181b4dc2c7d0e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33433219"
---
# <a name="iclrruntimeinfoloaderrorstring-method"></a><span data-ttu-id="71859-102">ICLRRuntimeInfo::LoadErrorString 메서드</span><span class="sxs-lookup"><span data-stu-id="71859-102">ICLRRuntimeInfo::LoadErrorString Method</span></span>
<span data-ttu-id="71859-103">지정된 된 문화권에 대 한 적절 한 오류 메시지를 HRESULT 값을 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="71859-103">Translates an HRESULT value into an appropriate error message for the specified culture.</span></span>  
  
 <span data-ttu-id="71859-104">이 메서드는 다음과 같은 기능을 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="71859-104">This method supersedes the following functions:</span></span>  
  
-   [<span data-ttu-id="71859-105">LoadStringRC</span><span class="sxs-lookup"><span data-stu-id="71859-105">LoadStringRC</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)  
  
-   [<span data-ttu-id="71859-106">LoadStringRCEx</span><span class="sxs-lookup"><span data-stu-id="71859-106">LoadStringRCEx</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md)  
  
## <a name="syntax"></a><span data-ttu-id="71859-107">구문</span><span class="sxs-lookup"><span data-stu-id="71859-107">Syntax</span></span>  
  
```  
HRESULT LoadErrorString(  
     [in] UINT iResourceID,  
     [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
     [in, out]  DWORD *pcchBuffer,  
     [in, lcid] LONG iLocaleID);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="71859-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="71859-108">Parameters</span></span>  
 `iResourceID`  
 <span data-ttu-id="71859-109">[in] 변환할 HRESULT입니다.</span><span class="sxs-lookup"><span data-stu-id="71859-109">[in] The HRESULT to translate.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="71859-110">[out] 지정 된 HRESULT와 관련 된 메시지 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="71859-110">[out] The message string associated with the given HRESULT.</span></span>  
  
 `pcchBuffer`  
 <span data-ttu-id="71859-111">[out에서] 크기 `pwzbuffer` 버퍼 오버런을 방지 하기.</span><span class="sxs-lookup"><span data-stu-id="71859-111">[in, out] The size of `pwzbuffer` to avoid buffer overruns.</span></span> <span data-ttu-id="71859-112">경우 `pwzbuffer` 매개 변수가 null 이면 `pcchBuffer` 의 예상된 크기를 제공 `pwzbuffer` 사전 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="71859-112">If `pwzbuffer` is null, `pcchBuffer` provides the expected size of `pwzbuffer` to allow preallocation.</span></span>  
  
 `iLocaleID`  
 <span data-ttu-id="71859-113">[in] 문화권 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="71859-113">[in] The culture identifier.</span></span> <span data-ttu-id="71859-114">기본 문화권을 사용 하려면-1을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="71859-114">To use the default culture, you must specify -1.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="71859-115">반환 값</span><span class="sxs-lookup"><span data-stu-id="71859-115">Return Value</span></span>  
 <span data-ttu-id="71859-116">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="71859-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="71859-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="71859-117">HRESULT</span></span>|<span data-ttu-id="71859-118">설명</span><span class="sxs-lookup"><span data-stu-id="71859-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="71859-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="71859-119">S_OK</span></span>|<span data-ttu-id="71859-120">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="71859-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="71859-121">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="71859-121">E_POINTER</span></span>|<span data-ttu-id="71859-122">`pcchBuffer`가 null인 경우</span><span class="sxs-lookup"><span data-stu-id="71859-122">`pcchBuffer` is null.</span></span>|  
|<span data-ttu-id="71859-123">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="71859-123">E_INVALIDARG</span></span>|<span data-ttu-id="71859-124">`pwzBuffer`가 null인 경우</span><span class="sxs-lookup"><span data-stu-id="71859-124">`pwzBuffer` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="71859-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="71859-125">Requirements</span></span>  
 <span data-ttu-id="71859-126">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="71859-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71859-127">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="71859-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="71859-128">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="71859-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="71859-129">**.NET framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71859-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71859-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="71859-130">See Also</span></span>  
 [<span data-ttu-id="71859-131">ICLRRuntimeInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="71859-131">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [<span data-ttu-id="71859-132">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="71859-132">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="71859-133">호스팅</span><span class="sxs-lookup"><span data-stu-id="71859-133">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
