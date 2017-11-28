---
title: "ICorDebugMemoryBuffer::GetSize 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 9ffd5482-268e-4680-9fd1-bfb0b7d66450
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a21198c70512af703e106870d1bc3f7882d62fe9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmemorybuffergetsize-method"></a><span data-ttu-id="09a1b-102">ICorDebugMemoryBuffer::GetSize 메서드</span><span class="sxs-lookup"><span data-stu-id="09a1b-102">ICorDebugMemoryBuffer::GetSize Method</span></span>
<span data-ttu-id="09a1b-103">메모리 버퍼의 크기(바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="09a1b-103">Gets the size of the memory buffer in bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09a1b-104">구문</span><span class="sxs-lookup"><span data-stu-id="09a1b-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
   [out] ULONG32 *pcbBufferLength  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="09a1b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="09a1b-105">Parameters</span></span>  
 `pcbBufferLength`  
 <span data-ttu-id="09a1b-106">[out] 메모리 버퍼 크기에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="09a1b-106">[out] A pointer to the size of the memory buffer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="09a1b-107">설명</span><span class="sxs-lookup"><span data-stu-id="09a1b-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="09a1b-108">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09a1b-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09a1b-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="09a1b-109">Requirements</span></span>  
 <span data-ttu-id="09a1b-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="09a1b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09a1b-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="09a1b-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="09a1b-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="09a1b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="09a1b-113">**.NET framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09a1b-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09a1b-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="09a1b-114">See Also</span></span>  
 [<span data-ttu-id="09a1b-115">ICorDebugMemoryBuffer 인터페이스</span><span class="sxs-lookup"><span data-stu-id="09a1b-115">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)  
 [<span data-ttu-id="09a1b-116">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="09a1b-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
