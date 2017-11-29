---
title: "ICorProfilerModuleEnum 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerModuleEnum
api_location: mscorwks.cll
api_type: COM
f1_keywords: ICorProfilerModuleEnum
helpviewer_keywords: ICorProfilerModuleEnum interface [.NET Framework profiling]
ms.assetid: 24d0fcfa-1601-4fba-868f-da8c97303467
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 43cc6afc42fc1a02fd7d7b3df2973cc9b3e31251
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilermoduleenum-interface"></a>ICorProfilerModuleEnum 인터페이스
응용 프로그램이나 프로파일러가 로드한 모듈 컬렉션을 순서대로 반복하는 메서드를 제공합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[Clone 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-clone-method.md)|이 `ICorProfilerModuleEnum` 인터페이스의 복사본에 대한 인터페이스 포인터를 가져옵니다.|  
|[GetCount 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-getcount-method.md)|응용 프로그램에 로드된 관리되는 모듈 수를 가져옵니다.|  
|[Next 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-next-method.md)|시퀀스에서 열거자의 현재 위치부터 시작하여 순차적 개체 컬렉션에서 지정된 개수의 연속 모듈을 가져옵니다.|  
|[Reset 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-reset-method.md)|열거자의 커서를 시퀀스의 시작 위치로 이동합니다.|  
|[Skip 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-skip-method.md)|지정한 개수의 요소를 건너뛰도록 열거자의 커서 위치를 진행합니다.|  
  
## <a name="remarks"></a>설명  
 `ICorProfilerModuleEnum` 인터페이스는 열거자입니다. 배열의 수신기가 수신기에 적합한 속도로 송신기에서 요소를 끌어올 수 있게 합니다. 즉, 수신기가 배열 요소의 흐름을 명시적으로 제어하여 대형 배열을 메서드 매개 변수로 전달하는 기능과 관련된 문제를 방지할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorProf.idl, CorProf.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorProfilerInfo 인터페이스](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [프로 파일링 인터페이스](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [EnumModules 메서드](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enummodules-method.md)
