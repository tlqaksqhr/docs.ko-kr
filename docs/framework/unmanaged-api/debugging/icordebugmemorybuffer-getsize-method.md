---
title: ICorDebugMemoryBuffer::GetSize 메서드
ms.date: 03/30/2017
ms.assetid: 9ffd5482-268e-4680-9fd1-bfb0b7d66450
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: caf95e0b5c8d4ae942bb428f53d4e58313e0e78e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33414754"
---
# <a name="icordebugmemorybuffergetsize-method"></a><span data-ttu-id="b2251-102">ICorDebugMemoryBuffer::GetSize 메서드</span><span class="sxs-lookup"><span data-stu-id="b2251-102">ICorDebugMemoryBuffer::GetSize Method</span></span>
<span data-ttu-id="b2251-103">메모리 버퍼의 크기(바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b2251-103">Gets the size of the memory buffer in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2251-104">구문</span><span class="sxs-lookup"><span data-stu-id="b2251-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcbBufferLength  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b2251-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b2251-105">Parameters</span></span>  
 `pcbBufferLength`  
 <span data-ttu-id="b2251-106">[out] 메모리 버퍼 크기에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b2251-106">[out] A pointer to the size of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b2251-107">설명</span><span class="sxs-lookup"><span data-stu-id="b2251-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b2251-108">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2251-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2251-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b2251-109">Requirements</span></span>  
 <span data-ttu-id="b2251-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b2251-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2251-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b2251-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b2251-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b2251-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b2251-113">**.NET framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2251-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2251-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b2251-114">See Also</span></span>  
 [<span data-ttu-id="b2251-115">ICorDebugMemoryBuffer 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b2251-115">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)  
 [<span data-ttu-id="b2251-116">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b2251-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
