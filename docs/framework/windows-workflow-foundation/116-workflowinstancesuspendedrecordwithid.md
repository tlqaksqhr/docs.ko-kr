---
title: 116 - WorkflowInstanceSuspendedRecordWithId
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 38232c03-6139-4494-a020-79bc83eb9dce
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6dc875721c323a48f5cc0b49e4ef0e7c167622b5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="116---workflowinstancesuspendedrecordwithid"></a>116 - WorkflowInstanceSuspendedRecordWithId
## <a name="properties"></a>속성  
  
|||  
|-|-|  
|ID|116|  
|키워드|HealthMonitoring, WFTracking|  
|수준|정보|  
|채널|Microsoft-Windows-응용 프로그램 서버-응용 프로그램/분석|  
  
## <a name="description"></a>설명  
 워크플로 인스턴스가 WorkflowInstanceSuspended Record를 내보내면 ETW 추적 참가자가 이 이벤트를 내보냅니다.  
  
## <a name="message"></a>메시지  
 TrackRecord = WorkflowInstanceSuspendedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, Reason = %5, Annotations = %6, ProfileName = %7, WorkflowDefinitionIdentity = %8  
  
## <a name="details"></a>설명  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|--------------------|--------------------|-----------------|  
|InstanceId|xs:GUID|워크플로의 인스턴스 ID|  
|RecordNumber|xs:long|내보낸 레코드의 시퀀스 번호|  
|EventTime|xs:dateTime|이벤트를 내보낸 시간(UTC)|  
|ActivityDefinitionId|xs:string|워크플로의 루트 활동 이름|  
|상태|xs:string|워크플로의 현재 상태|  
|주석|xs:string|이 이벤트에 추가된 주석입니다. 값 형식으로 xml 요소에 저장 됩니다 \<항목 >\< 항목 이름 = "annotationName" type = "> annotationValue\<항목/>\<항목/>입니다. 주석을 지정 하지 않으면 문자열을 포함 하는 경우 \<항목 / >입니다. ETW 이벤트 크기는 ETW 버퍼 크기 또는 ETW 이벤트의 최대 페이로드에 따라 제한됩니다. 이벤트 크기가 ETW 제한을 초과 하면 주석을 삭제 하 고 주석 값으로 바꿔 이벤트 잘립니다 경우 \<항목 >... \<항목/>입니다.|  
|ProfileName|xs:string|이 이벤트를 내보낸 이름 또는 추적 프로필|  
|WorkflowDefinitionIdentity|xs:string|워크플로 정의 ID입니다.|  
|AppDomain|xs:string|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|
