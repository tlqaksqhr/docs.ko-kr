---
title: "ICLRDebugging::CanUnloadNow 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDebugging.CanUnloadNow Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDebugging::CanUnloadNow
helpviewer_keywords:
- CanUnloadNow method [.NET Framework debugging]
- ICLRDebugging::CanUnloadNow method [.NET Framework debugging]
ms.assetid: 62e0630c-8cb7-45d2-b622-5a472abfd8cf
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b013231666ca6dfde5ab16e58023da1ae2a72941
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="iclrdebuggingcanunloadnow-method"></a><span data-ttu-id="c37dc-102">ICLRDebugging::CanUnloadNow 메서드</span><span class="sxs-lookup"><span data-stu-id="c37dc-102">ICLRDebugging::CanUnloadNow Method</span></span>
<span data-ttu-id="c37dc-103">제공 하는 라이브러리 여부를 확인 한 [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) 인터페이스 사용 되 고 또는 언로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c37dc-103">Determines whether a library that was provided by an [ICLRDebuggingLibraryProvider](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md) interface is still in use or can be unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c37dc-104">구문</span><span class="sxs-lookup"><span data-stu-id="c37dc-104">Syntax</span></span>  
  
```  
HRESULT CanUnloadNow(HMODULE hModule);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c37dc-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c37dc-105">Parameters</span></span>  
 `hmodule`  
 <span data-ttu-id="c37dc-106">[in] 대상 프로세스에서 특정 모듈의 기본 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="c37dc-106">[in] The base address of a module in the target process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c37dc-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="c37dc-107">Return Value</span></span>  
 <span data-ttu-id="c37dc-108">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c37dc-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="c37dc-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c37dc-109">HRESULT</span></span>|<span data-ttu-id="c37dc-110">설명</span><span class="sxs-lookup"><span data-stu-id="c37dc-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c37dc-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="c37dc-111">S_OK</span></span>|<span data-ttu-id="c37dc-112">참조 하는 모듈 `hmodule` 언로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c37dc-112">The module that is referenced by `hmodule` can be unloaded.</span></span>|  
|<span data-ttu-id="c37dc-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="c37dc-113">S_FALSE</span></span>|<span data-ttu-id="c37dc-114">참조 하는 모듈 `hmodule` 사용 중입니다.</span><span class="sxs-lookup"><span data-stu-id="c37dc-114">The module that is referenced by `hmodule` is still in use.</span></span>|  
|<span data-ttu-id="c37dc-115">COR_E_NOT_CLR</span><span class="sxs-lookup"><span data-stu-id="c37dc-115">COR_E_NOT_CLR</span></span>|<span data-ttu-id="c37dc-116">표시 된 모듈이 CLR 모듈이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="c37dc-116">The indicated module is not a CLR module.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="c37dc-117">예외</span><span class="sxs-lookup"><span data-stu-id="c37dc-117">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c37dc-118">설명</span><span class="sxs-lookup"><span data-stu-id="c37dc-118">Remarks</span></span>  
 <span data-ttu-id="c37dc-119">이 메서드를 모든 확인 인스턴스의 `ICorDebug*` 릴리스된 인터페이스를 스레드가 현재 내에 대 한 호출의 [iclrdebugging:: Openvirtualprocess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="c37dc-119">This method checks to see if all instances of `ICorDebug*` interfaces have been released and no thread is currently within a call to the [ICLRDebugging::OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c37dc-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c37dc-120">Requirements</span></span>  
 <span data-ttu-id="c37dc-121">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c37dc-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c37dc-122">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c37dc-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c37dc-123">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c37dc-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c37dc-124">**.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c37dc-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c37dc-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c37dc-125">See Also</span></span>  
 [<span data-ttu-id="c37dc-126">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c37dc-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="c37dc-127">디버깅</span><span class="sxs-lookup"><span data-stu-id="c37dc-127">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
