---
title: CorMethodImpl 열거형
ms.date: 03/30/2017
api_name:
- CorMethodImpl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorMethodImpl
helpviewer_keywords:
- CorMethodImpl enumeration [.NET Framework metadata]
ms.assetid: ffbb3caf-20da-4a4b-8983-77376e72b990
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4bb91423b2eaeda7d945cf14553609fd33ce9b0c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33443491"
---
# <a name="cormethodimpl-enumeration"></a>CorMethodImpl 열거형
메서드 구현 기능을 설명하는 값을 포함합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef enum CorMethodImpl {  
  
    miCodeTypeMask      =   0x0003,  
    miIL                =   0x0000,  
    miNative            =   0x0001,  
    miOPTIL             =   0x0002,  
    miRuntime           =   0x0003,  
  
    miManagedMask       =   0x0004,  
    miUnmanaged         =   0x0004,  
    miManaged           =   0x0000,  
  
    miForwardRef        =   0x0010,  
    miPreserveSig       =   0x0080,  
  
    miInternalCall      =   0x1000,  
    miSynchronized      =   0x0020,  
    miNoInlining        =   0x0008,  
    miAggressiveInlining =  0x0100,  
    miNoOptimization     =  0x0040,  
    miMaxMethodImplVal  =   0xffff  
  
} CorMethodImpl;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`miCodeTypeMask`|코드 형식을 설명 하는 플래그입니다.|  
|`miIL`|메서드 구현 Microsoft MSIL (intermediate language) 임을 지정 합니다.|  
|`miNative`|메서드 구현이 네이티브임을 지정합니다.|  
|`miOPTIL`|메서드 구현 optil로 임을 지정 합니다.|  
|`miRuntime`|공용 언어 런타임에 의해 메서드 구현을 제공 되도록 지정 합니다.|  
|`miManagedMask`|코드 관리 여부를 나타내는 플래그입니다.|  
|`miUnmanaged`|메서드 구현 관리 되는 임을 지정 합니다.|  
|`miManaged`|메서드 구현 관리 되 고 있는지를 지정 합니다.|  
|`miForwardRef`|메서드가 정의 된 지정 합니다. 이 플래그는 병합 시나리오에 주로 사용 됩니다.|  
|`miPreserveSig`|HRESULT 변환에 대 한 메서드 시그니처를 변환 될 수 없는 지정 합니다.|  
|`miInternalCall`|공용 언어 런타임에서 내부 용도로 예약 되어 있습니다.|  
|`miSynchronized`|메서드 본문을 통해 단일 스레드 임을 지정 합니다.|  
|`miNoInlining`|메서드를 인라인될 수 없도록 지정합니다.|  
|`miAggressiveInlining`|이어야 함을 지정 메서드가 하지 인라인 처리 가능한 경우.|  
|`miNoOptimization`|메서드를 최적화 되지 않도록 지정 합니다.|  
|`miMaxMethodImplVal`|에 대 한 최대 유효 값은 `CorMethodImpl`합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorHdr.h  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [메타데이터 열거형](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
