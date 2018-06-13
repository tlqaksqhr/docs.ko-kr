---
title: ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod 메서드
ms.date: 03/30/2017
ms.assetid: b933dfe6-7833-40cb-aad8-40842dc3034f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 564f3b1cdfab2a3020b6bb5ac8d9af03c6532c8b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33459673"
---
# <a name="icorprofilerinfo6enumngenmodulemethodsinliningthismethod-method"></a>ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod 메서드
[.NET Framework 4.6 이상 버전에서 지원 됨]  
  
 지정 된 NGen 모듈 및 지정된 된 메서드에 인라인에 정의 된 모든 메서드에 열거자를 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT EnumNgenModuleMethodsInliningThisMethod(  
        [in] ModuleID inlinersModuleId,  
        [in] ModuleID inlineeModuleId,  
        [in] mdMethodDef inlineeMethodId,  
        [out] BOOL *incompleteData,  
        [out] ICorProfilerMethodEnum** ppEnum  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `inlinersModuleId`  
 [in] NGen 모듈의 식별자입니다.  
  
 `inlineeModuleId`  
 [in] 정의 하는 모듈의 식별자 `inlineeMethodId`합니다. 자세한 내용은 설명 부분을 참조하세요.  
  
 `inlineeMethodId`  
 [in] 인라인 메서드의 식별자입니다. 자세한 내용은 설명 부분을 참조하세요.  
  
 `incompleteData`  
 [out] 나타내는 플래그 여부 `ppEnum` 주어진된 메서드에 인라인 처리 하는 모든 메서드를 포함 합니다.  자세한 내용은 설명 부분을 참조하세요.  
  
 `ppEnum`  
 [out] 열거자의 주소에 대 한 포인터  
  
## <a name="remarks"></a>설명  
 `inlineeModuleId` 및 `inlineeMethodId` 함께 인라인 처리 하지 않을 수 있는 메서드에 대 한 전체 식별자를 형성 합니다. 예를 들어 모듈 `A` 메서드를 정의 `Simple.Add`:  
  
```csharp  
Simple.Add(int a, int b)   
{ return a + b; }  
```  
  
 및 모듈 Bdefines `Fancy.AddTwice`:  
  
```csharp  
Fancy.AddTwice(int a, int b)   
{ return Simple.Add(a,b) + Simple.Add(a,b); }  
```  
  
 또한를 가정해 보겠습니다 `Fancy.AddTwice` 인라인 호출을 `SimpleAdd`합니다. 프로파일러는이 열거자를 사용 하 여 어떤 인라인 B 모듈에 정의 된 모든 메서드를 찾을 수 수 `Simple.Add`, 하 고 결과 열거는 `AddTwice`합니다.  `inlineeModuleId` 모듈의 식별자 `A`, 및 `inlineeeMethodId` 식별자 `Simple.Add(int a, int b)`합니다.  
  
 경우 `incompleteData` 함수 뒤에 true가 반환 열거자 인라인 처리 하는 모든 메서드는 지정 된 메서드가 없습니다. 이 한 경우에 발생할 수 있습니다 또는 아직 로드 되지 않은 inliners 모듈의 직접 또는 간접 종속성 더 합니다. 프로파일러 정확한 데이터를 필요한 경우 것을 다시 시도해 야 나중에 더 많은 모듈을 로드할 때, 특히 각 모듈을 로드할 합니다.  
  
 `EnumNgenModuleMethodsInliningThisMethod` 에서 제한 사항을 해결 하려면 메서드를 사용할 수 ReJIT에 대 한 인라인 처리 합니다. ReJIT 프로파일러를 메서드의 구현을 변경 및 다음 새 코드를 신속 하 게 만들 수 있습니다. 마침을 예를 들어 `Simple.Add` 다음과 같습니다.  
  
```csharp  
Simple.Add(int a, int b)   
{ return 42; }  
```  
  
 그러나 때문에 `Fancy.AddTwice` 가 이미 인라인 `Simple.Add`를 동일 하 게 동작 이전과 같이 계속 합니다. 를 해당 제한 사항을 해결 하려면 호출자에 게 인라인 있는 모든 모듈의 모든 메서드에 대 한 검색 `Simple.Add` 사용 하 여 `ICorProfilerInfo5::RequestRejit` 이러한 메서드의 각 합니다. 메서드는 다시 컴파일된, 새 동작을 갖게 됩니다 `Simple.Add` 이전 동작을 대신 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorProfilerInfo6 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md)
