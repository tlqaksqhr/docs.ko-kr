---
title: "IEnumRAWINPUTDEVIC:Skip | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Skip 메서드"
ms.assetid: c967b0f8-1c6a-459c-8c16-d4f08918ab65
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# IEnumRAWINPUTDEVIC:Skip
[IEnumRAWINPUTDEVIC:Next](../../../../docs/framework/wpf/app-development/ienumrawinputdevic-next.md)에 대한 다음 호출이 해당 요소를 반환하지 않도록 열거형의 다음 `celt` 요소를 건너뛸 것을 열거자에 지시합니다.  
  
## 구문  
  
```  
HRESULT Skip( [in] ULONG celt);  
```  
  
#### 매개 변수  
 `celt`  
  
 \[in\] 건너뛸 요소의 수입니다.  
  
## 속성 값\/반환 값  
 HRESULT: 제공된 요소 수가 `celt`이면 S\_OK이고, 그렇지 않으면 S\_FALSE입니다.