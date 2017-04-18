---
title: "방법: 바인딩 유효성 검사 구현 | Microsoft Docs"
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
  - "바인딩, 유효성 검사"
  - "데이터 바인딩(data binding), 바인딩 유효성 검사"
  - "바인딩 유효성 검사"
ms.assetid: eb98b33d-9866-49ae-b981-bc5ff20d607a
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# 방법: 바인딩 유효성 검사 구현
이 예제에서는 <xref:System.Windows.Controls.Validation.ErrorTemplate%2A> 및 스타일 트리거를 사용하여 잘못된 값이 입력될 때 사용자 지정 유효성 검사 규칙을 기반으로 사용자에게 입력 내용이 잘못되었음을 알려 주는 시각적 피드백을 제공하는 방법을 보여 줍니다.  
  
## 예제  
 다음 예제에 나오는 <xref:System.Windows.Controls.TextBox>의 텍스트 콘텐츠는 `ods`라는 [바인딩 소스](GTMT) 개체의 `Age` 속성\(int 형식\)에 바인딩되어 있습니다.  여기에서는 `AgeRangeRule`이라는 유효성 검사 규칙을 사용하도록 바인딩이 설정되어 있으므로 사용자가 숫자가 아닌 문자 또는 21보다 작거나 130보다 큰 값을 입력하면 텍스트 상자 옆에 빨간색 느낌표가 나타나고 사용자가 텍스트 상자 위로 마우스를 이동하면 오류 메시지가 포함된 도구 설명이 나타납니다.  
  
 [!code-xml[BindValidation#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#2)]  
  
 다음 예제에서는 <xref:System.Windows.Controls.ValidationRule>에서 상속되고 <xref:System.Windows.Controls.ValidationRule.Validate%2A> 메서드를 재정의하는 `AgeRangeRule` 구현을 보여 줍니다.  Int32.Parse\(\) 메서드가 값에 호출되어 값에 잘못된 문자가 포함되어 있지 않은지 확인합니다.  <xref:System.Windows.Controls.ValidationRule.Validate%2A> 메서드가 구문 분석 중 예외가 catch되었는지 여부 및 연령 값이 하한 및 상한을 벗어나는지 여부에 따라 값이 유효한지를 나타내는 <xref:System.Windows.Controls.ValidationResult>를 반환합니다.  
  
 [!code-csharp[BindValidation#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/AgeRangeRule.cs#3)]  
  
 다음 예제에서는 사용자에게 유효성 검사 오류를 알려 주기 위해 빨간색 느낌표를 만드는 사용자 지정 <xref:System.Windows.Controls.ControlTemplate> `validationTemplate`을 보여 줍니다.  컨트롤 템플릿을 사용하여 컨트롤의 모양을 다시 정의합니다.  
  
 [!code-xml[BindValidation#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#4)]  
  
 앞의 예제에서 볼 수 있듯이 오류 메시지를 표시하는 <xref:System.Windows.Controls.ToolTip>은 `textBoxInError`라는 스타일을 사용하여 만들어집니다.  <xref:System.Windows.Controls.Validation.HasError%2A> 값이 `true`이면 트리거가 현재 <xref:System.Windows.Controls.TextBox>의 도구 설명을 첫 번째 유효성 검사 오류로 설정합니다.  <xref:System.Windows.Data.Binding.RelativeSource%2A>는 현재 요소를 참조하여 <xref:System.Windows.Data.RelativeSourceMode>로 설정됩니다.  
  
 [!code-xml[BindValidation#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindValidation/CSharp/Window1.xaml#5)]  
  
 전체 예제를 보려면 [Binding Validation 샘플](http://go.microsoft.com/fwlink/?LinkID=159972)을 참조하십시오.  
  
 사용자 지정 <xref:System.Windows.Controls.Validation.ErrorTemplate%2A>을 제공하지 않으면 유효성 검사 오류가 있을 때 사용자에게 시각적 피드백을 제공하기 위해 기본 오류 템플릿이 나타납니다.  자세한 내용은 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)에서 "데이터 유효성 검사"를 참조하십시오.  또한 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]는 바인딩 소스 속성 업데이트 중 throw된 예외를 catch하는 기본 제공 유효성 검사 규칙을 제공합니다.  자세한 내용은 <xref:System.Windows.Controls.ExceptionValidationRule>을 참조하십시오.  
  
## 참고 항목  
 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [방법 항목](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)