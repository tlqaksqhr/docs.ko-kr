---
title: "프로파일링 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], profiling
- profiling interfaces [.NET Framework]
- interfaces [.NET Framework profiling]
ms.assetid: d9303db8-e881-4217-91b7-8c7573c8ef9e
caps.latest.revision: "31"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5c0423f9c8b01c1289e1107c0c16c59968a6e2a4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="profiling-interfaces"></a>프로파일링 인터페이스
이 섹션에서는 CLR(공용 언어 런타임)에서 실행되는 프로그램을 프로파일링하는 데 사용할 수 있는 관리되지 않는 인터페이스에 대해 설명합니다.  
  
## <a name="in-this-section"></a>단원 내용  
 [ICLRProfiling 인터페이스](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-interface.md)  
 제공 된 [AttachProfiler](../../../../docs/framework/unmanaged-api/profiling/iclrprofiling-attachprofiler-method.md) 프로파일러를 실행 중인 프로세스에 연결할 수 있도록 하는 방법입니다.  
  
 [ICorProfilerAssemblyReferenceProvider 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerassemblyreferenceprovider-interface.md)  
 CLR 프로파일러에 추가할 어셈블리 참조에 알릴 수 있습니다는 [icorprofilercallback:: Moduleloadfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) 콜백 합니다.  
  
 [ICorProfilerCallback 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 코드 프로파일러가 구독한 이벤트가 발생하면 CLR이 해당 프로파일러에 알림을 보내는 데 사용되는 메서드를 제공합니다.  
  
 [ICorProfilerCallback2 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)  
 .NET Framework 2.0 이상 버전에서 지원되는 콜백으로 `ICorProfilerCallback` 인터페이스를 확장합니다.  
  
 [ICorProfilerCallback3 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-interface.md)  
 CLR이 프로파일러에 연결 및 분리 상태 정보를 전달하는 데 사용하는 콜백 메서드를 제공합니다.  
  
 [ICorProfilerCallback4 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)  
 CLR이 프로파일러에 정보를 전달하는 데 사용하는 콜백 메서드를 제공합니다.  
  
 [ICorProfilerCallback5 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-interface.md)  
 가비지 컬렉션 루트에서 참조하는 개체의 전이적 Closure를 식별하는 메서드를 제공합니다.  
  
 [ICorProfilerCallback6 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-interface.md)  
 CLR이 어셈블리를 로드하는 중임을 프로파일러에 알리는 데 사용하는 콜백 메서드를 제공합니다.  
  
 [ICorProfilerCallback7 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-interface.md)  
 메모리 내 모듈과 연관 된 기호 스트림이 업데이트 되었음을 프로파일러에 알리기 위해 공용 언어 런타임에서 사용 하는 콜백 메서드를 제공 합니다.  
  
 [ICorProfilerFunctionControl 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md)  
 코드 프로파일러가 CLR과 통신하여 특정 메서드를 다시 컴파일할 때 JIT 컴파일러가 코드를 생성하는 방법을 제어할 수 있도록 하는 메서드를 제공합니다.  
  
 [ICorProfilerFunctionEnum 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)  
 CLR에서 함수 컬렉션을 순서대로 반복하는 메서드를 제공합니다.  
  
 [ICorProfilerInfo 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 코드 프로파일러가 CLR과 통신하여 이벤트 모니터링을 제어하고 정보를 요청하는 데 사용하는 메서드를 제공합니다.  
  
 [ICorProfilerInfo2 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)  
 .NET Framework 2.0 이상 버전에서 지원되는 메서드로 `ICorProfilerInfo` 인터페이스를 확장합니다.  
  
 [ICorProfilerInfo3 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 `ICorProfilerInfo2` 이상 버전에서 지원되는 메서드로 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] 인터페이스를 확장합니다.  
  
 [ICorProfilerInfo4 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)  
 코드 프로파일러가 CLR과 통신하여 이벤트 모니터링을 제어하고 정보를 요청하는 데 사용하는 메서드를 제공합니다.  
  
 [ICorProfilerInfo5 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md)  
 코드 프로파일러가 CLR과 통신하여 이벤트 모니터링을 제어하는 데 사용하는 메서드를 제공합니다.  
  
 [ICorProfilerInfo6 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md)  
 지정 된 NGen 모듈에 속하고 지정 된 메서드의 본문에 인라인 처리 되지 않은 모든 메서드에 열거자를 제공 합니다.  
  
 [ICorProfilerInfo7 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)  
 메모리 기호 스트림에 대 한 액세스를 제공 하는 및 모듈에 정의 된 메타 데이터가 새로 적용할 방법을 제공 합니다.  
  
 [ICorProfilerModuleEnum 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md)  
 응용 프로그램이나 프로파일러가 로드한 모듈 컬렉션을 순서대로 반복하는 메서드를 제공합니다.  
  
 [ICorProfilerObjectEnum 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)  
 생성 되는 고정된 개체의 컬렉션을 순차적으로 반복 하는 방법을 제공 [Ngen.exe (네이티브 이미지 생성기)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md)합니다.  
  
 [ICorProfilerThreadEnum 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)  
 CLR에서 스레드 컬렉션을 순서대로 반복하는 메서드를 제공합니다.  
  
 [IMethodMalloc 인터페이스](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md)  
 제공 된 [Alloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-alloc-method.md) 새 Microsoft MSIL (intermediate language) 함수 본문에 메모리를 할당 하는 메서드.  
  
## <a name="related-sections"></a>관련 단원  
 [프로 파일링 개요](../../../../docs/framework/unmanaged-api/profiling/profiling-overview.md)  
  
 [프로 파일링 전역 정적 함수](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)  
  
 [프로 파일링 열거형](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)  
  
 [프로 파일링 구조체](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
