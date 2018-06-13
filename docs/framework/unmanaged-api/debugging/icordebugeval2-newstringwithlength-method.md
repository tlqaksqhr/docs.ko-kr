---
title: ICorDebugEval2::NewStringWithLength 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.NewStringWithLength
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::NewStringWithLength
helpviewer_keywords:
- NewStringWithLength method [.NET Framework debugging]
- ICorDebugEval2::NewStringWithLength method [.NET Framework debugging]
ms.assetid: d5f54a34-6335-4708-b407-a756ec70fab4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6b3b77a0ffc7af3b3640d1b255bd3be522f45a7a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413552"
---
# <a name="icordebugeval2newstringwithlength-method"></a><span data-ttu-id="029f3-102">ICorDebugEval2::NewStringWithLength 메서드</span><span class="sxs-lookup"><span data-stu-id="029f3-102">ICorDebugEval2::NewStringWithLength Method</span></span>
<span data-ttu-id="029f3-103">지정 된 내용으로 지정 된 길이의 문자열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="029f3-103">Creates a string of the specified length, with the specified contents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="029f3-104">구문</span><span class="sxs-lookup"><span data-stu-id="029f3-104">Syntax</span></span>  
  
```  
HRESULT NewStringWithLength (  
    [in] LPCWSTR               string,  
    [in] UINT                  uiLength  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="029f3-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="029f3-105">Parameters</span></span>  
 `string`  
 <span data-ttu-id="029f3-106">[in] 문자열 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="029f3-106">[in] A pointer to the string value.</span></span>  
  
 `uiLength`  
 <span data-ttu-id="029f3-107">[in] 문자열의 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="029f3-107">[in] Length of the string.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="029f3-108">설명</span><span class="sxs-lookup"><span data-stu-id="029f3-108">Remarks</span></span>  
 <span data-ttu-id="029f3-109">Null 문자의 호출자에 관리 되는 문자열 이어야 하는데 경우 문자열의 후행는 `NewStringWithLength` 메서드가 문자열 길이 후행 null 문자가 포함 되어 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="029f3-109">If the string's trailing null character is expected to be in the managed string, the caller of the `NewStringWithLength` method must ensure that the string length includes the trailing null character.</span></span>  
  
 <span data-ttu-id="029f3-110">문자열은 항상 스레드가 현재 실행 중인 응용 프로그램 도메인에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="029f3-110">The string is always created in the application domain in which the thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="029f3-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="029f3-111">Requirements</span></span>  
 <span data-ttu-id="029f3-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="029f3-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="029f3-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="029f3-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="029f3-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="029f3-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="029f3-115">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="029f3-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
