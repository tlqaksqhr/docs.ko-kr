---
title: ICorDebugBoxValue::GetObject 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugBoxValue.GetObject
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBoxValue::GetObject
helpviewer_keywords:
- ICorDebugBoxValue::GetObject method [.NET Framework debugging]
- GetObject method, ICorDebugBoxValue interface [.NET Framework debugging]
ms.assetid: 3a867a5b-bf94-493f-a4f5-b28685cf5325
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cfc8800915009912716ec2ed9044a633a8ad0582
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33401747"
---
# <a name="icordebugboxvaluegetobject-method"></a><span data-ttu-id="cf5ae-102">ICorDebugBoxValue::GetObject 메서드</span><span class="sxs-lookup"><span data-stu-id="cf5ae-102">ICorDebugBoxValue::GetObject Method</span></span>
<span data-ttu-id="cf5ae-103">Boxed 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cf5ae-103">Gets the boxed value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf5ae-104">구문</span><span class="sxs-lookup"><span data-stu-id="cf5ae-104">Syntax</span></span>  
  
```  
HRESULT GetObject (  
    [out] ICorDebugObjectValue **ppObject  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cf5ae-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cf5ae-105">Parameters</span></span>  
 `ppObject`  
 <span data-ttu-id="cf5ae-106">[out] Boxed 값을 나타내는 ICorDebugObjectValue 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="cf5ae-106">[out] A pointer to the address of an ICorDebugObjectValue object that represents the boxed value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cf5ae-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cf5ae-107">Requirements</span></span>  
 <span data-ttu-id="cf5ae-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="cf5ae-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf5ae-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cf5ae-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cf5ae-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cf5ae-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cf5ae-111">**.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf5ae-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
