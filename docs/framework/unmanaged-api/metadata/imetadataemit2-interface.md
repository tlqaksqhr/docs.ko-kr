---
title: IMetaDataEmit2 인터페이스
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2
helpviewer_keywords:
- IMetaDataEmit2 interface [.NET Framework metadata]
ms.assetid: 866dc96b-bbfc-4c0f-80c2-38ce93072106
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 418e5287852b1a8d69d310d2ba71e4f2a3b5d7bd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="imetadataemit2-interface"></a>IMetaDataEmit2 인터페이스
확장 된 [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) 주로 제네릭 형식을 사용할 수 있는 기능을 제공 하는 인터페이스입니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[DefineGenericParam 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md)|제네릭 형식 매개 변수에 대 한 정의 만들고 해당 제네릭 형식 매개 변수에 대 한 토큰을 가져옵니다.|  
|[DefineMethodSpec 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md)|메서드의 제네릭 인스턴스를 만들고 정의에 토큰을 가져옵니다.|  
|[GetDeltaSaveSize 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-getdeltasavesize-method.md)|편집 하며 계속 하기는 현재 세션에 대 한 변경 내용을 표현 하는 데 필요한 데이터 크기의 차이 나타내는 값을 가져옵니다.|  
|[ResetENCLog 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-resetenclog-method.md)|편집 하며 계속 하기 로그를 다시 설정 하 고 새 세션을 시작 합니다.|  
|[SaveDelta 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedelta-method.md)|편집 하며 계속 하기는 현재 세션에서 지정된 된 파일 변경 내용을 저장합니다.|  
|[SaveDeltaToMemory 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md)|편집 하며 계속 하기는 현재 세션에서 변경 내용을 메모리에 저장 합니다.|  
|[SaveDeltaToStream 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatostream-method.md)|변경 내용을 편집 하며 계속 하기는 현재 세션에서 지정 된 스트림에 저장 합니다.|  
|[SetGenericParamProps 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-setgenericparamprops-method.md)|지정 된 토큰에서 참조 하는 제네릭 매개 변수 정의 대 한 속성 값을 설정 합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에서 리소스로 사용  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [메타데이터 인터페이스](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [IMetaDataEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
