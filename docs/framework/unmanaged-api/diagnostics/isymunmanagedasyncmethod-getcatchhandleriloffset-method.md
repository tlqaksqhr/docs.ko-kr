---
title: ISymUnmanagedAsyncMethod::GetCatchHandlerILOffset 메서드
ms.date: 03/30/2017
ms.assetid: d5f88656-433d-447c-b21c-2a12bed2e72a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 527e686eb0c354c3a1ebba36772e30211e995ab2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33425355"
---
# <a name="isymunmanagedasyncmethodgetcatchhandleriloffset-method"></a><span data-ttu-id="a1c81-102">ISymUnmanagedAsyncMethod::GetCatchHandlerILOffset 메서드</span><span class="sxs-lookup"><span data-stu-id="a1c81-102">ISymUnmanagedAsyncMethod::GetCatchHandlerILOffset Method</span></span>
<span data-ttu-id="a1c81-103">참조 [DefineCatchHandlerILOffset 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c81-103">See [DefineCatchHandlerILOffset Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1c81-104">구문</span><span class="sxs-lookup"><span data-stu-id="a1c81-104">Syntax</span></span>  
  
```idl  
HRESULT GetCatchHandlerILOffset(    [out, retval] ULONG32* pRetVal);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a1c81-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a1c81-105">Parameters</span></span>  
  
|<span data-ttu-id="a1c81-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a1c81-106">Parameter</span></span>|<span data-ttu-id="a1c81-107">설명</span><span class="sxs-lookup"><span data-stu-id="a1c81-107">Description</span></span>|  
|---------------|-----------------|  
|`pRetVal`||  
  
## <a name="return-value"></a><span data-ttu-id="a1c81-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="a1c81-108">Return Value</span></span>  
 <span data-ttu-id="a1c81-109">`HRESULT`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c81-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1c81-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a1c81-110">Requirements</span></span>  
 <span data-ttu-id="a1c81-111">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="a1c81-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1c81-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a1c81-112">See Also</span></span>  
 [<span data-ttu-id="a1c81-113">ISymUnmanagedAsyncMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a1c81-113">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
