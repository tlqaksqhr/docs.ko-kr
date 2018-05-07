---
title: ICorProfilerInfo2::DoStackSnapshot 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.DoStackSnapshot
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::DoStackSnapshot
helpviewer_keywords:
- ICorProfilerInfo2::DoStackSnapshot method [.NET Framework profiling]
- DoStackSnapshot method [.NET Framework profiling]
ms.assetid: 287b11e9-7c52-4a13-ba97-751203fa97f4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 338120932b0bcbe390332515856aaeaa3bc34a56
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilerinfo2dostacksnapshot-method"></a>ICorProfilerInfo2::DoStackSnapshot 메서드
에서는 지정 된 스레드에 대 한 스택 관리 되는 프레임에 설명 하 고 프로파일러는 콜백을 통해 정보를 보냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT DoStackSnapshot(  
    [in] ThreadID thread,  
    [in] StackSnapshotCallback *callback,  
    [in] ULONG32 infoFlags,  
    [in] void *clientData,  
    [in, size_is(contextSize), length_is(contextSize)] BYTE context[],  
    [in] ULONG32 contextSize);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `thread`  
 [in] 대상 스레드가의 ID입니다.  
  
 에 null을 전달 `thread` 현재 스레드에 대 한 스냅숏을 생성 합니다. 경우는 `ThreadID` 의 다른 스레드에 전달 됩니다, 공용 언어 런타임 (CLR) 해당 스레드를 일시 중단, 스냅숏, 수행 및 다시 시작 합니다.  
  
 `callback`  
 [in] 구현에 대 한 포인터는 [StackSnapshotCallback](../../../../docs/framework/unmanaged-api/profiling/stacksnapshotcallback-function.md) 메서드를 각 관리 되는 프레임 및 관리 되지 않는 프레임의 각 실행에 대 한 정보와 함께 프로파일러를 제공 하는 CLR에 의해 호출 됩니다.  
  
 `StackSnapshotCallback` 메서드는 프로파일러 기록기에 의해 구현 됩니다.  
  
 `infoFlags`  
 [in] 값은 [COR_PRF_SNAPSHOT_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-snapshot-info-enumeration.md) 하 여 각 프레임에 대 한 다시 전달할 데이터의 양을 지정 하는 열거형 `StackSnapshotCallback`합니다.  
  
 `clientData`  
 [in] 에 직접 전달 되는 클라이언트 데이터에 대 한 포인터는 `StackSnapshotCallback` 콜백 함수입니다.  
  
 `context`  
 [in] Win32에 대 한 포인터 `CONTEXT` 스택 워크를 초기값으로 사용 되는 구조입니다. Win32 `CONTEXT` 구조 CPU 레지스터의 값을 포함 하 고 특정 시점에서 CPU의 상태를 나타냅니다.  
  
 시드 스택 워크가 스택의 맨이 관리 되지 않는 도우미 코드; 시작 위치를 결정 하는 CLR을 사용 하면 그렇지 않으면 초기값은 무시 됩니다. 비동기 워크에 대 한 초기값을 제공 되어야 합니다. 동기 워크를 수행 하는 없는 시드가 필요 합니다.  
  
 `context` 매개 변수는 COR_PRF_SNAPSHOT_CONTEXT 플래그에 전달 된 경우에 유효는 `infoFlags` 매개 변수입니다.  
  
 `contextSize`  
 [in] 크기는 `CONTEXT` 에서 참조 하는 구조는 `context` 매개 변수입니다.  
  
