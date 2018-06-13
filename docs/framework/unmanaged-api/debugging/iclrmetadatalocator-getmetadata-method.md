---
title: ICLRMetadataLocator::GetMetadata 메서드
ms.date: 03/30/2017
api_name:
- ICLRMetadataLocator.GetMetadata
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRMetadataLocator::GetMetadata
helpviewer_keywords:
- GetMetadata method, ICLRMetadataLocator interface [.NET Framework debugging]
- ICLRMetadataLocator::GetMetadata method [.NET Framework debugging]
ms.assetid: 704a8893-ac56-43b4-90ea-715f38ccb40e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4338619414c9c9ac8c5fe85479562410d1678698
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33403860"
---
# <a name="iclrmetadatalocatorgetmetadata-method"></a>ICLRMetadataLocator::GetMetadata 메서드
이미지의 메타 데이터를 검색 하는 공용 언어 런타임 (CLR) 데이터 액세스 서비스에서 호출 됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetMetadata(  
    [in]  LPCWSTR         imagePath,  
    [in]  ULONG32         imageTimestamp,  
    [in]  ULONG32         imageSize,  
    [in]  GUID*           mvid,  
    [in]  ULONG32         mdRva,  
    [in]  ULONG32         flags,  
    [in]  ULONG32         bufferSize,  
    [out, size_is(bufferSize), length_is(*dataSize)]  
          BYTE*           buffer,  
    [out] ULONG32*        dataSize  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `imagePath`  
 [in] 이미지 파일의 경로 지정 하는 문자열입니다.  
  
 `imageTimestamp`  
 [in] 이미지 파일의 타임 스탬프입니다.  
  
 `imageSize`  
 [in] 이미지 파일의 크기입니다.  
  
 `mvid`  
 [in] 이미지의 전역 고유 식별자입니다.  
  
 `mdRva`  
 [in] 상대 가상 주소 (RVA) 메타 데이터의 합니다. 주소는 이미지 기준 주소에 상대적입니다.  
  
 `flags`  
 [in] 나중에 사용할 수는 예약 되어 있습니다.  
  
 `bufferSize`  
 [in] 메타 데이터를 배치할 수 있는 버퍼의 크기입니다.  
  
 `buffer`  
 [out] 메타 데이터를 저장할 버퍼입니다.  
  
 `dataSize`  
 [out] 반환 되는 메타 데이터의 크기입니다.  
  
## <a name="remarks"></a>설명  
 이 메서드는 디버깅 응용 프로그램의 작성자가 구현합니다.  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** ClrData.idl, ClrData.h  
  
 **라이브러리:** CorGuids.lib  
  
 **.NET framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [ICLRMetadataLocator 인터페이스](../../../../docs/framework/unmanaged-api/debugging/iclrmetadatalocator-interface.md)
