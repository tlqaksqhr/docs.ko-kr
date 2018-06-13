---
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo 메서드
ms.date: 03/30/2017
ms.assetid: f738a6ed-7cd9-4106-a5cd-355481e5771c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3ebd4bb1d674a27785ccbe5460a65fed764638ea
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33435879"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefineasyncstepinfo-method"></a><span data-ttu-id="f7508-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="f7508-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo Method</span></span>
<span data-ttu-id="f7508-103">비동기의 그룹을 정의 현재 메서드에 대 한 작업을 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="f7508-103">Define a group of async await operations in the current method.</span></span>  
  
 <span data-ttu-id="f7508-104">각 yield 오프셋 잠재적인 yield 식별 하는 await 반환 명령을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="f7508-104">Each yield offset matches an await's return instruction, identifying a potential yield.</span></span> <span data-ttu-id="f7508-105">각 `breakpointMethod` / `breakpointOffset` 쌍 알려줍니다. 여기서는 비동기 작업을 다시 시작 됩니다, (있는 다른 방법을에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7508-105">Each `breakpointMethod`/`breakpointOffset` pair tells us where the asynchronous operation will resume,(which could be in a different method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7508-106">구문</span><span class="sxs-lookup"><span data-stu-id="f7508-106">Syntax</span></span>  
  
```idl  
HRESULT DefineAsyncStepInfo(    [in] ULONG32 count,    [in, size_is(count)] ULONG32 yieldOffsets[],    [in, size_is(count)] ULONG32 breakpointOffset[],     [in, size_is(count)] mdToken breakpointMethod[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f7508-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f7508-107">Parameters</span></span>  
  
|<span data-ttu-id="f7508-108">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f7508-108">Parameter</span></span>|<span data-ttu-id="f7508-109">설명</span><span class="sxs-lookup"><span data-stu-id="f7508-109">Description</span></span>|  
|---------------|-----------------|  
|`count`||  
|`yieldOffsets`||  
|`breakpointOffset`||  
|`breakpointMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="f7508-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="f7508-110">Return Value</span></span>  
 <span data-ttu-id="f7508-111">`HRESULT`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f7508-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7508-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f7508-112">Requirements</span></span>  
 <span data-ttu-id="f7508-113">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="f7508-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7508-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f7508-114">See Also</span></span>  
 [<span data-ttu-id="f7508-115">ISymUnmanagedAsyncMethodPropertiesWriter 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f7508-115">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
