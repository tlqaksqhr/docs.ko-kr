---
title: "ISymUnmanagedWriter::DefineConstant 메서드"
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
- ISymUnmanagedWriter.DefineConstant
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineConstant
helpviewer_keywords:
- DefineConstant method [.NET Framework debugging]
- ISymUnmanagedWriter::DefineConstant method [.NET Framework debugging]
ms.assetid: 9e986986-2223-4d5f-b040-85d716146924
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9b22b0d9c9de27ba9950a0501193bc682586bfbc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriterdefineconstant-method"></a><span data-ttu-id="e837c-102">ISymUnmanagedWriter::DefineConstant 메서드</span><span class="sxs-lookup"><span data-stu-id="e837c-102">ISymUnmanagedWriter::DefineConstant Method</span></span>
<span data-ttu-id="e837c-103">상수 값에 대 한 이름을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="e837c-103">Defines a name for a constant value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e837c-104">구문</span><span class="sxs-lookup"><span data-stu-id="e837c-104">Syntax</span></span>  
  
```  
HRESULT DefineConstant(  
    [in] const WCHAR *name,  
    [in] VARIANT value,  
    [in] ULONG32 cSig,  
    [in, size_is(cSig)] unsigned char signature[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e837c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e837c-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="e837c-106">[in] 에 대 한 포인터는 `WCHAR` 상수 이름을 정의 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="e837c-106">[in] A pointer to a `WCHAR` that defines the constant name.</span></span>  
  
 `value`  
 <span data-ttu-id="e837c-107">[in] 상수의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="e837c-107">[in] The value of the constant.</span></span>  
  
 `cSig`  
 <span data-ttu-id="e837c-108">[in] `signature` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="e837c-108">[in] The size of the `signature` array.</span></span>  
  
 `signature`  
 <span data-ttu-id="e837c-109">[in] 상수에 대 한 형식 서명입니다.</span><span class="sxs-lookup"><span data-stu-id="e837c-109">[in] The type signature for the constant.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e837c-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="e837c-110">Return Value</span></span>  
 <span data-ttu-id="e837c-111">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="e837c-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e837c-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e837c-112">Requirements</span></span>  
 <span data-ttu-id="e837c-113">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e837c-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e837c-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e837c-114">See Also</span></span>  
 [<span data-ttu-id="e837c-115">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e837c-115">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [<span data-ttu-id="e837c-116">DefineConstant2 메서드</span><span class="sxs-lookup"><span data-stu-id="e837c-116">DefineConstant2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-defineconstant2-method.md)
