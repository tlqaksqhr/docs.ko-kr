---
title: ICorDebugType::GetBase 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetBase
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetBase
helpviewer_keywords:
- ICorDebugType::GetBase method [.NET Framework debugging]
- GetBase method [.NET Framework debugging]
ms.assetid: f24e1af9-c220-4f79-ae62-4153ec17ea81
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b96c6ab8fb9065e1a08ad45a7f4482ef0b32788b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33418887"
---
# <a name="icordebugtypegetbase-method"></a><span data-ttu-id="dfab5-102">ICorDebugType::GetBase 메서드</span><span class="sxs-lookup"><span data-stu-id="dfab5-102">ICorDebugType::GetBase Method</span></span>
<span data-ttu-id="dfab5-103">이 나타내는 형식이 있는 경우 기본 형식을 나타내는 ICorDebugType에 대 한 인터페이스 포인터를 가져옵니다 `ICorDebugType`합니다.</span><span class="sxs-lookup"><span data-stu-id="dfab5-103">Gets an interface pointer to an ICorDebugType that represents the base type, if one exists, of the type represented by this `ICorDebugType`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dfab5-104">구문</span><span class="sxs-lookup"><span data-stu-id="dfab5-104">Syntax</span></span>  
  
```  
HRESULT GetBase (  
    [out] ICorDebugType   **pBase  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="dfab5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="dfab5-105">Parameters</span></span>  
 `pBase`  
 <span data-ttu-id="dfab5-106">[out] 주소에 대 한 포인터는 `ICorDebugType` 기본 형식을 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="dfab5-106">[out] A pointer to the address of an `ICorDebugType` object that represents the base type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dfab5-107">설명</span><span class="sxs-lookup"><span data-stu-id="dfab5-107">Remarks</span></span>  
 <span data-ttu-id="dfab5-108">출력 개체 또는 해당 부모 클래스의 모든 필드 하는 등의 일반적인 디버거 기능을 구현 하는 형식에 대 한 기본 형식 조회 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfab5-108">Looking up the base type for a type is useful to implement common debugger functionality, such as printing out all the fields of an object or its parent classes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dfab5-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="dfab5-109">Requirements</span></span>  
 <span data-ttu-id="dfab5-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="dfab5-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dfab5-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dfab5-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dfab5-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dfab5-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dfab5-113">**.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dfab5-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
