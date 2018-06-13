---
title: ICorDebugProcess3::SetEnableCustomNotification 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugProcess3.SetEnableCustomNotification Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess3::SetEnableCustomNotification
helpviewer_keywords:
- ICorDebugProcess3::SetEnableCustomNotification method [.NET Framework debugging]
- SetEnableCustomNotification method [.NET Framework debugging]
ms.assetid: afd88ee9-2589-4461-a75a-9b6fe55a2525
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2a84061cff7cc5dbdeba1e0e66396e04a8f345cb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423158"
---
# <a name="icordebugprocess3setenablecustomnotification-method"></a><span data-ttu-id="af367-102">ICorDebugProcess3::SetEnableCustomNotification 메서드</span><span class="sxs-lookup"><span data-stu-id="af367-102">ICorDebugProcess3::SetEnableCustomNotification Method</span></span>
<span data-ttu-id="af367-103">사용 하도록 설정 하 고 지정 된 형식의 사용자 지정 디버거 알림을 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="af367-103">Enables and disables custom debugger notifications of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af367-104">구문</span><span class="sxs-lookup"><span data-stu-id="af367-104">Syntax</span></span>  
  
```  
HRESULT SetEnableCustomNotification(ICorDebugClass * pClass,  
                                    BOOL fEnable);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="af367-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="af367-105">Parameters</span></span>  
 `pClass`  
 <span data-ttu-id="af367-106">[in] 사용자 지정 디버거 알림을 지정 하는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="af367-106">[in] The type that specifies custom debugger notifications.</span></span>  
  
 `fEnable`  
 <span data-ttu-id="af367-107">[in] `true` 사용자 지정 디버거 알림을;를 사용 하도록 설정 하려면 `false` 알림을 사용 하지 않으려면입니다.</span><span class="sxs-lookup"><span data-stu-id="af367-107">[in] `true` to enable custom debugger notifications; `false` to disable notifications.</span></span> <span data-ttu-id="af367-108">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="af367-108">The default value is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="af367-109">설명</span><span class="sxs-lookup"><span data-stu-id="af367-109">Remarks</span></span>  
 <span data-ttu-id="af367-110">때 `fEnable` 로 설정 된 `true`에 대 한 호출이 <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> 메서드 트리거는 [icordebugmanagedcallback3:: Customnotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) 콜백 합니다.</span><span class="sxs-lookup"><span data-stu-id="af367-110">When `fEnable` is set to `true`, calls to the <xref:System.Diagnostics.Debugger.NotifyOfCrossThreadDependency%2A?displayProperty=nameWithType> method trigger an [ICorDebugManagedCallback3::CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) callback.</span></span> <span data-ttu-id="af367-111">기본적으로 알림이 비활성화 되었습니다. 따라서 디버거에서 인식 하 고 처리 하는 알림 유형을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af367-111">Notifications are disabled by default; therefore, the debugger must specify any notification types it knows about and wants to handle.</span></span> <span data-ttu-id="af367-112">때문에 [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) 클래스의 응용 프로그램 도메인에서 범위가, 디버거가 호출 해야 `SetEnableCustomNotification` 전체 프로세스에서 알림을 받으려는 경우 프로세스에 있는 모든 응용 프로그램 도메인에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="af367-112">Because the [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) class is scoped by application domain, the debugger must call `SetEnableCustomNotification` for every application domain in the process if it wants to receive the notification across the entire process.</span></span>  
  
 <span data-ttu-id="af367-113">부터는 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], 지원 됩니다 크로스 스레드 종속성 알림입니다.</span><span class="sxs-lookup"><span data-stu-id="af367-113">Starting with the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)], the only supported notification is a cross-thread dependency notification.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af367-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="af367-114">Requirements</span></span>  
 <span data-ttu-id="af367-115">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="af367-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af367-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="af367-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="af367-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="af367-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="af367-118">**.NET framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af367-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af367-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="af367-119">See Also</span></span>  
 [<span data-ttu-id="af367-120">ICorDebugProcess3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="af367-120">ICorDebugProcess3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-interface.md)  
 [<span data-ttu-id="af367-121">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="af367-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="af367-122">디버깅</span><span class="sxs-lookup"><span data-stu-id="af367-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
