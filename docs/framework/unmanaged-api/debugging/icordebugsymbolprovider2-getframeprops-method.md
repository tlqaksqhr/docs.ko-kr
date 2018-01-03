---
title: "ICorDebugSymbolProvider2::GetFrameProps 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: f07b73f3-188d-43a9-8f7d-44dce2f1ddb7
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f74ed8cdd7448d7ebeaa98108e84b42e86f428b1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugsymbolprovider2getframeprops-method"></a><span data-ttu-id="54aaf-102">ICorDebugSymbolProvider2::GetFrameProps 메서드</span><span class="sxs-lookup"><span data-stu-id="54aaf-102">ICorDebugSymbolProvider2::GetFrameProps Method</span></span>
<span data-ttu-id="54aaf-103">메서드의 메서드 시작 상대 가상 주소 및 코드 상대 가상 주소가 지정된 부모 프레임을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="54aaf-103">Returns the method starting relative virtual address of a method and the parent frame given a code relative virtual address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54aaf-104">구문</span><span class="sxs-lookup"><span data-stu-id="54aaf-104">Syntax</span></span>  
  
```  
HRESULT GetFrameProps(  
   [in] ULONG32 codeRva,  
   [out] ULONG32 *pCodeStartRva,  
   [out] ULONG32 *pParentFrameStartRva  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="54aaf-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="54aaf-105">Parameters</span></span>  
 `codeRva`  
 <span data-ttu-id="54aaf-106">[in] 코드 상대 가상 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="54aaf-106">[in] A code relative virtual address.</span></span>  
  
 `pCodeStartRva`  
 <span data-ttu-id="54aaf-107">[out] 메서드의 시작 상대 가상 주소에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="54aaf-107">[out] A pointer to the method's starting relative virtual address.</span></span>  
  
 `pParentFrameStartRva`  
 <span data-ttu-id="54aaf-108">[out] 프레임의 시작 상대 가상 주소에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="54aaf-108">[out] A pointer to the frame's starting relative virtual address.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="54aaf-109">설명</span><span class="sxs-lookup"><span data-stu-id="54aaf-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="54aaf-110">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54aaf-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54aaf-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="54aaf-111">Requirements</span></span>  
 <span data-ttu-id="54aaf-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="54aaf-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54aaf-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="54aaf-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="54aaf-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="54aaf-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="54aaf-115">**.NET framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54aaf-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54aaf-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="54aaf-116">See Also</span></span>  
 [<span data-ttu-id="54aaf-117">ICorDebugSymbolProvider2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="54aaf-117">ICorDebugSymbolProvider2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-interface.md)  
 [<span data-ttu-id="54aaf-118">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="54aaf-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
