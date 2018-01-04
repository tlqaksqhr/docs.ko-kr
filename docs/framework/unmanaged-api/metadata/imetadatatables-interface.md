---
title: "IMetaDataTables 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataTables
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataTables
helpviewer_keywords: IMetaDataTables interface [.NET Framework metadata]
ms.assetid: 31272cce-506a-4f18-bcbf-01ee45e36356
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ff70e99a963c929792a73cefd6e8feaefa8b252e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="imetadatatables-interface"></a>IMetaDataTables 인터페이스
테이블에서 메타데이터 정보를 저장 및 검색하는 메서드를 제공합니다.  
  
## <a name="methods"></a>메서드  
  
|메서드|설명|  
|------------|-----------------|  
|[GetBlob 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getblob-method.md)|이진 대형 개체 (BLOB)에 지정 된 열 인덱스에 대 한 포인터를 가져옵니다.|  
|[GetBlobHeapSize 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getblobheapsize-method.md)|BLOB 힙을 바이트 단위로 크기를 가져옵니다.|  
|[GetCodedTokenInfo 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcodedtokeninfo-method.md)|지정된 된 행 인덱스와 연결 된 토큰의 배열에 대 한 포인터를 가져옵니다.|  
|[GetColumn 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcolumn-method.md)|지정된 된 테이블 인덱스에 있는 테이블에 지정 된 열 인덱스의 열에 포함 된 값에 대 한 포인터를 가져옵니다.|  
|[GetColumnInfo 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcolumninfo-method.md)|지정된 된 테이블의 지정된 된 열에 대 한 데이터를 가져옵니다.|  
|[GetGuid 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getguid-method.md)|지정된 된 인덱스에서 행의 GUID를 가져옵니다.|  
|[GetGuidHeapSize 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getguidheapsize-method.md)|GUID 힙을 바이트 단위로 크기를 가져옵니다.|  
|[GetNextBlob 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextblob-method.md)|테이블의 다음 BLOB의 인덱스를 가져옵니다.|  
|[GetNextGuid 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextguid-method.md)|현재 테이블 열에 다음 GUID 값의 인덱스를 가져옵니다.|  
|[GetNextString 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextstring-method.md)|현재 테이블 열에 다음 문자열의 인덱스를 가져옵니다.|  
|[GetNextUserString 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextuserstring-method.md)|현재 테이블 열에 있는 다음 하드 코드 된 문자열이 포함 된 행의 인덱스를 가져옵니다.|  
|[GetNumTables 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnumtables-method.md)|현재 범위에 테이블의 수를 가져옵니다 `IMetaDataTables` 인스턴스.|  
|[GetRow 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getrow-method.md)|지정 된 행 인덱스에 지정된 된 테이블 인덱스에 있는 테이블에 행을 가져옵니다.|  
|[GetString 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getstring-method.md)|현재 참조 범위에서 테이블 열에서 지정된 된 인덱스에 문자열을 가져옵니다.|  
|[GetStringHeapSize 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getstringheapsize-method.md)|문자열 힙을 바이트 단위로 크기를 가져옵니다.|  
|[GetTableIndex 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-gettableindex-method.md)|지정한 토큰이 참조 하는 테이블에 대 한 인덱스를 가져옵니다.|  
|[GetTableInfo 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-gettableinfo-method.md)|지정한 테이블 인덱스에는 이름, 행 크기, 행의 수, 열 개수 및 테이블의 키 열 인덱스를 가져옵니다.|  
|[GetUserString 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getuserstring-method.md)|현재 범위에서 문자열 열에서 지정된 된 인덱스에 하드 코드 된 문자열을 가져옵니다.|  
|[GetUserStringHeapSize 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getuserstringheapsize-method.md)|사용자 문자열 힙을 바이트 단위로 크기를 가져옵니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** Cor.h  
  
 **라이브러리:** MsCorEE.dll에서 리소스로 사용  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [메타데이터 인터페이스](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [IMetaDataTables2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
