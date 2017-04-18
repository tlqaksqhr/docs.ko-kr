---
title: "1025 - BookmarkScopeInitialized | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 63584434-e709-471d-9e96-97d3d99e70d6
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 1025 - BookmarkScopeInitialized
## 속성  
  
|||  
|-|-|  
|ID|1025|  
|키워드|WFRuntime|  
|수준|Verbose|  
|채널|Microsoft\-Windows\-응용 프로그램 서버\-응용 프로그램\/디버그|  
  
## 설명  
 BookmarkScope가 초기화되었음을 나타냅니다.  
  
## 메시지  
 TemporaryId: '%1'인 BookmarkScope가 Id: '%2'\(으\)로 초기화되었습니다.  
  
## 설명  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|---------------|---------------|--------|  
|TemporaryId|xs:string|책갈피의 임시 ID입니다.|  
|InitializedId|xs:string|책갈피의 초기화된 ID입니다.|  
|AppDomain|xs:string|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|