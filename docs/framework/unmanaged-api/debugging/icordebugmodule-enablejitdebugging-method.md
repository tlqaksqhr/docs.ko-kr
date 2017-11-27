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
# <a name="icordebugmoduleenablejitdebugging-method"></a>ICorDebugModule::EnableJITDebugging 메서드
적시에 (JIT) 컴파일러가이 모듈 내에서 메서드에 대 한 디버깅 정보를 유지할지 여부를 제어 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT EnableJITDebugging(  
    [in] BOOL bTrackJITInfo,  
    [in] BOOL bAllowJitOpts  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `bTrackJITInfo`  
 [in] 이 값을 설정 `true` JIT 컴파일러는 Microsoft MSIL (intermediate language) 버전과이 단원에서는 각 메서드의 JIT 컴파일된 버전 간의 매핑 정보를 유지 하기 위해 사용할 수 있도록 합니다.  
  
 `bAllowJitOpts`  
 [in] 이 값을 설정 `true` JIT 컴파일러 디버깅에 대 한 특정 관련 JIT 최적화를 사용 하 여 코드 생성에 사용할 수 있도록 합니다.  
  
## <a name="remarks"></a>설명  
 디버거가 활성화 되어 있을 때 로드 되는 모든 모듈에 대해 기본적으로 JIT 디버깅을 사용 합니다. 프로그래밍 방식으로 또는 사용 안 함 설정을 전역 설정이 무시 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
