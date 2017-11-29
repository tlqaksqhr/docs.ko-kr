---
title: "ISymUnmanagedReader::GetNamespaces 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedReader.GetNamespaces
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedReader::GetNamespaces
helpviewer_keywords:
- ISymUnmanagedReader::GetNamespaces method [.NET Framework debugging]
- GetNamespaces method, ISymUnmanagedReader interface [.NET Framework debugging]
ms.assetid: 3feb4796-2fab-45ce-beca-6f5bc530b971
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c4404977fab42fb46292440473cd30f6cb162d6b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedreadergetnamespaces-method"></a><span data-ttu-id="cd606-102">ISymUnmanagedReader::GetNamespaces 메서드</span><span class="sxs-lookup"><span data-stu-id="cd606-102">ISymUnmanagedReader::GetNamespaces Method</span></span>
<span data-ttu-id="cd606-103">이 기호 저장소 내의 전역 범위에서 정의 된 네임 스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cd606-103">Gets the namespaces defined at global scope within this symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cd606-104">구문</span><span class="sxs-lookup"><span data-stu-id="cd606-104">Syntax</span></span>  
  
```  
HRESULT GetNamespaces (  
    [in]  ULONG32  cNameSpaces,  
    [out] ULONG32  *pcNameSpaces,  
    [out, size_is (cNameSpaces),  
        length_is (*pcNameSpaces)]  
        ISymUnmanagedNamespace*  namespaces[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cd606-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cd606-105">Parameters</span></span>  
 `cNameSpaces`  
 <span data-ttu-id="cd606-106">[in] 네임 스페이스 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="cd606-106">[in] The size of the namespaces array.</span></span>  
  
 `pcNameSpaces`  
 <span data-ttu-id="cd606-107">[out] 네임 스페이스 목록의 길이 받는 변수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="cd606-107">[out] A pointer to a variable that receives the length of the namespace list.</span></span>  
  
 `namespaces`  
 <span data-ttu-id="cd606-108">[out] 네임 스페이스 목록을 수신 하는 변수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="cd606-108">[out] A pointer to a variable that receives the namespace list.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cd606-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="cd606-109">Return Value</span></span>  
 <span data-ttu-id="cd606-110">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="cd606-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cd606-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cd606-111">Requirements</span></span>  
 <span data-ttu-id="cd606-112">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="cd606-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd606-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cd606-113">See Also</span></span>  
 [<span data-ttu-id="cd606-114">ISymUnmanagedReader 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cd606-114">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
