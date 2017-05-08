---
title: "3507 - ServiceEndpointAdded | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c068fc0e-07ee-4551-9824-ea7216e1fe37
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 3507 - ServiceEndpointAdded
## 속성  
  
|||  
|-|-|  
|ID|3507|  
|키워드|WFServices|  
|수준|정보|  
|채널|Microsoft\-Windows\-응용 프로그램 서버\-응용 프로그램\/분석|  
  
## 설명  
 서비스 끝점이 추가되었음을 나타냅니다.  
  
## 메시지  
 주소 '%1', 바인딩 '%2' 및 계약 '%3'에 대해 서비스 끝점이 추가되었습니다.  
  
## 설명  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|---------------|---------------|--------|  
|Address|xs:string|끝점의 주소입니다.|  
|바인딩|xs:string|끝점의 바인딩입니다.|  
|계약|xs:string|끝점의 계약입니다.|  
|AppDomain|xs:string|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|