---
title: ICorDebugILFrame::EnumerateArguments 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.EnumerateArguments
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::EnumerateArguments
helpviewer_keywords:
- ICorDebugILFrame::EnumerateArguments method [.NET Framework debugging]
- EnumerateArguments method [.NET Framework debugging]
ms.assetid: 00ac81e2-a774-422a-bd88-54a4b3c99f73
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2e4a727dcfbc80b131f526a08b00bd0ec91ca209
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33415024"
---
# <a name="icordebugilframeenumeratearguments-method"></a><span data-ttu-id="7e1ff-102">ICorDebugILFrame::EnumerateArguments 메서드</span><span class="sxs-lookup"><span data-stu-id="7e1ff-102">ICorDebugILFrame::EnumerateArguments Method</span></span>
<span data-ttu-id="7e1ff-103">이 프레임에는 인수에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7e1ff-103">Gets an enumerator for the arguments in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e1ff-104">구문</span><span class="sxs-lookup"><span data-stu-id="7e1ff-104">Syntax</span></span>  
  
```  
HRESULT EnumerateArguments (  
    [out] ICorDebugValueEnum    **ppValueEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7e1ff-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7e1ff-105">Parameters</span></span>  
 `ppValueEnum`  
 <span data-ttu-id="7e1ff-106">[out] 이 프레임에서 인수에 대 한 열거자를 ICorDebugValueEnum 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7e1ff-106">[out] A pointer to the address of an ICorDebugValueEnum object that is the enumerator for the arguments in this frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7e1ff-107">설명</span><span class="sxs-lookup"><span data-stu-id="7e1ff-107">Remarks</span></span>  
 <span data-ttu-id="7e1ff-108">`EnumerateArguments` 이 ICorDebugILFrame 개체로 표시 되는 호출 프레임에서 사용할 수 있는 인수를 나열할 수 있는 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7e1ff-108">`EnumerateArguments` gets an enumerator that can list the arguments available in the call frame that is represented by this ICorDebugILFrame object.</span></span> <span data-ttu-id="7e1ff-109">인수는이 목록에 포함 됩니다 [vararg](/cpp/windows/vararg) (즉,: 인수의 변수 번호)이 아닌 인수를 뿐만 아니라 `vararg`합니다.</span><span class="sxs-lookup"><span data-stu-id="7e1ff-109">The list will include arguments that are [vararg](/cpp/windows/vararg) (that is, a variable number of arguments) as well as arguments that are not `vararg`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e1ff-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7e1ff-110">Requirements</span></span>  
 <span data-ttu-id="7e1ff-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7e1ff-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e1ff-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7e1ff-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7e1ff-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7e1ff-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7e1ff-114">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e1ff-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
