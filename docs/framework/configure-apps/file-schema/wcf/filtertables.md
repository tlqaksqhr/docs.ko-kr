---
title: '&lt;filterTables&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 41f1ac35-f559-473a-b2c3-8cc83a6a3831
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 05c8d3f5ce5a01e5a88f37fce43f3b4f8d260812
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltfiltertablesgt"></a>&lt;filterTables&gt;
필터가 일치할 때 메시지를 보내기 위한 라우팅 필터와 대상 끝점 간의 매핑을 포함하는 라우팅 테이블을 정의하기 위한 구성 섹션을 나타냅니다.  
  
 \<system.serviceModel >  
\<라우팅 >  
\<routingTables >  
  
## <a name="syntax"></a>구문  
  
```xml
   <routing>      <filterTables>        <filterTable name="String">          <entries>            <add backupList="String"                 endpointName="String"                  filterName="String"                  priority="Integer" />          </entries>        </table>      </routingTables></routing>  
```

## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
 없음  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<필터 >](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|필터가 일치할 때 메시지를 보내기 위한 라우팅 필터와 대상 끝점 간의 매핑을 포함하는 라우팅 테이블입니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<라우팅 >](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|라우팅 필터와 라우팅 테이블을 포함하는 구성 섹션입니다.|  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Routing.Configuration.RoutingSection?displayProperty=nameWithType>       
 <xref:System.ServiceModel.Routing.Configuration.FilterTableCollection?displayProperty=nameWithType>    
