---
title: "ISymUnmanagedWriter::DefineLocalVariable 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.DefineLocalVariable
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::DefineLocalVariable
helpviewer_keywords:
- ISymUnmanagedWriter::DefineLocalVariable method [.NET Framework debugging]
- DefineLocalVariable method [.NET Framework debugging]
ms.assetid: 6fab8a58-3883-490f-8b27-64042c90f104
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e454aa2c2dd8ceb8f8dbbc03bdd1e70e8a800de2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedwriterdefinelocalvariable-method"></a><span data-ttu-id="10871-102">ISymUnmanagedWriter::DefineLocalVariable 메서드</span><span class="sxs-lookup"><span data-stu-id="10871-102">ISymUnmanagedWriter::DefineLocalVariable Method</span></span>
<span data-ttu-id="10871-103">현재 어휘 범위에 단일 변수를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="10871-103">Defines a single variable in the current lexical scope.</span></span> <span data-ttu-id="10871-104">이 메서드는 범위에 걸쳐 홈이 여러 개 있는 동일한 이름의 변수에 대 한 여러 번 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10871-104">This method can be called multiple times for a variable of the same name that has multiple homes throughout a scope.</span></span> <span data-ttu-id="10871-105">그러나이 경우의 값은 `startOffset` 및 `endOffset` 매개 변수는 겹치지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="10871-105">In this case, however, the values of the `startOffset` and `endOffset` parameters must not overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10871-106">구문</span><span class="sxs-lookup"><span data-stu-id="10871-106">Syntax</span></span>  
  
```  
HRESULT DefineLocalVariable(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      cSig,  
    [in, size_is(cSig)] unsigned char signature[],  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3,  
    [in] ULONG32      startOffset,  
    [in] ULONG32      endOffset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="10871-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="10871-107">Parameters</span></span>  
 `name`  
 <span data-ttu-id="10871-108">[in] 에 대 한 포인터는 `WCHAR` name 지역 변수를 정의 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="10871-108">[in] A pointer to a `WCHAR` that defines the local variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="10871-109">[in] 지역 변수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="10871-109">[in] The local variable attributes.</span></span>  
  
 `cSig`  
 <span data-ttu-id="10871-110">[in] A `ULONG32` 의 크기를 바이트 단위로 나타내는 `signature` 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="10871-110">[in] A `ULONG32` that indicates the size, in bytes, of the `signature` buffer.</span></span>  
  
 `signature`  
 <span data-ttu-id="10871-111">[in] 지역 변수 시그니처입니다.</span><span class="sxs-lookup"><span data-stu-id="10871-111">[in] The local variable signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="10871-112">[in] 주소 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="10871-112">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="10871-113">[in] 매개 변수 사양에 대 한 첫 번째 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="10871-113">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="10871-114">[in] 매개 변수 사양에 대 한 두 번째 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="10871-114">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="10871-115">[in] 매개 변수 사양에 대 한 세 번째 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="10871-115">[in] The third address for the parameter specification.</span></span>  
  
 `startOffset`  
 <span data-ttu-id="10871-116">[in] 변수의 시작 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="10871-116">[in] The start offset for the variable.</span></span> <span data-ttu-id="10871-117">이 매개 변수는 선택적 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="10871-117">This parameter is optional.</span></span> <span data-ttu-id="10871-118">0 이면이 매개 변수가 무시 되 고 변수에 전체 범위에서 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="10871-118">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="10871-119">0이 아닌 값 이면 변수는 현재 범위의 오프셋 내에 속합니다.</span><span class="sxs-lookup"><span data-stu-id="10871-119">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="10871-120">[in] 변수의 끝 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="10871-120">[in] The end offset for the variable.</span></span> <span data-ttu-id="10871-121">이 매개 변수는 선택적 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="10871-121">This parameter is optional.</span></span> <span data-ttu-id="10871-122">0 이면이 매개 변수가 무시 되 고 변수에 전체 범위에서 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="10871-122">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="10871-123">0이 아닌 값 이면 변수는 현재 범위의 오프셋 내에 속합니다.</span><span class="sxs-lookup"><span data-stu-id="10871-123">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="10871-124">반환 값</span><span class="sxs-lookup"><span data-stu-id="10871-124">Return Value</span></span>  
 <span data-ttu-id="10871-125">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="10871-125">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10871-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="10871-126">Requirements</span></span>  
 <span data-ttu-id="10871-127">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="10871-127">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10871-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="10871-128">See Also</span></span>  
 [<span data-ttu-id="10871-129">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="10871-129">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [<span data-ttu-id="10871-130">DefineGlobalVariable 메서드</span><span class="sxs-lookup"><span data-stu-id="10871-130">DefineGlobalVariable Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineglobalvariable-method.md)  
 [<span data-ttu-id="10871-131">DefineLocalVariable2 메서드</span><span class="sxs-lookup"><span data-stu-id="10871-131">DefineLocalVariable2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-definelocalvariable2-method.md)
