---
title: "ICorDebugAppDomain::GetName 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAppDomain.GetName
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugAppDomain::GetName
helpviewer_keywords:
- ICorDebugAppDomain::GetName method [.NET Framework debugging]
- GetName method, ICorDebugAppDomain interface [.NET Framework debugging]
ms.assetid: 02c596d7-00b0-4e2c-856b-5425158fcefd
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 590bfb5d7d8cac8e322bddfe6258ad9bf377dad6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugappdomaingetname-method"></a><span data-ttu-id="6fa85-102">ICorDebugAppDomain::GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="6fa85-102">ICorDebugAppDomain::GetName Method</span></span>
<span data-ttu-id="6fa85-103">응용 프로그램 도메인의 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6fa85-103">Gets the name of the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6fa85-104">구문</span><span class="sxs-lookup"><span data-stu-id="6fa85-104">Syntax</span></span>  
  
```  
HRESULT GetName (  
    [in]  ULONG32           cchName,  
    [out] ULONG32           *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]   
         WCHAR              szName[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6fa85-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6fa85-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="6fa85-106">[in] `szName` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="6fa85-106">[in] The size of the `szName` array.</span></span> <span data-ttu-id="6fa85-107">이 메서드를 쿼리 모드로 전환 하는 0으로이 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6fa85-107">Set this value to zero to put this method in query mode.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="6fa85-108">[out] 이름 또는에 실제로 반환 된 문자 수의 크기에 대 한 포인터 `szName`합니다.</span><span class="sxs-lookup"><span data-stu-id="6fa85-108">[out] A pointer to the size of the name or the number of characters actually returned in `szName`.</span></span> <span data-ttu-id="6fa85-109">이 값을 버퍼의 크기를 알고 호출자에 게 사용 하면 쿼리 모드에서 이름에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6fa85-109">In query mode, this value lets the caller know how large a buffer to allocate for the name.</span></span>  
  
 `szName`  
 <span data-ttu-id="6fa85-110">[out] 응용 프로그램 도메인의 이름을 저장 하는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="6fa85-110">[out] An array that stores the name of the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6fa85-111">설명</span><span class="sxs-lookup"><span data-stu-id="6fa85-111">Remarks</span></span>  
 <span data-ttu-id="6fa85-112">디버거 호출는 `GetName` 메서드를 한 번의 이름에 필요한 버퍼 크기를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6fa85-112">A debugger calls the `GetName` method once to get the size of a buffer needed for the name.</span></span> <span data-ttu-id="6fa85-113">디버거에서 버퍼를 할당 하 고 메서드를 호출 하는 두 번째 시간에 버퍼를 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="6fa85-113">The debugger allocates the buffer, and then calls the method a second time to fill the buffer.</span></span> <span data-ttu-id="6fa85-114">첫 번째 호출의 이름, 크기를 가져오려면 라고 *쿼리 모드*합니다.</span><span class="sxs-lookup"><span data-stu-id="6fa85-114">The first call, to get the size of the name, is referred to as *query mode*.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6fa85-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6fa85-115">Requirements</span></span>  
 <span data-ttu-id="6fa85-116">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6fa85-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6fa85-117">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6fa85-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6fa85-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6fa85-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6fa85-119">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6fa85-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
