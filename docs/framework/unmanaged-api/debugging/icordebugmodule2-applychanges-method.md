---
title: "ICorDebugModule2::ApplyChanges 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModule2.ApplyChanges
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugModule2::ApplyChanges
helpviewer_keywords:
- ApplyChanges method [.NET Framework debugging]
- ICorDebugModule2::ApplyChanges method [.NET Framework debugging]
ms.assetid: 96fa3406-6a6f-41a1-88c6-d9bc5d1a16d1
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 51c14bd6937d4b588227f7cf748c9a8052fb449c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmodule2applychanges-method"></a>ICorDebugModule2::ApplyChanges 메서드
실행 중인 프로세스에 메타 데이터의 변경 내용과 Microsoft MSIL (intermediate language) 코드의 변경 내용을 적용합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT ApplyChanges (  
    [in] ULONG                       cbMetadata,  
    [in, size_is(cbMetadata)] BYTE   pbMetadata[],  
    [in] ULONG                       cbIL,  
    [in, size_is(cbIL)] BYTE         pbIL[]  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `cbMetadata`  
 [in] 델타 메타 데이터를 바이트 단위로 크기입니다.  
  
 `pbMetadata`  
 [in] 델타 메타 데이터가 들어 있는 버퍼입니다. 버퍼의 주소에서 반환 되는 [imetadataemit2:: Savedeltatomemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md) 메서드.  
  
 메타 데이터에 상대 가상 주소 (Rva)는 MSIL 코드의 시작을 기준으로 해야 합니다.  
  
 `cbIL`  
 [in] MSIL 코드 델타를 바이트 단위로 크기입니다.  
  
 `pbIL`  
 [in] 업데이트 된 MSIL 코드를 포함 하는 버퍼입니다.  
  
## <a name="remarks"></a>설명  
 `pbMetadata` 특수 델타 메타 데이터 형식으로 매개 변수는 (으로 출력 하 여 [imetadataemit2:: Savedeltatomemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md)). `pbMetadata`이전 메타 데이터를 기반으로 하 고 해당 자료에 적용 하려면 개별 변경 내용을 설명 합니다.  
  
 반면,는 `pbIL[`] 매개 변수는 새 업데이트 방법이 MSIL 포함 해당 메서드에 대 한 이전 MSIL을 완전히 대체 것 이며  
  
 디버거를 호출 하는 메모리에서 델타 MSIL 및 메타 데이터 생성 되 면 `ApplyChanges` 공용 언어 런타임 (CLR)로 변경 내용을 보냅니다. 메뉴 및 도구 모음을 런타임에 해당 메타 데이터 테이블 업데이트는 프로세스에 저장 하 고 새 MSIL 새 MSIL 적시에 (JIT) 컴파일 설정 합니다. 디버거를 호출 해야 변경 내용이 적용 된 경우 [imetadataemit2:: Resetenclog](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-resetenclog-method.md) 다음 편집 세션에 대 한 준비를 합니다. 디버거 다음 프로세스를 계속할 수 있습니다.  
  
 디버거 호출할 때마다 `ApplyChanges` 델타 메타 데이터가 포함 모듈에서 호출 또한 해야 [imetadataemit:: Applyeditandcontinue](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-applyeditandcontinue-method.md) 모든 복사본을 제외한 해당 모듈의 메타 데이터의 해당 복사본에 같은 델타 메타 데이터와 변경 내용을 생성 하는 데 사용 합니다. 메타 데이터의 복사본을 어떻게 하 든 되 면 동기화를-실제 메타 데이터와 수 항상 해당 복사본 버리는 디버거와 새 복사본을 가져옵니다.  
  
 경우는 `ApplyChanges` 메서드가 실패 하면 디버그 세션이 유효 하지 않은 상태 이므로 다시 시작 해야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
