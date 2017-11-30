---
title: "CorOpenFlags 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorOpenFlags
api_location: mscoree.dll
api_type: COM
f1_keywords: CorOpenFlags
helpviewer_keywords: CorOpenFlags enumeration [.NET Framework metadata]
ms.assetid: e27a83b5-2698-4996-9032-1e0fed8b91ca
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c7599a4b85a166aedd7a2293b79699b3ef03d14d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="coropenflags-enumeration"></a>CorOpenFlags 열거형
매니페스트 파일을 열 때 메타데이터 동작을 제어하는 플래그 값을 포함합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef enum CorOpenFlags  
{  
    ofRead              =   0x00000000,  
    ofWrite             =   0x00000001,  
    ofReadWriteMask     =   0x00000001,  
    ofCopyMemory        =   0x00000002,  
    ofCacheImage        =   0x00000004,  
    ofManifestMetadata  =   0x00000008,  
    ofReadOnly          =   0x00000010,  
    ofTakeOwnership     =   0x00000020,  
    ofCacheImage        =   0x00000004,  
    ofNoTypeLib         =   0x00000080,  
    ofNoTransform       =   0x00001000,  
    ofReserved1         =   0x00000100,  
    ofReserved2         =   0x00000200,  
    ofReserved          =   0xffffff40  
} CorOpenFlags;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`ofRead`|파일을 읽기 전용으로 열어야 함을 나타냅니다.|  
|`ofWrite`|쓸 수 있도록 파일을 열어야 함을 나타냅니다.<br /><br /> .winmd 파일을 열 때 `ofWrite` 플래그를 사용하는 경우에는 `ofNoTransform` 플래그도 전달해야 합니다.|  
|`ofReadWriteMask`|읽기 및 쓰기용 마스크입니다.|  
|`ofCopyMemory`|파일을 메모리로 읽어들여야 함을 나타냅니다. 메타데이터는 자체 복사본을 유지해야 합니다.|  
|`ofCacheImage`|사용되지 않습니다. 이 플래그는 무시됩니다.|  
|`ofManifestMetadata`|사용되지 않습니다. 이 플래그는 무시됩니다.|  
|`ofReadOnly`|읽기, 및에 대 한 파일을 열 수 있는지 나타냅니다에 대 한 호출 `QueryInterface` 에 대 한 프로그램 [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) 만들 수 없습니다.|  
|`ofTakeOwnership`|에 대 한 호출을 사용 하 여 메모리가 할당 된 나타냅니다 [CoTaskMemAlloc](http://msdn.microsoft.com/en-us/c4cb588d-9482-4f90-a92e-75b604540d5c) 메타 데이터에서 해제 합니다.|  
|`ofNoTypeLib`|사용되지 않습니다. 이 플래그는 무시됩니다.|  
|`ofNoTransform`|.winmd 파일의 자동 변환을 사용하지 않도록 설정해야 함을 나타냅니다. 즉, Windows 런타임 형식에서 .NET Framework 형식으로의 프로젝션을 사용하지 않도록 설정해야 합니다. 자세한 내용은 참조 [아래 고급.NET 및 Windows Runtime](http://msdn.microsoft.com/magazine/jj651569.aspx)합니다.|  
|`ofReserved1`|내부용으로 예약됩니다.|  
|`ofReserved2`|내부용으로 예약됩니다.|  
|`ofReserved`|내부용으로 예약됩니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorHdr.h  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [메타 데이터 열거형](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
