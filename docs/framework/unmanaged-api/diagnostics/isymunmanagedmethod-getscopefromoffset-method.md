---
title: "ISymUnmanagedMethod::GetScopeFromOffset 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedMethod.GetScopeFromOffset
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedMethod::GetScopeFromOffset
helpviewer_keywords:
- GetScopeFromOffset method [.NET Framework debugging]
- ISymUnmanagedMethod::GetScopeFromOffset method [.NET Framework debugging]
ms.assetid: d14cf210-81f8-46e1-8b19-6ddec0ba8b11
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b863031cae487a2c081f23aeada1971893aa339f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedmethodgetscopefromoffset-method"></a><span data-ttu-id="983c6-102">ISymUnmanagedMethod::GetScopeFromOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="983c6-102">ISymUnmanagedMethod::GetScopeFromOffset Method</span></span>
<span data-ttu-id="983c6-103">지정된 된 오프셋을 포함 하는이 메서드 내에서 최대 포함 어휘 범위를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="983c6-103">Gets the most enclosing lexical scope within this method that encloses the given offset.</span></span> <span data-ttu-id="983c6-104">지역 변수 검색을 시작 데 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="983c6-104">This can be used to start local variable searches.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="983c6-105">구문</span><span class="sxs-lookup"><span data-stu-id="983c6-105">Syntax</span></span>  
  
```  
HRESULT GetScopeFromOffset(  
    [in]  ULONG32 offset,  
    [out, retval] ISymUnmanagedScope**  pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="983c6-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="983c6-106">Parameters</span></span>  
 `offset`  
 <span data-ttu-id="983c6-107">[in] A `ULONG` 오프셋을 포함 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="983c6-107">[in] A `ULONG` that contains the offset.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="983c6-108">[out] 설정 된 포인터를 반환 되 [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="983c6-108">[out] A pointer that is set to the returned [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="983c6-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="983c6-109">Return Value</span></span>  
 <span data-ttu-id="983c6-110">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="983c6-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="983c6-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="983c6-111">Requirements</span></span>  
 <span data-ttu-id="983c6-112">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="983c6-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="983c6-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="983c6-113">See Also</span></span>  
 [<span data-ttu-id="983c6-114">ISymUnmanagedMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="983c6-114">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
