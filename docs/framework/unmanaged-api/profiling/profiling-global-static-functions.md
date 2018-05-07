---
title: 프로파일링 전역 정적 함수
ms.date: 03/30/2017
helpviewer_keywords:
- global static functions [.NET Framework profiling]
- profiling global static functions [.NET Framework]
- unmanaged global static functions [.NET Framework], profiling
ms.assetid: 08a13a57-dc49-488d-b937-31e3051fda97
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8bb5d93c91de857ebbee63009cad73fba7e1d284
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="profiling-global-static-functions"></a>프로파일링 전역 정적 함수
이 섹션에서는 프로 파일링 API를 사용 하는 관리 되지 않는 API 함수를 설명 합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
  
## <a name="net-framework-version-1-profiling-functions"></a>.NET framework 버전 1 프로 파일링 함수  
 [FunctionEnter 함수](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md)  
 제어는 함수에 전달 되 고 있음을 프로파일러에 알립니다. .NET Framework 2.0의에서 사용 되지 않습니다.  
  
 [FunctionLeave 함수](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md)  
 호출자에 게 반환 하는 함수 인지 프로파일러에 알립니다. .NET Framework 2.0의에서 사용 되지 않습니다.  
  
 [FunctionTailcall 함수](../../../../docs/framework/unmanaged-api/profiling/functiontailcall-function.md)  
 다른 함수에 대 한 마무리 호출이 수행 하려고 합니다. 현재 실행 중인 함수는 프로파일러에 알립니다. .NET Framework 2.0의에서 사용 되지 않습니다.  
  
## <a name="net-framework-version-2-profiling-functions"></a>.NET framework 버전 2 프로 파일링 함수  
 [FunctionIDMapper 함수](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md)  
 지정 된 식별자는 함수에 사용할 대체 ID에 다시 매핑할 수는 프로파일러에 알립니다.는 [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md), [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md), 및 [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) 해당 함수에 대 한 콜백을 합니다. 또한 프로파일러를를 해당 함수에 대 한 콜백을 받을지 여부를 나타낼 수 있습니다.  
  
 [FunctionEnter2 함수](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)  
 제어는 함수에 전달 되는 및 프레임 및 함수 인수는 스택에 대 한 정보를 제공 합니다. 프로파일러에 알립니다. 사용 되지 않는 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]합니다.  
  
 [FunctionLeave2 함수](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)  
 함수는 호출자에 반환 하 고 스택 프레임 및 함수 반환 값에 대 한 정보를 제공 프로파일러에 알립니다. 사용 되지 않는 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]합니다.  
  
 [FunctionTailcall2 함수](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)  
 현재 실행 중인 함수를 다른 함수에 대 한 마무리 호출이 수행 하려고 하 고 스택 프레임에 대 한 정보를 제공 프로파일러에 알립니다. 사용 되지 않는 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]합니다.  
  
 [StackSnapshotCallback 함수](../../../../docs/framework/unmanaged-api/profiling/stacksnapshotcallback-function.md)  
 프로파일러 동안 시작 되는 스택 워크가 스택의 각 관리 되는 프레임 및 관리 되지 않는 프레임의 각 실행에 대 한 정보 제공의 [icorprofilerinfo2:: Dostacksnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) 메서드.  
  
## <a name="net-framework-version-4-profiling-functions"></a>.NET framework 버전 4 프로 파일링 함수  
 [FunctionIDMapper2 함수](../../../../docs/framework/unmanaged-api/profiling/functionidmapper2-function.md)  
 지정 된 식별자는 함수에 사용할 대체 ID에 다시 매핑할 수는 프로파일러에 알립니다.는 [FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md), [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md), 및 [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md), 또는[FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md), 및 [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) 해당 함수에 대 한 콜백을 합니다. 또한 프로파일러를를 해당 함수에 대 한 콜백을 받을지 여부를 나타낼 수 있습니다.  
  
 `FunctionIDMapper2` 확장은 [FunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/functionidmapper-function.md) 작동는 `clientData` 프로파일러는 런타임 중 명확히 구분 하기 사용할 수 있는 매개 변수입니다.  
  
 [FunctionEnter3 함수](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)  
 제어는 함수에 전달 되 고 있음을 프로파일러에 알립니다.  
  
 [FunctionEnter3WithInfo 함수](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)  
 에 전달 될 수 있는 핸들을 제공 및 제어는 함수에 전달 되 고 있음을 프로파일러에 알립니다. [icorprofilerinfo3:: Getfunctionenter3info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionenter3info-method.md) 스택 프레임 및 함수 인수를 검색 합니다.  
  
 [FunctionLeave3 함수](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)  
 제어는 함수에서 반환 되는 프로파일러에 알립니다.  
  
 [FunctionLeave3WithInfo 함수](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)  
 에 전달 될 수 있는 핸들을 제공 하 고 제어는 함수에서 반환 되는 프로파일러에 알립니다 [icorprofilerinfo3:: Getfunctionleave3info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md) 스택 프레임 및 반환 값을 검색 합니다.  
  
 [FunctionTailcall3 함수](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)  
 다른 함수에 대 한 마무리 호출이 수행 하려고 합니다. 현재 실행 중인 함수는 프로파일러에 알립니다.  
  
 [FunctionTailcall3WithInfo 함수](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)  
 에 전달 될 수 있는 핸들을 제공 하 고 현재 실행 중인 함수가 다른 함수에 대 한 마무리 호출이 수행 하려고 하는 프로파일러에 알립니다 [icorprofilerinfo3:: Getfunctiontailcall3info](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctiontailcall3info-method.md) 스택 프레임을 검색할 수 있습니다.  
  
## <a name="related-sections"></a>관련 단원  
 [프로파일링 개요](../../../../docs/framework/unmanaged-api/profiling/profiling-overview.md)  
  
 [프로파일링 인터페이스](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
  
 [프로파일링 열거형](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)  
  
 [프로파일링 구조체](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
