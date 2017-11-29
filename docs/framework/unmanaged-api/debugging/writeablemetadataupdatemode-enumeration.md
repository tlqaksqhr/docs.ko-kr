---
title: "WriteableMetadataUpdateMode 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: WriteableMetadataUpdateMode
api_location: mscordbi.dll
api_type: COM
ms.assetid: 6758f4d3-6bc7-4c99-8582-e9be00566784
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 001d80a2232f5b6fbfb43b9de5deafb3317e426d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="writeablemetadataupdatemode-enumeration"></a><span data-ttu-id="5d14d-102">WriteableMetadataUpdateMode 열거형</span><span class="sxs-lookup"><span data-stu-id="5d14d-102">WriteableMetadataUpdateMode Enumeration</span></span>
<span data-ttu-id="5d14d-103">[.NET Framework 4.5.2 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="5d14d-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="5d14d-104">메타데이터에 대한 메모리 내 업데이트가 디버거에 표시되는지 여부를 지정하는 값을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5d14d-104">Provides values that specify whether in-memory updates to metadata are visible to a debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d14d-105">구문</span><span class="sxs-lookup"><span data-stu-id="5d14d-105">Syntax</span></span>  
  
```cpp
typedef enum WriteableMetadataUpdateMode {  
   LegacyCompatPolicy,  
   AlwaysShowUpdates  
} WriteableMetadataUpdateMode;  
```  
  
## <a name="members"></a><span data-ttu-id="5d14d-106">멤버</span><span class="sxs-lookup"><span data-stu-id="5d14d-106">Members</span></span>  
  
|<span data-ttu-id="5d14d-107">멤버 이름</span><span class="sxs-lookup"><span data-stu-id="5d14d-107">Member name</span></span>|<span data-ttu-id="5d14d-108">설명</span><span class="sxs-lookup"><span data-stu-id="5d14d-108">Description</span></span>|  
|-----------------|-----------------|  
|`LegacyCompatPolicy`|<span data-ttu-id="5d14d-109">메타데이터에 대한 메모리 내 업데이트를 표시할 때 .NET Framework 이전 버전과의 호환성을 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="5d14d-109">Maintain compatibility with previous versions of the .NET Framework when making in-memory updates to metadata visible.</span></span> <span data-ttu-id="5d14d-110">자세한 내용은 설명 부분을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5d14d-110">See the Remarks section for more information.</span></span>|  
|`AlwaysShowUpdates`|<span data-ttu-id="5d14d-111">메타데이터에 대한 메모리 내 업데이트를 디버거에 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="5d14d-111">Make in-memory updates to metadata visible to the debugger.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5d14d-112">설명</span><span class="sxs-lookup"><span data-stu-id="5d14d-112">Remarks</span></span>  
 <span data-ttu-id="5d14d-113">멤버는 `WriteableMetadataUpdateMode` 열거형에 전달 될 수는 [SetWriteableMetadataUpdateMode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess7-setwriteablemetadataupdatemode-method.md) 메타 데이터는 대상 프로세스의 메모리 내 업데이트가 있는지 여부를 제어 하는 메서드를 디버거에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d14d-113">A member of the `WriteableMetadataUpdateMode` enumeration can be passed to the [SetWriteableMetadataUpdateMode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess7-setwriteablemetadataupdatemode-method.md) method to control whether in-memory updates to metadata in the target process are visible to the debugger.</span></span>  
  
 <span data-ttu-id="5d14d-114">`LegacyCompatPolicy` 옵션은 .NET Framework 4.5.2 이전 버전에서와 같은 동작을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="5d14d-114">The `LegacyCompatPolicy` option enforces the same behavior as in versions of the .NET Framework before 4.5.2.</span></span> <span data-ttu-id="5d14d-115">이로 인해 업데이트의 메타데이터가 표시되지 않는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="5d14d-115">This often means that metadata from updates is not visible.</span></span> <span data-ttu-id="5d14d-116">그러나 여러 디버깅 메서드를 호출하면 디버거가 업데이트를 표시하도록 암시적으로 강제 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d14d-116">However, calls to a number of debugging methods implicitly coerce the debugger to make updates visible.</span></span> <span data-ttu-id="5d14d-117">예를 들어, 디버거 통과 하는 경우 [icordebugilframe:: Getlocalvariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md) 모듈의 현재 상태와 일치 하는 스냅숏으로 업데이트 됩니다 메서드의 원래 메타 데이터를 모든 메타 데이터에 없는 변수의 인덱스는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="5d14d-117">For example, if the debugger passes [ICorDebugILFrame::GetLocalVariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md) the index of a variable not found in the method's original metadata, all metadata for the module is updated to a snapshot matching the current state of the process.</span></span> <span data-ttu-id="5d14d-118">다시 말해서, `LegacyCompatPolicy` 옵션을 사용하는 경우에는 디버거가 관리되지 않는 디버깅 API의 다른 부분을 사용하는 방식에 따라 사용 가능한 메타데이터 업데이트가 표시되지 않을 수도 있고 일부 또는 모든 업데이트가 표시될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d14d-118">In other words, with the `LegacyCompatPolicy` option, the debugger might see none, some, or all of the available metadata updates, depending on how it uses other parts of the unmanaged debugging API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d14d-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5d14d-119">Requirements</span></span>  
 <span data-ttu-id="5d14d-120">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5d14d-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d14d-121">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5d14d-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5d14d-122">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5d14d-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5d14d-123">**.NET framework 버전:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d14d-123">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d14d-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5d14d-124">See Also</span></span>  
 [<span data-ttu-id="5d14d-125">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="5d14d-125">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
 [<span data-ttu-id="5d14d-126">SetWriteableMetadataUpdateMode 메서드</span><span class="sxs-lookup"><span data-stu-id="5d14d-126">SetWriteableMetadataUpdateMode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess7-setwriteablemetadataupdatemode-method.md)
