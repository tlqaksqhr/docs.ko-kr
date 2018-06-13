---
title: ISymUnmanagedWriter2::DefineLocalVariable2 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter2.DefineLocalVariable2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter2::DefineLocalVariable2
helpviewer_keywords:
- ISymUnmanagedWriter2::DefineLocalVariable2 method [.NET Framework debugging]
- DefineLocalVariable2 method [.NET Framework debugging]
ms.assetid: e774eefe-858c-4362-8d2d-28ebf2ba1a24
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 53f02499bbc64f1502951ff9fbf16a848e77f0ca
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33430810"
---
# <a name="isymunmanagedwriter2definelocalvariable2-method"></a><span data-ttu-id="3b2e4-102">ISymUnmanagedWriter2::DefineLocalVariable2 메서드</span><span class="sxs-lookup"><span data-stu-id="3b2e4-102">ISymUnmanagedWriter2::DefineLocalVariable2 Method</span></span>
<span data-ttu-id="3b2e4-103">현재 어휘 범위에 단일 변수를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="3b2e4-103">Defines a single variable in the current lexical scope.</span></span> <span data-ttu-id="3b2e4-104">이 메서드는 범위에 걸쳐 홈이 여러 개 있는 동일한 이름의 변수에 대 한 여러 번 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b2e4-104">This method can be called multiple times for a variable of the same name that has multiple homes throughout a scope.</span></span> <span data-ttu-id="3b2e4-105">그러나이 경우의 값은 `startOffset` 및 `endOffset` 매개 변수는 겹치지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b2e4-105">In this case, however, the values of the `startOffset` and `endOffset` parameters must not overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b2e4-106">구문</span><span class="sxs-lookup"><span data-stu-id="3b2e4-106">Syntax</span></span>  
  
```  
HRESULT DefineLocalVariable2(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] mdSignature  sigToken,  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3,  
    [in] ULONG32      startOffset,  
    [in] ULONG32      endOffset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3b2e4-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3b2e4-107">Parameters</span></span>  
 `name`  
 <span data-ttu-id="3b2e4-108">[in] 지역 변수 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="3b2e4-108">[in] The local variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="3b2e4-109">[in] 지역 변수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="3b2e4-109">[in] The local variable attributes.</span></span>  
  
 `sigToken`  
 <span data-ttu-id="3b2e4-110">[in] 서명의 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="3b2e4-110">[in] The metadata token of the signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="3b2e4-111">[in] 주소 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="3b2e4-111">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="3b2e4-112">[in] 매개 변수 사양에 대 한 첫 번째 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="3b2e4-112">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="3b2e4-113">[in] 매개 변수 사양에 대 한 두 번째 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="3b2e4-113">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="3b2e4-114">[in] 매개 변수 사양에 대 한 세 번째 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="3b2e4-114">[in] The third address for the parameter specification.</span></span>  
  
 `startOffset`  
 <span data-ttu-id="3b2e4-115">[in] 변수의 시작 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="3b2e4-115">[in] The start offset for the variable.</span></span> <span data-ttu-id="3b2e4-116">이 매개 변수는 선택적 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="3b2e4-116">This parameter is optional.</span></span> <span data-ttu-id="3b2e4-117">0 이면이 매개 변수가 무시 되 고 변수에 전체 범위에서 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b2e4-117">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="3b2e4-118">0이 아닌 값 이면 변수는 현재 범위의 오프셋 내에 속합니다.</span><span class="sxs-lookup"><span data-stu-id="3b2e4-118">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="3b2e4-119">[in] 변수의 끝 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="3b2e4-119">[in] The end offset for the variable.</span></span> <span data-ttu-id="3b2e4-120">이 매개 변수는 선택적 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="3b2e4-120">This parameter is optional.</span></span> <span data-ttu-id="3b2e4-121">0 이면이 매개 변수가 무시 되 고 변수에 전체 범위에서 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b2e4-121">If it is 0, this parameter is ignored and the variable is defined throughout the entire scope.</span></span> <span data-ttu-id="3b2e4-122">0이 아닌 값 이면 변수는 현재 범위의 오프셋 내에 속합니다.</span><span class="sxs-lookup"><span data-stu-id="3b2e4-122">If it is a nonzero value, the variable falls within the offsets of the current scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3b2e4-123">반환 값</span><span class="sxs-lookup"><span data-stu-id="3b2e4-123">Return Value</span></span>  
 <span data-ttu-id="3b2e4-124">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="3b2e4-124">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b2e4-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3b2e4-125">Requirements</span></span>  
 <span data-ttu-id="3b2e4-126">**헤더:** CorSym.idl</span><span class="sxs-lookup"><span data-stu-id="3b2e4-126">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b2e4-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3b2e4-127">See Also</span></span>  
 [<span data-ttu-id="3b2e4-128">ISymUnmanagedWriter2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3b2e4-128">ISymUnmanagedWriter2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)  
 [<span data-ttu-id="3b2e4-129">DefineLocalVariable 메서드</span><span class="sxs-lookup"><span data-stu-id="3b2e4-129">DefineLocalVariable Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definelocalvariable-method.md)
