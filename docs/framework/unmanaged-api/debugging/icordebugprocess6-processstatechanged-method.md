---
title: ICorDebugProcess6::ProcessStateChanged 메서드
ms.date: 03/30/2017
ms.assetid: fb6d30d9-54f3-462b-8ebf-ce0440791ad5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bc5861762242412d7ab6f0c02f2b8f5c149f9453
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33420181"
---
# <a name="icordebugprocess6processstatechanged-method"></a><span data-ttu-id="b82ae-102">ICorDebugProcess6::ProcessStateChanged 메서드</span><span class="sxs-lookup"><span data-stu-id="b82ae-102">ICorDebugProcess6::ProcessStateChanged Method</span></span>
<span data-ttu-id="b82ae-103">알립니다 [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) 프로세스가 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b82ae-103">Notifies [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) that the process is running.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b82ae-104">구문</span><span class="sxs-lookup"><span data-stu-id="b82ae-104">Syntax</span></span>  
  
```  
HRESULT ProcessStateChanged(   [in] CorDebugStateChange change);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b82ae-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b82ae-105">Parameters</span></span>  
 `change`  
 <span data-ttu-id="b82ae-106">[in] 멤버는 [ProcessStateChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md) 열거형</span><span class="sxs-lookup"><span data-stu-id="b82ae-106">[in] A member of the [ProcessStateChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-processstatechanged-method.md) enumeration</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b82ae-107">설명</span><span class="sxs-lookup"><span data-stu-id="b82ae-107">Remarks</span></span>  
 <span data-ttu-id="b82ae-108">에 알리기 위해이 메서드를 호출 하는 디버거 [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) 프로세스가 실행 되는 합니다.</span><span class="sxs-lookup"><span data-stu-id="b82ae-108">The debugger calls this method to notify [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) that the process is running.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b82ae-109">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b82ae-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b82ae-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b82ae-110">Requirements</span></span>  
 <span data-ttu-id="b82ae-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b82ae-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b82ae-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b82ae-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b82ae-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b82ae-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b82ae-114">**.NET framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b82ae-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b82ae-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b82ae-115">See Also</span></span>  
 [<span data-ttu-id="b82ae-116">ICorDebugProcess6 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b82ae-116">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)  
 [<span data-ttu-id="b82ae-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b82ae-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
