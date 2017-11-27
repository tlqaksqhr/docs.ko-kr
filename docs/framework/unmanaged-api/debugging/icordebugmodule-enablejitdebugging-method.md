---
title: "ICorDebugModule::EnableJITDebugging 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModule.EnableJITDebugging
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugModule::EnableJITDebugging
helpviewer_keywords:
- ICorDebugModule::EnableJITDebugging method [.NET Framework debugging]
- EnableJITDebugging method [.NET Framework debugging]
ms.assetid: 0a65e2a4-5bb6-496c-ae6f-40474426b5a6
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 31fc3b7c2b977dbfd6f10cc767f81748243dfce4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmoduleenablejitdebugging-method"></a><span data-ttu-id="5ef25-102">ICorDebugModule::EnableJITDebugging 메서드</span><span class="sxs-lookup"><span data-stu-id="5ef25-102">ICorDebugModule::EnableJITDebugging Method</span></span>
<span data-ttu-id="5ef25-103">적시에 (JIT) 컴파일러가이 모듈 내에서 메서드에 대 한 디버깅 정보를 유지할지 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ef25-103">Controls whether the just-in-time (JIT) compiler preserves debugging information for methods within this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ef25-104">구문</span><span class="sxs-lookup"><span data-stu-id="5ef25-104">Syntax</span></span>  
  
```  
HRESULT EnableJITDebugging(  
    [in] BOOL bTrackJITInfo,  
    [in] BOOL bAllowJitOpts  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5ef25-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5ef25-105">Parameters</span></span>  
 `bTrackJITInfo`  
 <span data-ttu-id="5ef25-106">[in] 이 값을 설정 `true` JIT 컴파일러는 Microsoft MSIL (intermediate language) 버전과이 단원에서는 각 메서드의 JIT 컴파일된 버전 간의 매핑 정보를 유지 하기 위해 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ef25-106">[in] Set this value to `true` to enable the JIT compiler to preserve mapping information between the Microsoft intermediate language (MSIL) version and the JIT-compiled version of each method in this module.</span></span>  
  
 `bAllowJitOpts`  
 <span data-ttu-id="5ef25-107">[in] 이 값을 설정 `true` JIT 컴파일러 디버깅에 대 한 특정 관련 JIT 최적화를 사용 하 여 코드 생성에 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ef25-107">[in] Set this value to `true` to enable the JIT compiler to generate code with certain JIT-specific optimizations for debugging.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5ef25-108">설명</span><span class="sxs-lookup"><span data-stu-id="5ef25-108">Remarks</span></span>  
 <span data-ttu-id="5ef25-109">디버거가 활성화 되어 있을 때 로드 되는 모든 모듈에 대해 기본적으로 JIT 디버깅을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ef25-109">JIT debugging is enabled by default for all modules that are loaded when the debugger is active.</span></span> <span data-ttu-id="5ef25-110">프로그래밍 방식으로 또는 사용 안 함 설정을 전역 설정이 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ef25-110">Programmatically enabling or disabling the settings overrides global settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ef25-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5ef25-111">Requirements</span></span>  
 <span data-ttu-id="5ef25-112">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5ef25-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ef25-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5ef25-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5ef25-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5ef25-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5ef25-115">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ef25-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
