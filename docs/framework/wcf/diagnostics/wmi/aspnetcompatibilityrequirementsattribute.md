---
title: "AspNetCompatibilityRequirementsAttribute | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 00908a39-a21b-4029-bbb9-33e5a6ed25a7
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# AspNetCompatibilityRequirementsAttribute
AspNetCompatibilityRequirementsAttribute  
  
## 구문  
  
```  
class AspNetCompatibilityRequirementsAttribute : Behavior  
{  
  string RequirementsMode;  
};  
```  
  
## 메서드  
 AspNetCompatibilityRequirementsAttribute 클래스는 메서드를 정의하지 않습니다.  
  
## 속성  
 AspNetCompatibilityRequirementsAttribute 클래스에는 다음과 같은 속성이 있습니다.  
  
### RequirementsMode  
 데이터 형식: string  
  
 액세스 형식: 읽기 전용  
  
 Asp.Net 호환 모드가 활성화되었는지 여부를 나타냅니다.  
  
## 요구 사항  
  
|MOF|Servicemodel.mof에 선언되어 있습니다.|  
|---------|----------------------------------|  
|네임스페이스|root\\ServiceModel에 정의되어 있습니다.|  
  
## 참고 항목  
 <xref:System.ServiceModel.ServiceHostingEnvironment.AspNetCompatibilityEnabled%2A>