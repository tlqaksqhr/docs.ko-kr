---
title: ICorDebugFunction::GetClass 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetClass
helpviewer_keywords:
- GetClass method, ICorDebugFunction interface [.NET Framework debugging]
- ICorDebugFunction::GetClass method [.NET Framework debugging]
ms.assetid: 27967230-144f-40d3-9e23-961d0241abd9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 184e578efb549a1dc2e9ec1e30a29ff289b68719
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33411705"
---
# <a name="icordebugfunctiongetclass-method"></a><span data-ttu-id="8f808-102">ICorDebugFunction::GetClass 메서드</span><span class="sxs-lookup"><span data-stu-id="8f808-102">ICorDebugFunction::GetClass Method</span></span>
<span data-ttu-id="8f808-103">이 함수는 멤버의 클래스를 나타내는 ICorDebugClass 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8f808-103">Gets an ICorDebugClass object that represents the class this function is a member of.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f808-104">구문</span><span class="sxs-lookup"><span data-stu-id="8f808-104">Syntax</span></span>  
  
```  
HRESULT GetClass (  
    [out] ICorDebugClass **ppClass  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8f808-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8f808-105">Parameters</span></span>  
 `ppClass`  
 <span data-ttu-id="8f808-106">[out] 주소에 대 한 포인터는 `ICorDebugClass` 이 함수가 클래스의 멤버인 경우 클래스 또는 null을 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="8f808-106">[out] A pointer to the address of the `ICorDebugClass` object that represents the class, or null, if this function is not a member of a class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f808-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8f808-107">Requirements</span></span>  
 <span data-ttu-id="8f808-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8f808-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f808-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8f808-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8f808-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8f808-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8f808-111">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f808-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
