---
title: ISymUnmanagedMethod::GetScopeFromOffset 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedMethod.GetScopeFromOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedMethod::GetScopeFromOffset
helpviewer_keywords:
- GetScopeFromOffset method [.NET Framework debugging]
- ISymUnmanagedMethod::GetScopeFromOffset method [.NET Framework debugging]
ms.assetid: d14cf210-81f8-46e1-8b19-6ddec0ba8b11
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0898d554a2602a1139f2e37eb67f3aa00c5bd79e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33436087"
---
# <a name="isymunmanagedmethodgetscopefromoffset-method"></a><span data-ttu-id="21f3b-102">ISymUnmanagedMethod::GetScopeFromOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="21f3b-102">ISymUnmanagedMethod::GetScopeFromOffset Method</span></span>
<span data-ttu-id="21f3b-103">지정된 된 오프셋을 포함 하는이 메서드 내에서 최대 포함 어휘 범위를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="21f3b-103">Gets the most enclosing lexical scope within this method that encloses the given offset.</span></span> <span data-ttu-id="21f3b-104">지역 변수 검색을 시작 데 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21f3b-104">This can be used to start local variable searches.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21f3b-105">구문</span><span class="sxs-lookup"><span data-stu-id="21f3b-105">Syntax</span></span>  
  
```  
HRESULT GetScopeFromOffset(  
    [in]  ULONG32 offset,  
    [out, retval] ISymUnmanagedScope**  pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="21f3b-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="21f3b-106">Parameters</span></span>  
 `offset`  
 <span data-ttu-id="21f3b-107">[in] A `ULONG` 오프셋을 포함 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="21f3b-107">[in] A `ULONG` that contains the offset.</span></span>  
  
 `pRetVal`  
 <span data-ttu-id="21f3b-108">[out] 설정 된 포인터를 반환 되 [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="21f3b-108">[out] A pointer that is set to the returned [ISymUnmanagedScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="21f3b-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="21f3b-109">Return Value</span></span>  
 <span data-ttu-id="21f3b-110">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="21f3b-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21f3b-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="21f3b-111">Requirements</span></span>  
 <span data-ttu-id="21f3b-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="21f3b-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21f3b-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="21f3b-113">See Also</span></span>  
 [<span data-ttu-id="21f3b-114">ISymUnmanagedMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="21f3b-114">ISymUnmanagedMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedmethod-interface.md)
