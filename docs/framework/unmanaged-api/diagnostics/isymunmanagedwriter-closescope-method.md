---
title: "ISymUnmanagedWriter::CloseScope 메서드"
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
- ISymUnmanagedWriter.CloseScope
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::CloseScope
helpviewer_keywords:
- CloseScope method [.NET Framework debugging]
- ISymUnmanagedWriter::CloseScope method [.NET Framework debugging]
ms.assetid: 6dade525-7770-4cb4-bafd-4bb995ad0d87
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d47be1d220729ed32fcf77a77e611003085c15d6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriterclosescope-method"></a><span data-ttu-id="9a62d-102">ISymUnmanagedWriter::CloseScope 메서드</span><span class="sxs-lookup"><span data-stu-id="9a62d-102">ISymUnmanagedWriter::CloseScope Method</span></span>
<span data-ttu-id="9a62d-103">현재 어휘 범위를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="9a62d-103">Closes the current lexical scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a62d-104">구문</span><span class="sxs-lookup"><span data-stu-id="9a62d-104">Syntax</span></span>  
  
```  
HRESULT CloseScope(  
    [in] ULONG32 endOffset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9a62d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9a62d-105">Parameters</span></span>  
 `endOffset`  
 <span data-ttu-id="9a62d-106">[in] 바이트 단위로 어휘 범위에서 마지막 명령의 끝에 있는 점의 메서드의 시작 부분에서 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="9a62d-106">[in] The offset from the beginning of the method of the point at the end of the last instruction in the lexical scope, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9a62d-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="9a62d-107">Return Value</span></span>  
 <span data-ttu-id="9a62d-108">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="9a62d-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9a62d-109">설명</span><span class="sxs-lookup"><span data-stu-id="9a62d-109">Remarks</span></span>  
 <span data-ttu-id="9a62d-110">범위를 닫은 후 그 안에 없는 많은 변수를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a62d-110">Once a scope is closed, no more variables can be defined within it.</span></span>  
  
 <span data-ttu-id="9a62d-111">[Isymunmanagedwriter:: Openscope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) 함께 사용할 수 있는 불투명 한 범위 식별자를 반환 [isymunmanagedwriter:: Setscoperange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md) 나중에 범위를 정의 하의 시작과 끝 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="9a62d-111">[ISymUnmanagedWriter::OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) returns an opaque scope identifier that can be used with [ISymUnmanagedWriter::SetScopeRange](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md) to later define a scope's starting and ending offset.</span></span> <span data-ttu-id="9a62d-112">이 경우 `ISymUnmanagedWriter::OpenScope` 및 `ISymUnmanagedWriter::CloseScope`에 전달된 오프셋은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a62d-112">In this case, the offsets passed to `ISymUnmanagedWriter::OpenScope` and `ISymUnmanagedWriter::CloseScope` are ignored.</span></span> <span data-ttu-id="9a62d-113">범위 식별자는 현재 메서드에서만 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a62d-113">Scope identifiers are valid only in the current method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a62d-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9a62d-114">Requirements</span></span>  
 <span data-ttu-id="9a62d-115">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="9a62d-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a62d-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9a62d-116">See Also</span></span>  
 [<span data-ttu-id="9a62d-117">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9a62d-117">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
