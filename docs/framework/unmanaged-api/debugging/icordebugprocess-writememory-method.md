---
title: "ICorDebugProcess::WriteMemory 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess.WriteMemory
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess::WriteMemory
helpviewer_keywords:
- ICorDebugProcess::WriteMemory method [.NET Framework debugging]
- WriteMemory method [.NET Framework debugging]
ms.assetid: d5c07d86-045d-4391-893b-0bcd2959f90e
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 053c6bf5f451377308f4defbeb6eff9525c4332e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugprocesswritememory-method"></a><span data-ttu-id="77fd8-102">ICorDebugProcess::WriteMemory 메서드</span><span class="sxs-lookup"><span data-stu-id="77fd8-102">ICorDebugProcess::WriteMemory Method</span></span>
<span data-ttu-id="77fd8-103">이 프로세스의 메모리 영역에 데이터를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="77fd8-103">Writes data to an area of memory in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77fd8-104">구문</span><span class="sxs-lookup"><span data-stu-id="77fd8-104">Syntax</span></span>  
  
```  
HRESULT WriteMemory(  
    [in]  CORDB_ADDRESS address,  
    [in]  DWORD size,  
    [in, size_is(size)] BYTE buffer[],  
    [out] SIZE_T *written);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="77fd8-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="77fd8-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="77fd8-106">[in] A `CORDB_ADDRESS` 는 메모리 영역을 데이터의 기본 주소 값이 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="77fd8-106">[in] A `CORDB_ADDRESS` value that is the base address of the memory area to which data is written.</span></span> <span data-ttu-id="77fd8-107">데이터 전송 발생 하기 전에 시스템 기본 주소에서 시작 하 고 지정된 된 크기의 메모리 영역에 쓰기 위해 액세스할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="77fd8-107">Before data transfer occurs, the system verifies that the memory area of the specified size, beginning at the base address, is accessible for writing.</span></span> <span data-ttu-id="77fd8-108">액세스할 수 없는 경우 메서드가 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="77fd8-108">If it is not accessible, the method fails.</span></span>  
  
 `size`  
 <span data-ttu-id="77fd8-109">[in] 메모리 영역에 쓸 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="77fd8-109">[in] The number of bytes to be written to the memory area.</span></span>  
  
 `buffer`  
 <span data-ttu-id="77fd8-110">[in] 쓸 데이터를 포함 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="77fd8-110">[in] A buffer that contains data to be written.</span></span>  
  
 `written`  
 <span data-ttu-id="77fd8-111">[out] 이 프로세스에서 메모리 영역에 쓴 바이트 수를 받는 변수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="77fd8-111">[out] A pointer to a variable that receives the number of bytes written to the memory area in this process.</span></span> <span data-ttu-id="77fd8-112">경우 `written` 가 null 인 경우이 매개 변수는 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="77fd8-112">If `written` is NULL, this parameter is ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="77fd8-113">설명</span><span class="sxs-lookup"><span data-stu-id="77fd8-113">Remarks</span></span>  
 <span data-ttu-id="77fd8-114">데이터는 중단점 뒤 자동으로 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="77fd8-114">Data is automatically written behind any breakpoints.</span></span> <span data-ttu-id="77fd8-115">.NET Framework 버전 2.0, 네이티브 디버거 명령 스트림에 중단점을 삽입할이 메서드를 사용 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77fd8-115">In the .NET Framework version 2.0, native debuggers should not use this method to inject breakpoints into the instruction stream.</span></span> <span data-ttu-id="77fd8-116">사용 하 여 [icordebugprocess2:: Setunmanagedbreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md) 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="77fd8-116">Use [ICorDebugProcess2::SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md) instead.</span></span>  
  
 <span data-ttu-id="77fd8-117">`WriteMemory` 메서드는 관리 코드 외에 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77fd8-117">The `WriteMemory` method should be used only outside of managed code.</span></span> <span data-ttu-id="77fd8-118">이 메서드는 제대로 사용 하지 않으면 런타임을 손상 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77fd8-118">This method can corrupt the runtime if used improperly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77fd8-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="77fd8-119">Requirements</span></span>  
 <span data-ttu-id="77fd8-120">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="77fd8-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77fd8-121">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="77fd8-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="77fd8-122">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="77fd8-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="77fd8-123">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77fd8-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
