---
title: "ISymUnmanagedConstant::GetSignature 메서드"
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
- ISymUnmanagedConstant.GetSignature
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedConstant::GetSignature
helpviewer_keywords:
- GetSignature method, ISymUnmanagedConstant interface [.NET Framework debugging]
- ISymUnmanagedConstant::GetSignature method [.NET Framework debugging]
ms.assetid: 3eb41151-a228-43e3-ba8f-e6dd3ceb8542
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 10bdf7b8b83b56ff856d966d2764ed04e06090aa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedconstantgetsignature-method"></a><span data-ttu-id="ca13e-102">ISymUnmanagedConstant::GetSignature 메서드</span><span class="sxs-lookup"><span data-stu-id="ca13e-102">ISymUnmanagedConstant::GetSignature Method</span></span>
<span data-ttu-id="ca13e-103">상수의 서명을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ca13e-103">Gets the signature of the constant.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca13e-104">구문</span><span class="sxs-lookup"><span data-stu-id="ca13e-104">Syntax</span></span>  
  
```  
HRESULT GetSignature(  
    [in]  ULONG32  cSig,  
    [out] ULONG32  *pcSig,  
    [out, size_is(cSig),  
        length_is(*pcSig)] BYTE sig[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ca13e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ca13e-105">Parameters</span></span>  
 `cSig`  
 <span data-ttu-id="ca13e-106">[in] 버퍼의 길이는 `pcSig` 매개 변수를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="ca13e-106">[in] The length of the buffer that the `pcSig` parameter points to.</span></span>  
  
 `pcSig`  
 <span data-ttu-id="ca13e-107">[out] 에 대 한 포인터는 `ULONG32` 시그니처를 포함 하는 데 필요한 버퍼의 문자에는 크기를 받는 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca13e-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the signature.</span></span>  
  
 `sig`  
 <span data-ttu-id="ca13e-108">[out] 서명을 저장 하는 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="ca13e-108">[out] The buffer that stores the signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ca13e-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="ca13e-109">Return Value</span></span>  
 <span data-ttu-id="ca13e-110">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="ca13e-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca13e-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ca13e-111">Requirements</span></span>  
 <span data-ttu-id="ca13e-112">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ca13e-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca13e-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ca13e-113">See Also</span></span>  
 [<span data-ttu-id="ca13e-114">ISymUnmanagedConstant 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ca13e-114">ISymUnmanagedConstant Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-interface.md)  
 [<span data-ttu-id="ca13e-115">GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="ca13e-115">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getname-method.md)  
 [<span data-ttu-id="ca13e-116">GetValue 메서드</span><span class="sxs-lookup"><span data-stu-id="ca13e-116">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedconstant-getvalue-method.md)
