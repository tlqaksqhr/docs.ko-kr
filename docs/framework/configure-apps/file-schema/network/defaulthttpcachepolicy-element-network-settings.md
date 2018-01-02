---
title: "&lt;defaultHttpCachePolicy&gt; 요소 (네트워크 설정)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching/defaultHttpCachePolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultHttpCachePolicy
helpviewer_keywords:
- defaultHttpCachePolicy element
- <defaultHttpCachePolicy> element
ms.assetid: 2c1247d0-39b0-4c12-919a-a925ce075c79
caps.latest.revision: "19"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 048d9a373c77e530bd352b3caa0e122b3833a5c2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltdefaulthttpcachepolicygt-element-network-settings"></a>&lt;defaultHttpCachePolicy&gt; 요소 (네트워크 설정)
HTTP 캐싱이 활성 인지 여부와 기본 캐싱 정책은 설명에 대해 설명 합니다.  
  
 \<configuration>  
\<system.net >  
\<requestCaching >  
\<defaultHttpCachePolicy >  
  
## <a name="syntax"></a>구문  
  
```xml  
<defaultHttpCachePolicy  
  policyLevel="BypassCache|Default"  
  minimumFresh="d.hh:mm:ss|minValue|maxValue"  
  maximumAge="d.hh:mm:ss|minValue|maxValue"  
  maximumStale="d.hh:mm:ss|minValue|maxValue"  
/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`maximumAge`|캐시 된 개체는 만료 상태로 표시 되기 전에 최대 시간 간격을 지정 합니다.|  
|`maximumStale`|캐시 된 개체는 만료 상태로 표시 되기 전에 계산된 새로 고침 시간이 지난 최대 시간을 지정 합니다.|  
|`minimumFresh`|새로운 것으로 간주 되려면 캐시 된 개체에 대 한 최소 시간을 지정 합니다.|  
|`policyLevel`|캐싱 정책은 자동으로 아니면 캐시 무시 되는지 여부를 지정 합니다. 기본값은 `BypassCache`입니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[requestCaching](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|네트워크 요청에 대 한 캐싱 메커니즘을 제어합니다.|  
  
## <a name="remarks"></a>설명  
 에 대 한 값은 `policyLevel` 특성은 `BypassCache` 또는 `Default`합니다.  
  
 에 대 한 값은 `maximumAge`, `maximumStale`, 및 `minimumFresh` 요소 형식의 지정 된 시간 간격을는 *d*. *hh*:*mm*:*ss* (일, 시, 분 및 초) 또는 상수 `minValue` 또는 `maxValue`를 적절 하 게 합니다.  
  
## <a name="configuration-files"></a>구성 파일  
 이 요소는 응용 프로그램 구성 파일 또는 컴퓨터 구성 파일(Machine.config)에서 사용할 수 있습니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 6 시간, 2 일의 최대 사용 기간 및 최대 부실 시간의 부여한 지 4 시간 동안 최소 새로 고침 시간을 지정 하는 방법을 보여 줍니다.  
  
```xml  
<configuration>  
  <system.net>  
    <requestCaching>  
      <defaultHttpCachePolicy  
        minimumFresh="0.06:00:00"  
        maximumAge="2.00:00:00"  
        maximumStale="0.04:00:00"
      />  
    </requestCaching>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Net.Cache>  
 <xref:System.Net.WebRequest>  
 <xref:System.Net.Cache.RequestCacheLevel>  
 [네트워크 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
