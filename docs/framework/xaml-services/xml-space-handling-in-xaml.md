---
title: "xml:space Handling in XAML | Microsoft Docs"
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
  - "XAML [XAML Services], xml:space attribute"
  - "XAML [XAML Services], whitespace processing"
  - "xml:space attribute [XAML Services]"
  - "whitespace processing [XAML Services]"
ms.assetid: 5e1814f0-5b30-43d5-8c88-dede335a89d7
caps.latest.revision: 15
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 15
---
# xml:space Handling in XAML
`xml:space` 특성은 개체 요소 내에 중요한 공백 처리 동작을 선언하는 XML 정의 특성입니다.  이 동작은 `xml:space`이 선언된 요소 내에 포함된 모든 콘텐츠\(내부 텍스트\)와 관련이 있으며 자식 요소도 범위에 포함됩니다.  
  
## XAML 특성 사용  
  
```  
<object xml:space="preserve" />  
```  
  
 \-또는\-  
  
```  
<object xml:space="default" />  
```  
  
## 설명  
 XAML의 `xml:space` 특성 및 이 특성의 가능한 두 값에 대한 정의는 XML에 대한 W3C 사양에서 "특수 특성"으로 정의된 `xml:space`에서 파생됩니다.  
  
 `xml:space` 특성의 기본값은 리터럴 값 `"default"`입니다.  `"default"` 값을 사용하거나 `xml:space`를 지정하지 않은 경우에는 [Whitespace Processing in XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md) 항목에 정의되어 있는 유효한 공백 구문 분석 동작이 기본 처리 동작입니다.  
  
 개체 요소 콘텐츠 내에서 공백을 유지하려면 해당 개체 요소에서 `xml:space="preserve"`를 지정합니다.  
  
 대부분의 해석에서는 `xml:space` 특성 효과 및 특성의 값은 자식 요소로 범위가 지정됩니다.  
  
 XAML에서 공백 처리에 대한 자세한 설명은 [Whitespace Processing in XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md)를 참조하십시오.  
  
## 참고 항목  
 [Whitespace Processing in XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md)   
 [XAML 개요\(WPF\)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)