---
title: "ICorDebugAssembly::GetName 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAssembly.GetName
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugAssembly::GetName
helpviewer_keywords:
- ICorDebugAssembly::GetName method [.NET Framework debugging]
- GetName method, ICorDebugAssembly interface [.NET Framework debugging]
ms.assetid: cdeda721-b214-4503-a291-c70b68b5f36b
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d54139f8d7562f7f1ceb6e704731cd890a5f99df
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugassemblygetname-method"></a><span data-ttu-id="2d139-102">ICorDebugAssembly::GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="2d139-102">ICorDebugAssembly::GetName Method</span></span>
<span data-ttu-id="2d139-103">하는 어셈블리의 이름을 가져옵니다이 `ICorDebugAssembly` 인스턴스가 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="2d139-103">Gets the name of the assembly that this `ICorDebugAssembly` instance represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d139-104">구문</span><span class="sxs-lookup"><span data-stu-id="2d139-104">Syntax</span></span>  
  
```  
HRESULT GetName (  
    [in] ULONG32  cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2d139-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2d139-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="2d139-106">[in] `szName` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="2d139-106">[in] The size of the `szName` array.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="2d139-107">[out] 이름의 실제 길이 지정 하는 정수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2d139-107">[out] A pointer to an integer that specifies the actual length of the name.</span></span>  
  
 `szName`  
 <span data-ttu-id="2d139-108">[out] 이름을 저장 하는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="2d139-108">[out] An array that stores the name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2d139-109">설명</span><span class="sxs-lookup"><span data-stu-id="2d139-109">Remarks</span></span>  
 <span data-ttu-id="2d139-110">`GetName` 메서드는 어셈블리의 전체 경로 파일 이름을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d139-110">The `GetName` method returns the full path and file name of the assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2d139-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2d139-111">Requirements</span></span>  
 <span data-ttu-id="2d139-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2d139-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d139-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2d139-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2d139-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2d139-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2d139-115">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d139-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
