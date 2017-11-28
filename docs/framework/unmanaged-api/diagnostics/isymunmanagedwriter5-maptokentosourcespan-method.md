---
title: "ISymUnmanagedWriter5::MapTokenToSourceSpan 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: d0fbbf61-71c6-4fb1-8c9f-d619ca5d7d68
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: adcdf44582aaf801a39c9beb9831c493a9945fd0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedwriter5maptokentosourcespan-method"></a><span data-ttu-id="8795e-102">ISymUnmanagedWriter5::MapTokenToSourceSpan 메서드</span><span class="sxs-lookup"><span data-stu-id="8795e-102">ISymUnmanagedWriter5::MapTokenToSourceSpan Method</span></span>
<span data-ttu-id="8795e-103">지도 지정 된 소스 줄에 지정 된 메타 데이터 토큰 지정 된 소스 파일에 걸쳐 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8795e-103">Maps the given metadata token to the given source line span in the specified source file.</span></span>  
  
 <span data-ttu-id="8795e-104">호출 하는 사이 호출 해야 [OpenMapTokensToSourceSpans 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md) 및 [CloseMapTokensToSourceSpans 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8795e-104">Must be called between calls to [OpenMapTokensToSourceSpans Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md) and [CloseMapTokensToSourceSpans Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8795e-105">구문</span><span class="sxs-lookup"><span data-stu-id="8795e-105">Syntax</span></span>  
  
```idl  
HRESULT MapTokenToSourceSpan(    [in] mdToken token,    [in] ISymUnmanagedDocumentWriter* document,    [in] ULONG32 line,    [in] ULONG32 column,    [in] ULONG32 endLine,    [in] ULONG32 endColumn);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8795e-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8795e-106">Parameters</span></span>  
  
|<span data-ttu-id="8795e-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8795e-107">Parameter</span></span>|<span data-ttu-id="8795e-108">설명</span><span class="sxs-lookup"><span data-stu-id="8795e-108">Description</span></span>|  
|---------------|-----------------|  
|`token`||  
|`document`||  
|`line`||  
|`column`||  
|`endLine`||  
|`endColumn`||  
  
## <a name="return-value"></a><span data-ttu-id="8795e-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="8795e-109">Return Value</span></span>  
 <span data-ttu-id="8795e-110">`HRESULT`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="8795e-110">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8795e-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8795e-111">Requirements</span></span>  
 <span data-ttu-id="8795e-112">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="8795e-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8795e-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8795e-113">See Also</span></span>  
 [<span data-ttu-id="8795e-114">ISymUnmanagedWriter5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8795e-114">ISymUnmanagedWriter5 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)
