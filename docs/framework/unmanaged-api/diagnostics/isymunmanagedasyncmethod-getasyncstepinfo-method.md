---
title: ISymUnmanagedAsyncMethod::GetAsyncStepInfo 메서드
ms.date: 03/30/2017
ms.assetid: 3ef5b4b8-4ac7-4906-849b-f932c5e3db07
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a26ff1e0b1bb4d0de662f0186dc2f7958b9707f2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33425381"
---
# <a name="isymunmanagedasyncmethodgetasyncstepinfo-method"></a><span data-ttu-id="30358-102">ISymUnmanagedAsyncMethod::GetAsyncStepInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="30358-102">ISymUnmanagedAsyncMethod::GetAsyncStepInfo Method</span></span>
<span data-ttu-id="30358-103">참조 [DefineAsyncStepInfo 메서드](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="30358-103">See [DefineAsyncStepInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30358-104">구문</span><span class="sxs-lookup"><span data-stu-id="30358-104">Syntax</span></span>  
  
```idl  
HRESULT GetAsyncStepInfo(    [in] ULONG32 cStepInfo,    [out] ULONG32 *pcStepInfo,    [in, size_is(cStepInfo)] ULONG32 yieldOffsets[],    [in, size_is(cStepInfo)] ULONG32 breakpointOffset[],    [in, size_is(cStepInfo)] mdToken breakpointMethod[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="30358-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="30358-105">Parameters</span></span>  
  
|<span data-ttu-id="30358-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="30358-106">Parameter</span></span>|<span data-ttu-id="30358-107">설명</span><span class="sxs-lookup"><span data-stu-id="30358-107">Description</span></span>|  
|---------------|-----------------|  
|`cStepInfo`||  
|`pcStepInfo`||  
|`yieldOffsets`||  
|`breakpointOffset`||  
|`breakpointMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="30358-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="30358-108">Return Value</span></span>  
 <span data-ttu-id="30358-109">`HRESULT`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="30358-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30358-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="30358-110">Requirements</span></span>  
 <span data-ttu-id="30358-111">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="30358-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30358-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="30358-112">See Also</span></span>  
 [<span data-ttu-id="30358-113">ISymUnmanagedAsyncMethod 인터페이스</span><span class="sxs-lookup"><span data-stu-id="30358-113">ISymUnmanagedAsyncMethod Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethod-interface.md)
