---
title: ICLRRuntimeInfo::BindAsLegacyV2Runtime 메서드
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.BindAsLegacyV2Runtime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::BindAsLegacyV2Runtime
helpviewer_keywords:
- ICLRRuntimeInfo::BindAsLegacyV2Runtime method [.NET Framework hosting]
- BindAsLegacyV2Runtime method [.NET Framework hosting]
ms.assetid: 65fd55ac-4a24-4479-9384-a2e8013bfb2b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 690287bf54f98c19298504ee3058a59ef88a87f9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33433163"
---
# <a name="iclrruntimeinfobindaslegacyv2runtime-method"></a><span data-ttu-id="06f33-102">ICLRRuntimeInfo::BindAsLegacyV2Runtime 메서드</span><span class="sxs-lookup"><span data-stu-id="06f33-102">ICLRRuntimeInfo::BindAsLegacyV2Runtime Method</span></span>
<span data-ttu-id="06f33-103">모든 기존 공용 언어 런타임 (CLR) 버전 2 정품 인증 정책 결정에 대 한 현재 런타임에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="06f33-103">Binds the current runtime for all legacy common language runtime (CLR) version 2 activation policy decisions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06f33-104">구문</span><span class="sxs-lookup"><span data-stu-id="06f33-104">Syntax</span></span>  
  
```  
HRESULT BindAsLegacyV2Runtime ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="06f33-105">반환 값</span><span class="sxs-lookup"><span data-stu-id="06f33-105">Return Value</span></span>  
 <span data-ttu-id="06f33-106">이 메서드는 다음과 같은 특정 Hresult를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="06f33-106">This method returns the following specific HRESULTs:</span></span>  
  
|<span data-ttu-id="06f33-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="06f33-107">HRESULT</span></span>|<span data-ttu-id="06f33-108">설명</span><span class="sxs-lookup"><span data-stu-id="06f33-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="06f33-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="06f33-109">S_OK</span></span>|<span data-ttu-id="06f33-110">바인딩 성공, 또는 레거시 CLR 버전 2 정품 인증 정책 런타임이 이미이 런타임 바인딩 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="06f33-110">Either binding succeeded, or this runtime was already bound as the legacy CLR version 2 activation policy runtime.</span></span>|  
|<span data-ttu-id="06f33-111">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span><span class="sxs-lookup"><span data-stu-id="06f33-111">CLR_E_SHIM_LEGACYRUNTIMEALREADYBOUND</span></span>|<span data-ttu-id="06f33-112">각기 다른 런타임 레거시 CLR 버전 2 정품 인증 정책에 이미 바인딩 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="06f33-112">A different runtime was already bound to the legacy CLR version 2 activation policy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="06f33-113">설명</span><span class="sxs-lookup"><span data-stu-id="06f33-113">Remarks</span></span>  
 <span data-ttu-id="06f33-114">모든 레거시 CLR 버전 2 정품 인증 정책 결정에 대 한 현재 런타임 이미 바인딩된 경우 (예를 들어를 사용 하 여는 `useLegacyV2RuntimeActivationPolicy` 특성에 [ \<시작 > 요소](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) 구성 파일에),이 메서드 오류 결과 반환 하지 않습니다. 대신, 결과 s_ok이 고, 메서드가 레거시 활성화 정책에 성공적으로 바인딩할 경우 것 처럼.</span><span class="sxs-lookup"><span data-stu-id="06f33-114">If the current runtime is already bound for all legacy CLR version 2 activation policy decisions (for example, by using the `useLegacyV2RuntimeActivationPolicy` attribute on the [\<startup> element](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md) in the configuration file), this method does not return an error result; instead, the result is S_OK, just as it would be if the method had successfully bound legacy activation policy.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06f33-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="06f33-115">Requirements</span></span>  
 <span data-ttu-id="06f33-116">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="06f33-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06f33-117">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="06f33-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="06f33-118">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="06f33-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="06f33-119">**.NET framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06f33-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06f33-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="06f33-120">See Also</span></span>  
 [<span data-ttu-id="06f33-121">ICLRRuntimeInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="06f33-121">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [<span data-ttu-id="06f33-122">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="06f33-122">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="06f33-123">호스팅</span><span class="sxs-lookup"><span data-stu-id="06f33-123">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)  
 [<span data-ttu-id="06f33-124">\<startup> 요소</span><span class="sxs-lookup"><span data-stu-id="06f33-124">\<startup> Element</span></span>](../../../../docs/framework/configure-apps/file-schema/startup/startup-element.md)
