---
title: "ISymUnmanagedWriter::DefineGlobalVariable 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.DefineGlobalVariable
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::DefineGlobalVariable
helpviewer_keywords:
- ISymUnmanagedWriter::DefineGlobalVariable method [.NET Framework debugging]
- DefineGlobalVariable method [.NET Framework debugging]
ms.assetid: 843c904a-8176-4d8f-bd47-b4d4c29f4c5c
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 7540dfcefbe7a331a26220a07b2e206c1302ddc8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedwriterdefineglobalvariable-method"></a><span data-ttu-id="28586-102">ISymUnmanagedWriter::DefineGlobalVariable 메서드</span><span class="sxs-lookup"><span data-stu-id="28586-102">ISymUnmanagedWriter::DefineGlobalVariable Method</span></span>
<span data-ttu-id="28586-103">단일 전역 변수를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="28586-103">Defines a single global variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28586-104">구문</span><span class="sxs-lookup"><span data-stu-id="28586-104">Syntax</span></span>  
  
```  
HRESULT DefineGlobalVariable(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      cSig,  
    [in, size_is(cSig)] unsigned char signature[],  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="28586-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="28586-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="28586-106">[in] 에 대 한 포인터는 `WCHAR` 전역 변수 이름을 정의 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="28586-106">[in] A pointer to a `WCHAR` that defines the global variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="28586-107">[in] 전역 변수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="28586-107">[in] The global variable attributes.</span></span>  
  
 `cSig`  
 <span data-ttu-id="28586-108">[in] A `ULONG32` 의 크기를 문자 단위로 나타내는 `signature` 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="28586-108">[in] A `ULONG32` that indicates the size, in characters, of the `signature` buffer.</span></span>  
  
 `signature`  
 <span data-ttu-id="28586-109">[in] 전역 변수 시그니처입니다.</span><span class="sxs-lookup"><span data-stu-id="28586-109">[in] The global variable signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="28586-110">[in] 주소 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="28586-110">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="28586-111">[in] 매개 변수 사양에 대 한 첫 번째 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="28586-111">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="28586-112">[in] 매개 변수 사양에 대 한 두 번째 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="28586-112">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="28586-113">[in] 매개 변수 사양에 대 한 세 번째 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="28586-113">[in] The third address for the parameter specification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="28586-114">반환 값</span><span class="sxs-lookup"><span data-stu-id="28586-114">Return Value</span></span>  
 <span data-ttu-id="28586-115">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="28586-115">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28586-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="28586-116">Requirements</span></span>  
 <span data-ttu-id="28586-117">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="28586-117">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28586-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="28586-118">See Also</span></span>  
 [<span data-ttu-id="28586-119">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="28586-119">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [<span data-ttu-id="28586-120">DefineLocalVariable 메서드</span><span class="sxs-lookup"><span data-stu-id="28586-120">DefineLocalVariable Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definelocalvariable-method.md)  
 [<span data-ttu-id="28586-121">DefineGlobalVariable2 메서드</span><span class="sxs-lookup"><span data-stu-id="28586-121">DefineGlobalVariable2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-defineglobalvariable2-method.md)
