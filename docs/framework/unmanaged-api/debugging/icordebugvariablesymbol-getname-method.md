---
title: "ICorDebugVariableSymbol::GetName 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: c922b7d4-44e5-45e4-aef3-cc9c35a0be80
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 747249c23089cbeba04c3a872823f01f2b334203
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugvariablesymbolgetname-method"></a><span data-ttu-id="07af1-102">ICorDebugVariableSymbol::GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="07af1-102">ICorDebugVariableSymbol::GetName Method</span></span>
<span data-ttu-id="07af1-103">변수의 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="07af1-103">Gets the name of a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07af1-104">구문</span><span class="sxs-lookup"><span data-stu-id="07af1-104">Syntax</span></span>  
  
```  
HRESULT GetName(  
   [in] ULONG32 cchName,   
   [out] ULONG32 *pcchName,   
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="07af1-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="07af1-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="07af1-106">[in] `szName` 버퍼의 문자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="07af1-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="07af1-107">[out] `szName` 버퍼에 실제로 기록된 문자 수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="07af1-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="07af1-108">변수 이름이 포함된 문자 배열에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="07af1-108">A pointer to a character array that contains the variable name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="07af1-109">설명</span><span class="sxs-lookup"><span data-stu-id="07af1-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="07af1-110">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07af1-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="07af1-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="07af1-111">Requirements</span></span>  
 <span data-ttu-id="07af1-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="07af1-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07af1-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="07af1-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="07af1-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="07af1-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="07af1-115">**.NET framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07af1-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07af1-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="07af1-116">See Also</span></span>  
 [<span data-ttu-id="07af1-117">ICorDebugVariableSymbol 인터페이스</span><span class="sxs-lookup"><span data-stu-id="07af1-117">ICorDebugVariableSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)  
 [<span data-ttu-id="07af1-118">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="07af1-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
