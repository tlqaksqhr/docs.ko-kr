---
title: "ISymUnmanagedENCUpdate::GetLocalVariables 메서드"
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
- ISymUnmanagedENCUpdate.GetLocalVariables
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariables
helpviewer_keywords:
- ISymUnmanagedENCUpdate::GetLocalVariables method [.NET Framework debugging]
- GetLocalVariables method [.NET Framework debugging]
ms.assetid: 5c8840be-ffea-447f-9c8d-178f1eaf8d06
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: eefd64441221a7e6e00689d6be272540f9c2423c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedencupdategetlocalvariables-method"></a><span data-ttu-id="b6540-102">ISymUnmanagedENCUpdate::GetLocalVariables 메서드</span><span class="sxs-lookup"><span data-stu-id="b6540-102">ISymUnmanagedENCUpdate::GetLocalVariables Method</span></span>
<span data-ttu-id="b6540-103">지역 변수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b6540-103">Gets the local variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6540-104">구문</span><span class="sxs-lookup"><span data-stu-id="b6540-104">Syntax</span></span>  
  
```  
HRESULT GetLocalVariables(  
    [in]  mdMethodDef  mdMethodToken,  
    [in]  ULONG        cLocals,  
    [out, size_is(cLocals), length_is(*pceltFetched)]  
        ISymUnmanagedVariable *rgLocals[],  
    [out] ULONG        *pceltFetched);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b6540-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b6540-105">Parameters</span></span>  
 `mdMethodToken`  
 <span data-ttu-id="b6540-106">[in] 메서드의 메타 데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="b6540-106">[in] The metadata token of the method.</span></span>  
  
 `cLocals`  
 <span data-ttu-id="b6540-107">[in] A `ULONG` 크기를 표시 하는 `rgLocals` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="b6540-107">[in] A `ULONG` that indicates the size of the `rgLocals` parameter.</span></span>  
  
 `rgLocals`  
 <span data-ttu-id="b6540-108">[out] 반환된 된 배열 <!--zz<xref:ISymUnmanagedVariable>--> `ISymUnmanagedVariable` 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="b6540-108">[out] The returned array of <!--zz<xref:ISymUnmanagedVariable>--> `ISymUnmanagedVariable`  instances.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="b6540-109">[out] 에 대 한 포인터는 `ULONG` 의 크기를 받는 `rgLocals` 지역 변수를 포함 하는 데 필요한 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="b6540-109">[out] A pointer to a `ULONG` that receives the size of the `rgLocals` buffer required to contain the locals.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b6540-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="b6540-110">Return Value</span></span>  
 <span data-ttu-id="b6540-111">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="b6540-111">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6540-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b6540-112">Requirements</span></span>  
 <span data-ttu-id="b6540-113">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b6540-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6540-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b6540-114">See Also</span></span>  
 [<span data-ttu-id="b6540-115">ISymUnmanagedENCUpdate 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b6540-115">ISymUnmanagedENCUpdate Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedencupdate-interface.md)
