---
title: "방법: Windows Forms 컨트롤에서 특성 적용 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "특성[Windows Forms], 적용"
  - "컨트롤[Windows Forms], 특성 적용"
  - "Windows Forms 컨트롤, 특성 적용"
ms.assetid: af0a3f7f-155b-4ba1-83c4-9cf721331a06
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# 방법: Windows Forms 컨트롤에서 특성 적용
디자인 환경과 올바르게 상호 작용하고 런타임에 올바르게 실행되는 구성 요소 및 컨트롤을 개발하려면 클래스와 멤버에 특성을 올바르게 적용해야 합니다.  
  
## 예제  
 다음 코드 예제에서는 사용자 지정 컨트롤에 여러 가지 특성을 사용하는 방법을 보여 줍니다.  사용된 컨트롤에서는 간단한 로깅 기능을 보여 줍니다.  해당 컨트롤이 데이터 소스에 바인딩되면 <xref:System.Windows.Forms.DataGridView> 컨트롤의 데이터 소스에서 보낸 값을 표시합니다.  이 값이 `Threshold` 속성에 의해 지정된 값을 초과하면 `ThresholdExceeded` 이벤트가 발생됩니다.  
  
 `AttributesDemoControl`은 `LogEntry` 클래스로 값을 기록합니다.  `LogEntry` 클래스는 템플릿 클래스이며 기록하는 형식으로 매개 변수화됩니다.  예를 들어, `AttributesDemoControl`이 `float` 형식의 값을 기록하는 경우 다음과 같이 각 `LogEntry` 인스턴스가 선언되고 사용됩니다.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#110](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#110)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#110](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#110)]  
  
> [!NOTE]
>  `LogEntry`는 임의의 형식에 의해 매개 변수화되므로 매개 변수 형식에서 동작하려면 리플렉션을 사용해야 합니다.  임계값 기능이 동작하려면 매개 변수 형식 `T`에서 <xref:System.IComparable> 인터페이스를 구현해야 합니다.  
  
 `AttributesDemoControl`을 호스팅하는 폼은 성능 카운터를 정기적으로 쿼리합니다.  각 값은 적절한 형식의 `LogEntry`에 패키지되며 폼의 <xref:System.Windows.Forms.BindingSource>에 추가됩니다.  `AttributesDemoControl`은 해당 데이터 바인딩을 통해 값을 받으며 <xref:System.Windows.Forms.DataGridView> 컨트롤에 해당 값을 표시합니다.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#1)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#1)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#100)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#100)]  
  
 첫 번째 코드 예제에서는 `AttributesDemoControl`을 구현합니다.  두 번째 코드 예제에서는 `AttributesDemoControl`을 사용하는 폼을 보여 줍니다.  
  
## 클래스 수준 특성  
 일부 특성은 클래스 수준에서 적용됩니다.  다음 코드 예제에서는 Windows Forms 컨트롤에 일반적으로 적용되는 특성을 보여 줍니다.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#20)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#20)]  
  
### TypeConverter 특성  
 <xref:System.ComponentModel.TypeConverterAttribute>는 일반적으로 사용되는 클래스 수준 특성입니다.  다음 코드 예제에서는 `LogEntry` 클래스에 대해 이 특성을 사용하는 방법을 보여 줍니다.  또한 이 예제에서는 `LogEntry` 형식에 대해 `LogEntryTypeConverter`라는 <xref:System.ComponentModel.TypeConverter>를 구현하는 방법도 보여 줍니다.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#5)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#5)]  
  
## 멤버 수준 특성  
 일부 특성은 멤버 수준에서 적용됩니다.  다음 코드 예제에서는 Windows Forms 컨트롤의 속성에 일반적으로 적용되는 일부 특성을 보여 줍니다.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#21)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#21)]  
  
### AmbientValue 특성  
 다음 예제에서는 <xref:System.ComponentModel.AmbientValueAttribute>를 보여 주고 디자인 환경과의 상호 작용을 지원하는 코드를 보여 줍니다.  이러한 상호 작용을 *앰비언스*라고 합니다.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#23](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#23)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#23](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#23)]  
  
### 데이터 바인딩 특성  
 다음 예제에서는 복합 데이터 바인딩의 구현을 보여 줍니다.  위에서 볼 수 있는 클래스 수준의 <xref:System.ComponentModel.ComplexBindingPropertiesAttribute>는 데이터 바인딩에 사용할 `DataSource` 및 `DataMember` 속성을 지정합니다.  <xref:System.ComponentModel.AttributeProviderAttribute>는 `DataSource` 속성이 바인딩될 형식을 지정합니다.  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#25](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#25)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#25](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#25)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#26](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#26)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#26](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#26)]  
  
## 코드 컴파일  
  
-   `AttributesDemoControl`을 호스팅하는 폼에는 빌드를 위해 `AttributesDemoControl` 어셈블리에 대한 참조가 필요합니다.  
  
## 참고 항목  
 <xref:System.IComparable>   
 <xref:System.Windows.Forms.DataGridView>   
 [.NET Framework에서 사용자 지정 Windows Forms 컨트롤 개발](../../../../docs/framework/winforms/controls/developing-custom-windows-forms-controls.md)   
 [Windows Forms 컨트롤의 특성](../../../../docs/framework/winforms/controls/attributes-in-windows-forms-controls.md)   
 [How to: Serialize Collections of Standard Types with the DesignerSerializationVisibilityAttribute](../Topic/How%20to:%20Serialize%20Collections%20of%20Standard%20Types%20with%20the%20DesignerSerializationVisibilityAttribute.md)