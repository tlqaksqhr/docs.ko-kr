---
title: ICorDebugEval::NewString 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugEval.NewString
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::NewString
helpviewer_keywords:
- NewString method [.NET Framework debugging]
- ICorDebugEval::NewString method [.NET Framework debugging]
ms.assetid: 29e7a14b-d50e-4852-bfda-011b76c0c9ee
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e5eb86bb80aea5fc65a7362467b78b16a59794d7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33412232"
---
# <a name="icordebugevalnewstring-method"></a>ICorDebugEval::NewString 메서드
지정 된 내용으로 새 문자열 인스턴스를 할당합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT NewString (  
    [in] LPCWSTR   string  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `string`  
 [in] 문자열에 대 한 내용에 대 한 포인터입니다.  
  
## <a name="remarks"></a>설명  
 문자열은 항상 스레드가 현재 실행 중인 응용 프로그램 도메인에 만들어집니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorDebug.idl, CorDebug.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
