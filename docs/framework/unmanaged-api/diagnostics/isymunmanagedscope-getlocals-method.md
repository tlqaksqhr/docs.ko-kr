---
title: ISymUnmanagedScope::GetLocals 메서드
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetLocals
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetLocals
helpviewer_keywords:
- GetLocals method [.NET Framework debugging]
- ISymUnmanagedScope::GetLocals method [.NET Framework debugging]
ms.assetid: 17c45f15-8c44-44da-b070-f902077b36e4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 781111db30ae664c9dd45744f88387e161f2716f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33426801"
---
# <a name="isymunmanagedscopegetlocals-method"></a><span data-ttu-id="09cca-102">ISymUnmanagedScope::GetLocals 메서드</span><span class="sxs-lookup"><span data-stu-id="09cca-102">ISymUnmanagedScope::GetLocals Method</span></span>
<span data-ttu-id="09cca-103">이 범위 내에 정의 된 지역 변수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="09cca-103">Gets the local variables defined within this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09cca-104">구문</span><span class="sxs-lookup"><span data-stu-id="09cca-104">Syntax</span></span>  
  
```  
HRESULT GetLocals(  
    [in]  ULONG32  cLocals,  
    [out] ULONG32  *pcLocals,  
    [out, size_is(cLocals),  
        length_is(*pcLocals)] ISymUnmanagedVariable* locals[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="09cca-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="09cca-105">Parameters</span></span>  
 `cLocals`  
 <span data-ttu-id="09cca-106">[in] A `ULONG32` 크기를 표시 하는 `locals` 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="09cca-106">[in] A `ULONG32` that indicates the size of the `locals` array.</span></span>  
  
 `pcLocals`  
 <span data-ttu-id="09cca-107">[out] 에 대 한 포인터는 `ULONG32` 로컬 변수를 포함 하는 데 필요한 버퍼의 크기를 받는 합니다.</span><span class="sxs-lookup"><span data-stu-id="09cca-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the local variables.</span></span>  
  
 `locals`  
 <span data-ttu-id="09cca-108">[out] 지역 변수를 수신 하는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="09cca-108">[out] The array that receives the local variables.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="09cca-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="09cca-109">Return Value</span></span>  
 <span data-ttu-id="09cca-110">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="09cca-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09cca-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="09cca-111">Requirements</span></span>  
 <span data-ttu-id="09cca-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="09cca-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09cca-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="09cca-113">See Also</span></span>  
 [<span data-ttu-id="09cca-114">ISymUnmanagedScope 인터페이스</span><span class="sxs-lookup"><span data-stu-id="09cca-114">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)