## <a name="remarks"></a>설명  
 에 대 한 null을 전달 `thread` 현재 스레드에 대 한 스냅숏을 생성 합니다. 대상 스레드가 일시 중단 된 경우에 스냅숏은 다른 스레드의 가져올 수 있습니다.  
  
 프로파일러가 스택을 탐색 하는 경우 호출 `DoStackSnapshot`합니다. CLR에서 해당 호출에서 반환 되기 전에 호출 하면 `StackSnapshotCallback` 여러 번 한 번 각각에 대해 관리 되는 프레임 (또는 관리 되지 않는 프레임의 실행) 스택에 합니다. 관리 되지 않는 프레임이 발생 한 경우를 검색 해야 해당 사용자가 직접 합니다.  
  
 스택 워크는 순서는 반대 프레임으로 스택에 밀어넣은 어떻게입니다: (마지막 푸시할) 첫 번째, 기본 (첫 번째 푸시) 프레임별 마지막 리프입니다.  
  
 프로파일러는 관리 되는 스택 워크를 프로그래밍 하는 방법에 대 한 자세한 내용은 참조 [.NET Framework 2.0의 프로파일러 스택 워크: 기본 사항 및 기능 이외에](http://go.microsoft.com/fwlink/?LinkId=73638)합니다.  
  
 다음 섹션에 설명 된 대로 스택 워크는 동기적 이거나 비동기적일 수 있습니다.  
  
## <a name="synchronous-stack-walk"></a>동기 스택 워크  
 동기 스택 워크는 콜백에 대 한 응답의 현재 스레드 스택을 탐색 하는 작업이 포함 됩니다. 시드 나 일시 중단에 필요 하지 않습니다.  
  
 동기 수행한 프로파일러 중 하나를 호출 하는 CLR에 대 한 응답으로 호출 하는 시기를 [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) (또는 [ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)) 메서드를 호출 하면 `DoStackSnapshot` 의 스택을 탐색 하 고 현재 스레드입니다. 스택 모양을 알림을에서 같은 보려는 경우 유용 [icorprofilercallback:: Objectallocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md)합니다. 호출 하면 `DoStackSnapshot` 내에서 프로그램 `ICorProfilerCallback` 에 null을 전달 메서드는 `context` 및 `thread` 매개 변수입니다.  
  
## <a name="asynchronous-stack-walk"></a>비동기 스택 워크  
 비동기 스택 워크는 다른 스레드의 스택 또는 현재 스레드의 현재 스레드에 대 한 스택 워크가 하지만 콜백에 대 한 응답에 없는 과정이 수반 됩니다. 비동기 워크 필요 스택 맨 관리 되지 않는 하지 않은 코드를 플랫폼의 일부 이면 시드 호출 (PInvoke) 또는 COM 호출 되었지만 CLR 자체의 도우미 코드입니다. 예를 들어 코드 적시에 (JIT) 컴파일 또는 가비지 수집을 수행 하는 도우미 코드입니다.  
  
 직접 대상 스레드가 일시 중단 하 여 초기값을 가져와야 하 고 스택 워크 맨 위의 찾을 때까지 직접 관리 되는 프레임입니다. 대상 스레드를 일시 중단 된 후에 대상 스레드의 현재 레지스터 컨텍스트를 가져옵니다. 다음으로 호출 하 여 비관리 코드에 레지스터 컨텍스트로 가리키는지 여부를 결정 [icorprofilerinfo:: Getfunctionfromip](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getfunctionfromip-method.md) -반환 하는 경우는 `FunctionID` 0과 같은 프레임은 관리 되지 않는 코드입니다. 첫 번째 관리 되는 프레임에 도달 하 고 해당 프레임에 대 한 레지스터 컨텍스트에 따라 시드 컨텍스트 계산 될 때까지 스택을 이제 합니다.  
  
 호출 `DoStackSnapshot` 비동기 스택 워크를 시작 하 여 시드 컨텍스트를 사용 합니다. 초기값을 지정 하지 않으면 경우 `DoStackSnapshot` 스택의 맨 위에 있는 관리 되는 프레임을 건너뛸 수 있습니다 및 결과적 하면 스택 워크가 불완전 합니다. JIT 컴파일 또는 네이티브 이미지 생성기 (Ngen.exe)를 가리켜야 초기값을 제공한 경우-생성 된 코드입니다. 그렇지 않으면 `DoStackSnapshot` CORPROF_E_STACKSNAPSHOT_UNMANAGED_CTX 오류 코드를 반환 합니다.  
  
 비동기 스택 워크 수 쉽게 교착 상태가 발생할 또는 액세스 위반, 다음이 지침을 따르지 않는 경우:  
  
-   직접 스레드를 중지 하면에서 관리 되는 코드를 실행 하지 않은 스레드만 다른 스레드를 일시 중단 해야 합니다.  
  
-   블록 항상 프로그램 [icorprofilercallback:: Threaddestroyed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threaddestroyed-method.md) 해당 스레드의 스택 워크 완료 될 때까지 콜백 합니다.  
  
-   프로파일러 가비지 수집을 트리거할 수 있는 CLR 함수를 호출 하는 동안 잠금을 보유 하지 않습니다. 즉, 소유 하는 스레드에서 가비지 수집을 트리거하는 호출을 수행할 수 있는 경우는 잠금을 유지 하지 않습니다.  
  
 이기도 교착 상태의 위험이 호출 하는 경우 `DoStackSnapshot` 별도 대상 스레드 스택을 탐색할 수 있도록 프로파일러 만든 스레드가 있습니다. 특정 처음으로 만든 스레드에서 시작 `ICorProfilerInfo*` 메서드 (포함 하 여 `DoStackSnapshot`), CLR 스레드별 해당 스레드에서 CLR 관련 초기화를 수행 합니다. 프로파일러는를 안내 하려는 해당 스택 대상 스레드가 일시 중단 및 해당 대상 스레드가이 스레드 초기화를 수행 하는 데 필요한 잠금을 소유한에 발생 하는 경우 교착 상태가 발생 합니다. 이러한 교착 상태를 방지 하려면 초기에 호출을 확인 `DoStackSnapshot` 안내 하는 경우 프로파일러 만든 스레드에서는 별도 스레드를 대상으로 하지만 대상 스레드를 먼저 일시지 않습니다. 이 초기 호출 스레드를 초기화 하는 교착 상태 없이 완료할 수 있는지 확인 합니다. 경우 `DoStackSnapshot` 성공 하 고 하나 이상의 프레임을 보고 해당 시점 이후에 것이 해당 프로파일러 만든 스레드를 모든 대상 스레드 및 호출을 일시 중단에 대 한 안전 `DoStackSnapshot` 대상 스레드 스택을 탐색 하 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorProfilerInfo 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [ICorProfilerInfo2 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
