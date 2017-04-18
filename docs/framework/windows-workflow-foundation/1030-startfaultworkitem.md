---
title: "1030 - StartFaultWorkItem | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e1601fb9-0bc6-4dbe-816f-f24914063d34
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 1030 - StartFaultWorkItem
## 속성  
  
|||  
|-|-|  
|ID|1030|  
|키워드|WFRuntime|  
|수준|Verbose|  
|채널|Microsoft\-Windows\-응용 프로그램 서버\-응용 프로그램\/디버그|  
  
## 설명  
 FaultWorkItem이 실행을 시작했음을 나타냅니다.  
  
## 메시지  
 작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 FaultWorkItem의 실행을 시작합니다. 작업 '%4', DisplayName: '%5', InstanceId: '%6'에서 예외가 전파되었습니다.  
  
## 설명  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|---------------|---------------|--------|  
|FaultActivity|xs:string|오류 작업의 형식 이름입니다.|  
|FaultActivityDisplayName|xs:string|오류 작업의 표시 이름입니다.|  
|FaultActivityInstanceId|xs:string|오류 작업의 인스턴스 ID입니다.|  
|ExceptionActivity|xs:string|예외를 throw한 작업의 형식 이름입니다.|  
|ExceptionActivityDisplayName|xs:string|예외를 throw한 작업의 표시 이름입니다.|  
|ExceptionActivityInstanceId|xs:string|예외를 throw한 작업의 인스턴스 ID입니다.|  
|예외|xs:string|예외에 대한 예외 정보|  
|AppDomain|xs:string|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|