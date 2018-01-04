---
title: "ICorDebugSymbolProvider::GetAssemblyImageBytes 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 3db215aa-e180-4f70-8d23-6d5a0ffbc8e5
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 23c6dc836aefe1dd89431e003058ba2056eba3ff
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugsymbolprovidergetassemblyimagebytes-method"></a><span data-ttu-id="cf9b7-102">ICorDebugSymbolProvider::GetAssemblyImageBytes 메서드</span><span class="sxs-lookup"><span data-stu-id="cf9b7-102">ICorDebugSymbolProvider::GetAssemblyImageBytes Method</span></span>
<span data-ttu-id="cf9b7-103">병합된 어셈블리의 RVA(상대 가상 주소)가 지정된 경우 병합된 어셈블리에서 데이터를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="cf9b7-103">Reads data from a merged assembly given a relative virtual address (RVA) in the merged assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf9b7-104">구문</span><span class="sxs-lookup"><span data-stu-id="cf9b7-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyImageBytes(  
   [in] CORDB_ADDRESS rva,   
   [in] ULONG32 length,   
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cf9b7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cf9b7-105">Parameters</span></span>  
 `rva`  
 <span data-ttu-id="cf9b7-106">[in] 병합된 어셈블리의 RVA(상대 가상 주소)입니다.</span><span class="sxs-lookup"><span data-stu-id="cf9b7-106">[in] A relative virtual address (RVA) in a merged assembly.</span></span>  
  
 `length`  
 <span data-ttu-id="cf9b7-107">병합된 어셈블리에서 읽을 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="cf9b7-107">The number of bytes to read from the merged assembly.</span></span>  
  
 `ppMemoryBuffer`  
 <span data-ttu-id="cf9b7-108">주소에 대 한 포인터는 [ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) 병합 된 어셈블리 메타 데이터가 있는 메모리 버퍼에 대 한 정보를 포함 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="cf9b7-108">A pointer to the address of an [ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) object that contains information about the memory buffer with merged assembly metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cf9b7-109">설명</span><span class="sxs-lookup"><span data-stu-id="cf9b7-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cf9b7-110">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf9b7-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf9b7-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cf9b7-111">Requirements</span></span>  
 <span data-ttu-id="cf9b7-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="cf9b7-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf9b7-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cf9b7-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cf9b7-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cf9b7-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cf9b7-115">**.NET framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf9b7-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf9b7-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cf9b7-116">See Also</span></span>  
 [<span data-ttu-id="cf9b7-117">ICorDebugSymbolProvider 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cf9b7-117">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)  
 [<span data-ttu-id="cf9b7-118">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cf9b7-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
