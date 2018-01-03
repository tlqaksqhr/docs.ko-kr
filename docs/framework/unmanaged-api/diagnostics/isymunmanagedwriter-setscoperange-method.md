---
title: "ISymUnmanagedWriter::SetScopeRange 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.SetScopeRange
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::SetScopeRange
helpviewer_keywords:
- SetScopeRange method [.NET Framework debugging]
- ISymUnmanagedWriter::SetScopeRange method [.NET Framework debugging]
ms.assetid: d4d98676-444b-46ca-bfe6-0d827385cd22
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9afb0038adc4273033fb9f1db1ebc57f43eae779
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwritersetscoperange-method"></a><span data-ttu-id="cff92-102">ISymUnmanagedWriter::SetScopeRange 메서드</span><span class="sxs-lookup"><span data-stu-id="cff92-102">ISymUnmanagedWriter::SetScopeRange Method</span></span>
<span data-ttu-id="cff92-103">지정된 어휘 범위에 대한 오프셋 범위를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="cff92-103">Defines the offset range for the specified lexical scope.</span></span> <span data-ttu-id="cff92-104">범위 새로운 현재 범위가 되 고 범위 스택으로 푸시됩니다.</span><span class="sxs-lookup"><span data-stu-id="cff92-104">The scope becomes the new current scope and is pushed onto a stack of scopes.</span></span> <span data-ttu-id="cff92-105">범위 계층을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cff92-105">Scopes must form a hierarchy.</span></span> <span data-ttu-id="cff92-106">형제 겹칠 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cff92-106">Siblings are not allowed to overlap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cff92-107">구문</span><span class="sxs-lookup"><span data-stu-id="cff92-107">Syntax</span></span>  
  
```  
HRESULT OpenScope(  
    [in] ULONG32  scopeID,  
    [in] ULONG32  startOffset,  
    [in] ULONG32  endOffset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cff92-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cff92-108">Parameters</span></span>  
 `scopeId`  
 <span data-ttu-id="cff92-109">[in] 범위에 대 한 범위 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="cff92-109">[in] The scope identifier for the scope.</span></span>  
  
 `startOffset`  
 <span data-ttu-id="cff92-110">[in] 메서드의 시작 부분에서 어휘 범위에서 첫 번째 명령의 바이트 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="cff92-110">[in] The offset, in bytes, of the first instruction in the lexical scope from the beginning of the method.</span></span>  
  
 `endOffset`  
 <span data-ttu-id="cff92-111">[in] 메서드의 시작 부분에서 어휘 범위에서 마지막 명령의 바이트 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="cff92-111">[in] The offset, in bytes, of the last instruction in the lexical scope from the beginning of the method.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cff92-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="cff92-112">Return Value</span></span>  
 <span data-ttu-id="cff92-113">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="cff92-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cff92-114">설명</span><span class="sxs-lookup"><span data-stu-id="cff92-114">Remarks</span></span>  
 <span data-ttu-id="cff92-115">[Isymunmanagedwriter:: Openscope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) 함께 사용할 수 있는 불투명 한 범위 식별자를 반환 `ISymUnmanagedWriter::SetScopeRange` 범위를 정의 하의 시작과 끝 오프셋 나중에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cff92-115">[ISymUnmanagedWriter::OpenScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md) returns an opaque scope identifier that can be used with `ISymUnmanagedWriter::SetScopeRange` to define a scope's starting and ending offset at a later time.</span></span> <span data-ttu-id="cff92-116">이 경우에 전달 된 오프셋 `ISymUnmanagedWriter::OpenScope` 및 [isymunmanagedwriter:: Closescope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md) 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cff92-116">In this case, the offsets passed to `ISymUnmanagedWriter::OpenScope` and [ISymUnmanagedWriter::CloseScope](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md) are ignored.</span></span> <span data-ttu-id="cff92-117">범위 식별자는 현재 메서드에서만에서 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="cff92-117">Scope identifiers are only valid in the current method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cff92-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cff92-118">Requirements</span></span>  
 <span data-ttu-id="cff92-119">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="cff92-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cff92-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cff92-120">See Also</span></span>  
 [<span data-ttu-id="cff92-121">ISymUnmanagedWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cff92-121">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
