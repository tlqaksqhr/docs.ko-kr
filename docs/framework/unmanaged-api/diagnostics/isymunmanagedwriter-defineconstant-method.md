---
title: "ISymUnmanagedWriter::DefineConstant 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.DefineConstant
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::DefineConstant
helpviewer_keywords:
- DefineConstant method [.NET Framework debugging]
- ISymUnmanagedWriter::DefineConstant method [.NET Framework debugging]
ms.assetid: 9e986986-2223-4d5f-b040-85d716146924
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 910f2e753849b955a398f2175342b2f94849fba6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedwriterdefineconstant-method"></a><span data-ttu-id="e694b-102">ISymUnmanagedWriter::DefineConstant 메서드</span><span class="sxs-lookup"><span data-stu-id="e694b-102">ISymUnmanagedWriter::DefineConstant Method</span></span>
<span data-ttu-id="e694b-103">상수 값에 대 한 이름을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="e694b-103">Defines a name for a constant value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e694b-104">구문</span><span class="sxs-lookup"><span data-stu-id="e694b-104">Syntax</span></span>  
  
```  
HRESULT DefineConstant(  
    [in] const WCHAR *name,  
    [in] VARIANT value,  
    [in] ULONG32 cSig,  
    [in, size_is(cSig)] unsigned char signature[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e694b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e694b-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="e694b-106">[in] 에 대 한 포인터는 `WCHAR` 상수 이름을 정의 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="e694b-106">[in] A pointer to a `WCHAR` that defines the constant name.</span></span>  
  
 `value`  
 <span data-ttu-id="e694b-107">[in] 상수의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="e694b-107">[in] The value of the constant.</span></span>  
  
 `cSig`  
 <span data-ttu-id="e694b-108">[in] `signature` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="e694b-108">[in] The size of the `signature` array.</span></span>  
  
 `signature`  
 <span data-ttu-id="e694b-109">[in] 상수에 대 한 형식 서명입니다.</span><span class="sxs-lookup"><span data-stu-id="e694b-109">[in] The type signature for the constant.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e694b-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="e694b-110">Return Value</span></span>  
 <span data-ttu-id="e694b-111">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="e694b-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e694b-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e694b-112">Requirements</span></span>  
 <span data-ttu-id="e694b-113">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e694b-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e694b-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e694b-114">See Also</span></span>  
 [<span data-ttu-id="e694b-115">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e694b-115">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [<span data-ttu-id="e694b-116">DefineConstant2 메서드</span><span class="sxs-lookup"><span data-stu-id="e694b-116">DefineConstant2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-defineconstant2-method.md)
