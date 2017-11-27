---
title: "ICorDebugAppDomain3 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAppDomain3
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugAppDomain3
helpviewer_keywords: ICorDebugAppDomain3 interface [.NET Framework debugging]
ms.assetid: 875ef5be-c1e7-4d95-97e9-d3a667aeaba0
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 08f125d7fc388a9b2d31c9cc1cebf2605ffa7e23
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugappdomain3-interface"></a><span data-ttu-id="afebf-102">ICorDebugAppDomain3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="afebf-102">ICorDebugAppDomain3 Interface</span></span>
<span data-ttu-id="afebf-103">관리 되는 표현에 대 한 정보를 검색 하는 메서드를 제공 [!INCLUDE[wrt](../../../../includes/wrt-md.md)] 응용 프로그램 도메인에 현재 로드 된 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="afebf-103">Provides methods to retrieve information about the managed representations of [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types currently loaded in an application domain.</span></span> <span data-ttu-id="afebf-104">이 인터페이스는 ICorDebugAppDomain 및 ICorDebugAppDomain2 인터페이스의 확장입니다.</span><span class="sxs-lookup"><span data-stu-id="afebf-104">This interface is an extension of the ICorDebugAppDomain and ICorDebugAppDomain2 interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="afebf-105">메서드</span><span class="sxs-lookup"><span data-stu-id="afebf-105">Methods</span></span>  
  
|<span data-ttu-id="afebf-106">메서드</span><span class="sxs-lookup"><span data-stu-id="afebf-106">Method</span></span>|<span data-ttu-id="afebf-107">설명</span><span class="sxs-lookup"><span data-stu-id="afebf-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="afebf-108">Icordebugappdomain3:: Getcachedwinrttypes</span><span class="sxs-lookup"><span data-stu-id="afebf-108">ICorDebugAppDomain3::GetCachedWinRTTypes</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md)|<span data-ttu-id="afebf-109">모든 캐시에 대 한 열거자를 가져옵니다 [!INCLUDE[wrt](../../../../includes/wrt-md.md)] 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="afebf-109">Gets an enumerator for all cached [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types.</span></span>|  
|[<span data-ttu-id="afebf-110">Icordebugappdomain3:: Getcachedwinrttypesforiids</span><span class="sxs-lookup"><span data-stu-id="afebf-110">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypesforiids-method.md)|<span data-ttu-id="afebf-111">캐시에 대 한 열거자를 가져옵니다 [!INCLUDE[wrt](../../../../includes/wrt-md.md)] 10 인터페이스 식별자에 따라 응용 프로그램 도메인의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="afebf-111">Gets an enumerator for cached [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types in an application domain based on their interface identifiers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="afebf-112">설명</span><span class="sxs-lookup"><span data-stu-id="afebf-112">Remarks</span></span>  
 <span data-ttu-id="afebf-113">이 인터페이스는 디버거가 함수 평가 호출을 함께 사용할 수를 위한 `M:System.Runtime.InteropServices.Marshal.GetInspectableIIDs(System.Object)`합니다.</span><span class="sxs-lookup"><span data-stu-id="afebf-113">This interface is meant to be used by a debugger in conjunction with a function evaluation call to `M:System.Runtime.InteropServices.Marshal.GetInspectableIIDs(System.Object)`.</span></span> <span data-ttu-id="afebf-114">메서드가에서 지 원하는 인터페이스 식별자를 검색 하는 경우는 [!INCLUDE[wrt](../../../../includes/wrt-md.md)] 서버 개체를 디버거에서이 인터페이스에 정의 된 메서드를 사용 하 여 이러한 인터페이스에 해당 하는 관리 되는 형식에 매핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="afebf-114">When the method retrieves the interface identifiers supported by a [!INCLUDE[wrt](../../../../includes/wrt-md.md)] server object, the debugger may use the methods defined in this interface to map them to managed types that correspond to those interfaces.</span></span>  
  
 <span data-ttu-id="afebf-115">이 인터페이스의 인스턴스를 검색 하려면 실행 `QueryInterface` ICorDebugAppDomain 또는 ICorDebugAppDomain2 인터페이스의 인스턴스에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="afebf-115">To retrieve an instance of this interface, run `QueryInterface` on an instance of the ICorDebugAppDomain or ICorDebugAppDomain2 interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="afebf-116">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="afebf-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="afebf-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="afebf-117">Requirements</span></span>  
 <span data-ttu-id="afebf-118">**플랫폼:**[!INCLUDE[wrt](../../../../includes/wrt-md.md)]</span><span class="sxs-lookup"><span data-stu-id="afebf-118">**Platforms:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]</span></span>  
  
 <span data-ttu-id="afebf-119">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="afebf-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="afebf-120">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="afebf-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="afebf-121">**.NET framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="afebf-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afebf-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="afebf-122">See Also</span></span>  
 [<span data-ttu-id="afebf-123">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="afebf-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
