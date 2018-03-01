---
title: "ISymUnmanagedVariable::GetEndOffset 메서드"
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
- ISymUnmanagedVariable.GetEndOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable::GetEndOffset
helpviewer_keywords:
- ISymUnmanagedVariable::GetEndOffset method [.NET Framework debugging]
- GetEndOffset method, ISymUnmanagedVariable interface [.NET Framework debugging]
ms.assetid: e5d777c5-d450-4c0f-999c-b3953ee22cfb
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f91c2b0f4ecb4cc901a0389d15f4d69e926cf8f6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedvariablegetendoffset-method"></a><span data-ttu-id="f0ce1-102">ISymUnmanagedVariable::GetEndOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="f0ce1-102">ISymUnmanagedVariable::GetEndOffset Method</span></span>
<span data-ttu-id="f0ce1-103">해당 부모 노드에이 변수의 끝 오프셋을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f0ce1-103">Gets the end offset of this variable within its parent.</span></span> <span data-ttu-id="f0ce1-104">범위 내에 지역 변수 인 경우 끝 오프셋 범위에 대해 정의 된 오프셋 대체 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0ce1-104">If this is a local variable within a scope, the end offset will fall within the offsets defined for the scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0ce1-105">구문</span><span class="sxs-lookup"><span data-stu-id="f0ce1-105">Syntax</span></span>  
  
```  
HRESULT GetEndOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f0ce1-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f0ce1-106">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="f0ce1-107">[out] 에 대 한 포인터는 `ULONG32` 받는 끝 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="f0ce1-107">[out] A pointer to a `ULONG32` that receives the end offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f0ce1-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="f0ce1-108">Return Value</span></span>  
 <span data-ttu-id="f0ce1-109">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="f0ce1-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0ce1-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f0ce1-110">Requirements</span></span>  
 <span data-ttu-id="f0ce1-111">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="f0ce1-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0ce1-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f0ce1-112">See Also</span></span>  
 [<span data-ttu-id="f0ce1-113">ISymUnmanagedVariable 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f0ce1-113">ISymUnmanagedVariable Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-interface.md)  
 [<span data-ttu-id="f0ce1-114">GetStartOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="f0ce1-114">GetStartOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getstartoffset-method.md)
