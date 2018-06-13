---
title: CorDebugCodeInvokePurpose 열거형
ms.date: 03/30/2017
api_name:
- CorDebugInvokePurpose
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 31833a2d-a0d6-48a1-b05f-995ca307a08f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 79730bb98a7e2d84517ed068a52614ad8650f541
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33406223"
---
# <a name="cordebugcodeinvokepurpose-enumeration"></a><span data-ttu-id="43501-102">CorDebugCodeInvokePurpose 열거형</span><span class="sxs-lookup"><span data-stu-id="43501-102">CorDebugCodeInvokePurpose Enumeration</span></span>
<span data-ttu-id="43501-103">내보낸 함수가 관리 코드를 호출하는 이유를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="43501-103">Describes why an exported function calls managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43501-104">구문</span><span class="sxs-lookup"><span data-stu-id="43501-104">Syntax</span></span>  
  
```  
typedef enum CorDebugCodeInvokePurpose  
{  
    CODE_INVOKE_PURPOSE_NONE,  
    CODE_INVOKE_PURPOSE_NATIVE_TO_MANAGED_TRANSITION,    
    CODE_INVOKE_PURPOSE_CLASS_INIT,  
    CODE_INVOKE_PURPOSE_INTERFACE_DISPATCH,  
} CorDebugCodeInvokePurpose;  
```  
  
## <a name="members"></a><span data-ttu-id="43501-105">멤버</span><span class="sxs-lookup"><span data-stu-id="43501-105">Members</span></span>  
  
|<span data-ttu-id="43501-106">멤버</span><span class="sxs-lookup"><span data-stu-id="43501-106">Member</span></span>|<span data-ttu-id="43501-107">설명</span><span class="sxs-lookup"><span data-stu-id="43501-107">Description</span></span>|  
|------------|-----------------|  
|`CODE_INVOKE_PURPOSE_NONE`|<span data-ttu-id="43501-108">없음 또는 알 수 없음.</span><span class="sxs-lookup"><span data-stu-id="43501-108">None or unknown.</span></span>|  
|`CODE_INVOKE_PURPOSE_NATIVE_TO_MANAGED_TRANSITION`|<span data-ttu-id="43501-109">관리 코드는 역방향 p-invoke 등의 관리되는 진입점을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="43501-109">The managed code will run any managed entry point, such as a reverse p-invoke.</span></span> <span data-ttu-id="43501-110">그보다 자세한 용도는 런타임에서 확인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="43501-110">Any more detailed purpose is unknown by the runtime.</span></span>|  
|`CODE_INVOKE_PURPOSE_CLASS_INIT`|<span data-ttu-id="43501-111">관리 코드가 정적 생성자를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="43501-111">The managed code will run a static constructor.</span></span>|  
|`CODE_INVOKE_PURPOSE_INTERFACE_DISPATCH`|<span data-ttu-id="43501-112">관리 코드가 호출된 일부 인터페이스 메서드에 대한 구현을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="43501-112">The managed code will run the implementation for some interface method that was called.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="43501-113">설명</span><span class="sxs-lookup"><span data-stu-id="43501-113">Remarks</span></span>  
 <span data-ttu-id="43501-114">이 열거형을 사용 하 여는 [icordebugprocess6::](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-getexportstepinfo-method.md) 메서드에서 관리 코드를 통해 단계별로 실행 하는 방법에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="43501-114">This enumeration is used by the [ICorDebugProcess6::GetExportStepInfo](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-getexportstepinfo-method.md) method to provide information about stepping through managed code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="43501-115">이 열거형은 .NET 네이티브 디버깅 시나리오에서만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="43501-115">This enumeration is intended for use in .NET Native debugging scenarios only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43501-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="43501-116">Requirements</span></span>  
 <span data-ttu-id="43501-117">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="43501-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43501-118">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="43501-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="43501-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="43501-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="43501-120">**.NET framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43501-120">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43501-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="43501-121">See Also</span></span>  
 [<span data-ttu-id="43501-122">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="43501-122">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
 [<span data-ttu-id="43501-123">디버깅</span><span class="sxs-lookup"><span data-stu-id="43501-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
