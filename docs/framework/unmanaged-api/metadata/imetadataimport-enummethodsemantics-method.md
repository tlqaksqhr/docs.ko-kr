---
title: "IMetaDataImport::EnumMethodSemantics 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumMethodSemantics
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumMethodSemantics
helpviewer_keywords:
- EnumMethodSemantics method [.NET Framework metadata]
- IMetaDataImport::EnumMethodSemantics method [.NET Framework metadata]
ms.assetid: e7e3c630-9691-46d6-94df-b5593a7bb08a
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 883505076fa9ff4f335c08b069e801ebda1ebb2d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportenummethodsemantics-method"></a>IMetaDataImport::EnumMethodSemantics 메서드
지정한 메서드와 관련된 속성 및 속성 변경 이벤트를 열거합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT EnumMethodSemantics (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdMethodDef     mb,   
   [out] mdToken         rEventProp[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcEventProp  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `phEnum`  
 [out에서] 열거자에 대 한 포인터입니다. 이 메서드의 첫 번째 호출에 대 한 NULL 이어야 합니다.  
  
 `mb`  
 [in] 열거형의 범위를 제한 하는 MethodDef 토큰입니다.  
  
 `rEventProp`  
 [out] 모든 이벤트 또는 속성을 저장 하는 데 사용 되는 배열입니다.  
  
 `cMax`  
 [in] `rEventProp` 배열의 최대 크기입니다.  
  
 `pcEventProp`  
 [out] 이벤트 또는 속성에서 반환 된 수가 `rEventProp`합니다.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|`S_OK`|`EnumMethodSemantics`성공적으로 반환 합니다.|  
|`S_FALSE`|이벤트 또는 속성 열거에 없는 합니다. 이 경우 `pcEventProp` 은 0입니다.|  
  
## <a name="remarks"></a>설명  
 많은 수의 공용 언어 런타임 형식 정의 *속성* `Changed` 이벤트 및 `On` *속성* `Changed` 메서드 관련 속성입니다. 예를 들어는 <xref:System.Windows.Forms.Control?displayProperty=nameWithType> 형식은 정의 <xref:System.Windows.Forms.Control.Font%2A> 속성을는 <xref:System.Windows.Forms.Control.FontChanged> 이벤트 및 <xref:System.Windows.Forms.Control.OnFontChanged%2A> 메서드. set 접근자 메서드는 <xref:System.Windows.Forms.Control.Font%2A> 속성 호출 <xref:System.Windows.Forms.Control.OnFontChanged%2A> 차례로 발생 시키는 메서드는 <xref:System.Windows.Forms.Control.FontChanged> 이벤트입니다. 호출 하는 것 `EnumMethodSemantics` 에 대 한 MethodDef를 사용 하 여 <xref:System.Windows.Forms.Control.OnFontChanged%2A> 에 대 한 참조를 얻으려고는 <xref:System.Windows.Forms.Control.Font%2A> 속성 및 <xref:System.Windows.Forms.Control.FontChanged> 이벤트입니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에 리소스로 포함  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IMetaDataImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
