---
title: "ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: f738a6ed-7cd9-4106-a5cd-355481e5771c
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2e305ca13e419a40e9838a46a61fe7a435b7ce56
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefineasyncstepinfo-method"></a><span data-ttu-id="eccfa-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="eccfa-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo Method</span></span>
<span data-ttu-id="eccfa-103">비동기의 그룹을 정의 현재 메서드에 대 한 작업을 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="eccfa-103">Define a group of async await operations in the current method.</span></span>  
  
 <span data-ttu-id="eccfa-104">각 yield 오프셋 잠재적인 yield 식별 하는 await 반환 명령을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="eccfa-104">Each yield offset matches an await's return instruction, identifying a potential yield.</span></span> <span data-ttu-id="eccfa-105">각 `breakpointMethod` / `breakpointOffset` 쌍 알려줍니다. 여기서는 비동기 작업을 다시 시작 됩니다, (있는 다른 방법을에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eccfa-105">Each `breakpointMethod`/`breakpointOffset` pair tells us where the asynchronous operation will resume,(which could be in a different method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eccfa-106">구문</span><span class="sxs-lookup"><span data-stu-id="eccfa-106">Syntax</span></span>  
  
```idl  
HRESULT DefineAsyncStepInfo(    [in] ULONG32 count,    [in, size_is(count)] ULONG32 yieldOffsets[],    [in, size_is(count)] ULONG32 breakpointOffset[],     [in, size_is(count)] mdToken breakpointMethod[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="eccfa-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="eccfa-107">Parameters</span></span>  
  
|<span data-ttu-id="eccfa-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="eccfa-108">Parameter</span></span>|<span data-ttu-id="eccfa-109">설명</span><span class="sxs-lookup"><span data-stu-id="eccfa-109">Description</span></span>|  
|---------------|-----------------|  
|`count`||  
|`yieldOffsets`||  
|`breakpointOffset`||  
|`breakpointMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="eccfa-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="eccfa-110">Return Value</span></span>  
 <span data-ttu-id="eccfa-111">`HRESULT`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="eccfa-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eccfa-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="eccfa-112">Requirements</span></span>  
 <span data-ttu-id="eccfa-113">**헤더:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="eccfa-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eccfa-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="eccfa-114">See Also</span></span>  
 [<span data-ttu-id="eccfa-115">ISymUnmanagedAsyncMethodPropertiesWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="eccfa-115">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
