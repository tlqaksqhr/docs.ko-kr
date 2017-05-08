---
title: "39458 - TrackingRecordTruncated | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5352f0eb-d571-454a-bab5-e2162888b218
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 39458 - TrackingRecordTruncated
## 속성  
  
|||  
|-|-|  
|ID|39458|  
|키워드|WFTracking|  
|수준|경고|  
|채널|Microsoft\-Windows\-응용 프로그램 서버\-응용 프로그램\/디버그|  
  
## 설명  
 추적 레코드가 잘렸음을 나타냅니다.  변수\/주석\/사용자 데이터가 제거되었습니다.  
  
## 메시지  
 잘린 추적 레코드 %1이\(가\) 공급자가 %2인 ETW 세션에 기록되었습니다.  변수\/주석\/사용자 데이터가 제거되었습니다.  
  
## 설명  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|---------------|---------------|--------|  
|RecordNumber|xs:string|추적 레코드 번호입니다.|  
|ProviderId|xs:string|ETW 공급자 ID입니다.|  
|AppDomain|xs:string|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|