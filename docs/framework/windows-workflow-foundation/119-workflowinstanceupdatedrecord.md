---
title: "119 - WorkflowInstanceUpdatedRecord | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 32485d0a-dcdb-45bc-b1e3-79fa9ad9439b
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# 119 - WorkflowInstanceUpdatedRecord
## 속성  
  
|||  
|-|-|  
|ID|119|  
|키워드|HealthMonitoring, WFTracking|  
|수준|정보|  
|채널|Microsoft\-Windows\-응용 프로그램 서버\-응용 프로그램\/분석|  
  
## 설명  
 워크플로 인스턴스가 업데이트되면 ETW 추적 참가자가 이 이벤트를 내보냅니다.  
  
## 메시지  
 TrackRecord\= WorkflowInstanceUpdatedRecord, InstanceID \= %1, RecordNumber \= %2, EventTime \= %3, ActivityDefinitionId \= %4, State \= %5, OriginalDefinitionIdentity \= %6, UpdatedDefinitionIdentity \= %7, Annotations \= %8, ProfileName \= %9  
  
## 설명  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|---------------|---------------|--------|  
|InstanceId|xs:GUID|워크플로의 인스턴스 ID|  
|RecordNumber|xs:long|내보낸 레코드의 시퀀스 번호|  
|EventTime|xs:dateTime|이벤트를 내보낸 시간\(UTC\)|  
|ActivityDefinitionId|xs:string|워크플로의 루트 활동 이름|  
|상태|xs:string|워크플로의 현재 상태|  
|OriginalDefinitionIdentity|xs:string|원래 워크플로 정의 ID입니다.|  
|UpdatedDefinitionIdentity|xs:string|업로드된 워크플로 정의 ID입니다.|  
|주석|xs:string|이 이벤트에 추가된 주석입니다.  값은 xml 요소에 \<items\>\< item name \= "annotationName" type\="System.String"\>annotationValue\<\/item\>\<\/items\> 형식으로 저장됩니다.  주석을 지정하지 않으면 문자열에 \<items\/\>가 포함됩니다.  ETW 이벤트 크기는 ETW 버퍼 크기 또는 ETW 이벤트의 최대 페이로드에 따라 제한됩니다.  이벤트 크기가 ETW 제한을 초과하면 주석을 삭제하고 주석 값을 \<items\>...\<\/items\>로 대체하여 이벤트를 자릅니다.|  
|ProfileName|xs:string|이 이벤트를 내보낸 이름 또는 추적 프로필|  
|WorkflowDefinitionIdentity|xs:string|워크플로 정의 ID입니다.|  
|AppDomain|xs:string|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|