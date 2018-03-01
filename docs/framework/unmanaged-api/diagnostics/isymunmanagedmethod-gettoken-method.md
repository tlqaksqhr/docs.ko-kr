---
title: "ISymUnmanagedMethod::GetToken 메서드"
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
- ISymUnmanagedMethod.GetToken
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetToken
helpviewer_keywords:
- ISymUnmanagedMethod::GetToken method [.NET Framework debugging]
- GetToken method, ISymUnmanagedMethod interface [.NET Framework debugging]
ms.assetid: 4effbe95-c36e-4a45-8b2a-ee21339415fb
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: bfdc070c21c7929166bfa957c0e0dd63da80f761
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedmethodgettoken-method"></a><span data-ttu-id="6b8e7-102">ISymUnmanagedMethod::GetToken 메서드</span><span class="sxs-lookup"><span data-stu-id="6b8e7-102">ISymUnmanagedMethod::GetToken Method</span></span>
<span data-ttu-id="6b8e7-103">이 메서드에 대 한 메타 데이터 토큰을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6b8e7-103">Returns the metadata token for this method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b8e7-104">구문</span><span class="sxs-lookup"><span data-stu-id="6b8e7-104">Syntax</span></span>  
  
```  
HRESULT GetToken(  
   [out, retval]  mdMethodDef  *pToken);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6b8e7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6b8e7-105">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="6b8e7-106">[out] 에 대 한 포인터는 `mdMethodDef` 메타 데이터를 포함 하는 데 필요한 버퍼의 문자에는 크기를 받는 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b8e7-106">[out] A pointer to a `mdMethodDef` that receives the size, in characters, of the buffer required to contain the metadata.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6b8e7-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="6b8e7-107">Return Value</span></span>  
 <span data-ttu-id="6b8e7-108">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="6b8e7-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b8e7-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6b8e7-109">Requirements</span></span>  
 <span data-ttu-id="6b8e7-110">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="6b8e7-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b8e7-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6b8e7-111">See Also</span></span>  
 [<span data-ttu-id="6b8e7-112">ISymUnmanagedMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6b8e7-112">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
