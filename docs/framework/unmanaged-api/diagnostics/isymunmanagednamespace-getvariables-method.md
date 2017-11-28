---
title: "ISymUnmanagedNamespace::GetVariables 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedNamespace.GetVariables
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedNamespace::GetVariables
helpviewer_keywords:
- ISymUnmanagedNamespace::GetVariables method [.NET Framework debugging]
- GetVariables method, ISymUnmanagedNamespace interface [.NET Framework debugging]
ms.assetid: ea7c1617-f3ce-4220-8288-f2b50eaf0f0f
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 6f2de9f683a9ce667b4b72c94204d39082cdaee4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagednamespacegetvariables-method"></a><span data-ttu-id="596b1-102">ISymUnmanagedNamespace::GetVariables 메서드</span><span class="sxs-lookup"><span data-stu-id="596b1-102">ISymUnmanagedNamespace::GetVariables Method</span></span>
<span data-ttu-id="596b1-103">이 네임 스페이스 내에서 전역 범위에서 정의 된 모든 변수를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="596b1-103">Returns all variables defined at global scope within this namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="596b1-104">구문</span><span class="sxs-lookup"><span data-stu-id="596b1-104">Syntax</span></span>  
  
```  
HRESULT GetVariables(  
    [in]  ULONG32  cVars,  
    [out] ULONG32  *pcVars,  
    [out, size_is(cVars), length_is(*pcVars)]  
        ISymUnmanagedVariable *pVars[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="596b1-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="596b1-105">Parameters</span></span>  
 `cVars`  
 <span data-ttu-id="596b1-106">[in] A `ULONG32` 크기를 표시 하는 `pVars` 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="596b1-106">[in] A `ULONG32` that indicates the size of the `pVars` array.</span></span>  
  
 `pcVars`  
 <span data-ttu-id="596b1-107">[out] 에 대 한 포인터는 `ULONG32` 네임 스페이스를 포함 하는 데 필요한 버퍼의 크기를 받는 합니다.</span><span class="sxs-lookup"><span data-stu-id="596b1-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the namespaces.</span></span>  
  
 `pVars`  
 <span data-ttu-id="596b1-108">[out] 네임 스페이스를 포함 하는 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="596b1-108">[out] A pointer to a buffer that contains the namespaces.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="596b1-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="596b1-109">Return Value</span></span>  
 <span data-ttu-id="596b1-110">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="596b1-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="596b1-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="596b1-111">Requirements</span></span>  
 <span data-ttu-id="596b1-112">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="596b1-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="596b1-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="596b1-113">See Also</span></span>  
 [<span data-ttu-id="596b1-114">ISymUnmanagedNamespace 인터페이스</span><span class="sxs-lookup"><span data-stu-id="596b1-114">ISymUnmanagedNamespace Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)
