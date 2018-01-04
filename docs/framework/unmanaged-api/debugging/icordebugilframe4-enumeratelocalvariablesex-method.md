---
title: "ICorDebugILFrame4::EnumerateLocalVariablesEx 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: ICorDebugILFrame4.EnumerateLocalVariablesEx
api_location: mscordbi.dll
api_type: COM
ms.assetid: 6f60aae6-70ec-4c4c-963a-138df98c4668
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c82ecd9045deb772e31e549bf1050f85b148fd0b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugilframe4enumeratelocalvariablesex-method"></a>ICorDebugILFrame4::EnumerateLocalVariablesEx 메서드
[.NET Framework 4.5.2 이상 버전에서 지원됨]  
  
 프레임의 로컬 변수에 대한 열거자를 가져오고 필요에 따라 프로파일러 ReJIT 계측에 추가된 변수를 포함합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
HRESULT EnumerateLocalVariablesEx(  
   [in] ILCodeKind flags,   
   [out] ICorDebugValueEnum **ppValueEnum  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `flags`  
 [in] [ILCodeKind](../../../../docs/framework/unmanaged-api/debugging/ilcodekind-enumeration.md) 프로파일러 ReJIT 계측에에서 추가 된 변수가 프레임에 포함 되는지 여부를 지정 하는 열거형 멤버입니다.  
  
 `ppValueEnum`  
 [out] 이 프레임에서 로컬 변수의 열거자 인 "ICorDebugValueEnum" 개체의 주소에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는 비슷합니다는 [EnumerateLocalVariables](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md) 메서드를 필요에 따라 프로파일러 ReJIT 계측에에서 추가 된 변수를 액세스 한다는 점을 제외 하 고 있습니다. 설정 `flags` 를 `ILCODE_ORIGINAL_IL` 호출과 같습니다 [icordebugilframe:: Enumeratelocalvariables](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-enumeratelocalvariables-method.md)합니다. `flags`을 `ILCODE_REJIT_IL`로 설정하면 디버거가 프로파일러 ReJIT 계측에 추가된 로컬 변수에 액세스할 수 있습니다. IL(중간 언어)이 계측되지 않는 경우 열거형은 비어 있으며 메서드는 `S_OK`를 반환합니다.  
  
 열거자는 실행 중인 메서드의 모든 로컬 변수를 포함하지 않을 수 있습니다. 이러한 변수 중 일부는 활성 상태가 아닐 수 있기 때문입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICorDebugILFrame4 인터페이스](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)  
 [디버깅 인터페이스](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [방법 가이드는 ReJIT:](http://blogs.msdn.com/b/davbr/archive/2011/10/12/rejit-a-how-to-guide.aspx)
