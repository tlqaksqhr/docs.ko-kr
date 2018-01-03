---
title: "ICorDebugProcess7::SetWriteableMetadataUpdateMode 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: ICorDebugProcess7.SetWriteableMetadataUpdateMode
api_location: mscordbi.dll
api_type: COM
ms.assetid: 8589bba7-7304-45ba-9e31-7bf43dfd5c19
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e901fd623893b9c03e1b5835adc72c6bd225ead4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugprocess7setwriteablemetadataupdatemode-method"></a><span data-ttu-id="1b008-102">ICorDebugProcess7::SetWriteableMetadataUpdateMode 메서드</span><span class="sxs-lookup"><span data-stu-id="1b008-102">ICorDebugProcess7::SetWriteableMetadataUpdateMode Method</span></span>
<span data-ttu-id="1b008-103">[.NET Framework 4.5.2 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="1b008-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="1b008-104">대상 프로세스 내에서 디버거가 메타데이터에 대한 메모리 내 업데이트를 처리하는 방법을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="1b008-104">Configures how the debugger handles in-memory updates to metadata within the target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b008-105">구문</span><span class="sxs-lookup"><span data-stu-id="1b008-105">Syntax</span></span>  
  
```cpp
HRESULT SetWriteableMetadataUpdateMode(  
   WriteableMetadataUpdateMode flags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1b008-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1b008-106">Parameters</span></span>  
 `flags`  
 <span data-ttu-id="1b008-107">A [WriteableMetadataUpdateMode](../../../../docs/framework/unmanaged-api/debugging/writeablemetadataupdatemode-enumeration.md) 대상 프로세스의 메타 데이터에 대 한 메모리 내 업데이트 표시 되는지 여부를 지정 하는 열거형 값 (`WriteableMetadataUpdateMode::AlwaysShowUpdates`) 않거나 표시 되지 않는 (`WriteableMetadataUpdateMode::LegacyCompatPolicy`)을 디버거에 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b008-107">A [WriteableMetadataUpdateMode](../../../../docs/framework/unmanaged-api/debugging/writeablemetadataupdatemode-enumeration.md) enumeration value that specifies whether in-memory updates to metadata in the target process are visible (`WriteableMetadataUpdateMode::AlwaysShowUpdates`) or not visible (`WriteableMetadataUpdateMode::LegacyCompatPolicy`) to the debugger.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1b008-108">설명</span><span class="sxs-lookup"><span data-stu-id="1b008-108">Remarks</span></span>  
 <span data-ttu-id="1b008-109">대상 프로세스의 메타데이터는 편집하며 계속하기, 프로파일러 또는 <xref:System.Reflection.Emit?displayProperty=nameWithType>에 의해 업데이트될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b008-109">Updates to the metadata of the target process can come from Edit and Continue, a profiler, or <xref:System.Reflection.Emit?displayProperty=nameWithType>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b008-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1b008-110">Requirements</span></span>  
 <span data-ttu-id="1b008-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1b008-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b008-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1b008-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1b008-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1b008-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1b008-114">**.NET framework 버전:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b008-114">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b008-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1b008-115">See Also</span></span>  
 [<span data-ttu-id="1b008-116">ICorDebugProcess7 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1b008-116">ICorDebugProcess7 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess7-interface.md)  
 [<span data-ttu-id="1b008-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1b008-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
