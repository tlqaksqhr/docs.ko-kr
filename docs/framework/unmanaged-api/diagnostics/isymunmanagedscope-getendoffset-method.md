---
title: "ISymUnmanagedScope::GetEndOffset 메서드"
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
- ISymUnmanagedScope.GetEndOffset
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetEndOffset
helpviewer_keywords:
- ISymUnmanagedScope::GetEndOffset method [.NET Framework debugging]
- GetEndOffset method, ISymUnmanagedScope interface [.NET Framework debugging]
ms.assetid: 1d0b15c9-8059-435f-9fce-346a08b9bd36
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 64990dc2785a3804e683e281c823f459ec48e8a2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedscopegetendoffset-method"></a><span data-ttu-id="13ddf-102">ISymUnmanagedScope::GetEndOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="13ddf-102">ISymUnmanagedScope::GetEndOffset Method</span></span>
<span data-ttu-id="13ddf-103">이 범위에 대 한 끝 오프셋을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="13ddf-103">Gets the end offset for this scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13ddf-104">구문</span><span class="sxs-lookup"><span data-stu-id="13ddf-104">Syntax</span></span>  
  
```  
HRESULT GetEndOffset(  
    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="13ddf-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="13ddf-105">Parameters</span></span>  
 `pRetVal`  
 <span data-ttu-id="13ddf-106">[out] 에 대 한 포인터는 `ULONG32` 받는 끝 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="13ddf-106">[out] A pointer to a `ULONG32` that receives the end offset.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="13ddf-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="13ddf-107">Return Value</span></span>  
 <span data-ttu-id="13ddf-108">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="13ddf-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13ddf-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="13ddf-109">Requirements</span></span>  
 <span data-ttu-id="13ddf-110">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="13ddf-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13ddf-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="13ddf-111">See Also</span></span>  
 [<span data-ttu-id="13ddf-112">ISymUnmanagedScope 인터페이스</span><span class="sxs-lookup"><span data-stu-id="13ddf-112">ISymUnmanagedScope Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-interface.md)  
 [<span data-ttu-id="13ddf-113">GetStartOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="13ddf-113">GetStartOffset Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedscope-getstartoffset-method.md)
