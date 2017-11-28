---
title: '&lt;tokenReplayCache&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1572ab23-6933-41b5-bfb4-0c4548145500
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: e43e79416ddb8862cbc6e52d9d449a02b123af83
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="lttokenreplaycachegt"></a>&lt;tokenReplayCache&gt;
토큰 재생 캐시는 서비스 또는 보안 토큰 처리기 컬렉션에 등록합니다.  
  
 \<system.identityModel >  
\<identityConfiguration >  
\<캐시 >  
\<tokenReplayCache >  
  
## <a name="syntax"></a>구문  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
      <tokenReplayCache type=xs:string>  
      </tokenReplayCache>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|type|파생 되는 형식을 <xref:System.IdentityModel.Tokens.TokenReplayCache> 클래스입니다. 사용자 지정 하는 방법에 대 한 자세한 내용은 `type`, [사용자 지정 형식 참조]를 참조 하세요.
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<캐시 >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/caches.md)|서비스 또는 보안 토큰 처리기 컬렉션에서 사용 하는 캐시에 등록 합니다.|  
  
## <a name="remarks"></a>설명  
 토큰 재생 캐시가 재생 된 토큰을 검색 하는 데 사용 됩니다. 토큰 재생 검색으로 사용 되는 [ \<tokenReplayDetection >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md) 또한 토큰에 대 한 최대 만료 시간을 지정 하는 요소입니다.  
  
## <a name="example"></a>예제  
 다음 XML에서는 토큰 재생된 검색에 대 한 사용자 지정 캐시의 구성을 보여 줍니다.  
  
```xml  
<caches>  
  <tokenReplayCache type="MyCacheLibrary.MyTokenReplayCache, MyCacheLibrary">  
  </tokenReplayCache>  
</caches>  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.IdentityModel.Tokens.TokenReplayCache>  
 [\<tokenReplayDetection >](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaydetection.md)
