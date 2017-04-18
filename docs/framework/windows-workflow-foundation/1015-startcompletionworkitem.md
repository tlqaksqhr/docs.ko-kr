---
title: "1015 - StartCompletionWorkItem | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 96fd1d4e-c5d0-46ad-8a71-4b4b49ac7262
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 1015 - StartCompletionWorkItem
## 속성  
  
|||  
|-|-|  
|ID|1015|  
|키워드|WFRuntime|  
|수준|Verbose|  
|채널|Microsoft\-Windows\-응용 프로그램 서버\-응용 프로그램\/디버그|  
  
## 설명  
 CompletionWorkItem이 실행을 시작했음을 나타냅니다.  
  
## 메시지  
 부모 작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 CompletionWorkItem의 실행을 시작합니다.  작업 '%4', DisplayName: '%5', InstanceId: '%6'이\(가\) 완료되었습니다.  
  
## 설명  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|---------------|---------------|--------|  
|ParentActivity|xs:string|부모 작업의 형식 이름입니다.|  
|ParentDisplayName|xs:string|부모 작업의 표시 이름입니다.|  
|ParentInstanceId|xs:string|부모 작업의 인스턴스 ID입니다.|  
|CompletedActivity|xs:string|완료된 작업의 형식 이름입니다.|  
|CompletedActivityDisplayName|xs:string|완료된 작업의 표시 이름입니다.|  
|CompletedActivityInstanceId|xs:string|완료된 작업의 인스턴스 ID입니다.|  
|AppDomain|xs:string|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|