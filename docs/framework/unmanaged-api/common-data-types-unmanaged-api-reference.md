---
title: "공통 데이터 유형(관리되지 않는 API 참조)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: e4ab2c4c-9433-4eba-9e9a-096de406cafb
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 03350825b3de4515a0d30e8644f34df71efa25db
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="common-data-types-unmanaged-api-reference"></a>공통 데이터 유형(관리되지 않는 API 참조)
이 항목에서는 C/C++ `typedef` 문에 의해 정의되는 .NET Framework용 관리되지 않는 API에서 사용하는 단순 데이터 형식을 소개합니다. 이러한 데이터 형식은 보통 C/C++ 원시 데이터 형식의 별칭입니다. 일반적으로 이러한 데이터 형식의 값은 불투명합니다. 즉, 이러한 값은 수정하지 않고도 다른 함수나 메서드로 전달할 수 있도록 특정 함수나 메서드에서 반환됩니다.  
  
|데이터 형식|정의|정의 위치|설명|  
|---------------|----------------|----------------|-----------------|  
|AppDomainID|`typedef UINT_PTR AppDomainID;`|corprof.h|응용 프로그램 도메인의 식별자입니다.|  
|AssemblyID|`typedef UINT_PTR AssemblyID;`|corprof.h|어셈블리의 식별자입니다.|  
|ClassID|`typedef UINT_PTR ClassID;`|corprof.h|관리되는 클래스의 식별자입니다.|  
|CONNID|`typedef DWORD CONNID;`|cordebug.h, mscoree.h|Microsoft SQL Server 인스턴스에 연결되는 스레드의 연결 식별자입니다.|  
|ContextID|`typedef UINT_PTR ContextID;`|corprof.h|특정 관리되는 스레드와 연결된 컨텍스트의 식별자입니다.|  
|COR_PRF_ELT_INFO|`typedef UINT_PTR COR_PRF_ELT_INFO;`|corprof.h|특정 스택 프레임에 대한 정보를 나타내는 불투명 핸들입니다.|  
|COR_PRF_FRAME_INFO|`typedef UINT_PTR COR_PRF_FRAME_INFO;`|corprof.h|스택 프레임을 가리키는 불투명 핸들로, 전달된 콜백 중에만 유효합니다.|  
|CORDB_ADDRESS|`typedef ULONG64 CORDB_ADDRESS;`|cordebug.h|메모리의 주소입니다.|  
|CORDB_CONTINUE_STATUS|`typedef DWORD CORDB_CONTINUE_STATUS;`|cordebug.h|연속 상태입니다.|  
|CORDB_REGISTER|`typedef ULONG64 CORDB_REGISTER;`|cordebug.h|CPU 레지스터의 값입니다.|  
|FunctionID|`typedef UINT_PTR FunctionID;`|corprof.h|함수 또는 메서드의 식별자입니다.|  
|GCHandleID|`typedef UINT_PTR GCHandleID;`|corprof.h|가비지 수집 핸들입니다.|  
|mdToken|`typedef UINT32 mdToken;`|corprof.h|메타데이터 토큰입니다(메타데이터 테이블의 행).|  
|ModuleID|`typedef UINT_PTR ModuleID;`|corprof.h|어셈블리 모듈의 식별자입니다.|  
|ObjectID|`typedef UINT_PTR ObjectID;`|corprof.h|개체의 식별자입니다.|  
|ProcessID|`typedef UINT_PTR ProcessID;`|corprof.h|관리되는 프로세스의 식별자입니다.|  
|ReJITID|`typedef UINT_PTR ReJITID;`|corprof.h|JIT된 함수의 식별자입니다.|  
|TASKID|`typedef UINT64 TASKID;`|cordebug.h, mscoree.h|식별자는 [ICLRTask](../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) 인스턴스.|  
|ThreadID|`typedef UINT_PTR ThreadID;`|corprof.h|관리되는 스레드의 식별자입니다.|  
  
## <a name="see-also"></a>참고 항목  
 [관리되지 않는 API 참조](../../../docs/framework/unmanaged-api/index.md)
