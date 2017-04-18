---
title: "XamlWriter.Save의 serialization 제한 | Microsoft Docs"
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
  - "XamlWriter.Save의 제한"
  - "XamlWriter.Save의 serialization 제한"
  - "XamlWriter.Save, serialization 제한"
ms.assetid: f86acc91-2b67-4039-8555-505734491d36
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# XamlWriter.Save의 serialization 제한
[!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] <xref:System.Windows.Markup.XamlWriter.Save%2A>를 사용하여 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 응용 프로그램의 콘텐츠를 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 파일로 serialize할 수 있습니다.  하지만 serialize하는 내용에 대해서는 몇 가지 제한에 주목해야 합니다.  이 항목에서는 이러한 제한과 몇 가지 일반적인 고려 사항에 대해 설명합니다.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="Run_Time__Not_Design_Time_Representation"></a>   
## 디자인 타임이 아닌 런타임 표현  
 <xref:System.Windows.Markup.XamlWriter.Save%2A>를 호출하여 serialize될 내용에 대한 기본 원칙은 결과가 런타임에 serialize될 개체의 표현이 된다는 것입니다.  원본 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일의 많은 디자인 타임 속성은 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]이 메모리 내 개체로 로드될 때 이미 최적화되거나 손실될 수 있으며 serialize하기 위해 <xref:System.Windows.Markup.XamlWriter.Save%2A>를 호출할 때 보존되지 않습니다.  serialize된 결과는 응용 프로그램의 생성된 논리 트리를 효과적으로 표현한 것이지만 이를 만들어낸 원본 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]일 필요는 없습니다.  이러한 문제 때문에 <xref:System.Windows.Markup.XamlWriter.Save%2A> serialization을 확장 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 디자인 화면의 일부로 사용하는 것이 매우 어렵습니다.  
  
<a name="Serialization_is_Self_Contained"></a>   
## Serialization은 독립적임  
 <xref:System.Windows.Markup.XamlWriter.Save%2A>의 serialize된 출력은 독립적입니다. serialize된 모든 내용은 단일 루트 요소가 있고 [!INCLUDE[TLA2#tla_uri#plural](../../../../includes/tla2sharptla-urisharpplural-md.md)] 이외의 외부 참조는 없이 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 단일 페이지 내에 포함되어 있습니다.   예를 들어 사용자 페이지에서 응용 프로그램 리소스의 리소스를 참조한 경우 이러한 리소스가 serialize되는 페이지의 구성 요소인 것처럼 나타납니다.  
  
<a name="Extension_References_are_Dereferenced"></a>   
## 확장 참조가 역참조됨  
 다양한 태그 확장 형식으로 생성된 개체에 대한 일반적인 참조\(예: `StaticResource` 또는 `Binding`\)는 serialization 프로세스에 의해 역참조됩니다.  이러한 참조는 런타임에 응용 프로그램에 의해 메모리 내 개체가 생성되었을 때 이미 역참조되었으며 <xref:System.Windows.Markup.XamlWriter.Save%2A> 논리는 원본 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]을 다시 방문하여 이러한 참조를 serialize된 출력으로 복원하지 않습니다.  따라서 데이터 바인딩되거나 리소스가 얻은 값은 런타임 표현에서 마지막으로 사용된 값이 되게 잠재적으로 고정하며 이러한 값을 로컬로 설정된 다른 값과 구분하는 제한되거나 간접적인 기능만 유지합니다.  이미지도 프로젝트에 있을 때 원본 소스 참조가 아니라 이미지에 대한 개체 참조로 serialize되며 원래 참조되었던 파일 이름이나 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]는 손실됩니다.  같은 페이지 내에 선언된 리소스도 리소스 컬렉션의 키로 보존되는 것이 아니라 참조되었던 지점으로 serialize된 것으로 표시됩니다.  
  
<a name="Event_Handling_is_Not_Preserved"></a>   
## 이벤트 처리가 보존되지 않음  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]을 통해 추가된 이벤트 처리기는 serialize될 때 보존되지 않습니다.  코드 숨김이 없고 관련 x:Code 메커니즘도 없는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에서는 런타임 프로시저 논리를 serialize할 수 없습니다.  Serialization은 독립적이며 논리 트리에 제한되므로 이벤트 처리기를 보존하는 기능이 없습니다.  따라서 이벤트 처리기 특성\(특성 자체와 처리기의 이름을 지정하는 문자열 값 모두\)이 출력 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에서 제거됩니다.  
  
<a name="Realistic_Scenarios_for_Use_of_XAMLWriter_Save"></a>   
## XAMLWriter.Save 사용에 대한 실제 시나리오  
 여기에 나열된 제한 사항이 상당히 실제적이지만 <xref:System.Windows.Markup.XamlWriter.Save%2A>를 사용하는 몇 가지 적절한 시나리오가 여전히 있습니다.  
  
-   벡터 및 그래픽 출력: 렌더링된 영역의 출력을 사용하여 다시 로드될 때 같은 벡터나 그래픽을 재현할 수 있습니다.  
  
-   서식있는 텍스트 및 유동 문서: 텍스트 및 텍스트 내 모든 요소 서식 지정 및 요소 포함은 출력에서 보존됩니다.  이는 클립보드 기능과 유사한 메커니즘에서 유용할 수 있습니다.  
  
-   비즈니스 개체 데이터 보존: [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 데이터와 같은 데이터를 사용자 지정 요소에 저장한 경우 비즈니스 개체에서 사용자 지정 생성자 및 참조별 속성 값에 대한 변환을 제공하는 등 기본 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 규칙을 따르는 경우 이러한 비즈니스 개체는 serialization을 통해서 적용될 수 있습니다.