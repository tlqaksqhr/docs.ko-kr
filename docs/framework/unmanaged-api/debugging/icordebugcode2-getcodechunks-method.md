---
title: ICorDebugCode2::GetCodeChunks 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugCode2.GetCodeChunks
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode2::GetCodeChunks
helpviewer_keywords:
- GetCodeChunks method [.NET Framework debugging]
- ICorDebugCode2::GetCodeChunks method [.NET Framework debugging]
ms.assetid: 210a2f02-2678-4555-bc4a-78a0408764c8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bdfcd45b15ddc1491b12de0fa42901b6d3f7fe9b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413155"
---
# <a name="icordebugcode2getcodechunks-method"></a><span data-ttu-id="0bdbe-102">ICorDebugCode2::GetCodeChunks 메서드</span><span class="sxs-lookup"><span data-stu-id="0bdbe-102">ICorDebugCode2::GetCodeChunks Method</span></span>
<span data-ttu-id="0bdbe-103">이 코드 개체를 구성 하는 코드 청크를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0bdbe-103">Gets the chunks of code that this code object is composed of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0bdbe-104">구문</span><span class="sxs-lookup"><span data-stu-id="0bdbe-104">Syntax</span></span>  
  
```  
HRESULT GetCodeChunks (  
    [in]  ULONG32     cbufSize,  
    [out] ULONG32     *pcnumChunks,  
    [out, size_is(cbufSize), length_is(*pcnumChunks)]   
        CodeChunkInfo chunks[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0bdbe-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0bdbe-105">Parameters</span></span>  
 `cbufSize`  
 <span data-ttu-id="0bdbe-106">[in] 크기는 `chunks` 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="0bdbe-106">[in] Size of the `chunks` array.</span></span>  
  
 `pcnumChunks`  
 <span data-ttu-id="0bdbe-107">[out] 반환 된 청크 수는 `chunks` 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="0bdbe-107">[out] The number of chunks returned in the `chunks` array.</span></span>  
  
 `chunks`  
 <span data-ttu-id="0bdbe-108">[out] 단일 코드 청크를 각각 나타내는 "CodeChunkInfo" 구조의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="0bdbe-108">[out] An array of "CodeChunkInfo" structures, each of which represents a single chunk of code.</span></span> <span data-ttu-id="0bdbe-109">하는 경우의 값 `cbufSize` 가 0 이면이 매개 변수는 null 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bdbe-109">If the value of `cbufSize` is 0, this parameter can be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0bdbe-110">설명</span><span class="sxs-lookup"><span data-stu-id="0bdbe-110">Remarks</span></span>  
 <span data-ttu-id="0bdbe-111">코드 청크는 되지 나타나고, 순서는 것은 연결 된 여 따를 [icordebugcode:: Getcode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getcode-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0bdbe-111">The code chunks will never overlap, and they will follow the order in which they would have been concatenated by [ICorDebugCode::GetCode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getcode-method.md).</span></span> <span data-ttu-id="0bdbe-112">.NET Framework 버전 2.0에서에서 Microsoft MSIL (intermediate language) 코드 개체를 구성 하는 단일 코드 청크 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bdbe-112">A Microsoft intermediate language (MSIL) code object in the .NET Framework version 2.0 will comprise a single code chunk.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0bdbe-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0bdbe-113">Requirements</span></span>  
 <span data-ttu-id="0bdbe-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0bdbe-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0bdbe-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0bdbe-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0bdbe-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0bdbe-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0bdbe-117">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0bdbe-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bdbe-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0bdbe-118">See Also</span></span>  
 
