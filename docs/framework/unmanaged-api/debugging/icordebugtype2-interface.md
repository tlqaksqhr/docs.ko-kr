---
title: "ICorDebugType2 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name: ICorDebugType2
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugType2
helpviewer_keywords: ICorDebugType2 interface
ms.assetid: 376fb03f-f1ef-4107-baa4-4d9d55884862
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 658dd1541a1de852c3c001cc7fbb7954f6c7590f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugtype2-interface"></a><span data-ttu-id="a41fb-102">ICorDebugType2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a41fb-102">ICorDebugType2 Interface</span></span>
<span data-ttu-id="a41fb-103">ICorDebugType 인터페이스의 기본 형식 또는 복합 (사용자 정의) 형식을 형식 식별자를 검색 하는 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="a41fb-103">Extends the ICorDebugType interface to retrieve the type identifier  of a base type or complex (user-defined) type.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a41fb-104">메서드</span><span class="sxs-lookup"><span data-stu-id="a41fb-104">Methods</span></span>  
  
|<span data-ttu-id="a41fb-105">메서드</span><span class="sxs-lookup"><span data-stu-id="a41fb-105">Method</span></span>||  
|------------|-|  
|[<span data-ttu-id="a41fb-106">GetTypeID 메서드</span><span class="sxs-lookup"><span data-stu-id="a41fb-106">GetTypeID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype2-gettypeid-method.md)|<span data-ttu-id="a41fb-107">가져옵니다는 [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) 이 형식에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="a41fb-107">Gets a [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) for this type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a41fb-108">설명</span><span class="sxs-lookup"><span data-stu-id="a41fb-108">Remarks</span></span>  
 <span data-ttu-id="a41fb-109">이 인터페이스는 ICorDebugType 인터페이스를 논리적으로 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="a41fb-109">This interface is a logical extension of the ICorDebugType interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a41fb-110">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a41fb-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a41fb-111">예제</span><span class="sxs-lookup"><span data-stu-id="a41fb-111">Example</span></span>  
 <span data-ttu-id="a41fb-112">다음 코드 조각에서는 [ICorDebugType2::GetTypeID](../../../../docs/framework/unmanaged-api/debugging/icordebugtype2-gettypeid-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="a41fb-112">The following code fragment illustrates the use of the [ICorDebugType2::GetTypeID](../../../../docs/framework/unmanaged-api/debugging/icordebugtype2-gettypeid-method.md) method.</span></span>  
  
```  
// (error checking omitted for brevity)  
// given an ICorDebugType *pType  
  
ICorDebugType2 *pType2 = NULL;  
pType->QueryInterface(IID_ICorDebugType2, &pType);  
  
COR_TYPEID id;  
pType2->GetTypeID(&id);  
  
// now we can use existing APIs to get information about this COR_TYPEID  
```  
  
## <a name="requirements"></a><span data-ttu-id="a41fb-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a41fb-113">Requirements</span></span>  
 <span data-ttu-id="a41fb-114">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a41fb-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a41fb-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a41fb-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a41fb-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a41fb-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a41fb-117">**.NET framework 버전:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a41fb-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a41fb-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a41fb-118">See Also</span></span>  
 [<span data-ttu-id="a41fb-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a41fb-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
