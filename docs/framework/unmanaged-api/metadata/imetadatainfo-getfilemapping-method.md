---
title: IMetaDataInfo::GetFileMapping 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataInfo.GetFileMapping
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataInfo::GetFileMapping
helpviewer_keywords:
- IMetaDataInfo::GetFileMapping method [.NET Framework metadata]
- GetFileMapping method [.NET Framework metadata]
ms.assetid: 2868dfec-c992-4606-88bb-a8e0b6b18271
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 562b6fcd015441ce5eb6b5f0ab7a4f361bb229c3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="imetadatainfogetfilemapping-method"></a>IMetaDataInfo::GetFileMapping 메서드
매핑된 파일 및 형식 매핑의 메모리 영역을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetFileMapping (  
    [out] const void           **ppvData,   
    [out] ULONGLONG            *pcbData,   
    [out] DWORD                *pdwMappingType  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ppvData`  
 [out] 매핑된 파일의 시작 부분에 대 한 포인터입니다.  
  
 `pcbData`  
 [out] 매핑된 영역의 크기입니다. 경우 `pdwMappingType` 은 `fmFlat`, 파일의 크기입니다.  
  
 `pdwMappingType`  
 [out] A [CorFileMapping](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md) 매핑 유형을 나타내는 값입니다. 공용 언어 런타임 (CLR)의 현재 구현은 항상 반환 `fmFlat`합니다. 다른 값은 나중에 사용할 수는 예약 되어 있습니다. 그러나 다른 값 이후 버전에서 사용할 수 있습니다 또는 서비스 릴리스 때문에 반환된 된 값에 확인 해야 항상 합니다.  
  
## <a name="return-value"></a>반환 값  
  
|HRESULT|설명|  
|-------------|-----------------|  
|`S_OK`|모든 출력은 채워집니다.|  
|`E_INVALIDARG`|인수 값으로 NULL이 전달 되었습니다.|  
|`COR_E_NOTSUPPORTED`|CLR 구현 된 메모리 영역에 대 한 정보를 제공할 수 없습니다. 이 작업은 다음과 같은 이유로 발생할 수 있습니다.<br /><br /> -메타 데이터 범위의으로 열렸으면는 `ofWrite` 또는 `ofCopyMemory` 플래그입니다.<br />-메타 데이터 범위의 하지 않고 열림는 `ofReadOnly` 플래그입니다.<br />- [Imetadatadispenser:: Openscopeonmemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) 메서드는 파일의 메타 데이터 부분에 여는 데 사용 되었습니다.<br />-파일 (pe) 파일이 아닙니다. **참고:** 이러한 조건을 CLR 구현에 따라 다르며는 문제일 수 약화 이후 버전의 CLR 합니다.|  
  
## <a name="remarks"></a>설명  
 메모리는 `ppvData` 동안만 기본 메타 데이터 범위 열릴 가리키는 유효 합니다.  
  
 이 메서드를 호출 하 여 메모리에는 디스크에 파일의 메타 데이터를 매핑할 때 작동 되려면는 [imetadatadispenser:: Openscope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) 지정 해야 합니다는 `ofReadOnly` 플래그를 지정 해야 합니다는 `ofWrite` 또는 `ofCopyMemory` 플래그입니다.  
  
 각 범위에 대 한 파일 매핑 형식의 choice는 CLR의 지정 된 구현 관련이 있습니다. 사용자가 설정할 수 없습니다. CLR의 현재 구현은 항상 반환 `fmFlat` 에 `pdwMappingType`, CLR의 버전 또는 나중에 지정된 된 버전의 서비스 릴리스 나중에 변경할 수이 있습니다. 반환된 된 값을 항상 확인 해야 `pdwMappingType`때문에 유형이 다른 다양 한 레이아웃 및 오프셋, 합니다.  
  
 세 개의 매개 변수 중 하나에 대 한 NULL을 전달 하는 것은 지원 되지 않습니다. 메서드가 반환 `E_INVALIDARG`, 및 아무런 출력이 채워집니다. 매핑 유형 또는 크기의 영역을 무시 합니다. 비정상적인 프로그램 종료 될 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에서 리소스로 사용  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [IMetaDataInfo 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-interface.md)  
 [CorFileMapping 열거형](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md)
