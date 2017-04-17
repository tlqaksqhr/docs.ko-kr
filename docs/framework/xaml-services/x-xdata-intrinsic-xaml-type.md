---
title: "x:XData Intrinsic XAML Type | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "x:XData"
  - "XData"
  - "xXData"
helpviewer_keywords: 
  - "XAML [XAML Services], x:XData directive element"
  - "XData in XAML [XAML Services]"
  - "x:XData XAML directive element [XAML Services]"
ms.assetid: 7ce209c2-621b-4977-b643-565f7e663534
caps.latest.revision: 17
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 17
---
# x:XData Intrinsic XAML Type
XAML 프로덕션 내에서 XML 데이터 아일랜드를 배치할 수 있습니다.  `x:XData` 내의 XML 요소는 기본 XAML 네임스페이스 또는 기타 모든 XAML 네임스페이스의 일부인 듯이 XAML 프로세서로 처리되어서는 안 됩니다.  `x:XData`는 임의의 제대로 구성된 XML을 포함할 수 있습니다.  
  
## XAML 개체 요소 사용  
  
```  
<x:XData>  
  <elementDataRoot>  
    [elementData]  
  </elementDataRoot>  
</x:XData>  
```  
  
## XAML 값  
  
|||  
|-|-|  
|`elementDataRoot`|둘러싸인 데이터 아일랜드의 단일 루트 요소입니다.  대부분의 최종 소비자에 대해 단일 루트가 없는 XML은 유효하지 않은 것으로 간주됩니다.  특히 단일 루트는 `x:XData`가 WPF에 대한 XML 데이터 소스 또는 데이터 바인딩을 위해 XML 소스를 사용하는 다른 많은 기술로 사용되는 경우에 필요합니다.|  
|`[elementData]`|선택적 요소.  XML 데이터를 나타내는 XML입니다.  여러 요소를 요소 데이터로 포함할 수 있고 중첩된 요소를 다른 요소에 포함할 수 있지만 XML의 일반 규칙이 적용됩니다.|  
  
## 설명  
 `x:XData` 개체 내의 XML 요소는 데이터 내에 포함된 XMLDOM의 가능한 모든 네임스페이스 및 접두사를 다시 선언할 수 있습니다.  
  
 XML 데이터와 `x:XData` .NET Framework XAML 서비스에서는 <xref:System.Windows.Markup.XData> 클래스를 통해 내장 XAML 형식에 대한 프로그램 방식 액세스가 가능합니다.  
  
## WPF 사용 정보  
 `x:XData` 개체는 기본적으로 <xref:System.Windows.Data.XmlDataProvider>의 자식 요소로 사용되거나 <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=fullName> 속성의 자식 개체\(XAML에서는 일반적으로 속성 요소 구문으로 표현\)로 사용됩니다.  
  
 일반적으로 데이터는 데이터 아일랜드 내의 기반 XML 네임스페이스를 새 기본 XML 네임스페이스\(빈 문자열로 설정\)로 재정의해야 합니다.  이렇게 하면 데이터를 참조하고 바인딩하는 데 사용되는 <xref:System.Windows.Data.Binding.XPath%2A> 식에 접두사가 포함되는 것을 피할 수 있기 때문에 간단한 데이터 아일랜드의 경우 가장 쉬운 방법입니다.  좀 더 복잡한 데이터 아일랜드의 경우에는 데이터에 대해 접두사를 여러 개 정의하고 루트의 XML 네임스페이스에 대해 특정 접두사를 사용할 수 있습니다.  이 경우 모든 <xref:System.Windows.Data.Binding.XPath%2A> 식 참조는 적절한 네임스페이스 매핑 접두사를 포함해야 합니다.  자세한 내용은 [데이터 바인딩 개요](../../../ocs/framework/wpf/data/data-binding-overview.md)를 참조하십시오.  
  
 기술적으로 `x:XData`는 <xref:System.Xml.Serialization.IXmlSerializable> 형식의 모든 속성에 대해 콘텐츠로 사용할 수 있습니다.  하지만 주로 사용되는 구현은 <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=fullName>입니다.  
  
## 참고 항목  
 <xref:System.Windows.Data.XmlDataProvider>   
 [데이터 바인딩 개요](../../../ocs/framework/wpf/data/data-binding-overview.md)   
 [Binding 태그 확장](../../../ocs/framework/wpf/advanced/binding-markup-extension.md)