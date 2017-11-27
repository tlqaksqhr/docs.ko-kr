---
title: "ICorDebugModule::GetSize 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModule.GetSize
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugModule::GetSize
helpviewer_keywords:
- GetSize method, ICorDebugModule interface [.NET Framework debugging]
- ICorDebugModule::GetSize method [.NET Framework debugging]
ms.assetid: 5c68375d-145d-46ef-a7c8-2dc4257472de
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f7e107360bf26c05c3ab4c3bbcbfed7eb5b01675
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmodulegetsize-method"></a><span data-ttu-id="a25a6-102">ICorDebugModule::GetSize 메서드</span><span class="sxs-lookup"><span data-stu-id="a25a6-102">ICorDebugModule::GetSize Method</span></span>
<span data-ttu-id="a25a6-103">모듈의 바이트 단위로 크기를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a25a6-103">Gets the size, in bytes, of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a25a6-104">구문</span><span class="sxs-lookup"><span data-stu-id="a25a6-104">Syntax</span></span>  
  
```  
HRESULT GetSize(  
    [out] ULONG32 *pcBytes  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a25a6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a25a6-105">Parameters</span></span>  
 `pcBytes`  
 <span data-ttu-id="a25a6-106">[out] 크기 (바이트)에서 모듈입니다.</span><span class="sxs-lookup"><span data-stu-id="a25a6-106">[out] The size of the module in bytes.</span></span>  
  
 <span data-ttu-id="a25a6-107">모듈 네이티브 이미지 생성기 (NGen.exe)에서 생성 된, 경우 모듈의 크기는 0이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a25a6-107">If the module was produced from the native image generator (NGen.exe), the size of the module will be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a25a6-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a25a6-108">Requirements</span></span>  
 <span data-ttu-id="a25a6-109">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a25a6-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a25a6-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a25a6-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a25a6-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a25a6-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a25a6-112">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a25a6-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
