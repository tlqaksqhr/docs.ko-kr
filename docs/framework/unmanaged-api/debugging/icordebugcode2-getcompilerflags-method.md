---
title: "ICorDebugCode2::GetCompilerFlags 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugCode2.GetCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode2::GetCompilerFlags
helpviewer_keywords:
- GetCompilerFlags method [.NET Framework debugging]
- ICorDebugCode2::GetCompilerFlags method [.NET Framework debugging]
ms.assetid: 532e9dfd-d114-4c75-b952-1accce102643
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b0e8d36b3551b3520213e1c2ffa7e2d215e8535b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugcode2getcompilerflags-method"></a><span data-ttu-id="de637-102">ICorDebugCode2::GetCompilerFlags 메서드</span><span class="sxs-lookup"><span data-stu-id="de637-102">ICorDebugCode2::GetCompilerFlags Method</span></span>
<span data-ttu-id="de637-103">이 코드 개체의 중 하나에서 적시 (JIT)의 컴파일 또는 네이티브 이미지 생성기 (Ngen.exe)를 사용 하 여 생성 되었습니다는 조건을 지정 하는 플래그를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="de637-103">Gets the flags that specify the conditions under which this code object was either just-in-time (JIT) compiled or generated using the native image generator (Ngen.exe).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de637-104">구문</span><span class="sxs-lookup"><span data-stu-id="de637-104">Syntax</span></span>  
  
```  
HRESULT GetCompilerFlags (  
    [out] DWORD *pdwFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="de637-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="de637-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="de637-106">[out] 값에 대 한 포인터는 [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) JIT 컴파일러 또는 네이티브 이미지 생성기의 동작을 지정 하는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="de637-106">[out] A pointer to a value of the [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeration that specifies the behavior of the JIT compiler or the native image generator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de637-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="de637-107">Requirements</span></span>  
 <span data-ttu-id="de637-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="de637-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de637-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="de637-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="de637-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="de637-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="de637-111">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de637-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de637-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="de637-112">See Also</span></span>  
 
