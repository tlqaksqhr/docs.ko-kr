---
title: ICLRMetaHost::EnumerateInstalledRuntimes 메서드
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.EnumerateInstalledRuntimes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::EnumerateInstalledRuntimes
helpviewer_keywords:
- ICLRMetaHost::EnumerateInstalledRuntimes method [.NET Framework hosting]
- EnumerateInstalledRuntimes method [.NET Framework hosting]
ms.assetid: 9e359384-0d3d-451c-807e-5d7fcebf2be7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0ed4c09d910db6fa2e61d44e4ac777f9b6095a20
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434283"
---
# <a name="iclrmetahostenumerateinstalledruntimes-method"></a><span data-ttu-id="4f33a-102">ICLRMetaHost::EnumerateInstalledRuntimes 메서드</span><span class="sxs-lookup"><span data-stu-id="4f33a-102">ICLRMetaHost::EnumerateInstalledRuntimes Method</span></span>
<span data-ttu-id="4f33a-103">유효한를 포함 하는 열거형을 반환 [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) 는 컴퓨터에 설치 된 공용 언어 런타임 (CLR)의 각 버전에 대 한 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="4f33a-103">Returns an enumeration that contains a valid [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface for each version of the common language runtime (CLR) that is installed on a computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f33a-104">구문</span><span class="sxs-lookup"><span data-stu-id="4f33a-104">Syntax</span></span>  
  
```  
HRESULT EnumerateInstalledRuntimes (  
    [out, retval] IEnumUnknown **ppEnumerator);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4f33a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4f33a-105">Parameters</span></span>  
 `ppEnumerator`  
 <span data-ttu-id="4f33a-106">[out] 열거형 [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) 컴퓨터에 설치 된 CLR의 각 버전에 해당 하는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="4f33a-106">[out] An enumeration of [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaces corresponding to each version of the CLR that is installed on the computer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4f33a-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="4f33a-107">Return Value</span></span>  
 <span data-ttu-id="4f33a-108">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="4f33a-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="4f33a-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4f33a-109">HRESULT</span></span>|<span data-ttu-id="4f33a-110">설명</span><span class="sxs-lookup"><span data-stu-id="4f33a-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4f33a-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="4f33a-111">S_OK</span></span>|<span data-ttu-id="4f33a-112">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4f33a-112">The method completed successfully.</span></span>|  
|<span data-ttu-id="4f33a-113">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="4f33a-113">E_POINTER</span></span>|<span data-ttu-id="4f33a-114">`ppEnumerator`가 null인 경우</span><span class="sxs-lookup"><span data-stu-id="4f33a-114">`ppEnumerator` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4f33a-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4f33a-115">Requirements</span></span>  
 <span data-ttu-id="4f33a-116">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4f33a-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f33a-117">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="4f33a-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="4f33a-118">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="4f33a-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4f33a-119">**.NET framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f33a-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f33a-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4f33a-120">See Also</span></span>  
 [<span data-ttu-id="4f33a-121">ICLRMetaHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4f33a-121">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)  
 [<span data-ttu-id="4f33a-122">호스팅</span><span class="sxs-lookup"><span data-stu-id="4f33a-122">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
