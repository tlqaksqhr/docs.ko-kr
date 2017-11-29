---
title: "ICorDebugAssembly::EnumerateModules 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAssembly.EnumerateModules
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugAssembly::EnumerateModules
helpviewer_keywords:
- ICorDebugAssembly::EnumerateModules method [.NET Framework debugging]
- EnumerateModules method [.NET Framework debugging]
ms.assetid: c7ba51a1-0dd5-4452-b471-232febe0f897
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 28c6f2efe4a48c198bd64fa7f5665b97969dbc43
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugassemblyenumeratemodules-method"></a><span data-ttu-id="02952-102">ICorDebugAssembly::EnumerateModules 메서드</span><span class="sxs-lookup"><span data-stu-id="02952-102">ICorDebugAssembly::EnumerateModules Method</span></span>
<span data-ttu-id="02952-103">에 포함 된 모듈에 대 한 열거자를 가져옵니다는 `ICorDebugAssembly`합니다.</span><span class="sxs-lookup"><span data-stu-id="02952-103">Gets an enumerator for the modules contained in the `ICorDebugAssembly`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02952-104">구문</span><span class="sxs-lookup"><span data-stu-id="02952-104">Syntax</span></span>  
  
```  
HRESULT EnumerateModules (  
    [out] ICorDebugModuleEnum **ppModules  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="02952-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="02952-105">Parameters</span></span>  
 `ppModules`  
 <span data-ttu-id="02952-106">[out] ICorDebugModuleEnum 인터페이스는 열거자를 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="02952-106">[out] A pointer to the address of the ICorDebugModuleEnum interface that is the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="02952-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="02952-107">Requirements</span></span>  
 <span data-ttu-id="02952-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="02952-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="02952-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="02952-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="02952-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="02952-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="02952-111">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="02952-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
