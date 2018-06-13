---
title: ICorProfilerInfo 인터페이스
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo
helpviewer_keywords:
- ICorProfilerInfo interface [.NET Framework profiling]
ms.assetid: eb4e4ce0-06e7-4469-bbc4-edc2eb5da4b1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: da5a041e8a18420b4cf9962e4315683be8857711
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33462272"
---
# <a name="icorprofilerinfo-interface"></a>ICorProfilerInfo 인터페이스
코드 프로파일러가 공용 언어 런타임 (CLR) 이벤트 모니터링 및 제어 정보 요청을 통신 하 여 사용할 메서드를 제공 합니다.  
  
> [!NOTE]
>  각 메서드에 `ICorProfilerInfo` 인터페이스 성공 또는 실패를 나타내는 HRESULT를 반환 합니다. 가능한 반환 코드 목록은 CorError.h를 참조 하십시오.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[BeginInprocDebugging 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md)|초기화는 프로세스 디버깅을 지원 합니다. 이 메서드는.NET Framework 버전 2.0에서에서 사용 되지 않습니다.|  
|[EndInprocDebugging 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-endinprocdebugging-method.md)|In-process 디버깅 세션을 종료합니다. 이 메서드는.NET Framework 버전 2.0에서에서 사용 되지 않습니다.|  
|[ForceGC 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-forcegc-method.md)|가비지 수집이 런타임 내에서 수행 되도록 지정 합니다.|  
|[GetAppDomainInfo 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getappdomaininfo-method.md)|지정 된 응용 프로그램 도메인에 대 한 정보를 가져옵니다.|  
|[GetAssemblyInfo 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getassemblyinfo-method.md)|지정된 된 어셈블리에 대 한 정보를 가져옵니다.|  
|[GetClassFromObject 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getclassfromobject-method.md)|가져옵니다는 `ClassID` 의<br /><br /> 지정 된 개체의 `ObjectID`합니다.|  
|[GetClassFromToken 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getclassfromtoken-method.md)|메타 데이터 토큰이 지정 된 클래스의 ID를 가져옵니다. 이 메서드는.NET Framework 버전 2.0에서에서 사용 되지 않습니다. 사용 하 여 [icorprofilerinfo2:: Getclassfromtokenandtypeargs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassfromtokenandtypeargs-method.md) 메서드 대신 합니다.|  
|[GetClassIDInfo 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getclassidinfo-method.md)|지정된 된 클래스에 대 한 부모 모듈 및 메타 데이터 토큰을 가져옵니다.|  
|[GetCodeInfo 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getcodeinfo-method.md)|지정된 함수 ID와 연결된 네이티브 코드의 범위를 가져옵니다. 이 메서드는 사용되지 않습니다. 사용 하 여 [icorprofilerinfo2:: Getcodeinfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md) 메서드 대신 합니다.|  
|[GetCurrentThreadID 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getcurrentthreadid-method.md)|관리 되는 스레드 이면 현재 스레드의 ID를 가져옵니다.|  
|[GetEventMask 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md)|프로파일러가 CLR에서 이벤트 알림을 받으려는 현재 이벤트 범주를 가져옵니다.|  
|[GetFunctionFromIP 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getfunctionfromip-method.md)|관리 되는 코드의 명령 포인터에 매핑하는 `FunctionID`합니다.|  
|[GetFunctionFromToken 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getfunctionfromtoken-method.md)|함수의 ID를 가져옵니다. 이 메서드는.NET Framework 버전 2.0에서에서 사용 되지 않습니다. 사용 하 여 [icorprofilerinfo2:: Getfunctionfromtokenandtypeargs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md) 메서드 대신 합니다.|  
|[GetFunctionInfo 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getfunctioninfo-method.md)|부모 클래스와 메타 데이터가 지정된 된 함수에 대 한 토큰 가져옵니다.|  
|[GetHandleFromThread 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-gethandlefromthread-method.md)|Win32 스레드 핸들을 스레드 ID를 매핑합니다.|  
|[GetILFunctionBody 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getilfunctionbody-method.md)|헤더에서 시작 되는 Microsoft MSIL (intermediate language) 코드에서 메서드 본문에 대 한 포인터를 가져옵니다.|  
|[GetILFunctionBodyAllocator 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getilfunctionbodyallocator-method.md)|MSIL 코드에서 메서드 본문을 바꾸는 데 사용 하는 메모리를 할당 하기 위한 메서드를 제공 하는 인터페이스를 가져옵니다.|  
|[GetILToNativeMapping 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md)|지정된 된 함수에 포함 된 코드에 대 한 네이티브 오프셋 간의 맵을 MSIL 오프셋에서 가져옵니다.|  
|[GetInprocInspectionInterface 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getinprocinspectioninterface-method.md)|ICorDebugProcess 인터페이스에 대해 쿼리할 수 있는 개체를 가져옵니다. 이 메서드는.NET Framework 버전 2.0에서에서 사용 되지 않습니다.|  
|[GetInprocInspectionIThisThread 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getinprocinspectionithisthread-method.md)|ICorDebugThread 인터페이스에 대해 쿼리할 수 있는 개체를 가져옵니다. 이 메서드는.NET Framework 버전 2.0에서에서 사용 되지 않습니다.|  
|[GetModuleInfo 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmoduleinfo-method.md)|모듈 ID가 지정된 경우 모듈의 파일 이름 및 모듈의 부모 어셈블리 ID를 반환합니다.|  
|[GetModuleMetaData 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md)|지정된 된 모듈에 매핑되는 메타 데이터 인터페이스 인스턴스를 가져옵니다.|  
|[GetObjectSize 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getobjectsize-method.md)|지정된 된 개체의 크기를 가져옵니다.|  
|[GetThreadContext 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getthreadcontext-method.md)|현재 스레드와 연결 된 지정 된 컨텍스트 id를 가져옵니다.|  
|[GetThreadInfo 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getthreadinfo-method.md)|지정 된 스레드에 대 한 현재 Win32 스레드 id를 가져옵니다.|  
|[GetTokenAndMetadataFromFunction 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-gettokenandmetadatafromfunction-method.md)|메타 데이터 토큰 및 지정된 된 함수에 대 한 토큰에 대해 사용할 수 있는 메타 데이터 인터페이스의 인스턴스를 가져옵니다.|  
|[IsArrayClass 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-isarrayclass-method.md)|지정된 된 클래스 배열 클래스 인지 확인 합니다.|  
|[SetEnterLeaveFunctionHooks 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setenterleavefunctionhooks-method.md)|"입력", "둡니다" 및 "tailcall" 관리 되는 함수의 후크에서 호출 되는 프로파일러 구현 함수를 지정 합니다.|  
|[SetEventMask 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)|프로파일러가 CLR에서 알림을 받으려는 이벤트 형식을 지정 하는 값을 설정 합니다.|  
|[SetFunctionIDMapper 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)|`FunctionID` 값을 대체 값에 매핑하기 위해 호출되는 프로파일러 구현 함수를 지정합니다. 대체 값은 프로파일러의 함수 진입점/종료점 후크에 전달됩니다.|  
|[SetFunctionReJIT 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionrejit-method.md)|구현되지 않았습니다. 사용하지 마십시오.|  
|[SetILFunctionBody 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md)|지정된 된 모듈에 지정 된 함수의 본문을 바꿉니다.|  
|[SetILInstrumentedCodeMap 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md)|지정된 된 함수의 원래 MSIL 오프셋 새 함수의 프로파일러에 수정 된 MSIL 오프셋에 매핑하는 방법을 지정 합니다.|  
  
## <a name="remarks"></a>설명  
 메서드를 호출 하는 프로파일러는 `ICorProfilerInfo` 이벤트 모니터링을 제어 및 정보를 요청 하기 위해 CLR와 통신 하는 인터페이스입니다.  
  
 메서드는 `ICorProfilerInfo` 인터페이스 자유 스레드 모델을 사용 하 여 CLR에서 구현 됩니다. 각 메서드가 HRESULT를 반환하여 성공 또는 실패를 나타냅니다. 가능한 반환 코드 목록은 CorError.h를 참조 하십시오.  
  
 구현을 통해 CLR 전달 [icorprofilercallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md), `ICorProfilerInfo` 초기화 중 각 코드 프로파일러에 대 한 인터페이스입니다. 코드 프로파일러가의 메서드를 호출한 다음 수는 `ICorProfilerInfo` CLR의 제어를 받으며 실행 되는 관리 코드에 대 한 정보를 가져오는 인터페이스입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [프로파일링 인터페이스](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [ICorProfilerInfo2 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
