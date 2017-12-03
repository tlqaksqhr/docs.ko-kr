---
title: '&lt;backupList&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a3d9d1f9-4a53-45e9-a880-86c8bee0b833
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8cb8f08c1d9c48aee9d3b42aadce0f65c8fe0585
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="ltbackuplistgt"></a>&lt;backupList&gt;
라우팅 서비스는 기본 끝점 도달할 수 없는 경우 사용 하도록 할 끝점 집합을 열거 하는 백업 목록을 정의 하기 위한 구성 섹션을 나타냅니다. 목록의 첫 번째 끝점이 다운되는 경우 라우팅 서비스는 자동으로 목록의 다음 끝점으로 장애 조치(failover)됩니다.  따라서 복잡한 패턴을 처리하는 방법이나 모든 서비스가 배포되는 위치를 클라이언트 응용 프로그램에 지정할 필요 없이 응용 프로그램의 안정성을 빠르게 향상시킬 수 있습니다.  
  
 \<system.serviceModel >  
\<라우팅 >  
\<backupLists >  
\<backupList >  
  
## <a name="syntax"></a>구문  
  
```xml 
   <routing>  <backupLists>    <backupList name="String">      <add endpointName="String" />    </backupList>    </backupLists></routing>  
```

## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|name|이 끝점 목록을 식별하는 데 사용되는 이름을 지정하는 문자열입니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<filter>](../../../../../docs/framework/configure-apps/file-schema/wcf/filter.md)||  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<라우팅 >](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|백업 끝점의 목록입니다.|  
  
## <a name="remarks"></a>설명  
 이 섹션에는 기본 끝점으로 메시지를 보낼 때 통신 예외가 발생하면 이 메시지를 전송할 끝점의 정렬된 컬렉션이 포함됩니다.  
  
 에 나열 된 기본 끝점에 전달 하는 경우는 `endpointName` 특성 [ \<추가 >](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-entries.md) 라우팅 서비스는이 첫 번째 끝점에 메시지를 보내려고 시도 실패 통신 예외가 발생 하 고, 구성 섹션입니다. 이것도 통신 예외가 발생하여 실패하는 경우 라우팅 서비스는 보내기가 성공할 때까지, 통신 예외가 아닌 다른 원인으로 보내기가 실패할 때까지 또는 컬렉션의 모든 끝점에 대한 보내기가 실패할 때까지 이 섹션에 포함된 다음 끝점으로 메시지를 보내려고 시도합니다.  
  
 다음 예제에서는 "Destination" 이라는 기본 끝점으로 보내기 통신 예외가 반환 하는 경우 서비스를 "alternateservicequeue"로 메시지를 보내려고 시도 합니다. 이 시도에 대해서도 통신 예외가 반환되면 라우팅 서비스는 컬렉션의 다음 끝점으로 메시지를 보내려고 시도합니다.  
  
```xml  
<filterTables>  
     <filterTable name="filterTable1">  
          <add filterName="MatchAllFilter1" endpointName="Destination" backupList="backupEndpointList"/>  
     </filterTable>  
</filterTables>  
<backupLists>  
     <backupList name="backupEndpointList">  
          <add endpointName="backupServiceQueue" />  
          <add endpointName="alternateServiceQueue" />  
     </backupList>  
</backupLists>  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Routing.Configuration.BackupEndpointCollection?displayProperty=nameWithType>    
