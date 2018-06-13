---
title: '&lt;system.web&gt; 요소 (웹 설정)'
ms.date: 03/30/2017
helpviewer_keywords:
- Web.config configuration file [ASP.NET]
- system.Web element
- <system.Web> element
- ASP.NET configuration system
- configuration files [ASP.NET]
ms.assetid: 24c4cf4f-ad32-42b2-b040-8e4549e2855e
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 7527ee9e7528a0da47529bae93e8112705e03a36
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32755164"
---
# <a name="ltsystemwebgt-element-web-settings"></a>&lt;system.web&gt; 요소 (웹 설정)
ASP.NET 호스팅 계층에서 프로세스 전체 동작을 관리 하는 방법에 대 한 정보를 포함 합니다.  
  
 \<configuration>  
\<system.web > 요소 (웹 설정)  
  
## <a name="syntax"></a>구문  
  
```xml  
<system.web>  
</system.web>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
 없음  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<applicationPool>](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)|Aspnet.config 파일에서 IIS 응용 프로그램 풀에 대 한 구성 설정을 지정합니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<구성>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)|공용 언어 런타임 및 [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소를 지정합니다.|  
  
## <a name="remarks"></a>설명  
 `system.web` 요소와 해당 자식 `applicationPool` 요소에 추가 된는 [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] 의 [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)]합니다. 실행 하는 경우 [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] 또는 통합된 모드에서 이후 버전에서는이 요소 조합을 사용 하 여 ASP.NET 스레드를 관리 하는 방법 및 ASP.NET이 IIS 응용 프로그램 풀에서 호스팅되는 경우 요청 대기 하는 방법을 구성 합니다. 실행 하는 경우 [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] 또는 이후 버전 ISAPI 또는 클래식 모드에서는 이러한 설정이 무시 됩니다.  
  
## <a name="example"></a>예제  
 다음 예제에는 ASP.NET이 IIS 응용 프로그램 풀에서 호스팅되는 경우 aspnet.config 파일에서 ASP.NET 프로세스 수준 동작을 구성 하는 방법을 보여 줍니다. 이 예제에서는 통합에서 IIS가 실행 되 고 가정 모드와 응용 프로그램이 사용 하는 [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)] 또는 이후 버전입니다. 버전의이 문제가 발생 하지 않습니다는 [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] 이전의 [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)]합니다. 예제에서 값은 기본값입니다.  
  
```xml  
<configuration>  
  <system.web>  
    <applicationPool   
        maxConcurrentRequestsPerCPU="5000"   
        maxConcurrentThreadsPerCPU="0"   
        requestQueueLimit="5000" />  
  </system.web>  
</configuration>  
```  
  
## <a name="element-information"></a>요소 정보  
  
|||  
|-|-|  
|네임스페이스||  
|스키마 이름||  
|유효성 검사 파일||  
|비워 둘 수 있습니다.||  
  
## <a name="see-also"></a>참고 항목  
 [\<applicationPool> 요소(웹 설정)](../../../../../docs/framework/configure-apps/file-schema/web/applicationpool-element-web-settings.md)
