---
title: "ISymUnmanagedWriter2::DefineGlobalVariable2 메서드"
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
- ISymUnmanagedWriter2.DefineGlobalVariable2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter2::DefineGlobalVariable2
helpviewer_keywords:
- ISymUnmanagedWriter2::DefineGlobalVariable2 method [.NET Framework debugging]
- DefineGlobalVariable2 method [.NET Framework debugging]
ms.assetid: 04d569d6-a151-4957-9872-f3f694c3e4a9
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 617e3f03f4b1c126a56b47db34ec7044bea8c58b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriter2defineglobalvariable2-method"></a><span data-ttu-id="16c46-102">ISymUnmanagedWriter2::DefineGlobalVariable2 메서드</span><span class="sxs-lookup"><span data-stu-id="16c46-102">ISymUnmanagedWriter2::DefineGlobalVariable2 Method</span></span>
<span data-ttu-id="16c46-103">단일 전역 변수를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="16c46-103">Defines a single global variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16c46-104">구문</span><span class="sxs-lookup"><span data-stu-id="16c46-104">Syntax</span></span>  
  
```  
HRESULT DefineGlobalVariable2(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] mdSignature  sigToken,  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="16c46-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="16c46-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="16c46-106">[in] 전역 변수 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="16c46-106">[in] The global variable name.</span></span>  
  
 `attributes`  
 <span data-ttu-id="16c46-107">[in] 전역 변수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="16c46-107">[in] The global variable attributes.</span></span>  
  
 `sigToken`  
 <span data-ttu-id="16c46-108">[in] 서명의 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="16c46-108">[in] The metadata token of the signature.</span></span>  
  
 `addrKind`  
 <span data-ttu-id="16c46-109">[in] 주소 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="16c46-109">[in] The address type.</span></span>  
  
 `addr1`  
 <span data-ttu-id="16c46-110">[in] 매개 변수 사양에 대 한 첫 번째 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="16c46-110">[in] The first address for the parameter specification.</span></span>  
  
 `addr2`  
 <span data-ttu-id="16c46-111">[in] 매개 변수 사양에 대 한 두 번째 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="16c46-111">[in] The second address for the parameter specification.</span></span>  
  
 `addr3`  
 <span data-ttu-id="16c46-112">[in] 매개 변수 사양에 대 한 세 번째 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="16c46-112">[in] The third address for the parameter specification.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="16c46-113">반환 값</span><span class="sxs-lookup"><span data-stu-id="16c46-113">Return Value</span></span>  
 <span data-ttu-id="16c46-114">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="16c46-114">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16c46-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="16c46-115">Requirements</span></span>  
 <span data-ttu-id="16c46-116">**헤더:** CorSym.idl</span><span class="sxs-lookup"><span data-stu-id="16c46-116">**Header:** CorSym.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16c46-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="16c46-117">See Also</span></span>  
 [<span data-ttu-id="16c46-118">ISymUnmanagedWriter2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="16c46-118">ISymUnmanagedWriter2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)  
 [<span data-ttu-id="16c46-119">DefineGlobalVariable 메서드</span><span class="sxs-lookup"><span data-stu-id="16c46-119">DefineGlobalVariable Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineglobalvariable-method.md)
