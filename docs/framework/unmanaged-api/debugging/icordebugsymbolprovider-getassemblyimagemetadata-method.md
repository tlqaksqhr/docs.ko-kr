---
title: "ICorDebugSymbolProvider::GetAssemblyImageMetadata 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: c3c9de67-b865-4ecf-b887-1f1d0719a0c0
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ff6b26dd9a0ed56e5194dc997270cf9d2dbe42b2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugsymbolprovidergetassemblyimagemetadata-method"></a><span data-ttu-id="ecf79-102">ICorDebugSymbolProvider::GetAssemblyImageMetadata 메서드</span><span class="sxs-lookup"><span data-stu-id="ecf79-102">ICorDebugSymbolProvider::GetAssemblyImageMetadata Method</span></span>
<span data-ttu-id="ecf79-103">병합된 어셈블리에서 메타데이터를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ecf79-103">Returns the metadata from a merged assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ecf79-104">구문</span><span class="sxs-lookup"><span data-stu-id="ecf79-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyImageMetadata(  
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ecf79-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ecf79-105">Parameters</span></span>  
 `ppMemoryBuffer`  
 <span data-ttu-id="ecf79-106">[out] 주소에 대 한 포인터는 [ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) 병합 된 어셈블리의 메타 데이터의 주소와 크기에 대 한 정보를 포함 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="ecf79-106">[out] A pointer to the address of an [ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) object that contains information about the size and address of the merged assembly's metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ecf79-107">설명</span><span class="sxs-lookup"><span data-stu-id="ecf79-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ecf79-108">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ecf79-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ecf79-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ecf79-109">Requirements</span></span>  
 <span data-ttu-id="ecf79-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ecf79-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ecf79-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ecf79-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ecf79-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ecf79-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ecf79-113">**.NET framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ecf79-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecf79-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ecf79-114">See Also</span></span>  
 [<span data-ttu-id="ecf79-115">ICorDebugSymbolProvider 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ecf79-115">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)  
 [<span data-ttu-id="ecf79-116">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ecf79-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
