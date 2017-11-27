---
title: "ISymUnmanagedSymbolSearchInfo::GetSearchPathLength 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedSymbolSearchInfo.GetSearchPathLength
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedSymbolSearchInfo::GetSearchPathLength
helpviewer_keywords:
- GetSearchPathLength method [.NET Framework debugging]
- ISymUnmanagedSymbolSearchInfo::GetSearchPathLength method [.NET Framework debugging]
ms.assetid: 274e73cf-8333-47ba-ac12-70214e2b0112
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 58a788d8ef96a52c0b1bc361a97013f27c2809da
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedsymbolsearchinfogetsearchpathlength-method"></a><span data-ttu-id="87845-102">ISymUnmanagedSymbolSearchInfo::GetSearchPathLength 메서드</span><span class="sxs-lookup"><span data-stu-id="87845-102">ISymUnmanagedSymbolSearchInfo::GetSearchPathLength Method</span></span>
<span data-ttu-id="87845-103">검색 경로 길이 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="87845-103">Gets the search path length.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87845-104">구문</span><span class="sxs-lookup"><span data-stu-id="87845-104">Syntax</span></span>  
  
```  
HRESULT GetSearchPathLength(  
    [out] ULONG32 *pcchPath);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="87845-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="87845-105">Parameters</span></span>  
 `pcchPath`  
 <span data-ttu-id="87845-106">[out] 에 대 한 포인터는 `ULONG32` 검색 경로 길이 포함 하는 데 필요한 버퍼의 문자에는 크기를 받는 합니다.</span><span class="sxs-lookup"><span data-stu-id="87845-106">[out] A pointer to a `ULONG32` that receives the size, in characters, of the buffer required to contain the search path length.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="87845-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="87845-107">Return Value</span></span>  
 <span data-ttu-id="87845-108">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="87845-108">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87845-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="87845-109">Requirements</span></span>  
 <span data-ttu-id="87845-110">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="87845-110">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87845-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="87845-111">See Also</span></span>  
 [<span data-ttu-id="87845-112">ISymUnmanagedSymbolSearchInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="87845-112">ISymUnmanagedSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md)
