---
title: "방법: 바인딩 방향 지정 | Microsoft Docs"
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
  - "바인딩 방향"
  - "데이터 바인딩(data binding), 바인딩 방향"
  - "바인딩 방향"
ms.assetid: 37334478-028b-4514-86c9-1420709f4818
caps.latest.revision: 21
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 20
---
# 방법: 바인딩 방향 지정
이 예제에서는 바인딩으로 [바인딩 대상](GTMT)\(대상\) 속성만 업데이트되는지, [바인딩 소스](GTMT)\(소스\) 속성만 업데이트되는지 아니면 대상 속성과 소스 속성이 모두 업데이트되는지 여부를 지정하는 방법을 보여 줍니다.  
  
## 예제  
 <xref:System.Windows.Data.Binding.Mode%2A> 속성을 사용하여 바인딩의 방향을 지정합니다.  다음 열거 목록에서는 바인딩 업데이트에 사용할 수 있는 옵션을 보여 줍니다.  
  
-   <xref:System.Windows.Data.BindingMode>는 대상 속성이나 소스 속성 중 하나가 변경될 때마다 대상 속성이나 소스 속성을 업데이트합니다.  
  
-   <xref:System.Windows.Data.BindingMode>는 소스 속성이 변경될 때 대상 속성을 업데이트합니다.  
  
-   <xref:System.Windows.Data.BindingMode>은 응용 프로그램이 시작되거나 <xref:System.Windows.FrameworkElement.DataContext%2A>가 변경될 때만 대상 속성을 업데이트합니다.  
  
-   <xref:System.Windows.Data.BindingMode>는 대상 속성이 변경될 때 소스 속성을 업데이트합니다.  
  
-   <xref:System.Windows.Data.BindingMode>는 대상 속성의 기본 <xref:System.Windows.Data.Binding.Mode%2A> 값이 사용되게 합니다.  
  
 자세한 내용은 <xref:System.Windows.Data.BindingMode> 열거형을 참조하십시오.  
  
 다음 예제에서는 <xref:System.Windows.Data.Binding.Mode%2A> 속성을 설정하는 방법을 보여 줍니다.  
  
 [!code-xml[DirectionalBinding#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#4)]  
  
 소스 변경 내용을 검색하려면\(<xref:System.Windows.Data.BindingMode> 및 <xref:System.Windows.Data.BindingMode> 바인딩에 적용 가능\) 소스에서 <xref:System.ComponentModel.INotifyPropertyChanged>와 같은 적절한 속성 변경 알림 메커니즘을 구현해야 합니다.  <xref:System.ComponentModel.INotifyPropertyChanged> 구현에 대한 예제를 보려면 [속성 변경 알림 구현](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md)을 참조하십시오.  
  
 <xref:System.Windows.Data.BindingMode> 또는 <xref:System.Windows.Data.BindingMode> 바인딩의 경우 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 속성을 설정하여 소스 업데이트의 타이밍을 제어할 수 있습니다.  자세한 내용은 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>를 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Data.Binding>   
 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [방법 항목](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)