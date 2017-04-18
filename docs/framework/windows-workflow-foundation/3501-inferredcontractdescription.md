---
title: "3501 - InferredContractDescription | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 21a70849-4fc0-41d2-b9a4-db5aa2acdf1a
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# 3501 - InferredContractDescription
## 속성  
  
|||  
|-|-|  
|ID|3501|  
|키워드|WFServices|  
|수준|정보|  
|채널|Microsoft\-Windows\-응용 프로그램 서버\-응용 프로그램\/분석|  
  
## 설명  
 ContractDescription이 WorkflowService에서 유추되었음을 나타냅니다.  
  
## 메시지  
 Name\='%1'이고 Namespace\='%2'인 ContractDescription이 WorkflowService에서 유추되었습니다.  
  
## 설명  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|---------------|---------------|--------|  
|이름|xs:string|ContractDescription의 이름입니다.|  
|네임스페이스|xs:string|ContractDescription의 네임스페이스입니다.|  
|AppDomain|xs:string|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|