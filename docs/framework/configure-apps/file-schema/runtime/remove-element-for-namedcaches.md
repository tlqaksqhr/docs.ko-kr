---
title: "&lt;namedCaches&gt;에 대한 &lt;remove&gt; 요소 | Microsoft Docs"
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
  - "namedCaches에 대한 <remove> 요소"
  - "namedCaches에 대한 remove 요소"
ms.assetid: 24211ea5-163e-4fe5-aed8-004d8499760c
caps.latest.revision: 10
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 10
---
# &lt;namedCaches&gt;에 대한 &lt;remove&gt; 요소
메모리 캐시를 위해 `namedCaches` 컬렉션에서 명명된 캐시 항목을 제거합니다.  
  
## 구문  
  
```  
<namedCaches>  
    <remove name="default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## 형식  
 `None`  
  
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
 `remove` 요소는 메모리 캐시에 대한 명명된 캐시 컬렉션에서 `namedCache` 항목을 제거합니다.  
  
## 참고 항목  
 [\<namedCaches\> 요소\(캐시 설정\)](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)