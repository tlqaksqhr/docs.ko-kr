---
title: "1022 - StartBookmarkWorkItem | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4415fbdb-0329-4019-803f-aea66e75f3da
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# 1022 - StartBookmarkWorkItem
## 속성  
  
|||  
|-|-|  
|ID|1022|  
|키워드|WFRuntime|  
|수준|Verbose|  
|채널|Microsoft\-Windows\-응용 프로그램 서버\-응용 프로그램\/디버그|  
  
## 설명  
 BookmarkWorkItem이 실행을 시작했음을 나타냅니다.  
  
## 메시지  
 작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 BookmarkWorkItem의 실행을 시작합니다. BookmarkName: %4, BookmarkScope: %5.  
  
## 설명  
  
|데이터 항목 이름|데이터 항목 형식|설명|  
|---------------|---------------|--------|  
|동작|xs:string|작업의 형식 이름입니다.|  
|DisplayName|xs:string|작업의 표시 이름입니다.|  
|InstanceId|xs:string|작업의 인스턴스 ID입니다.|  
|BookmarkName|xs:string|책갈피 이름입니다.|  
|BookmarkScope|xs:string|책갈피의 범위입니다.|  
|AppDomain|xs:string|AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.|