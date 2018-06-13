---
title: ICorDebugHeapValue2::CreateHandle 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue2.CreateHandle
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue2::CreateHandle
helpviewer_keywords:
- CreateHandle method [.NET Framework debugging]
- ICorDebugHeapValue2::CreateHandle method [.NET Framework debugging]
ms.assetid: fbc418e8-fa22-420d-84ec-e0e1800db041
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c69d1f83a4591df4d2dcb7fb9724fa582ea28387
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413581"
---
# <a name="icordebugheapvalue2createhandle-method"></a><span data-ttu-id="111d8-102">ICorDebugHeapValue2::CreateHandle 메서드</span><span class="sxs-lookup"><span data-stu-id="111d8-102">ICorDebugHeapValue2::CreateHandle Method</span></span>
<span data-ttu-id="111d8-103">ICorDebugHeapValue2 개체가 나타내는 힙 값에 대 한 지정 된 형식의 핸들을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="111d8-103">Creates a handle of the specified type for the heap value represented by this ICorDebugHeapValue2 object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="111d8-104">구문</span><span class="sxs-lookup"><span data-stu-id="111d8-104">Syntax</span></span>  
  
```  
HRESULT CreateHandle (  
    [in] CorDebugHandleType      type,   
    [out] ICorDebugHandleValue   **ppHandle  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="111d8-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="111d8-105">Parameters</span></span>  
 `type`  
 <span data-ttu-id="111d8-106">[in] 만들 수에 대 한 핸들의 형식을 지정 하는 CorDebugHandleType 열거형의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="111d8-106">[in] A value of the CorDebugHandleType enumeration that specifies the type of handle to be created.</span></span>  
  
 `ppHandle`  
 <span data-ttu-id="111d8-107">[out] 이 힙 값에 대 한 새 핸들을 나타내는 ICorDebugHandleValue 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="111d8-107">[out] A pointer to the address of an ICorDebugHandleValue object that represents the new handle for this heap value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="111d8-108">설명</span><span class="sxs-lookup"><span data-stu-id="111d8-108">Remarks</span></span>  
 <span data-ttu-id="111d8-109">핸들 힙 값와 연결 된 응용 프로그램 도메인에서 만들어지고 응용 프로그램 도메인이 언로드되면 무효화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="111d8-109">The handle will be created in the application domain that is associated with the heap value, and will become invalid if the application domain gets unloaded.</span></span>  
  
 <span data-ttu-id="111d8-110">동일한 힙 값에 대해이 함수를 여러 번 호출에 여러 개의 핸들이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="111d8-110">Multiple calls to this function for the same heap value will create multiple handles.</span></span> <span data-ttu-id="111d8-111">핸들에는 가비지 수집기의 성능에 영향을 하기 때문에 디버거 자체에 상대적으로 적은 수의 한 번에 활성화 된 핸들이 약 256 개로 제한 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="111d8-111">Because handles affect the performance of the garbage collector, the debugger should limit itself to a relatively small number of handles (about 256) that are active at a time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="111d8-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="111d8-112">Requirements</span></span>  
 <span data-ttu-id="111d8-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="111d8-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="111d8-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="111d8-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="111d8-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="111d8-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="111d8-116">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="111d8-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
