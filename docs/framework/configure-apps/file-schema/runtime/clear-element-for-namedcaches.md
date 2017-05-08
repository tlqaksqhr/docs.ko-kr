---
title: "&lt;namedCaches&gt;에 대한 &lt;clear&gt; 요소 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<namedCaches>에 대한 <clear> 요소"
  - "<namedCaches>에 대한 clear 요소"
ms.assetid: ea01a858-65da-4348-800f-5e3df59d4d79
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 11
---
# &lt;namedCaches&gt;에 대한 &lt;clear&gt; 요소
메모리 캐시에 대한 `namedCaches` 컬렉션의 모든 `namedCache` 항목을 지웁니다.  
  
## 구문  
  
```  
<namedCaches>  
    <clear name="default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## 형식  
 `Type`  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
 `None`  
  
### 자식 요소  
 `None`  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<namedCaches\>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|명명된 <xref:System.Runtime.Caching.MemoryCache> 인스턴스의 구성 설정 컬렉션을 포함합니다.|  
  
## 설명  
 `clear` 요소는 메모리 캐시에 대한 명명된 캐시 컬렉션에서 모든 `namedCache` 항목을 지웁니다.  컬렉션에 다른 명명된 캐시가 없는지 확인하기 위해 새로운 명명된 캐시 항목을 추가하기 위해 `add` 요소를 사용하기 전에 `clear` 요소를 사용할 수 있습니다.  
  
## 참고 항목  
 [\<namedCaches\> 요소\(캐시 설정\)](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)