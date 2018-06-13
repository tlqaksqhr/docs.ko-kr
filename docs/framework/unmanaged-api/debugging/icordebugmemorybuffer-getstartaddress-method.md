---
title: ICorDebugMemoryBuffer::GetStartAddress 메서드
ms.date: 03/30/2017
ms.assetid: f804d9ab-8c88-44f0-b278-5fcca7f87726
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1aa816ea9e6185791e09bcdb0e47c50761a5ebc6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33422935"
---
# <a name="icordebugmemorybuffergetstartaddress-method"></a><span data-ttu-id="65fd4-102">ICorDebugMemoryBuffer::GetStartAddress 메서드</span><span class="sxs-lookup"><span data-stu-id="65fd4-102">ICorDebugMemoryBuffer::GetStartAddress Method</span></span>
<span data-ttu-id="65fd4-103">메모리 버퍼의 시작 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="65fd4-103">Gets the starting address of the memory buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65fd4-104">구문</span><span class="sxs-lookup"><span data-stu-id="65fd4-104">Syntax</span></span>  
  
```  
HRESULT GetStartAddress(  
   [out] LPCVOID *address  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="65fd4-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="65fd4-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="65fd4-106">[out] 메모리 버퍼의 시작 주소에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="65fd4-106">[out] A pointer to the starting address of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="65fd4-107">설명</span><span class="sxs-lookup"><span data-stu-id="65fd4-107">Remarks</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="65fd4-108">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65fd4-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65fd4-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="65fd4-109">Requirements</span></span>  
 <span data-ttu-id="65fd4-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="65fd4-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65fd4-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="65fd4-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="65fd4-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="65fd4-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="65fd4-113">**.NET framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65fd4-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65fd4-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="65fd4-114">See Also</span></span>  
 [<span data-ttu-id="65fd4-115">ICorDebugMemoryBuffer 인터페이스</span><span class="sxs-lookup"><span data-stu-id="65fd4-115">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)  
 [<span data-ttu-id="65fd4-116">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="65fd4-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
