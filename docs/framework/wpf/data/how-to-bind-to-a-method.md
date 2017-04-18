---
title: "방법: 메서드 바인딩 | Microsoft Docs"
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
  - "바인딩, 메서드에"
  - "클래스, ObjectDataProvider"
  - "데이터 바인딩(data binding), ObjectDataProvider를 사용하여 메서드에 바인딩"
  - "메서드, 바인딩"
  - "ObjectDataProvider 클래스"
ms.assetid: 5f55e71e-2182-42a0-88d1-700cc1427a7a
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 방법: 메서드 바인딩
다음 예제에서는 <xref:System.Windows.Data.ObjectDataProvider>를 사용하여 메서드를 바인딩하는 방법을 보여 줍니다.  
  
## 예제  
 이 예제에서 `TemperatureScale`은 `ConvertTemp`라는 메서드를 갖는 클래스입니다. 이 메서드는 두 개의 매개 변수\(`double` 형식과 `enum` 형식의 `TempType)`를 사용하고 지정된 값을 한 온도계에서 다른 온도계로 변환합니다.  다음 예제에서는 <xref:System.Windows.Data.ObjectDataProvider>를 사용하여 `TemperatureScale`을 인스턴스화합니다.  `ConvertTemp` 메서드는 두 개의 지정된 매개 변수를 호출합니다.  
  
 [!code-xml[BindToMethod#WindowResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToMethod/CS/Window1.xaml#windowresources)]  
  
 메서드를 리소스로 사용할 수 있으므로 해당 결과에 바인딩할 수 있습니다.  다음 예제에서는 <xref:System.Windows.Controls.TextBox>의 <xref:System.Windows.Controls.TextBox.Text%2A> 속성 및 <xref:System.Windows.Controls.ComboBox>의 <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> 속성을 메서드의 두 매개 변수에 바인딩합니다.  이렇게 하면 사용자가 변환할 온도와 변환할 온도계를 지정할 수 있습니다.  <xref:System.Windows.Data.ObjectDataProvider>로 래핑되는\(`TemperatureScale` 개체\) 개체의 속성이 아니라 <xref:System.Windows.Data.ObjectDataProvider> 인스턴스의 <xref:System.Windows.Data.ObjectDataProvider.MethodParameters%2A> 속성에 바딩인하므로 <xref:System.Windows.Data.Binding.BindsDirectlyToSource%2A>는 `true`로 설정됩니다.  
  
 사용자가 <xref:System.Windows.Controls.TextBox>나 선택한 <xref:System.Windows.Controls.ComboBox>의 내용을 수정하면 마지막 <xref:System.Windows.Controls.Label>의 <xref:System.Windows.Controls.ContentControl.Content%2A>가 업데이트됩니다.  
  
 [!code-xml[BindToMethod#UI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToMethod/CS/Window1.xaml#ui)]  
  
 변환기 `DoubleToString`은 <xref:System.Windows.Data.IValueConverter.Convert%2A> 방향\([바인딩 소스](GTMT)를 [b바인딩 대상](GTMT)으로, 후자는 <xref:System.Windows.Controls.TextBox.Text%2A> 속성임\)에서는 double를 string으로 변환하고 <xref:System.Windows.Data.IValueConverter.ConvertBack%2A> 방향에서는 `string`을 `double`로 변환합니다.  
  
 `InvalidationCharacterRule`은 잘못된 문자가 있는지 검사하는 <xref:System.Windows.Controls.ValidationRule>입니다.  입력 값이 double 값이 아니면 <xref:System.Windows.Controls.TextBox> 주위의 빨간 테두리인 기본 오류 템플릿이 표시되어 사용자에게 알려 줍니다.  
  
## 참고 항목  
 [방법 항목](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)   
 [열거형 바인딩](../../../../docs/framework/wpf/data/how-to-bind-to-an-enumeration.md)