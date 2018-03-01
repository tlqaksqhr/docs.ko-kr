---
title: "IMetaDataEmit::MergeEnd 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IMetaDataEmit.MergeEnd
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::MergeEnd
helpviewer_keywords:
- MergeEnd method [.NET Framework metadata]
- IMetaDataEmit::MergeEnd method [.NET Framework metadata]
ms.assetid: 2d64315a-1af1-4c60-aedf-f8a781914aea
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 265fc007b5817e8dffd5846738a7a0003bbddf9d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitmergeend-method"></a>IMetaDataEmit::MergeEnd 메서드
하나 이상의 이전 호출에 의해 지정 된 모든 메타 데이터 범위를 범위에 현재 병합 [트리거합니다](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md)합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT MergeEnd ();  
```  
  
#### <a name="parameters"></a>매개 변수  
 이 메서드는 매개 변수가 없습니다.  
  
## <a name="remarks"></a>설명  
 이 루틴은 메타 데이터의 실제 병합 트리거, 모든 범위에 대 한 호출 하 여 지정 된 가져오기 `IMetaDataEmit::Merge`, 현재 출력 범위에 있습니다.  
  
 병합에는 다음과 같은 특별 한 조건이 적용 됩니다.  
  
-   (MVID) 모듈 버전 식별자가 하므로 가져올 수 없습니다는 메타 데이터 가져오기 범위에 고유 합니다.  
  
-   기존 없음 모듈 수준 속성을 덮어씁니다.  
  
     현재 범위에 대 한 모듈 속성 이미 설정 된 경우 모듈 속성이 내보내게 됩니다. 그러나 현재 범위에서를 모듈 속성을 설정 하지 않은 경우 파일은 가져올 처음 발생 하면 한 번만. 이러한 모듈 속성 다시 발생 하면 중복 됩니다. (제외 MVID) 모든 모듈 속성의 값이 비교 되는 경우 중복 되는 오류가 발생 합니다.  
  
-   형식 정의 (`TypeDef`), 중복 행은 현재 범위에 병합 합니다. `TypeDef`개체를 각각에 대해 중복 검사 *정규화 된 개체 이름* + *GUID* + *버전 번호*합니다. 이름이 나 GUID, 일치 하는 경우 다른 두 요소 중 하나라도 다른 오류가 발생 합니다. 그렇지 않으면 일치 하는 모든 세 항목이 `MergeEnd` 한 간단한 검사 항목은 중복 항목이 실제로를 그렇지 않으면 오류가 발생 합니다. 이 한 간단한 검사가 찾습니다.  
  
    -   동일한 멤버 선언 순서 대로 발생 합니다. 으로 플래그가 지정 된 멤버 `mdPrivateScope` (참조는 [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) 열거형)이이 확인에 포함 되지 않은 특수 병합 됩니다.  
  
    -   동일한 클래스 레이아웃입니다.  
  
     즉, 한 `TypeDef` 개체 항상 완벽 하 게 하 고 일관 되 게를 정의 해야 모든 메타 데이터 범위에서는 자신이 선언 된; (클래스)에 대 한 해당 멤버 구현이 여러 컴파일 단위에 분산 되어 전체 정의로 간주 됩니다 모든 범위에 및 각 범위에 증분 되지 않습니다. 예를 들어 매개 변수 이름은 계약과 관련 인 내보내야 동일한 방식으로 모든 범위;에 관련이 없는 경우 이러한 내보내지 않아야 메타 데이터에 있습니다.  
  
     `TypeDef` 증분 멤버로 플래그가 지정 된 개체에 있을 수 `mdPrivateScope`합니다. 이러한, `MergeEnd` 증분 중복 관계 없이 현재 범위에 추가 합니다. 컴파일러에서 개인 범위를 식별 하기 때문에 컴파일러 규칙 적용을 담당 해야 합니다.  
  
-   (Rva) 상대 가상 주소 가져오거나 병합; 컴파일러는이 정보를 다시 생성 해야 합니다.  
  
-   사용자 지정 특성이 연결 되어 있는 항목이 병합 될 때에 병합 됩니다. 예를 들어 클래스와 연관 된 사용자 지정 특성 클래스 처음 발생 하는 경우 병합 됩니다. 사용자 지정 특성이 연결 된 경우는 `TypeDef` 또는 `MemberDef` 하는 (예: 멤버의 타임 스탬프) 컴파일 단위, 병합 되지 아니며 컴파일러에서 제거 하거나 해당 메타 데이터 업데이트를 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MSCorEE.dll에서 리소스로 사용  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IMetaDataEmit 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [IMetaDataEmit2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
