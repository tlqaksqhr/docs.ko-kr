---
title: "&lt;제거&gt; 요소에 대 한 &lt;namedCaches&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- remove element for namedCaches
- <remove> element for namedCaches
ms.assetid: 24211ea5-163e-4fe5-aed8-004d8499760c
caps.latest.revision: "10"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 6170b59e87948225708c9e697cba1542d756d2f4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="ltremovegt-element-for-ltnamedcachesgt"></a>&lt;제거&gt; 요소에 대 한 &lt;namedCaches&gt;
메모리 캐시용으로 명명된 캐시 항목을 `namedCaches` 컬렉션에서 제거합니다.  
  
 \<system.runtime.caching >  
\<memoryCache >  
\<namedCaches >  
\<제거 >  
  
## <a name="syntax"></a>구문  
  
```xml  
<namedCaches>  
    <remove name="default" />  
    <!-- child elements -->  
 </namedCaches>  
```  
  
## <a name="type"></a>형식  
 `None`  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
 `None`  
  
### <a name="child-elements"></a>자식 요소  
 `None`  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<namedCaches>](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)|명명 된 구성 설정의 컬렉션을 포함 <xref:System.Runtime.Caching.MemoryCache> 인스턴스.|  
  
## <a name="remarks"></a>설명  
 `remove` 요소 제거는 `namedCache` 메모리 내 캐시에 대 한 명명 된 캐시 컬렉션의 항목입니다.  
  
## <a name="see-also"></a>참고 항목  
 [\<namedCaches > 요소 (캐시 설정)](../../../../../docs/framework/configure-apps/file-schema/runtime/namedcaches-element-cache-settings.md)
