---
title: "ICorDebugClass::GetModule 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugClass.GetModule
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugClass::GetModule
helpviewer_keywords:
- GetModule method, ICorDebugClass interface [.NET Framework debugging]
- ICorDebugClass::GetModule method [.NET Framework debugging]
ms.assetid: 87029cc4-e5e1-42d5-8b98-655bb7ece520
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8021eb63b33f653e5b8c8a16d2e181223d5ee2b0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugclassgetmodule-method"></a><span data-ttu-id="ed714-102">ICorDebugClass::GetModule 메서드</span><span class="sxs-lookup"><span data-stu-id="ed714-102">ICorDebugClass::GetModule Method</span></span>
<span data-ttu-id="ed714-103">이 클래스를 정의 하는 모듈을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ed714-103">Gets the module that defines this class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed714-104">구문</span><span class="sxs-lookup"><span data-stu-id="ed714-104">Syntax</span></span>  
  
```  
HRESULT GetModule (  
    [out] ICorDebugModule    **pModule  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ed714-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ed714-105">Parameters</span></span>  
 `pModule`  
 <span data-ttu-id="ed714-106">[out] 이 클래스 정의 되어 있는 모듈을 나타내는 ICorDebugModule 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ed714-106">[out] A pointer to the address of an ICorDebugModule object that represents the module in which this class is defined.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed714-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ed714-107">Requirements</span></span>  
 <span data-ttu-id="ed714-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ed714-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed714-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ed714-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ed714-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ed714-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ed714-111">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed714-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
