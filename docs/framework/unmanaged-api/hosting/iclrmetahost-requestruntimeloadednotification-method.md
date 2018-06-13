---
title: ICLRMetaHost::RequestRuntimeLoadedNotification 메서드
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.RequestRuntimeLoadedNotification
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::RequestRuntimeLoadedNotification
helpviewer_keywords:
- RequestRuntimeLoadedNotification method [.NET Framework hosting]
- ICLRMetaHost::RequestRuntimeLoadedNotification method [.NET Framework hosting]
ms.assetid: 0d5ccc4d-0193-41f5-af54-45d7b70d5321
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9ac041db64a874cc143657c601f30e4482dd2462
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434437"
---
# <a name="iclrmetahostrequestruntimeloadednotification-method"></a><span data-ttu-id="6c3aa-102">ICLRMetaHost::RequestRuntimeLoadedNotification 메서드</span><span class="sxs-lookup"><span data-stu-id="6c3aa-102">ICLRMetaHost::RequestRuntimeLoadedNotification Method</span></span>
<span data-ttu-id="6c3aa-103">공용 언어 런타임 (CLR) 버전은 처음 로드 되었지만 아직 시작 되지 않았을 때 호출 될 보장 되는 콜백 함수를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c3aa-103">Provides a callback function that is guaranteed to be called when a common language runtime (CLR) version is first loaded, but not yet started.</span></span> <span data-ttu-id="6c3aa-104">이 메서드를 대체는 [LockClrVersion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md) 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="6c3aa-104">This method supersedes the [LockClrVersion](../../../../docs/framework/unmanaged-api/hosting/lockclrversion-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c3aa-105">구문</span><span class="sxs-lookup"><span data-stu-id="6c3aa-105">Syntax</span></span>  
  
```  
HRESULT RequestRuntimeLoadedNotification (  
    [in] RuntimeLoadedCallbackFnPtr pCallbackFunction);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6c3aa-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6c3aa-106">Parameters</span></span>  
 `pCallbackFunction`  
 <span data-ttu-id="6c3aa-107">[in] 에서는 새로운 런타임 로드 되었을 때 호출 되는 콜백 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="6c3aa-107">[in] The callback function that is invoked when a new runtime has been loaded.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6c3aa-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="6c3aa-108">Return Value</span></span>  
 <span data-ttu-id="6c3aa-109">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6c3aa-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="6c3aa-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6c3aa-110">HRESULT</span></span>|<span data-ttu-id="6c3aa-111">설명</span><span class="sxs-lookup"><span data-stu-id="6c3aa-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6c3aa-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="6c3aa-112">S_OK</span></span>|<span data-ttu-id="6c3aa-113">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6c3aa-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="6c3aa-114">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="6c3aa-114">E_POINTER</span></span>|<span data-ttu-id="6c3aa-115">`pCallbackFunction`가 null인 경우</span><span class="sxs-lookup"><span data-stu-id="6c3aa-115">`pCallbackFunction` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6c3aa-116">설명</span><span class="sxs-lookup"><span data-stu-id="6c3aa-116">Remarks</span></span>  
 <span data-ttu-id="6c3aa-117">콜백은 다음과 같은 방식으로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="6c3aa-117">The callback works in the following way:</span></span>  
  
-   <span data-ttu-id="6c3aa-118">런타임을 처음으로 로드 되는 경우에는 콜백이 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c3aa-118">The callback is invoked only when a runtime is loaded for the first time.</span></span>  
  
-   <span data-ttu-id="6c3aa-119">같은 런타임 재진입 로드에 대 한 콜백을 호출 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6c3aa-119">The callback is not invoked for reentrant loads of the same runtime.</span></span>  
  
-   <span data-ttu-id="6c3aa-120">재진입 런타임 로드에 대 한 콜백 함수 호출에 serialize 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c3aa-120">For non-reentrant runtime loads, calls to the callback function are serialized.</span></span>  
  
 <span data-ttu-id="6c3aa-121">콜백 함수에는 다음과 같은 프로토타입이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c3aa-121">The callback function has the following prototype:</span></span>  
  
```  
typedef void (__stdcall *RuntimeLoadedCallbackFnPtr)(  
                     ICLRRuntimeInfo *pRuntimeInfo,  
                     CallbackThreadSetFnPtr pfnCallbackThreadSet,  
                     CallbackThreadUnsetFnPtr pfnCallbackThreadUnset);  
