---
title: "3502 - InferredOperationDescription | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6aebb614-3c72-4537-ba11-3cc7200ef1f1
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 3502 - InferredOperationDescription
## 속성  
  
|||  
|-|-|  
|ID|3502|  
|키워드|WFServices|  
|수준|정보|  
|채널|Microsoft\-Windows\-응용 프로그램 서버\-응용 프로그램\/분석|  
  
## 설명  
 OperationDescription이 WorkflowService에서 유추되었음을 나타냅니다.  
  
## 메시지  
 계약 '%2'에서 Name\='%1'인 OperationDescription이 WorkflowService에서 유추되었습니다.  IsOneWay\=%3.  
  
## 설명  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|---------------|---------------|--------|  
|OperationName|xs:string|작업의 이름입니다.|  
|ContractName|xs:string|계약 이름입니다.|  
|IsOneWay|xs:string|계약이 단방향인지 여부를 나타내는 True 또는 False입니다.|  
|AppDomain|xs:string|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|