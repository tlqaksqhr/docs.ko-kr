---
title: "&lt;applicationPool&gt; 요소 (웹 설정)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- applicationPool element
- <applicationPool> element
ms.assetid: 46d1baaa-e343-4639-b70d-2a43a9f62b2a
caps.latest.revision: "12"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: d75e9eedf42523301b3c1745c05d90bcdafbdbf5
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="ltapplicationpoolgt-element-web-settings"></a>&lt;applicationPool&gt; 요소 (웹 설정)
ASP.NET 응용 프로그램 통합된 모드에서 실행 중인 경우 프로세스 전체 동작을 관리 하려면 ASP.NET에서 사용 되는 구성 설정을 지정 [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] 또는 이후 버전입니다.  
  
> [!IMPORTANT]
>  ASP.NET 응용 프로그램에서 호스팅되는 경우 유일한 작업 지원이 요소 및 기능 [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] 또는 이후 버전입니다.  
  
 \<configuration>  
\<system.web > 요소 (웹 설정)  
\<applicationPool > 요소 (웹 설정)  
  
## <a name="syntax"></a>구문  
  
```xml  
<applicationPool   
    maxConcurrentRequestsPerCPU="5000"   
    maxConcurrentThreadsPerCPU="0"   
    requestQueueLimit="5000" />  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|`maxConcurrentRequestsPerCPU`|ASP.NET을 사용 하면 CPU 당 동시 요청 수를 지정 합니다.|  
|`maxConcurrentThreadsPerCPU`|각 CPU에 대 한 응용 프로그램 풀에 대 한 동시 스레드를 실행할 수를 지정 합니다. 이 CPU 당는 요청을 처리 하는 데 사용할 수 있는 관리 되는 스레드 수를 제한할 수 있기 때문에 ASP.NET 동시성 제어 하는 대체 방법을 제공 합니다. 기본적으로이 설정은 0 이며 ASP.NET CLR 스레드 풀도 만들 수 있는 스레드 수를 제한 하지만 CPU 당 만들 수 있는 스레드 수가 제한 되지 않습니다입니다.|  
|`requestQueueLimit`|단일 프로세스에서 ASP.NET에 대해 대기할 수 있는 요청의 최대 수를 지정 합니다. 둘 이상의 ASP.NET 응용 프로그램을 단일 응용 프로그램 풀에서 실행 누적 집합 응용 프로그램 풀에서 응용 프로그램에 전송 되는 요청을이 설정을 적용 됩니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<system.web>](../../../../../docs/framework/configure-apps/file-schema/web/system-web-element-web-settings.md)|ASP.NET 응용 프로그램을 호스트와 상호 작용 하는 방법에 대 한 정보를 포함 합니다.|  
  
## <a name="remarks"></a>설명  
 실행 하는 경우 [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] 또는 통합된 모드에서 최신 버전을이 요소 조합을 사용 하 여 응용 프로그램은 IIS 응용 프로그램 풀에서 호스팅되는 경우 ASP.NET 스레드 및 큐 요청을 관리 하는 방법을 구성 합니다. IIS 6을 실행 하거나 실행 하면 [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] 클래식 모드에서 또는 ISAPI 모드에서 이러한 설정이 무시 됩니다.  
  
 `applicationPool` 설정은 특정 버전의.NET Framework에서 실행 되는 모든 응용 프로그램 풀에 적용 합니다. Aspnet.config 파일에는 설정이 포함 됩니다. 버전 2.0 및.NET framework 4.0이 파일 버전이 있습니다. (버전 3.0 및 3.5는.NET Framework의 공유할 aspnet.config 파일 버전 2.0.)  
  
> [!IMPORTANT]
>  실행 하는 경우 [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] 에 [!INCLUDE[win7](../../../../../includes/win7-md.md)], 모든 응용 프로그램 풀에 대 한 별도 aspnet.config 파일을 구성할 수 있습니다. 이렇게 하면 각 응용 프로그램 풀에 대 한 스레드의 성능을 조정할 수 있습니다.  
  
 에 대 한는 `maxConcurrentRequestsPerCPU` , "5000"의 기본 설정에서 설정 된 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)] 하는 경우가 아니면 CPU 당 5000 개 이상의 요청이 ASP.NET에서 제어 효과적으로 000입니다. 기본 설정은 자동으로 동시성을 관리할 수는 CPU 당 CLR 스레드 풀에 따라 대신 다릅니다. 비동기 요청 처리를 많이 사용 하는 하거나 네트워크 I/O에서 차단 된 많은 장기 실행 요청 응용 프로그램에서 향상 된 기본 제한에서 이익을 얻을 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)]합니다. 설정 `maxConcurrentRequestsPerCPU` 을 ASP.NET 요청을 처리 하기 위해 0으로 관리 되는 스레드 사용을 해제 합니다. 응용 프로그램 IIS 응용 프로그램 풀에서 실행 되 면 요청 IIS I/O 스레드에서 대기 하며 IIS 스레드 설정 하 여 동시성 스로틀 되는지는 따라서 합니다.  
  
 `requestQueueLimit` 동일한 방식으로 작동 하는 설정을 `requestQueueLimit` 특성에는 [processModel](http://msdn.microsoft.com/library/4b8fe20e-74c8-4566-b72c-ce5f83c8e32d) ASP.NET 응용 프로그램에 대 한 Web.config 파일에 설정 된 요소입니다. 그러나는 `requestQueueLimit` aspnet.config 파일의 설정 재정의 `requestQueueLimit` Web.config 파일에서 설정 합니다. 즉, 두 특성이 모두 설정 된 경우 (기본적으로 true 이면)는 `requestQueueLimit` aspnet.config 파일에서 설정이 우선 합니다.  
  
## <a name="example"></a>예  
 다음 예제에는 다음과 같은 경우 aspnet.config 파일에서 ASP.NET 프로세스 수준 동작을 구성 하는 방법을 보여 줍니다.  
  
-   응용 프로그램에서 호스트 되는 [!INCLUDE[iisver](../../../../../includes/iisver-md.md)] 응용 프로그램 풀.  
  
-   [!INCLUDE[iisver](../../../../../includes/iisver-md.md)]통합된 모드에서 실행 중입니다.  
  
-   응용 프로그램을 사용 하 여는 [!INCLUDE[net_v35SP1_short](../../../../../includes/net-v35sp1-short-md.md)] 또는 이후 버전입니다.  
  
 예제에서 값은 기본값입니다.  
  
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
 [\<system.web> 요소(웹 설정)](../../../../../docs/framework/configure-apps/file-schema/web/system-web-element-web-settings.md)
