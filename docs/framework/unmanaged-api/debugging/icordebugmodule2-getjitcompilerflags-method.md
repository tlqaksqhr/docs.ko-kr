---
title: ICorDebugModule2::GetJITCompilerFlags 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugModule2.GetJITCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2::GetJITCompilerFlags
helpviewer_keywords:
- GetJITCompilerFlags method [.NET Framework debugging]
- ICorDebugModule2::GetJITCompilerFlags method [.NET Framework debugging]
ms.assetid: 7212d9f4-989b-44e3-b8d4-ffc35922f6a0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4bb275f08143362d62f241ea659ea39ff8eef5d0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413084"
---
# <a name="icordebugmodule2getjitcompilerflags-method"></a><span data-ttu-id="64e87-102">ICorDebugModule2::GetJITCompilerFlags 메서드</span><span class="sxs-lookup"><span data-stu-id="64e87-102">ICorDebugModule2::GetJITCompilerFlags Method</span></span>
<span data-ttu-id="64e87-103">이 ICorDebugModule2의 컴파일 타임 JIT ()를 제어 하는 플래그를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="64e87-103">Gets the flags that control the just-in-time (JIT) compilation of this ICorDebugModule2.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64e87-104">구문</span><span class="sxs-lookup"><span data-stu-id="64e87-104">Syntax</span></span>  
  
```  
HRESULT GetJITCompilerFlags (  
    [out] DWORD   *pdwFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="64e87-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="64e87-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="64e87-106">[out] 값에 대 한 포인터는 [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) JIT 컴파일을 제어 하는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="64e87-106">[out] A pointer to a value of the [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeration that controls the JIT compilation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64e87-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="64e87-107">Requirements</span></span>  
 <span data-ttu-id="64e87-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="64e87-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64e87-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="64e87-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="64e87-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="64e87-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="64e87-111">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64e87-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
