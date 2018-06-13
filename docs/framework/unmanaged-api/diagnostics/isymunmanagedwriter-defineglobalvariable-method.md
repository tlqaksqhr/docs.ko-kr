---
title: ISymUnmanagedWriter::DefineGlobalVariable 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineGlobalVariable
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineGlobalVariable
helpviewer_keywords:
- ISymUnmanagedWriter::DefineGlobalVariable method [.NET Framework debugging]
- DefineGlobalVariable method [.NET Framework debugging]
ms.assetid: 843c904a-8176-4d8f-bd47-b4d4c29f4c5c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f1dd657c004c58480ea2f603ad4494753463c79b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33428447"
---
# <a name="isymunmanagedwriterdefineglobalvariable-method"></a><span data-ttu-id="d7fe2-102">ISymUnmanagedWriter::DefineGlobalVariable 메서드</span><span class="sxs-lookup"><span data-stu-id="d7fe2-102">ISymUnmanagedWriter::DefineGlobalVariable Method</span></span>
<span data-ttu-id="d7fe2-103">단일 전역 변수를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7fe2-103">Defines a single global variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7fe2-104">구문</span><span class="sxs-lookup"><span data-stu-id="d7fe2-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="d7fe2-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d7fe2-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="d7fe2-106">[in] 에 대 한 포인터는 `WCHAR` 전역 변수 이름을 정의 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7fe2-106">[in] A pointer to a `WCHAR` that defines the global variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="d7fe2-107">[in] 전역 변수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="d7fe2-107">[in] The global variable attributes.</span></span>  
  
 `cSig`  
 <span data-ttu-id="d7fe2-108">[in] A `ULONG32` 의 크기를 문자 단위로 나타내는 `signature` 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="d7fe2-108">[in] A `ULONG32` that indicates the size, in characters, of the `signature` buffer.</span></span>  
  
 `signature`  
 <span data-ttu-id="d7fe2-109">[in] 전역 변수 시그니처입니다.</span><span class="sxs-lookup"><span data-stu-id="d7fe2-109">[in] The global variable signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="d7fe2-110">[in] 주소 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="d7fe2-110">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="d7fe2-111">[in] 매개 변수 사양에 대 한 첫 번째 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="d7fe2-111">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="d7fe2-112">[in] 매개 변수 사양에 대 한 두 번째 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="d7fe2-112">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="d7fe2-113">[in] 매개 변수 사양에 대 한 세 번째 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="d7fe2-113">[in] The third address for the parameter specification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d7fe2-114">반환 값</span><span class="sxs-lookup"><span data-stu-id="d7fe2-114">Return Value</span></span>  
 <span data-ttu-id="d7fe2-115">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="d7fe2-115">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7fe2-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d7fe2-116">Requirements</span></span>  
 <span data-ttu-id="d7fe2-117">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d7fe2-117">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7fe2-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d7fe2-118">See Also</span></span>  
 [<span data-ttu-id="d7fe2-119">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d7fe2-119">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [<span data-ttu-id="d7fe2-120">DefineLocalVariable 메서드</span><span class="sxs-lookup"><span data-stu-id="d7fe2-120">DefineLocalVariable Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definelocalvariable-method.md)  
 [<span data-ttu-id="d7fe2-121">DefineGlobalVariable2 메서드</span><span class="sxs-lookup"><span data-stu-id="d7fe2-121">DefineGlobalVariable2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-defineglobalvariable2-method.md)
