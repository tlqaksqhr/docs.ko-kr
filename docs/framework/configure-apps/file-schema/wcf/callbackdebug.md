---
title: "&lt;callbackDebug&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4073feda-1857-4be4-9947-227afb847ced
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# &lt;callbackDebug&gt;
[!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 콜백 개체의 서비스 디버깅을 지정합니다.  
  
## 구문  
  
```  
  
<callbackDebug  includeExceptionDetailInFaults="Boolean" />  
```  
  
## 형식  
 `Type`  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|`includeExceptionDetailInFaults`|클라이언트 콜백 개체가 관리되는 예외 정보를 SOAP 오류의 형태로 서비스에 반환하는지 여부를 지정하는 값입니다.<br /><br /> 이 특성을 프로그래밍 방식으로 `true`로 설정한 경우 클라이언트 콜백 개체에 있는 관리되는 예외 정보 흐름을 디버깅을 위해 다시 서비스로 이동하게 할 수 있습니다. **Caution:**  관리되는 예외 정보를 클라이언트에 반환하면 보안상 위험할 수 있습니다.  예외 정보가 내부 서비스 구현 정보를 공개하여 권한 없는 클라이언트에서 이를 사용할 수 있기 때문입니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<behavior\>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|끝점 동작을 지정합니다.|  
  
## 참고 항목  
 <xref:System.ServiceModel.Configuration.CallbackDebugElement>   
 <xref:System.ServiceModel.Description.CallbackDebugBehavior>