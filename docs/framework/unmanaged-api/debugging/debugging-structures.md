---
title: 디버깅 구조체
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged structures [.NET Framework], debugging
- debugging structures [.NET Framework]
- structures [.NET Framework debugging]
ms.assetid: 173ba2c2-ab34-49ae-b6a8-e5c49882bf05
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6c7415920d34fc231bf82dd00199c7e01eec7a73
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="debugging-structures"></a>디버깅 구조체
이 섹션에서는 디버깅 API에서 사용하는 관리되지 않는 구조체에 대해 설명합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [CLR_DEBUGGING_VERSION 구조체](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-version-structure.md)  
 디버깅용 CLR(공용 언어 런타임)의 제품 버전을 정의합니다.  
  
 [CodeChunkInfo Structure1](../../../../docs/framework/unmanaged-api/debugging/codechunkinfo-structure.md)  
 메모리 내의 단일 코드 청크를 나타냅니다.  
  
 [CorDebugBlockingObject 구조체](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md)  
 스레드를 차단하는 개체 및 스레드 차단 이유를 정의합니다.  
  
 [CorDebugEHClause 구조체](../../../../docs/framework/unmanaged-api/debugging/cordebugehclause-structure.md)  
 지정된 IL(중간 언어) 부분에 대한 EH(예외 처리) 절을 나타냅니다.  
  
 [CorDebugExceptionObjectStackFrame 구조체](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md)  
 예외 개체의 스택 프레임 정보를 나타냅니다.  
  
 [CorDebugExceptionObjectStackFrame 구조체](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md)  
 지도 [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID를 해당 [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md) 개체입니다.  
  
 COR_ACTIVE_FUNCTION  
 스레드 프레임에서 현재 활성 상태인 함수에 대한 정보를 포함합니다.  
  
 [COR_ARRAY_LAYOUT 구조체](../../../../docs/framework/unmanaged-api/debugging/cor-array-layout-structure.md)  
 메모리 내 배열 개체의 레이아웃에 대한 정보를 제공합니다.  
  
 COR_DEBUG_IL_TO_NATIVE_MAP  
 MSIL(Microsoft Intermediate Language) 코드를 네이티브 코드에 매핑하는 데 사용되는 오프셋을 포함합니다.  
  
 COR_DEBUG_STEP_RANGE  
 코드 범위에 대한 오프셋 정보를 포함합니다.  
  
 [COR_FIELD 구조체](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md)  
 개체의 필드에 대한 정보를 포함합니다.  
  
 [COR_GC_REFERENCE 구조체](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md)  
 가비지 수집할 개체에 대한 정보를 포함합니다.  
  
 [COR_HEAPINFO 구조체](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md)  
 가비지 컬렉션 힙에 대한 일반 정보(열거 가능 여부 포함)를 제공합니다.  
  
 [COR_HEAPOBJECT 구조체](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md)  
 관리되는 힙의 개체에 대한 정보를 제공합니다.  
  
 COR_IL_MAP  
 함수의 상대 오프셋 변경 내용을 지정합니다.  
  
 [COR_SEGMENT 구조체](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md)  
 관리되는 힙의 메모리 영역에 대한 정보를 포함합니다.  
  
 [COR_TYPEID 구조체](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)  
 유형 식별자를 포함합니다.  
  
 [COR_TYPE_LAYOUT 구조체](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md)  
 메모리 내 개체의 레이아웃에 대한 정보를 제공합니다.  
  
 COR_VERSION  
 공용 언어 런타임의 4부분으로 구성된 표준 버전 번호를 저장합니다.  
  
 [StackTrace_SimpleContext 구조체](../../../../docs/framework/unmanaged-api/debugging/stacktrace-simplecontext-structure.md)  
 전체 `CONTEXT` 구조체 대신 사용할 수 있는 단순 컨텍스트를 제공합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [디버깅 Coclass](../../../../docs/framework/unmanaged-api/debugging/debugging-coclasses.md)  
  
 [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
  
 [디버깅 전역 정적 함수](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)  
  
 [디버깅 열거형](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
  
 [디버깅](../../../../docs/framework/unmanaged-api/debugging/index.md)
