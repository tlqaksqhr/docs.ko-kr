---
title: "ICorDebugManagedCallback::LoadClass 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.LoadClass
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::LoadClass
helpviewer_keywords:
- ICorDebugManagedCallback::LoadClass method [.NET Framework debugging]
- LoadClass method [.NET Framework debugging]
ms.assetid: e58dac7b-85c3-41ca-b9aa-3a7fc9ae6680
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3518a20567cdac8ed6587aa3dc06408ae6bf7b06
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmanagedcallbackloadclass-method"></a><span data-ttu-id="30125-102">ICorDebugManagedCallback::LoadClass 메서드</span><span class="sxs-lookup"><span data-stu-id="30125-102">ICorDebugManagedCallback::LoadClass Method</span></span>
<span data-ttu-id="30125-103">클래스 로드 된 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="30125-103">Notifies the debugger that a class has been loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30125-104">구문</span><span class="sxs-lookup"><span data-stu-id="30125-104">Syntax</span></span>  
  
```  
HRESULT LoadClass (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugClass     *c  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="30125-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="30125-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="30125-106">[in] 클래스 로드 된 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="30125-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain into which the class has been loaded.</span></span>  
  
 `c`  
 <span data-ttu-id="30125-107">[in] 클래스를 나타내는 ICorDebugClass 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="30125-107">[in] A pointer to an ICorDebugClass object that represents the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="30125-108">설명</span><span class="sxs-lookup"><span data-stu-id="30125-108">Remarks</span></span>  
 <span data-ttu-id="30125-109">이 콜백 클래스를 포함 하는 모듈에 대 한 클래스 로딩을 사용 하도록 설정 된 경우에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="30125-109">This callback occurs only if class loading has been enabled for the module that contains the class.</span></span> <span data-ttu-id="30125-110">클래스 로딩 동적 모듈의 항상 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="30125-110">Class loading is always enabled for dynamic modules.</span></span>  
  
 <span data-ttu-id="30125-111">`LoadClass` 콜백 동적 모듈에서 새로 생성 된 클래스에 중단점을 바인딩할 적절 한 시간을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="30125-111">The `LoadClass` callback provides an appropriate time to bind breakpoints to newly generated classes in dynamic modules.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30125-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="30125-112">Requirements</span></span>  
 <span data-ttu-id="30125-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="30125-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30125-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="30125-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="30125-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="30125-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="30125-116">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30125-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30125-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="30125-117">See Also</span></span>  
 [<span data-ttu-id="30125-118">UnloadClass 메서드</span><span class="sxs-lookup"><span data-stu-id="30125-118">UnloadClass Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md)  
 [<span data-ttu-id="30125-119">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="30125-119">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
