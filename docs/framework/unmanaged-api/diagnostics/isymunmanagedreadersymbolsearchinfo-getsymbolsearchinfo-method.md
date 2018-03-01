---
title: "ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo 메서드"
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
- ISymUnmanagedReaderSymbolSearchInfo.GetSymbolSearchInfo
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo
helpviewer_keywords:
- GetSymbolSearchInfo method [.NET Framework debugging]
- ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo method [.NET Framework debugging]
ms.assetid: 40fcdbc5-3bb2-41e9-b995-40984c209a7f
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0ecddc85ba473b4cff20331013b283ad12cf9bbd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedreadersymbolsearchinfogetsymbolsearchinfo-method"></a><span data-ttu-id="e8fe7-102">ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="e8fe7-102">ISymUnmanagedReaderSymbolSearchInfo::GetSymbolSearchInfo Method</span></span>
<span data-ttu-id="e8fe7-103">기호 검색 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e8fe7-103">Gets symbol search information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8fe7-104">구문</span><span class="sxs-lookup"><span data-stu-id="e8fe7-104">Syntax</span></span>  
  
```  
HRESULT GetSymbolSearchInfo(  
    [in]  ULONG32  cSearchInfo,  
    [out] ULONG32  *pcSearchInfo,  
    [out, size_is(cSearchInfo), length_is(*pcSearchInfo)]  
        ISymUnmanagedSymbolSearchInfo **rgpSearchInfo);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e8fe7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e8fe7-105">Parameters</span></span>  
 `cSearchInfo`  
 <span data-ttu-id="e8fe7-106">[in] A `ULONG32` 의 크기를 나타내는 `rgpSearchInfo`합니다.</span><span class="sxs-lookup"><span data-stu-id="e8fe7-106">[in] A `ULONG32` that indicates the size of `rgpSearchInfo`.</span></span>  
  
 `pcSearchInfo`  
 <span data-ttu-id="e8fe7-107">[out] 에 대 한 포인터는 `ULONG32` 검색 정보를 포함 하는 데 필요한 버퍼의 크기를 받는 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8fe7-107">[out] A pointer to a `ULONG32` that receives the size of the buffer required to contain the search information.</span></span>  
  
 `rgpSearchInfo`  
 <span data-ttu-id="e8fe7-108">[out] 설정 된 포인터를 반환 되 [ISymUnmanagedSymbolSearchInfo](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="e8fe7-108">[out] A pointer that is set to the returned [ISymUnmanagedSymbolSearchInfo](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedsymbolsearchinfo-interface.md) interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e8fe7-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="e8fe7-109">Return Value</span></span>  
 <span data-ttu-id="e8fe7-110">메서드가 성공 하면 s_ok이 고 그렇지 않으면 E_FAIL 또는 일부 기타 오류 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="e8fe7-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8fe7-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e8fe7-111">Requirements</span></span>  
 <span data-ttu-id="e8fe7-112">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="e8fe7-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8fe7-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e8fe7-113">See Also</span></span>  
 [<span data-ttu-id="e8fe7-114">ISymUnmanagedReaderSymbolSearchInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e8fe7-114">ISymUnmanagedReaderSymbolSearchInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreadersymbolsearchinfo-interface.md)
