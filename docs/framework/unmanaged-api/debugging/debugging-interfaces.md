---
title: 디버깅 인터페이스
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], debugging
- debugging interfaces [.NET Framework]
- interfaces [.NET Framework debugging]
ms.assetid: b6297c26-7624-4431-8af4-14112d07bcd5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 991e333c53101a2be2a8a19d3960c3d0879619be
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="debugging-interfaces"></a>디버깅 인터페이스
이 단원에서는 CLR(공용 언어 런타임)에서 실행되는 프로그램의 디버깅을 처리하는 관리되지 않는 인터페이스에 대해 설명합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [ICLRDataEnumMemoryRegions 인터페이스](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-interface.md)  
 호출자가 지정하는 메모리 영역을 열거하는 메서드를 제공합니다.  
  
 [ICLRDataEnumMemoryRegionsCallback 인터페이스](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md)  
 지정된 메모리 영역을 열거하려고 시도한 결과를 디버거에 보고하는 콜백 메서드를 `EnumMemoryRegions`에 제공합니다.  
  
 [ICLRDataTarget 인터페이스](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md)  
 대상 CLR 프로세스와 상호 작용하기 위한 메서드를 제공합니다.  
  
 [ICLRDataTarget2 인터페이스](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)  
 데이터 액세스 서비스 계층에서 대상 프로세스의 가상 메모리 영역을 조작하는 데 사용하는 `ICLRDataTarget`의 서브클래스입니다.  
  
 [ICLRDataTarget3 인터페이스](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-interface.md)  
 서브 클래스 [ICLRDataTarget2](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md) 예외 정보에 대 한 액세스를 제공 하는 합니다.  
  
 [ICLRDebugging 인터페이스](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-interface.md)  
 디버깅을 위해 모듈을 로드 및 언로드하는 작업을 처리하는 메서드를 제공합니다.  
  
 [ICLRDebuggingLibraryProvider 인터페이스](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-interface.md)  
 에 포함 되어는 [ProvideLibrary 메서드](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md) 메서드 라이브러리 공급자 콜백 인터페이스 공용 언어 런타임 버전별 디버깅 라이브러리를 찾아서에 로드할 요청 수를 가져옵니다.  
  
 [ICLRMetadataLocator 인터페이스](../../../../docs/framework/unmanaged-api/debugging/iclrmetadatalocator-interface.md)  
 데이터 액세스 서비스 계층에서 대상 프로세스의 어셈블리 메타데이터를 찾는 데 사용되는 인터페이스입니다.  
  
 [ICorDebug 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
 개발자가 CLR 환경에서 응용 프로그램을 디버깅하는 데 사용할 수 있는 메서드를 제공합니다.  
  
 [ICorDebugAppDomain Interface1](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-interface.md)  
 응용 프로그램 도메인 디버깅에 사용하는 메서드를 제공합니다.  
  
 [ICorDebugAppDomain2 Interface1](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain2-interface.md)  
 배열, 포인터, 함수 포인터 및 ByRef 형식에 사용할 수 있는 메서드를 제공합니다. 이 인터페이스는 `ICorDebugAppDomain` 인터페이스의 확장입니다.  
  
 [ICorDebugAppDomain3 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-interface.md)  
 응용 프로그램 도메인에서 [!INCLUDE[wrt](../../../../includes/wrt-md.md)] 형식으로 작동하기 위한 메서드를 제공합니다. 이 인터페이스는 `ICorDebugAppDomain` 및 `ICorDebugAppDomain2` 인터페이스의 확장입니다.  
  
 [ICorDebugAppDomain4 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain4-interface.md)  
 논리적으로 확장 된 [ICorDebugAppDomain](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain-interface.md) 인터페이스를 COM 호출 가능 래퍼에서 관리 되는 개체를 가져옵니다.  
  
 [ICorDebugAppDomainEnum Interface1](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomainenum-interface.md)  
 열거형의 다음 위치에서 시작하여 지정된 수만큼 `ICorDebugAppDomain` 값을 반환하는 메서드를 제공합니다.  
  
 [ICorDebugArrayValue Interface1](../../../../docs/framework/unmanaged-api/debugging/icordebugarrayvalue-interface.md)  
 1차원 배열이나 다차원 배열을 나타내는 `ICorDebugHeapValue`의 서브클래스입니다.  
  
 [ICorDebugAssembly Interface1](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-interface.md)  
 어셈블리를 나타냅니다.  
  
 [ICorDebugAssembly2 Interface1](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly2-interface.md)  
 어셈블리를 나타냅니다. 이 인터페이스는 `ICorDebugAssembly` 인터페이스의 확장입니다.  
  
 [ICorDebugAssembly3 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-interface.md)  
 논리적으로 확장 된 [ICorDebugAssembly](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly-interface.md) 컨테이너 어셈블리 및 해당 포함 된에 대 한 지원을 제공 하는 인터페이스입니다. **.NET 네이티브 에서만 사용할 수 있습니다.**  
  
 [ICorDebugAssemblyEnum Interface1](../../../../docs/framework/unmanaged-api/debugging/icordebugassemblyenum-interface.md)  
 `ICorDebugEnum` 메서드를 구현하고 `ICorDebugAssembly` 배열을 열거합니다.  
  
 [ICorDebugBlockingObjectEnum 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugblockingobjectenum-interface.md)  
 목록에 대 한 열거자를 제공 [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) 구조입니다.  
  
 [ICorDebugBoxValue Interface1](../../../../docs/framework/unmanaged-api/debugging/icordebugboxvalue-interface.md)  
 boxed 값 클래스 개체를 나타내는 `ICorDebugHeapValue`의 서브클래스입니다.  
  
 [ICorDebugBreakpoint Interface1](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpoint-interface.md)  
 함수의 중단점 또는 값에 대한 조사식 위치를 나타냅니다.  
  
 [ICorDebugBreakpointEnum Interface1](../../../../docs/framework/unmanaged-api/debugging/icordebugbreakpointenum-interface.md)  
 `ICorDebugEnum` 메서드를 구현하고 `ICorDebugBreakpoint` 배열을 열거합니다.  
  
 [ICorDebugChain Interface1](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-interface.md)  
 실제 또는 논리 호출 스택의 세그먼트를 나타냅니다.  
  
 [ICorDebugChainEnum Interface1](../../../../docs/framework/unmanaged-api/debugging/icordebugchainenum-interface.md)  
 `ICorDebugEnum` 메서드를 구현하고 `ICorDebugChain` 배열을 열거합니다.  
  
 [ICorDebugClass Interface1](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md)  
 기본 또는 복합(즉, 사용자 정의) 형식을 나타냅니다. 형식이 제네릭이면 `ICorDebugClass`는 인스턴스화되지 않은 제네릭 형식을 나타냅니다.  
  
 [ICorDebugClass2 Interface1](../../../../docs/framework/unmanaged-api/debugging/icordebugclass2-interface.md)  
 제네릭 클래스나 <xref:System.Type> 형식의 메서드 매개 변수를 사용하는 클래스를 나타냅니다. 이 인터페이스는 `ICorDebugClass`를 확장한 것입니다.  
  
 [ICorDebugCode Interface1](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-interface1.md)  
 MSIL(Microsoft Intermediate Language) 코드나 네이티브 코드의 세그먼트를 나타냅니다.  
  
 [ICorDebugCode2 Interface1](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-interface.md)  
 `ICorDebugCode`의 기능을 확장하는 메서드를 제공합니다.  
  
 [ICorDebugCode3 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)  
 확장 하는 메서드를 제공 [ICorDebugCode](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-interface1.md) 및 [ICorDebugCode2](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-interface.md) 관리 되는 반환 값에 대 한 정보를 제공 합니다.  
  
 [ICorDebugCode4 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-interface.md)  
 디버거를 지역 변수 및 함수에 인수를 열거 하는 메서드를 제공 합니다.  
  
 [ICorDebugCodeEnum Interface1](../../../../docs/framework/unmanaged-api/debugging/icordebugcodeenum-interface.md)  
 `ICorDebugEnum` 메서드를 구현하고 `ICorDebugCode` 배열을 열거합니다.  
  
 [ICorDebugComObjectValue 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugcomobjectvalue-interface.md)  
 캐시된 인터페이스 개체를 검색하는 메서드를 제공합니다.  
  
 [ICorDebugContext Interface1](../../../../docs/framework/unmanaged-api/debugging/icordebugcontext-interface.md)  
 컨텍스트 개체를 나타냅니다. 이 인터페이스는 아직 구현되지 않았습니다.  
  
 [ICorDebugController Interface1](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-interface.md)  
 <xref:System.Diagnostics.Process>나 <xref:System.AppDomain> 같이 코드 실행 컨텍스트를 제어할 수 있는 범위를 나타냅니다.  
  
 [ICorDebugDataTarget 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)  
 특정 대상 프로세스에 대한 액세스를 제공하는 콜백 인터페이스를 제공합니다.  
  
 [ICorDebugDataTarget2 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget2-interface.md)  
 논리적으로 확장 된 [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) 인터페이스입니다. **.NET 네이티브 에서만 사용할 수 있습니다.**  
  
 [ICorDebugDataTarget3 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget3-interface.md)  
 논리적으로 확장 된 [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) 로드 된 모듈에 대 한 정보를 제공 하는 인터페이스입니다. **.NET 네이티브 에서만 사용할 수 있습니다.**  
  
 [ICorDebugDebugEvent 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md)  
 모든 `ICorDebug` 디버그 이벤트가 파생되는 기본 인터페이스를 정의합니다. **.NET 네이티브 에서만 사용할 수 있습니다.**  
  
 [ICorDebugEditAndContinueErrorInfo 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugeditandcontinueerrorinfo-interface.md)  
 사용되지 않습니다. 이 인터페이스를 사용하지 마세요.  
  
 [ICorDebugEditAndContinueSnapshot Interface1](../../../../docs/framework/unmanaged-api/debugging/icordebugeditandcontinuesnapshot-interface.md)  
 사용되지 않습니다. 이 인터페이스를 사용하지 마세요.  
  
 [ICorDebugEnum Interface1](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-interface1.md)  
 열거자를 디버깅할 수 있는 추상 기본 인터페이스로 사용합니다.  
  
 [ICorDebugErrorInfoEnum Interface1](../../../../docs/framework/unmanaged-api/debugging/icordebugerrorinfoenum-interface.md)  
 사용되지 않습니다. 이 인터페이스를 사용하지 마세요.  
  
 [ICorDebugEval Interface1](../../../../docs/framework/unmanaged-api/debugging/icordebugeval-interface.md)  
 디버깅 중인 코드의 컨텍스트 내에서 디버거가 코드를 실행할 수 있도록 하는 메서드를 제공합니다.  
  
 [ICorDebugEval2 Interface1](../../../../docs/framework/unmanaged-api/debugging/icordebugeval2-interface.md)  
 제네릭 형식을 지원하도록 `ICorDebugEval`을 확장합니다.  
  
 [ICorDebugExceptionDebugEvent 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptiondebugevent-interface.md)  
 확장 된 [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) 예외 이벤트를 지 원하는 인터페이스입니다. **.NET 네이티브 에서만 사용할 수 있습니다.**  
  
 [ICorDebugExceptionObjectCallStackEnum 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md)  
 예외 개체에 포함된 호출 스택 정보에 대한 열거자를 제공합니다.  
  
 [ICorDebugExceptionObjectValue 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectvalue-interface.md)  
 확장 된 [ICorDebugObjectValue](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-interface.md) 인터페이스는 관리 되는 예외 개체에서 스택 추적 정보를 제공 합니다.  
  
 [ICorDebugFrame Interface1](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-interface.md)  
 현재 스택의 프레임을 나타냅니다.  
  
 [ICorDebugFrameEnum Interface1](../../../../docs/framework/unmanaged-api/debugging/icordebugframeenum-interface.md)  
 `ICorDebugEnum` 메서드를 구현하고 `ICorDebugFrame` 배열을 열거합니다.  
  
 [ICorDebugFunction Interface1](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-interface1.md)  
 관리되는 함수 또는 메서드를 나타냅니다.  
  
 [ICorDebugFunction2 Interface1](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction2-interface.md)  
 `ICorDebugFunction`의 기능을 논리적으로 확장하여 "내 코드만" 단계별 실행 디버깅을 지원합니다.  
  
 [ICorDebugFunction3 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction3-interface.md)  
 논리적으로 확장 된 [ICorDebugFunction](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-interface1.md) ReJIT 요청의 코드에 대 한 액세스를 제공 하는 인터페이스입니다.  
  
 [ICorDebugFunctionBreakpoint Interface1](../../../../docs/framework/unmanaged-api/debugging/icordebugfunctionbreakpoint-interface.md)  
 함수에서 중단점을 지원하기 위해 `ICorDebugBreakpoint`를 확장합니다.  
  
 [ICorDebugGCReferenceEnum 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)  
 가비지 수집되는 개체에 대한 열거자를 제공합니다.  
  
 [ICorDebugGenericValue Interface1](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-interface.md)  
 모든 값에 적용되는 `ICorDebugValue`의 서브클래스입니다. 이 인터페이스에서는 값의 Get 및 Set 메서드를 제공합니다.  
  
 [ICorDebugGuidToTypeEnum 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md)  
 GUID를 매핑하는 개체와 그에 해당하는 `ICorDebugType` 개체에 대한 열거자를 제공합니다.  
  
 [ICorDebugHandleValue Interface1](../../../../docs/framework/unmanaged-api/debugging/icordebughandlevalue-interface.md)  
 디버거에서 가비지 수집을 위해 핸들을 만든 대상 참조 값을 나타내는 `ICorDebugReferenceValue`의 서브클래스입니다.  
  
 [ICorDebugHeapEnum 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md)  
 관리되는 힙의 개체에 대한 열거자를 제공합니다.  
  
 [ICorDebugHeapSegmentEnum 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md)  
 관리되는 힙 메모리 영역에 대한 열거자를 제공합니다.  
  
 [ICorDebugHeapValue Interface1](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue-interface.md)  
 CLR 가비지 수집기에서 수집한 개체를 나타내는 `ICorDebugValue`의 서브클래스입니다.  
  
 [ICorDebugHeapValue2 Interface1](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue2-interface1.md)  
 런타임 핸들에 대한 지원을 제공하는 `ICorDebugHeapValue`의 확장입니다.  
  
 [ICorDebugHeapValue3 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue3-interface.md)  
 개체의 모니터 잠금 속성을 노출합니다.  
  
 [ICorDebugILCode 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md)  
 IL(중간 언어) 코드 세그먼트를 나타냅니다.  
  
 [ICorDebugILCode2 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-interface.md)  
 논리적으로 확장 된 [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) 함수의 로컬 변수 서명에 대해 토큰을 반환 하 고 프로파일러의 계측 된 IL (중간 언어)를 매핑하는 메서드를 제공 하는 인터페이스 원래 메서드 IL 오프셋 오프셋 합니다.  
  
 [ICorDebugILFrame Interface1](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-interface.md)  
 MSIL 코드의 스택 프레임을 나타냅니다.  
  
 [ICorDebugILFrame2 Interface1](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe2-interface.md)  
 `ICorDebugILFrame`에서 논리적으로 확장된 버전입니다.  
  
 [ICorDebugILFrame3 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-interface.md)  
 함수의 반환 값을 캡슐화하는 메서드를 제공합니다.  
  
 [ICorDebugILFrame4 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)  
 IL(중간 언어) 코드의 스택 프레임에서 로컬 변수 및 코드에 액세스하는 데 사용할 수 있는 메서드를 제공합니다. 디버거가 프로파일러 ReJIT 계측에 추가된 변수와 코드에 액세스할 수 있는지는 매개 변수를 통해 지정됩니다.  
  
 [ICorDebugInstanceFieldSymbol 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)  
 인스턴스 필드에 대한 디버그 기호 정보를 나타냅니다. **.NET 네이티브 에서만 사용할 수 있습니다.**  
  
 [ICorDebugInternalFrame Interface1](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe-interface.md)  
 디버거의 프레임 형식을 식별합니다.  
  
 [ICorDebugInternalFrame2 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebuginternalframe2-interface.md)  
 스택 주소 및 위치와 관련 하 여 내부 프레임에 대 한 정보를 제공 [ICorDebugFrame](../../../../docs/framework/unmanaged-api/debugging/icordebugframe-interface.md) 개체입니다.  
  
 [ICorDebugLoadedModule 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-interface.md)  
 로드된 모듈에 대한 정보를 제공합니다. **.NET 네이티브 에서만 사용할 수 있습니다.**  
  
 [ICorDebugManagedCallback 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)  
 디버거 콜백을 처리하는 메서드를 제공합니다.  
  
 [ICorDebugManagedCallback2 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 디버거 예외 처리 및 MDA(관리 디버깅 도우미)를 지원하기 위한 메서드를 제공합니다. `ICorDebugManagedCallback2`은 `ICorDebugManagedCallback`에서 논리적으로 확장된 버전입니다.  
  
 [ICorDebugManagedCallback3 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-interface.md)  
 활성화된 사용자 지정 디버거 알림이 발생했음을 나타내는 콜백 메서드를 제공합니다.  
  
 [ICorDebugMDA 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md)  
 MDA(관리 디버깅 도우미) 메시지를 나타냅니다.  
  
 [ICorDebugMemoryBuffer 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)  
 메모리 내 버퍼를 나타냅니다. **.NET 네이티브 에서만 사용할 수 있습니다.**  
  
 [ICorDebugMergedAssemblyRecord 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)  
 병합된 어셈블리에 대한 정보를 제공합니다. **.NET 네이티브 에서만 사용할 수 있습니다.**  
  
 [ICorDebugMetaDataLocator 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugmetadatalocator-interface.md)  
 디버거에 메타데이터 정보를 제공합니다.  
  
 [ICorDebugModule Interface1](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule-interface.md)  
 실행 파일이나 DLL(동적 연결 라이브러리)인 CLR 모듈을 나타냅니다.  
  
 [ICorDebugModule2 Interface1](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-interface.md)  
 `ICorDebugModule`에서 논리적으로 확장된 버전입니다.  
  
 [ICorDebugModule3 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule3-interface.md)  
 동적 모듈에 대한 기호 판독기를 만듭니다.  
  
 [ICorDebugModuleBreakpoint Interface1](../../../../docs/framework/unmanaged-api/debugging/icordebugmodulebreakpoint-interface.md)  
 특정 모듈에 액세스할 수 있도록 `ICorDebugBreakpoint`를 확장합니다.  
  
 [ICorDebugModuleDebugEvent 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduledebugevent-interface.md)  
 확장 된 [ICorDebugDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-interface.md) 모듈 수준 이벤트를 지 원하는 인터페이스입니다. **.NET 네이티브 에서만 사용할 수 있습니다.**  
  
 [ICorDebugModuleEnum Interface1](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduleenum-interface.md)  
 `ICorDebugEnum` 메서드를 구현하고 `ICorDebugModule` 배열을 열거합니다.  
  
 [ICorDebugMutableDataTarget 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-interface.md)  
 확장 된 [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) 인터페이스를 변경할 수 있는 데이터 대상을 지원 합니다.  
  
 [ICorDebugNativeFrame Interface1](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-interface.md)  
 네이티브 프레임에 사용되는 특수화된 `ICorDebugFrame` 구현입니다.  
  
 [ICorDebugNativeFrame2 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-interface.md)  
 자식 및 부모 프레임 관계를 테스트하는 메서드를 제공합니다.  
  
 [ICorDebugObjectEnum Interface1](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectenum-interface.md)  
 `ICorDebugEnum` 메서드를 구현하고 RVA(Relative Virtual Address)로 개체의 배열을 열거합니다.  
  
 [ICorDebugObjectValue Interface1](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-interface.md)  
 개체가 들어 있는 값을 나타내는 `ICorDebugValue`의 서브클래스입니다.  
  
 [ICorDebugObjectValue2 Interface1](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue2-interface.md)  
 상속 및 재정의 기능을 지원하도록 `ICorDebugObjectValue`를 확장합니다.  
  
 [ICorDebugProcess Interface1](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md)  
 관리 코드를 실행하는 프로세스를 나타냅니다.  
  
 [ICorDebugProcess2 Interface1](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-interface1.md)  
 `ICorDebugProcess`에서 논리적으로 확장된 버전입니다.  
  
 [ICorDebugProcess3 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess3-interface.md)  
 사용자 지정 디버거 알림을 제어합니다.  
  
 [ICorDebugProcess5 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 확장 된 [ICorDebugProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md) 관리 되는 개체의 가비지 수집에 대 한 정보를 제공 하 고 디버거가 응용 프로그램에서 이미지를 로드 하는지 여부를 결정 하는 관리 되는 힙에 대 한 액세스를 지원 하기 위해 인터페이스의 로컬 네이티브 이미지 캐시 합니다.  
  
 [ICorDebugProcess6 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)  
 논리적으로 확장 된 [ICorDebugProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md) 가상 모듈 분할 및 네이티브 예외 디버그 이벤트에서 인코딩 되는 관리 되는 디버그 이벤트 디코딩 등의 기능을 활성화 하는 인터페이스입니다. **.NET 네이티브 에서만 사용할 수 있습니다.**  
  
 [ICorDebugProcess7 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess7-interface.md)  
 대상 프로세스에서 디버거가 메모리 내 메타데이터 업데이트를 처리하도록 구성하는 메서드를 제공합니다.  
  
 [ICorDebugProcess8 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess8-interface.md)  
 논리적으로 확장 된 [ICorDebugProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-interface.md) 인터페이스를 특정 유형의 사용할지 [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) 예외 콜백을 합니다.  
  
 [ICorDebugProcessEnum Interface1](../../../../docs/framework/unmanaged-api/debugging/icordebugprocessenum-interface.md)  
 `ICorDebugEnum` 메서드를 구현하고 `ICorDebugProcess` 배열을 열거합니다.  
  
 [ICorDebugReferenceValue Interface1](../../../../docs/framework/unmanaged-api/debugging/icordebugreferencevalue-interface.md)  
 참조 형식을 지원하는 `ICorDebugValue`의 서브클래스입니다.  
  
 [ICorDebugRegisterSet 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)  
 코드가 실행되고 있는 컴퓨터에서 사용할 수 있는 레지스터 집합을 나타냅니다.  
  
 [ICorDebugRegisterSet2 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)  
 64개 이상의 레지스터가 있는 하드웨어 플랫폼의 `ICorDebugRegisterSet` 기능을 확장합니다.  
  
 [ICorDebugRemote 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugremote-interface.md)  
 시작할 수 있거나 원격 대상 프로세스에 관리되는 디버거를 연결할 수 있는 기능을 제공합니다.  
  
 [ICorDebugRemoteTarget 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)  
 CLR 환경에서 Silverlight 기반 응용 프로그램을 디버깅하는 데 사용할 수 있는 메서드를 제공합니다.  
  
 [ICorDebugRuntimeUnwindableFrame 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugruntimeunwindableframe-interface.md)  
 프레임을 해제하는 데 CLR(공용 언어 런타임)을 필요로 하는 관리되지 않는 메서드에 대한 지원을 제공합니다.  
  
 [ICorDebugStackWalk 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)  
 스레드 스택에서 관리되는 메서드나 프레임을 가져오기 위한 메서드를 제공합니다.  
  
 [ICorDebugStaticFieldSymbol 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)  
 정적 필드에 대한 디버그 기호 정보를 나타냅니다. **.NET 네이티브 에서만 사용할 수 있습니다.**  
  
 [ICorDebugStepper Interface1](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-interface.md)  
 디버거에서 수행하는 코드 실행 단계를 나타내며, 명령의 실행/완료를 구분하는 식별자로 사용되고, 단계를 취소하는 방법을 제공합니다.  
  
 [ICorDebugStepper2 Interface1](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper2-interface1.md)  
 JMC(내 코드만) 디버깅을 지원합니다.  
  
 [ICorDebugStepperEnum Interface1](../../../../docs/framework/unmanaged-api/debugging/icordebugstepperenum-interface.md)  
 `ICorDebugEnum` 메서드를 구현하고 `ICorDebugStepper` 배열을 열거합니다.  
  
 [ICorDebugStringValue Interface1](../../../../docs/framework/unmanaged-api/debugging/icordebugstringvalue-interface.md)  
 문자열 값에 적용되는 `ICorDebugHeapValue`의 서브클래스입니다.  
  
 [ICorDebugSymbolProvider 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)  
 디버그 기호 정보를 검색하는 데 사용할 수 있는 메서드를 제공합니다. **.NET 네이티브 에서만 사용할 수 있습니다.**  
  
 [ICorDebugSymbolProvider2 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider2-interface.md)  
 논리적으로 확장 된 [ICorDebugSymbolProvider](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md) 추가 디버그 기호 정보를 검색 하는 인터페이스입니다. **.NET 네이티브 에서만 사용할 수 있습니다.**  
  
 [ICorDebugThread Interface1](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-interface.md)  
 프로세스의 스레드를 나타냅니다. `ICorDebugThread` 인스턴스의 수명은 이 인스턴스가 나타내는 스레드의 수명과 같습니다.  
  
 [ICorDebugThread2 Interface1](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interface.md)  
 `ICorDebugThread`에서 논리적으로 확장된 버전입니다.  
  
 [ICorDebugThread3 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugthread3-interface.md)  
 진입점을 제공 된 [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) 및 해당 인터페이스입니다.  
  
 [ICorDebugThread4 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-interface.md)  
 스레드 차단 정보를 제공합니다.  
  
 [ICorDebugThreadEnum Interface1](../../../../docs/framework/unmanaged-api/debugging/icordebugthreadenum-interface1.md)  
 `ICorDebugEnum` 메서드를 구현하고 `ICorDebugThread` 배열을 열거합니다.  
  
 [ICorDebugType Interface1](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md)  
 기본 또는 복합(즉, 사용자 정의) 형식을 나타냅니다. 형식이 제네릭이면 `ICorDebugType`는 인스턴스화된 제네릭 형식을 나타냅니다.  
  
 [ICorDebugType2 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugtype2-interface.md)  
 확장 된 [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md) 기본 형식 또는 복합 (사용자 정의) 형식을의 형식 식별자를 검색 하는 인터페이스입니다.  
  
 [ICorDebugTypeEnum Interface1](../../../../docs/framework/unmanaged-api/debugging/icordebugtypeenum-interface.md)  
 `ICorDebugEnum` 메서드를 구현하고 `ICorDebugType` 배열을 열거합니다.  
  
 [ICorDebugUnmanagedCallback 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-interface.md)  
 CLR에 직접적으로 관련되지 않은 네이티브 이벤트에 대한 알림을 제공합니다.  
  
 "ICorDebugValue"  
 디버깅 중인 프로세스의 읽기 또는 쓰기 값을 나타냅니다.  
  
 "ICorDebugValue2"  
 `ICorDebugValue`을 지원하기 위해 `ICorDebugType`에서 확장된 버전입니다.  
  
 [ICorDebugValue3 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)  
 2GB 보다 큰 배열에 대 한 지원을 제공 하는 "ICorDebugValue" 및 "ICorDebugValue2" 인터페이스를 확장 합니다.  
  
 "ICorDebugValueBreakpoint"  
 특정 값에 액세스할 수 있도록 `ICorDebugBreakpoint`를 확장합니다.  
  
 "ICorDebugValueEnum"  
 `ICorDebugEnum` 메서드를 구현하고 `ICorDebugValue` 배열을 열거합니다.  
  
 [ICorDebugVariableHome 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)  
 지역 변수 또는 함수 '의 인수를 나타냅니다.  
  
 [ICorDebugVariableHomeEnum 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)  
 지역 변수 및 함수에 인수에는 열거자를 제공 합니다.  
  
 [ICorDebugVariableSymbol 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md)  
 변수에 대한 디버그 기호 정보를 검색합니다. **.NET 네이티브 에서만 사용할 수 있습니다.**  
  
 [ICorDebugVirtualUnwinder 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugvirtualunwinder-interface.md)  
 스택 해제에 도움이 되는 메서드를 제공합니다. **.NET 네이티브 에서만 사용할 수 있습니다.**  
  
 [ICorPublish 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)  
 게시 프로세스에 대한 일반적인 인터페이스로 사용합니다.  
  
 [ICorPublishAppDomain 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)  
 응용 프로그램 도메인을 나타내고 응용 프로그램 도메인에 대한 정보를 제공합니다.  
  
 [ICorPublishAppDomainEnum 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)  
 프로세스 내에 현재 있는 `ICorPublishAppDomain` 개체의 컬렉션을 이동하는 메서드를 제공합니다.  
  
 [ICorPublishEnum 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)  
 열거자를 게시하기 위한 추상 기본 열거형으로 사용됩니다.  
  
 [ICorPublishProcess 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)  
 프로세스에 대한 정보에 액세스하는 메서드를 제공합니다.  
  
 [ICorPublishProcessEnum 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)  
 `ICorPublishProcess` 개체의 컬렉션을 이동하는 메서드를 제공합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [디버깅 Coclass](../../../../docs/framework/unmanaged-api/debugging/debugging-coclasses.md)  
  
 [디버깅 전역 정적 함수](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)  
  
 [디버깅 열거형](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
  
 [디버깅 구조체](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
