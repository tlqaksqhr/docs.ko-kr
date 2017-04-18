---
title: "WSAT_TraceRecord | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 99bc7f66-1335-40d8-aa68-e754d569dc0d
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# WSAT_TraceRecord
WSAT\_TraceRecord  
  
## 구문  
  
```  
class WSAT_TraceRecord : WSAT_TraceEvent  
{  
  object ActivityID;  
  sint32 EventID;  
  string TraceRecord;  
};  
```  
  
## 메서드  
 WSAT\_TraceRecord 클래스는 메서드를 정의하지 않습니다.  
  
## 속성  
 WSAT\_TraceRecord 클래스에는 다음과 같은 속성이 있습니다.  
  
### ActivityID  
 데이터 형식: object  
액세스 형식: 읽기 전용  
  
 추적 레코드의 동작 ID입니다.  
  
### EventID  
 데이터 형식: sint32  
액세스 형식: 읽기 전용  
  
 추적 레코드의 이벤트 ID입니다.  
  
### TraceRecord  
 데이터 형식: string  
액세스 형식: 읽기 전용  
  
 추적 레코드  
  
## 요구 사항  
  
|MOF|Servicemodel.mof에 선언되어 있습니다.|  
|---------|----------------------------------|  
|네임스페이스|root\\ServiceModel에 정의되어 있습니다.|