---
title: "MustUnderstandBehavior | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 911ed04a-c4b8-4c72-a5c3-fc7b4e3b4348
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# MustUnderstandBehavior
MustUnderstandBehavior  
  
## 구문  
  
```  
class MustUnderstandBehavior : Behavior  
{  
  boolean ValidateMustUnderstand;  
};  
```  
  
## 메서드  
 MustUnderstandBehavior 클래스는 메서드를 정의하지 않습니다.  
  
## 속성  
 MustUnderstandBehavior 클래스에는 다음과 같은 속성이 있습니다.  
  
### ValidateMustUnderstand  
 데이터 형식: boolean  
  
 액세스 형식: 읽기 전용  
  
 이 속성이 `true`인 경우 처리되지 않은 `MustUnderstand` 특성이 있는 모든 SOAP 헤더로 인해 예외를 throw하는 동작이 발생합니다.  
  
## 요구 사항  
  
|MOF|Servicemodel.mof에 선언되어 있습니다.|  
|---------|----------------------------------|  
|네임스페이스|root\\ServiceModel에 정의되어 있습니다.|  
  
## 참고 항목  
 <xref:System.ServiceModel.Description.MustUnderstandBehavior>