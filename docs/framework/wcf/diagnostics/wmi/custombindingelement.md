---
title: "CustomBindingElement | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: df959dc5-1aef-4338-a123-6ff3e7bc37af
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# CustomBindingElement
CustomBindingElement  
  
## 구문  
  
```  
class CustomBindingElement : BindingElement  
{  
  string Name;  
};  
```  
  
## 메서드  
 CustomBindingElement 클래스는 메서드를 정의하지 않습니다.  
  
## 속성  
 CustomBindingElement 클래스에는 다음과 같은 속성이 있습니다.  
  
### 이름  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 바인딩의 구성 이름을 포함하는 문자열입니다.  이 값은 사용자 지정 바인딩의 식별 문자열 역할을 하는 사용자 정의 문자열입니다.  
  
## 요구 사항  
  
|MOF|Servicemodel.mof에 선언되어 있습니다.|  
|---------|----------------------------------|  
|네임스페이스|root\\ServiceModel에 정의되어 있습니다.|  
  
## 참고 항목  
 <xref:System.ServiceModel.Channels.CustomBinding>