---
title: ICorDebugLoadedModule::GetSize 메서드
ms.date: 03/30/2017
ms.assetid: aaa0e5c0-be9d-4fe1-8418-5295b9b184d6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9768fb91749158bf3193919b2106bde1c618468a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413233"
---
# <a name="icordebugloadedmodulegetsize-method"></a><span data-ttu-id="23d58-102">ICorDebugLoadedModule::GetSize 메서드</span><span class="sxs-lookup"><span data-stu-id="23d58-102">ICorDebugLoadedModule::GetSize Method</span></span>
<span data-ttu-id="23d58-103">로드된 모듈의 크기(바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="23d58-103">Gets the size in bytes of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23d58-104">구문</span><span class="sxs-lookup"><span data-stu-id="23d58-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcBytes  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="23d58-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="23d58-105">Parameters</span></span>  
 `pcBytes`  
 <span data-ttu-id="23d58-106">[out] 로드된 모듈의 바이트 수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="23d58-106">[out] A pointer to the number of bytes in the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="23d58-107">설명</span><span class="sxs-lookup"><span data-stu-id="23d58-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="23d58-108">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23d58-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23d58-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="23d58-109">Requirements</span></span>  
 <span data-ttu-id="23d58-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="23d58-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23d58-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="23d58-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="23d58-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="23d58-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="23d58-113">**.NET framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23d58-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23d58-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="23d58-114">See Also</span></span>  
 [<span data-ttu-id="23d58-115">ICorDebugLoadedModule 인터페이스</span><span class="sxs-lookup"><span data-stu-id="23d58-115">ICorDebugLoadedModule Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)  
 [<span data-ttu-id="23d58-116">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="23d58-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
