---
title: "ICorDebugILFrame::GetArgument 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugILFrame.GetArgument
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugILFrame::GetArgument
helpviewer_keywords:
- GetArgument method [.NET Framework debugging]
- ICorDebugILFrame::GetArgument method [.NET Framework debugging]
ms.assetid: 4e2fd423-f643-4c27-ba5f-41b5ebc3b416
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 592354f11faac1fb4d5b050a096f4eab04643c0f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugilframegetargument-method"></a><span data-ttu-id="fdc73-102">ICorDebugILFrame::GetArgument 메서드</span><span class="sxs-lookup"><span data-stu-id="fdc73-102">ICorDebugILFrame::GetArgument Method</span></span>
<span data-ttu-id="fdc73-103">이 Microsoft MSIL (intermediate language) 스택 프레임에서 지정 된 인수 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="fdc73-103">Gets the value of the specified argument in this Microsoft intermediate language (MSIL) stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fdc73-104">구문</span><span class="sxs-lookup"><span data-stu-id="fdc73-104">Syntax</span></span>  
  
```  
HRESULT GetArgument (  
    [in] DWORD                  dwIndex,  
    [out] ICorDebugValue        **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fdc73-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fdc73-105">Parameters</span></span>  
 `dwIndex`  
 <span data-ttu-id="fdc73-106">[in] MSIL이 스택 프레임에 대 한 인수의 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="fdc73-106">[in] The index of the argument in this MSIL stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="fdc73-107">[out] 검색 된 값을 나타내는 ICorDebugValue 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="fdc73-107">[out] A pointer to the address of an ICorDebugValue object that represents the retrieved value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fdc73-108">설명</span><span class="sxs-lookup"><span data-stu-id="fdc73-108">Remarks</span></span>  
 <span data-ttu-id="fdc73-109">`GetArgument` 시간 (JIT) 컴파일된 프레임 또는 MSIL 스택 프레임에 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fdc73-109">The `GetArgument` method can be used either in an MSIL stack frame or in a just-in-time (JIT) compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fdc73-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fdc73-110">Requirements</span></span>  
 <span data-ttu-id="fdc73-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fdc73-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fdc73-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fdc73-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fdc73-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fdc73-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fdc73-114">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fdc73-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
