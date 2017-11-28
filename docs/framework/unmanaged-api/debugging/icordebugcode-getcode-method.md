---
title: "ICorDebugCode::GetCode 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugCode.GetCode
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugCode::GetCode
helpviewer_keywords:
- ICorDebugCode::GetCode method [.NET Framework debugging]
- GetCode method, ICorDebugCode interface [.NET Framework debugging]
ms.assetid: 7137e3d1-1dad-48d8-8c37-16ac816534d3
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 12820d0be725c92754640aaa4eebca56bbc33ab6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugcodegetcode-method"></a><span data-ttu-id="236bc-102">ICorDebugCode::GetCode 메서드</span><span class="sxs-lookup"><span data-stu-id="236bc-102">ICorDebugCode::GetCode Method</span></span>
<span data-ttu-id="236bc-103">디스어셈블리로 설정 된 지정된 된 함수에 대 한 모든 코드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="236bc-103">Gets all the code for the specified function, formatted for disassembly.</span></span> <span data-ttu-id="236bc-104">이 메서드는.NET Framework 버전 2.0에서에서 사용 되지 합니다.</span><span class="sxs-lookup"><span data-stu-id="236bc-104">This method has been deprecated in the .NET Framework version 2.0.</span></span> <span data-ttu-id="236bc-105">사용 하 여 [icordebugcode2:: Getcodechunks](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md) 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="236bc-105">Use [ICorDebugCode2::GetCodeChunks](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md) instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="236bc-106">구문</span><span class="sxs-lookup"><span data-stu-id="236bc-106">Syntax</span></span>  
  
```  
HRESULT GetCode (  
    [in] ULONG32     startOffset,   
    [in] ULONG32     endOffset,  
    [in] ULONG32     cBufferAlloc,  
    [out, size_is(cBufferAlloc),  
        length_is(*pcBufferSize)] BYTE buffer[],  
    [out] ULONG32    *pcBufferSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="236bc-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="236bc-107">Parameters</span></span>  
 `startOffset`  
 <span data-ttu-id="236bc-108">[in] 오프셋은 함수의 시작 부분입니다.</span><span class="sxs-lookup"><span data-stu-id="236bc-108">[in] The offset of the beginning of the function.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="236bc-109">[in] 함수의 끝의 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="236bc-109">[in] The offset of the end of the function.</span></span>  
  
 `cBufferAlloc`  
 <span data-ttu-id="236bc-110">[in] 크기는 `buffer` 배열에 코드가 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="236bc-110">[in] The size of the `buffer` array into which the code will be returned.</span></span>  
  
 `buffer`  
 <span data-ttu-id="236bc-111">[out] 코드가 반환 하는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="236bc-111">[out] The array into which the code will be returned.</span></span>  
  
 `pcBufferSize`  
 <span data-ttu-id="236bc-112">[out] 반환 된 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="236bc-112">[out] The number of bytes returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="236bc-113">설명</span><span class="sxs-lookup"><span data-stu-id="236bc-113">Remarks</span></span>  
 <span data-ttu-id="236bc-114">여러 개의 청크로 나뉘어진 함수의 코드, 네이티브 오프셋의 오름차순에 연결 되며 됩니다.</span><span class="sxs-lookup"><span data-stu-id="236bc-114">If the function's code has been divided into multiple chunks, they are concatenated in order of increasing native offset.</span></span> <span data-ttu-id="236bc-115">명령 경계를 확인 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="236bc-115">Instruction boundaries are not checked.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="236bc-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="236bc-116">Requirements</span></span>  
 <span data-ttu-id="236bc-117">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="236bc-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="236bc-118">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="236bc-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="236bc-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="236bc-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="236bc-120">**.NET framework 버전:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="236bc-120">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="236bc-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="236bc-121">See Also</span></span>  
 [<span data-ttu-id="236bc-122">GetCodeChunks 메서드</span><span class="sxs-lookup"><span data-stu-id="236bc-122">GetCodeChunks Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md)  
 
