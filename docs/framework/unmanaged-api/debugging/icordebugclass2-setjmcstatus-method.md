---
title: ICorDebugClass2::SetJMCStatus 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugClass2.SetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass2::SetJMCStatus
helpviewer_keywords:
- ICorDebugClass2::SetJMCStatus method [.NET Framework debugging]
- SetJMCStatus method, ICorDebugClass2 interface [.NET Framework debugging]
ms.assetid: 077e6c7f-f857-480c-bebb-76ee1de4e8fc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d234e01e3d47a64b9a001591ee2b61074eea8afb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33403396"
---
# <a name="icordebugclass2setjmcstatus-method"></a><span data-ttu-id="43cd9-102">ICorDebugClass2::SetJMCStatus 메서드</span><span class="sxs-lookup"><span data-stu-id="43cd9-102">ICorDebugClass2::SetJMCStatus Method</span></span>
<span data-ttu-id="43cd9-103">클래스의 각 메서드에 대해 메서드가 사용자 지정 코드 인지 여부를 나타내는 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="43cd9-103">For each method of the class, sets a value that indicates whether the method is user-defined code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43cd9-104">구문</span><span class="sxs-lookup"><span data-stu-id="43cd9-104">Syntax</span></span>  
  
```  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="43cd9-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="43cd9-105">Parameters</span></span>  
 `bIsJustMyCode`  
 <span data-ttu-id="43cd9-106">[in] 로 설정 `true` 사용자 정의 메서드가 임을 나타내기 위해 코딩 합니다; 그렇지 않으면로 설정 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="43cd9-106">[in] Set to `true` to indicate that the method is user-defined code; otherwise, set to `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="43cd9-107">설명</span><span class="sxs-lookup"><span data-stu-id="43cd9-107">Remarks</span></span>  
 <span data-ttu-id="43cd9-108">내 코드만 (JMC) 스텝 퍼는 사용자 지정 코드를 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="43cd9-108">A just-my-code (JMC) stepper will skip non-user-defined code.</span></span> <span data-ttu-id="43cd9-109">사용자 정의 코드는 디버깅할 수 있는 코드의 하위 집합 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="43cd9-109">User-defined code must be a subset of debuggable code.</span></span>  
  
 <span data-ttu-id="43cd9-110">`SetJMCStatus` 성공적으로 다른 모든 방법에 대 한 값을 설정 하는 경우에 어떤 방법에 대 한 값을 설정할 수 없는 경우 s_false HRESULT 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="43cd9-110">`SetJMCStatus` returns an HRESULT value of S_FALSE if it fails to set the value for any method, even if it successfully sets the value for all other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43cd9-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="43cd9-111">Requirements</span></span>  
 <span data-ttu-id="43cd9-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="43cd9-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43cd9-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="43cd9-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="43cd9-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="43cd9-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="43cd9-115">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43cd9-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