```  
  
 <span data-ttu-id="6c3aa-122">콜백 함수 프로토타입에 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6c3aa-122">The callback function prototypes are as follows:</span></span>  
  
-   <span data-ttu-id="6c3aa-123">`pfnCallbackThreadSet`:</span><span class="sxs-lookup"><span data-stu-id="6c3aa-123">`pfnCallbackThreadSet`:</span></span>  
  
    ```  
    typedef HRESULT (__stdcall *CallbackThreadSetFnPtr)();  
    ```  
  
-   <span data-ttu-id="6c3aa-124">`pfnCallbackThreadUnset`:</span><span class="sxs-lookup"><span data-stu-id="6c3aa-124">`pfnCallbackThreadUnset`:</span></span>  
  
    ```  
    typedef HRESULT (__stdcall *CallbackThreadUnsetFnPtr)();  
    ```  
  
 <span data-ttu-id="6c3aa-125">호스트가를 로드 하거나 다른 런타임을 재진입 방식으로 로드 되도록 하는 경우는 `pfnCallbackThreadSet` 및 `pfnCallbackThreadUnset` 콜백에서 함수는 다음과 같이 사용 해야 하는 제공 되는 매개 변수:</span><span class="sxs-lookup"><span data-stu-id="6c3aa-125">If the host intends to load or cause another runtime to be loaded in a reentrant manner, the `pfnCallbackThreadSet` and `pfnCallbackThreadUnset` parameters that are provided in the callback function must be used in the following way:</span></span>  
  
-   <span data-ttu-id="6c3aa-126">`pfnCallbackThreadSet` 로드를 시도 되기 전에 런타임 부하를 일으킬 수 있는 스레드에서 호출 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c3aa-126">`pfnCallbackThreadSet` must be called by the thread that might cause a runtime load before such a load is attempted.</span></span>  
  
-   <span data-ttu-id="6c3aa-127">`pfnCallbackThreadUnset` 스레드가 더 이상 이러한 런타임 로드 될 때 (및 초기 콜백에서 반환 하기 전에) 호출 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c3aa-127">`pfnCallbackThreadUnset` must be called when the thread will no longer cause such a runtime load (and before returning from the initial callback).</span></span>  
  
-   <span data-ttu-id="6c3aa-128">`pfnCallbackThreadSet` 및 `pfnCallbackThreadUnset` 재진입은 모두입니다.</span><span class="sxs-lookup"><span data-stu-id="6c3aa-128">`pfnCallbackThreadSet` and `pfnCallbackThreadUnset` are both non-reentrant.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6c3aa-129">호스트 응용 프로그램 호출 해서는 안 `pfnCallbackThreadSet` 및 `pfnCallbackThreadUnset` 범위 밖에 서는 `pCallbackFunction` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="6c3aa-129">Host applications must not call `pfnCallbackThreadSet` and `pfnCallbackThreadUnset` outside the scope of the `pCallbackFunction` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c3aa-130">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6c3aa-130">Requirements</span></span>  
 <span data-ttu-id="6c3aa-131">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6c3aa-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c3aa-132">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="6c3aa-132">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="6c3aa-133">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="6c3aa-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6c3aa-134">**.NET framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c3aa-134">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c3aa-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6c3aa-135">See Also</span></span>  
 [<span data-ttu-id="6c3aa-136">ICLRMetaHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6c3aa-136">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)  
 [<span data-ttu-id="6c3aa-137">호스팅</span><span class="sxs-lookup"><span data-stu-id="6c3aa-137">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
