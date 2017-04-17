---
title: "1035 - RuntimeTransactionSet | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 03b37de9-778c-4beb-b0e3-de73ece6088e
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 1035 - RuntimeTransactionSet
## 속성  
  
|||  
|-|-|  
|ID|1035|  
|키워드|WFRuntime|  
|수준|Verbose|  
|채널|Microsoft\-Windows\-응용 프로그램 서버\-응용 프로그램\/디버그|  
  
## 설명  
 작업이 런타임 트랜잭션으로 설정되었음을 나타냅니다.  
  
## 메시지  
 런타임 트랜잭션이 작업 '%1', DisplayName: '%2', InstanceId: '%3'\(으\)로 설정되었습니다. 작업 '%4', DisplayName: '%5', InstanceId: '%6'\(으\)로 실행이 격리되었습니다.  
  
## 설명  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|---------------|---------------|--------|  
|동작|xs:string|작업의 형식 이름입니다.|  
|DisplayName|xs:string|작업의 표시 이름입니다.|  
|InstanceId|xs:string|작업의 인스턴스 ID입니다.|  
|IsolatedActivity|xs:string|트랜잭션이 격리된 작업의 형식 이름입니다.|  
|IsolatedActivityDisplayName|xs:string|트랜잭션이 격리된 작업의 표시 이름입니다.|  
|IsolatedActivityInstanceId|xs:string|트랜잭션이 격리된 작업의 인스턴스 ID입니다.|  
|AppDomain|xs:string|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|