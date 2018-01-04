---
title: "ISymUnmanagedNamespace::GetNamespaces 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedNamespace.GetNamespaces
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedNamespace::GetNamespaces
helpviewer_keywords:
- ISymUnmanagedNamespace::GetNamespaces method [.NET Framework debugging]
- GetNamespaces method, ISymUnmanagedNamespace interface [.NET Framework debugging]
ms.assetid: 0ea9d9af-8709-4a46-872b-f54d9e840088
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 69ee0f6385abf78a368d488d0190796516c4f3d7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagednamespacegetnamespaces-method"></a><span data-ttu-id="20427-102">ISymUnmanagedNamespace::GetNamespaces 메서드</span><span class="sxs-lookup"><span data-stu-id="20427-102">ISymUnmanagedNamespace::GetNamespaces Method</span></span>
<span data-ttu-id="20427-103">이 네임 스페이스의 자식을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="20427-103">Gets the children of this namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20427-104">구문</span><span class="sxs-lookup"><span data-stu-id="20427-104">Syntax</span></span>  
  
```  
HRESULT GetNamespaces(  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is(cNameSpaces), length_is(*pcNameSpaces)]  
        ISymUnmanagedNamespace* namespaces[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="20427-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="20427-105">Parameters</span></span>  
 `cNameSpaces`  
 <span data-ttu-id="20427-106">[in] A `ULONG32` 크기를 표시 하는 `namespaces` 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="20427-106">[in] A `ULONG32` that indicates the size of the `namespaces` array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="20427-107">[out] 에 대 한 포인터는 `ULONG32` 네임 스페이스를 포함 하는 데 필요한 버퍼의 문자에는 크기를 받는 합니다.</span><span class="sxs-lookup"><span data-stu-id="20427-107">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the namespaces.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="20427-108">[out] 네임 스페이스를 포함 하는 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="20427-108">[out] A pointer to the buffer that contains the namespaces.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="20427-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="20427-109">Return Value</span></span>  
 <span data-ttu-id="20427-110">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="20427-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20427-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="20427-111">Requirements</span></span>  
 <span data-ttu-id="20427-112">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="20427-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20427-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="20427-113">See Also</span></span>  
 [<span data-ttu-id="20427-114">ISymUnmanagedNamespace 인터페이스</span><span class="sxs-lookup"><span data-stu-id="20427-114">ISymUnmanagedNamespace Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagednamespace-interface.md)
