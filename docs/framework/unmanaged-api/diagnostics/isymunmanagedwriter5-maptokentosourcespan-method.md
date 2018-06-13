---
title: ISymUnmanagedWriter5::MapTokenToSourceSpan 메서드
ms.date: 03/30/2017
ms.assetid: d0fbbf61-71c6-4fb1-8c9f-d619ca5d7d68
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7751ed951c213c52c68125543622ed110124f5b1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33427945"
---
# <a name="isymunmanagedwriter5maptokentosourcespan-method"></a><span data-ttu-id="85fac-102">ISymUnmanagedWriter5::MapTokenToSourceSpan 메서드</span><span class="sxs-lookup"><span data-stu-id="85fac-102">ISymUnmanagedWriter5::MapTokenToSourceSpan Method</span></span>
<span data-ttu-id="85fac-103">지도 지정 된 소스 줄에 지정 된 메타 데이터 토큰 지정 된 소스 파일에 걸쳐 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85fac-103">Maps the given metadata token to the given source line span in the specified source file.</span></span>  
  
 <span data-ttu-id="85fac-104">호출 하는 사이 호출 해야 [OpenMapTokensToSourceSpans 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md) 및 [CloseMapTokensToSourceSpans 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="85fac-104">Must be called between calls to [OpenMapTokensToSourceSpans Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md) and [CloseMapTokensToSourceSpans Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85fac-105">구문</span><span class="sxs-lookup"><span data-stu-id="85fac-105">Syntax</span></span>  
  
```idl  
HRESULT MapTokenToSourceSpan(    [in] mdToken token,    [in] ISymUnmanagedDocumentWriter* document,    [in] ULONG32 line,    [in] ULONG32 column,    [in] ULONG32 endLine,    [in] ULONG32 endColumn);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="85fac-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="85fac-106">Parameters</span></span>  
  
|<span data-ttu-id="85fac-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="85fac-107">Parameter</span></span>|<span data-ttu-id="85fac-108">설명</span><span class="sxs-lookup"><span data-stu-id="85fac-108">Description</span></span>|  
|---------------|-----------------|  
|`token`||  
|`document`||  
|`line`||  
|`column`||  
|`endLine`||  
|`endColumn`||  
  
## <a name="return-value"></a><span data-ttu-id="85fac-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="85fac-109">Return Value</span></span>  
 <span data-ttu-id="85fac-110">`HRESULT`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="85fac-110">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85fac-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="85fac-111">Requirements</span></span>  
 <span data-ttu-id="85fac-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="85fac-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85fac-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="85fac-113">See Also</span></span>  
 [<span data-ttu-id="85fac-114">ISymUnmanagedWriter5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="85fac-114">ISymUnmanagedWriter5 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-interface.md)
