---
title: "방법: TextBox 텍스트의 소스를 업데이트하는 시점 제어 | Microsoft Docs"
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
  - "데이터 바인딩(data binding), 소스 업데이트 타이밍"
  - "소스 업데이트, 타이밍"
  - "소스 업데이트 타이밍"
ms.assetid: ffb7b96a-351d-4c68-81e7-054033781c64
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# 방법: TextBox 텍스트의 소스를 업데이트하는 시점 제어
이 항목에서는 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 속성을 사용하여 [바인딩 소스](GTMT) 업데이트의 타이밍을 제어하는 방법을 설명합니다.  이 항목에서는 <xref:System.Windows.Controls.TextBox> 컨트롤을 예제로 사용합니다.  
  
## 예제  
 <xref:System.Windows.Controls.TextBox>.<xref:System.Windows.Controls.TextBox.Text%2A> 속성에는 <xref:System.Windows.Data.UpdateSourceTrigger>의 기본 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 값이 있습니다.  이는 응용 프로그램에 데이터 바인딩된 <xref:System.Windows.Controls.TextBox>.<xref:System.Windows.Controls.TextBox.Text%2A> 속성이 있는 <xref:System.Windows.Controls.TextBox>가 있는 경우 <xref:System.Windows.Controls.TextBox>에 입력한 텍스트는 <xref:System.Windows.Controls.TextBox>에서 포커스를 잃을 때까지\(예: <xref:System.Windows.Controls.TextBox> 바깥쪽을 누르는 경우\) 소스를 업데이트하지 않음을 의미합니다.  
  
 입력할 때 소스가 업데이트되도록 하려면 바인딩의 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>를 <xref:System.Windows.Data.UpdateSourceTrigger>로 설정합니다.  다음 예제에서는 <xref:System.Windows.Controls.TextBox>와 <xref:System.Windows.Controls.TextBlock> 둘 다에 대한 `Text` 속성이 같은 소스 속성에 바인딩됩니다.  <xref:System.Windows.Controls.TextBox> 바인딩의 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 속성은 <xref:System.Windows.Data.UpdateSourceTrigger>로 설정됩니다.  
  
 [!code-xml[SimpleBinding#USTHowTo](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml#usthowto)]  
  
 따라서 다음 샘플의 스크린샷에서 설명한 대로 <xref:System.Windows.Controls.TextBlock>에는 사용자가 <xref:System.Windows.Controls.TextBox>에 텍스트를 입력할 때와 같은 텍스트\(소스가 변경되므로\)가 표시됩니다.  
  
 ![간단한 데이터 바인딩 샘플 스크린 샷](../../../../docs/framework/wpf/data/media/databindingsimplebindingsample2.png "DataBindingSimpleBindingSample2")  
  
 대화 상자나 사용자 입력 가능한 폼에 사용자가 필드 편집을 마치고 "확인"을 클릭할 때까지 소스 업데이트를 지연하려는 경우 다음 예제와 같이 바인딩의 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 값을 <xref:System.Windows.Data.UpdateSourceTrigger>로 설정할 수 있습니다.  
  
 [!code-xml[UpdateSource#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UpdateSource/CSharp/Window1.xaml#2)]  
  
 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 값을 <xref:System.Windows.Data.UpdateSourceTrigger>로 설정하면 응용 프로그램에서 <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> 메서드를 호출할 때만 소스 값이 변경됩니다.  다음 예제에서는 `itemNameTextBox`의 <xref:System.Windows.Data.BindingExpression.UpdateSource%2A>를 호출하는 방법을 보여 줍니다.  
  
 [!code-csharp[UpdateSource#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UpdateSource/CSharp/Window1.xaml.cs#1)]
 [!code-vb[UpdateSource#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UpdateSource/VisualBasic/Window1.xaml.vb#1)]  
  
> [!NOTE]
>  다른 컨트롤의 속성에 대해 동일한 기법을 사용할 수 있지만 대부분의 다른 속성은 <xref:System.Windows.Data.UpdateSourceTrigger>의 기본 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 값을 갖습니다.  자세한 내용은 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 속성 페이지를 참조하십시오.  
  
> [!NOTE]
>  <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 속성은 소스 업데이트를 처리하므로 <xref:System.Windows.Data.BindingMode> 또는 <xref:System.Windows.Data.BindingMode> 바인딩에 대해서만 관련이 있습니다.  <xref:System.Windows.Data.BindingMode> 및 <xref:System.Windows.Data.BindingMode> 바인딩이 작동하려면 소스 개체에서 속성 변경 알림을 제공해야 합니다.  자세한 내용은 이 항목에 표시된 샘플을 참조하십시오.  또한 [속성 변경 알림 구현](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md)을 참조할 수 있습니다.  
  
## 참고 항목  
 [방법 항목](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)