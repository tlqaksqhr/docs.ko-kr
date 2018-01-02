---
title: "&lt;requestCaching&gt; 요소 (네트워크 설정)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#requestCaching
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching
helpviewer_keywords:
- requestCaching element
- <requestCaching> element
ms.assetid: 9962a2fe-cbda-41a6-9377-571811eaea84
caps.latest.revision: "20"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 35665bd79a14b74e192fed439e935936411d85c3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltrequestcachinggt-element-network-settings"></a>&lt;requestCaching&gt; 요소 (네트워크 설정)
네트워크 요청에 대 한 캐싱 메커니즘을 제어합니다.  
  
 \<configuration>  
\<system.net >  
\<requestCaching >  
  
## <a name="syntax"></a>구문  
  
```xml  
      <requestCaching>  
        isPrivateCache ="true|false"  
        disableAllCaching="true|false"  
        defaultPolicyLevel="BypassCache|Default|CacheOnly|CacheIfAvailable|Revalidate|Reload|NoCacheNoStore|Revalidate"  
        unspecifiedMaximumAge= "d.hh.mm.ss">  
          <defaultHttpCachePolicy> … </defaultHttpCachePolicy>  
          <defaultFtpCachePolicy> … </defaultFtpCachePolicy>  
      </requestCaching>
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`isPrivateCache`|캐시에서 다양 한 사용자 정보 간에 격리 제공 여부를 지정 합니다. 기본값은 `true`입니다. 이 값은 이어야 `false` 중간 계층 응용 프로그램에 대 한 합니다.|  
|`disableAllCaching`|캐싱 모든 웹 응답에 대해 사용 되지 않는지 및 프로그래밍 방식으로 재정의할 수 없습니다 지정 합니다.|  
|`defaultPolicyLevel`|<xref:System.Net.Cache.RequestCacheLevel> 열거형에 값 중 하나입니다. 기본값은 `BypassCache`입니다.|  
|`unspecifiedMaximumAge`|지나면 콘텐츠가 만료로 표시 된 기본 시간을 지정 합니다.|  
  
## <a name="policylevel-attribute"></a>policyLevel 특성  
  
|값|설명|  
|-----------|-----------------|  
|`Default`|리소스를 새, 콘텐츠 길이 정확 하 게, 만료, 수정 및 콘텐츠 길이 특성이 있는 경우에 캐시 된 리소스를 반환 합니다.|  
|`BypassCache`|서버에서 리소스를 반환합니다.|  
|`CacheOnly`|콘텐츠 길이 있고 항목 크기와 일치 하는 경우 캐시 된 리소스를 반환 합니다.|  
|`CacheIfAvailable`|콘텐츠 길이가 제공 되 고 일치 항목 크기가; 캐시 된 리소스를 반환 합니다. 그렇지 않으면 리소스는 서버에서 다운로드 하 고 호출자에 게 반환 됩니다.|  
|`Revalidate`|캐시 된 리소스의 타임 스탬프 서버에서 리소스의 타임 스탬프와 동일한 경우 캐시 된 리소스를 반환 합니다. 그렇지 않으면 리소스는 캐시에 저장 하는 서버에서 다운로드 되 고 호출자에 게 반환 됩니다.|  
|`Reload`|서버에서 리소스를 다운로드, 캐시에 저장 하 고 호출자에 게 리소스를 반환 합니다.|  
|`NoCacheNoStore`|캐시 된 리소스가 있는 경우 삭제 됩니다. 리소스는 서버에서 다운로드 되 고 호출자에 게 반환 됩니다.|  
|`Revalidate`|타임 스탬프 서버에서 리소스의 타임 스탬프와 동일한 경우 리소스의 캐시 된 복사본을 사용 하 여 요청을 만족 시킵니다. 그렇지 리소스 호출자에 게 표시 되는 서버에서 다운로드 되 고 캐시에 저장 됩니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[defaultHttpCachePolicy](../../../../../docs/framework/configure-apps/file-schema/network/defaulthttpcachepolicy-element-network-settings.md)|선택적 요소입니다.<br /><br /> HTTP 캐싱이 활성 인지 여부와 기본 캐싱 정책은 설명에 대해 설명 합니다.|  
|[\<defaultFtpCachePolicy > 요소 (네트워크 설정)](../../../../../docs/framework/configure-apps/file-schema/network/defaultftpcachepolicy-element-network-settings.md)|선택적 요소입니다.<br /><br /> FTP 캐싱이 활성 인지 여부와 기본 캐싱 정책은 설명에 대해 설명 합니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[system.net](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|.NET Framework의 네트워크 연결 방법을 지정하는 설정을 포함합니다.|  
  
## <a name="example"></a>예  
 다음 예제에서는 모든 캐싱을 사용 하지 않도록 설정 하는 방법을 보여 줍니다.  
  
```xml  
<configuration>  
  <system.net>  
    <requestCaching  
      disableAllCaching="true"  
    />  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Net.Cache?displayProperty=nameWithType>  
 [네트워크 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
