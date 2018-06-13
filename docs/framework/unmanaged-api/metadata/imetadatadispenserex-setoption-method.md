---
title: IMetaDataDispenserEx::SetOption 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.SetOption
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::SetOption
helpviewer_keywords:
- IMetaDataDispenserEx::SetOption method [.NET Framework metadata]
- SetOption method [.NET Framework metadata]
ms.assetid: 9f1c7ccd-7fb2-41d8-aa00-24b823376527
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cfe600b54eb03a07ea01375355c5ff94190e5d9d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33449470"
---
# <a name="imetadatadispenserexsetoption-method"></a>IMetaDataDispenserEx::SetOption 메서드
현재 메타 데이터 범위에 대 한 지정된 된 값에 지정된 된 옵션을 설정합니다. 옵션은 현재 메타 데이터 범위에 대 한 호출의 처리 방법을 제어 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT SetOption (  
    [in] REFGUID optionId,   
    [in] const VARIANT *pValue  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `optionId`  
 [in] 설정할 옵션을 지정 하는 GUID에 대 한 포인터입니다.  
  
 `pValue`  
 [in] 옵션을 설정 하는 데 사용할 값입니다. 이 값의 형식은 지정된 된 옵션 형식의 variant를 이어야 합니다.  
  
## <a name="remarks"></a>설명  
 다음 표에서 사용할 수 있는 Guid는는 `optionId` 매개 변수를 가리킬 수 있습니다 및 해당 유효한 값에 대 한는 `pValue` 매개 변수입니다.  
  
|GUID|설명|`pValue` 매개 변수|  
|----------|-----------------|------------------------|  
|MetaDataCheckDuplicatesFor|중복 선택한 항목을 제어 합니다. 호출할 때마다는 [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) 새 항목을 만드는 메서드를 현재 범위에 항목이 이미 있는지 여부를 검사 하도록 요청할 수 있습니다. 예를 들어 있는지 여부를 확인할 수 있습니다 `mdMethodDef` 항목;이 경우 호출 하는 경우 [imetadataemit:: Definemethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md), 메서드는 현재 범위에 이미 존재 하지 않습니다 확인 합니다. 이 검사에서는 고유 하 게 지정된 된 메서드를 식별 하는 키: 부모 유형, 이름 및 서명 합니다.|UI4, 유형의 variant 이어야 하며 값의 조합이 포함 되어야는 [CorCheckDuplicatesFor](../../../../docs/framework/unmanaged-api/metadata/corcheckduplicatesfor-enumeration.md) 열거 합니다.|  
|MetaDataRefToDefCheck|항목이 참조 되는 제어를 정의로 변환 됩니다. 기본적으로 메타 데이터 엔진은 참조 된 항목은 현재 범위에 실제로 정의 된 경우 해당 정의에 참조 된 항목을 변환 하 여 코드를 최적화 합니다.|UI4, 유형의 variant 이어야 하며 값의 조합이 포함 되어야는 [CorRefToDefCheck](../../../../docs/framework/unmanaged-api/metadata/correftodefcheck-enumeration.md) 열거 합니다.|  
|MetaDataNotificationForTokenMovement|콜백을 생성 하는 컨트롤 토큰 메타 데이터를 병합 하는 동안 발생 다시 매핑합니다. 사용 하 여는 [imetadataemit:: Sethandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md) 메서드 설정 하 여 [IMapToken](../../../../docs/framework/unmanaged-api/metadata/imaptoken-interface.md) 인터페이스입니다.|UI4, 유형의 variant 이어야 하며 값의 조합이 포함 되어야는 [CorNotificationForTokenMovement](../../../../docs/framework/unmanaged-api/metadata/cornotificationfortokenmovement-enumeration.md) 열거 합니다.|  
|MetaDataSetENC|편집 하며 계속 하기 (ENC)의 동작을 제어 합니다. 한 번에 하나의 모드의 동작을 설정할 수 있습니다.|UI4, 유형의 variant 이어야 하며 값이 있어야 합니다.는 [CorSetENC](../../../../docs/framework/unmanaged-api/metadata/corsetenc-enumeration.md) 열거 합니다. 값이 비트 마스크입니다.|  
|MetaDataErrorIfEmitOutOfOrder|어떤 내보내집니다-의 순서가 오류 콜백을 생성을 제어 합니다. 메타 데이터의 순서가 치명적이 지 않으면 그러나 메타 데이터 엔진에서 선호 하는 순서에에서 대 한 메타 데이터를 생성 경우 메타 데이터 더 간결 하며 따라서 보다 효율적으로 검색할 수 있습니다. 사용 하 여는 `IMetaDataEmit::SetHandler` 메서드 설정 하 여 [IMetaDataError](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md) 인터페이스입니다.|UI4, 유형의 variant 이어야 하며 값의 조합이 포함 되어야는 [CorErrorIfEmitOutOfOrder](../../../../docs/framework/unmanaged-api/metadata/corerrorifemitoutoforder-enumeration.md) 열거 합니다.|  
|MetaDataImportOption|열거자에서 어떤 종류의 ENC 하는 동안 삭제 된 항목을 검색 하는 제어 합니다.|UI4, 유형의 variant 이어야 하며 값의 조합이 포함 되어야는 [CorImportOptions 열거형](../../../../docs/framework/unmanaged-api/metadata/corimportoptions-enumeration.md) 열거 합니다.|  
|MetaDataThreadSafetyOptions|메타 데이터 엔진 가져오면 되므로 스레드로부터의 안전성 잠금을 판독기/작성기 있는지 여부를 제어 합니다. 기본적으로는 엔진을 단일 스레드는 호출자가 잠금 없음 이루어지고 것을 가정 합니다. 클라이언트는 메타 데이터 API를 사용 하는 경우 적절 한 스레드 동기화를 유지 관리 해야 합니다.|UI4, 유형의 variant 이어야 하며 값이 있어야 합니다.는 [CorThreadSafetyOptions](../../../../docs/framework/unmanaged-api/metadata/corthreadsafetyoptions-enumeration.md) 열거 합니다. 값이 비트 마스크입니다.|  
|MetaDataGenerateTCEAdapters|형식 라이브러리 가져오기 COM 연결 지점 컨테이너에 대 한 밀접 하 게 결합 된 이벤트 (TCE) 어댑터를 생성할지 여부를 제어 합니다.|BOOL 형식의 variant를 이어야 합니다. 경우 `pValue` 로 설정 된 `true`, 형식 라이브러리 가져오기 TCE 어댑터를 생성 합니다.|  
|MetaDataTypeLibImportNamespace|가져올 형식 라이브러리에 대해 기본이 아닌 네임 스페이스를 지정 합니다.|Null 값 또는 BSTR 유형의 variant 중 하나 여야 합니다. 경우 `pValue` null 값이 null이 하 고, 그렇지 않으면 현재 네임 스페이스 설정 되어, 현재 네임 스페이스는 variant의 BSTR 형식을 문자열로 설정 됩니다.|  
|MetaDataLinkerOptions|링커에서 어셈블리 또는.NET Framework 모듈 파일을 생성할지 여부를 제어 합니다.|UI4, 유형의 variant 이어야 하며 값의 조합이 포함 되어야는 [CorLinkerOptions](../../../../docs/framework/unmanaged-api/metadata/corlinkeroptions-enumeration.md) 열거 합니다.|  
|MetaDataRuntimeVersion|이 이미지를 빌드할 대상 공용 언어 런타임의 버전을 지정 합니다. 버전은 "v1.0.3705" 같이 문자열으로 저장 됩니다.|Null 값, VT_EMPTY 값 또는 bstr의 변형 이어야 합니다. 경우 `pValue` 가 null 이면 런타임 버전이 설정 되어 null로 합니다. 경우 `pValue` VT_EMPTY를이 버전은이 메타 데이터 코드 실행 되 고 있는 Mscorwks.dll 버전에서 출발 하는 기본값을로 설정 합니다. 그렇지 않으면 런타임 버전은 variant의 BSTR 형식에서 보관 된 문자열에 설정 됩니다.|  
|MetaDataMergerOptions|메타 데이터를 병합 하는 것에 대 한 옵션을 지정 합니다.|UI4, 유형의 variant 이어야 하며 값의 조합이 포함 되어야는 `MergeFlags` 열거형 CorHdr.h 파일에 설명 되어 있습니다.|  
|MetaDataPreserveLocalRefs|정의에 로컬 참조를 최적화 하는 데 사용 하지 않습니다.|값의 조합이 포함 되어야는 [CorLocalRefPreservation](../../../../docs/framework/unmanaged-api/metadata/corlocalrefpreservation-enumeration.md) 열거 합니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에서 리소스로 사용  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IMetaDataDispenserEx 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 [IMetaDataDispenser 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
