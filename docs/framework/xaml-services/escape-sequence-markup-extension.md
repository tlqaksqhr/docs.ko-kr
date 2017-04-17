---
title: "{} Escape Sequence / Markup Extension | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "{}"
helpviewer_keywords: 
  - "XAML [XAML Services], quotation mark (")"
  - "{} escape sequence [XAML Services]"
  - "XAML [XAML Services], {} escape sequence"
  - "XAML [XAML Services], escape sequence"
  - "quotation mark (") [XAML Services]"
  - "escape sequence [XAML Services]"
ms.assetid: 3ce3e2ad-a868-43f9-9c98-b29561cb146e
caps.latest.revision: 21
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
---
# {} Escape Sequence / Markup Extension
특성 값의 XAML 이스케이프 시퀀스를 제공합니다.  이스케이프 시퀀스를 사용하면 특성 값에서 이스케이프 시퀀스 다음에 오는 값이 리터럴로 해석됩니다.  
  
## XAML 특성 사용  
  
```  
<object property="{} literalValue" .../>  
```  
  
## XAML 속성 요소 사용  
  
```  
<object>  
  <object.property>  
    {} literalValue  
  </object.property>  
</object>  
```  
  
## XAML 값  
  
|||  
|-|-|  
|*literalValue*|이스케이프 시퀀스 다음에 오는 리터럴 문자열입니다.  일반적으로 이 문자열에는 여는 또는 닫는 중괄호\({또는}\)가 포함됩니다.|  
  
## 설명  
 XAML에서 여는 중괄호\({\)를 리터럴 문자로 사용할 수 있도록 이스케이프 문자\({}\)가 사용됩니다.  
  
 XAML 판독기는 일반적으로 태그 확장의 진입점을 나타내기 위해 여는 괄호\({\)를 사용하지만, 먼저 다음 문자를 점검하여 닫는 괄호\(}\)인지 여부를 확인합니다.  두 개의 중괄호\({}\)가 인접한 경우에만 이스케이프 시퀀스로 간주됩니다.  
  
 이스케이프 시퀀스가 발생하는 경우 XAML 판독기에서 문자열의 나머지를 문자열로 처리해야 합니다.  그러나 형식 변환기가 있는 멤버에 이스케이프 시퀀스가 적용된 경우에는 XAML 작성기에서 해석할 때 문자열이 형식 변환기를 거쳐야 할 수 있습니다.  
  
 이스케이프 시퀀스는 태그 확장이 아니며 클래스에 기반하지 않습니다.  그러나, XAML 판독기\(사용자 지정 XAML 판독기 포함\)가 고려해야 하는 변환입니다.  
  
 따옴표를 이러한 방식으로 이스케이프 시퀀스로 사용할 수 없습니다.  콘텐츠가 아닌 속성에서 큰따옴표 문자를 속성 값으로 설정해야 한다면 속성 요소 구문을 사용하여 속성 요소 내부에 큰따옴표를 문자열로 배치하거나 XML 문자 엔터티를 사용합니다.  콘텐츠 속성의 경우에는 큰따옴표가 전체 콘텐츠가 될 수 있습니다.  
  
 이스케이프 시퀀스\({}\)는 대개 XAML 태그 확장이 나타나는 위치에 네임스페이스 한정자를 포함해야 하는 XML 형식을 지정하는 경우 필요합니다.  여기에는 XAML 특성 값의 시작 부분이 포함되며 태그 확장 내에서 등호\(\=\) 기호 바로 뒤에 올 수 있습니다.  다음 예제에서는 XAML 특성 값이 시작되는 곳에 나타나는 XML 네임스페이스에 대한 이스케이프 시퀀스를 보여 줍니다.  
  
 [!code-xml[XLINQExample#StackPanelResources](../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#stackpanelresources)]  
  
## 참고 항목  
 [Type Converters and Markup Extensions for XAML](../../../docs/framework/xaml-services/type-converters-and-markup-extensions-for-xaml.md)   
 [XML Character Entities and XAML](../../../docs/framework/xaml-services/xml-character-entities-and-xaml.md)