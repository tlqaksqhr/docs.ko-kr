---
title: "ISymUnmanagedSymbolSearchInfo::GetSearchPath 메서드"
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
- ISymUnmanagedSymbolSearchInfo.GetSearchPath
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedSymbolSearchInfo::GetSearchPath
helpviewer_keywords:
- GetSearchPath method [.NET Framework debugging]
- ISymUnmanagedSymbolSearchInfo::GetSearchPath method [.NET Framework debugging]
ms.assetid: b588d470-53c2-4492-be8c-957323eaca0b
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d1c4e1873aa3441e0348751717443e8189a67e61
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedsymbolsearchinfogetsearchpath-method"></a><span data-ttu-id="ac4ce-102">ISymUnmanagedSymbolSearchInfo::GetSearchPath 메서드</span><span class="sxs-lookup"><span data-stu-id="ac4ce-102">ISymUnmanagedSymbolSearchInfo::GetSearchPath Method</span></span>
<span data-ttu-id="ac4ce-103">검색 경로를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ac4ce-103">Gets the search path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac4ce-104">구문</span><span class="sxs-lookup"><span data-stu-id="ac4ce-104">Syntax</span></span>  
  
```  
HRESULT GetSearchPathLength(  
    [out] ULONG32 *pcchPath);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ac4ce-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ac4ce-105">Parameters</span></span>  
 `pcchPath`  
 <span data-ttu-id="ac4ce-106">[out] 에 대 한 포인터는 `ULONG32` 검색 경로 포함 하는 데 필요한 버퍼의 문자에는 크기를 받는 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac4ce-106">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the search path.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ac4ce-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="ac4ce-107">Return Value</span></span>  
 <span data-ttu-id="ac4ce-108">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="ac4ce-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac4ce-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ac4ce-109">Requirements</span></span>  
 <span data-ttu-id="ac4ce-110">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="ac4ce-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac4ce-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ac4ce-111">See Also</span></span>  
 [<span data-ttu-id="ac4ce-112">ISymUnmanagedSymbolSearchInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ac4ce-112">ISymUnmanagedSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)
