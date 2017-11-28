---
title: "CorAssemblyFlags 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorAssemblyFlags
api_location: mscoree.dll
api_type: COM
f1_keywords: CorAssemblyFlags
helpviewer_keywords: CorAssemblyFlags enumeration [.NET Framework metadata]
ms.assetid: bb8db3b6-d81d-49fc-b74c-dbc908a9eab9
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 67057944705a1cecd1754c3c11da08725c9a93f9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="corassemblyflags-enumeration"></a>CorAssemblyFlags 열거형
어셈블리 컴파일에 적용되는 메타데이터를 설명하는 값을 포함합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef enum CorAssemblyFlags {  
  
    afPublicKey             =   0x0001,  
    afPA_None               =   0x0000,  
    afPA_MSIL               =   0x0010,  
    afPA_x86                =   0x0020,  
    afPA_IA64               =   0x0030,  
    afPA_AMD64              =   0x0040,  
    afPA_ARM                =   0x0050,  
    afPA_NoPlatform         =   0x0070,  
    afPA_Specified          =   0x0080,  
    afPA_Mask               =   0x0070,  
    afPA_FullMask           =   0x00F0,  
    afPA_Shift              =   0x0004,  
  
    afEnableJITcompileTracking  =   0x8000,  
    afDisableJITcompileOptimizer=   0x4000,  
  
    afRetargetable          =   0x0100,  
    afContentType_Default        =   0x0000,  
    afContentType_WindowsRuntime =   0x0200,  
    afContentType_Mask           =   0x0E00,  
  
} CorAssemblyFlags;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`afPublicKey`|어셈블리 참조는 전체, 해시 되지 않은 공개 키 함을 나타냅니다.|  
|`afPA_None`|프로세서 아키텍처 지정 임을 나타냅니다.|  
|`afPA_MSIL`|프로세서 아키텍처 중립 임을 나타냅니다 (PE32).|  
|`afPA_x86`|프로세서 아키텍처 x86 (PE32) 임을 나타냅니다.|  
|`afPA_IA64`|프로세서 아키텍처 Itanium (PE32 +) 임을 나타냅니다.|  
|`afPA_AMD64`|프로세서 아키텍처 AMD X64 (PE32 +) 임을 나타냅니다.|  
|`afPA_ARM`|프로세서 아키텍처 ARM (PE32) 임을 나타냅니다.|  
|`afPA_NoPlatform`|어셈블리가 참조 어셈블리; 임을 나타냅니다. 즉, 모든 아키텍처에 적용 되지만 모든 아키텍처에서 실행할 수 없습니다. 따라서 플래그는 동일 `afPA_Mask`합니다.|  
|`afPA_Specified`|프로세서 아키텍처 플래그에 전파 해야 있는지 나타냅니다는 `AssemblyRef` 레코드입니다.|  
|`afPA_Mask`|프로세서 아키텍처를 설명 하는 마스크입니다.|  
|`afPA_FullMask`|프로세서 아키텍처 설명을 포함 되어 있는지를 지정 합니다.|  
|`afPA_Shift`|프로세서 아키텍처 플래그 인덱스에서 시프트 횟수를 나타냅니다.|  
|`afEnableJITcompileTracking`|해당 값을 나타냅니다는 <xref:System.Diagnostics.DebuggableAttribute.DebuggingModes> 의 <xref:System.Diagnostics.DebuggableAttribute>합니다.|  
|`afDisableJITcompileOptimizer`|해당 값을 나타냅니다는 <xref:System.Diagnostics.DebuggableAttribute.DebuggingModes> 의 <xref:System.Diagnostics.DebuggableAttribute>합니다.|  
|`afRetargetable`|어셈블리가 다른 게시자의 어셈블리에 실행 시 대상이 될 수 있는지를 나타냅니다.|  
|`afContentType_Mask`|콘텐츠 형식을 설명 하는 마스크입니다.|  
|`afContentType_Default`|기본 콘텐츠 형식을 나타냅니다.|  
|`afContentType_WindowsRuntime`|나타냅니다는 [!INCLUDE[wrt](../../../../includes/wrt-md.md)] 콘텐츠 형식입니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.  
  
 **헤더:** CorHdr.h  
  
 **.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [메타 데이터 열거형](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
