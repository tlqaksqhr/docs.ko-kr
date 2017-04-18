---
title: "방법: Windows Forms BindingSource를 사용하여 항목 추가 사용자 지정 | Microsoft Docs"
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
  - "컨트롤[Windows Forms], 새 항목 만들기"
  - "BindingSource 구성 요소[Windows Forms], 항목 추가 사용자 지정"
  - "예제[Windows Forms], BindingSource 구성 요소"
  - "BindingSource 구성 요소[Windows Forms], 예제"
ms.assetid: 1aae11fc-6fb2-4cb9-b3d0-e0638fe77ef0
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# 방법: Windows Forms BindingSource를 사용하여 항목 추가 사용자 지정
<xref:System.Windows.Forms.BindingSource> 구성 요소를 사용하여 Windows Forms 컨트롤을 데이터 소스에 바인딩하는 경우 새 항목의 생성을 사용자 지정해야 할 수도 있습니다.<xref:System.Windows.Forms.BindingSource> 구성 요소는 일반적으로 바인딩된 컨트롤이 새 항목을 만들어야 할 때 발생하는 <xref:System.Windows.Forms.BindingSource.AddingNew> 이벤트를 제공하여 이 작업을 간소화합니다. 이벤트 처리기에서 필요한 사용자 지정 동작\(예: 웹 서비스에 대해 메서드 호출 또는 클래스 팩터리에서 새 개체 가져오기\)을 제공할 수 있습니다.  
  
> [!NOTE]
>  <xref:System.Windows.Forms.BindingSource.AddingNew> 이벤트를 처리하여 항목을 추가하는 경우 추가 작업을 취소할 수 없습니다.  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.Forms.BindingSource> 구성 요소를 사용하여 <xref:System.Windows.Forms.DataGridView> 컨트롤을 클래스 팩터리에 바인딩하는 방법을 보여 줍니다. 사용자가 <xref:System.Windows.Forms.DataGridView> 컨트롤의 새 행을 클릭하면 <xref:System.Windows.Forms.BindingSource.AddingNew> 이벤트가 발생합니다. 이벤트 처리기에서 `DemoCustomer` 개체를 새로 만들고 <xref:System.ComponentModel.AddingNewEventArgs.NewObject%2A?displayProperty=fullName> 속성에 개체가 할당됩니다. 그러면 새 `DemoCustomer` 개체가 <xref:System.Windows.Forms.BindingSource> 구성 요소의 목록에 추가되고 <xref:System.Windows.Forms.DataGridView> 컨트롤의 새 행에 표시됩니다.  
  
 [!code-cpp[System.Windows.Forms.DataConnector.AddingNew#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.AddingNew/CPP/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.DataConnector.AddingNew#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.AddingNew/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnector.AddingNew#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.AddingNew/VB/form1.vb#1)]  
  
## 코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   System, System.Data, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조  
  
 명령줄에서 [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] 또는 [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]용으로 이 예제를 빌드하는 방법에 대한 자세한 내용은 [명령줄에서 빌드](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) 또는 [csc.exe를 사용한 명령줄 빌드](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)를 참조하세요.[!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]에서 코드를 새 프로젝트에 붙여넣어 이 예제를 빌드할 수도 있습니다.[방법: Visual Studio를 사용하여 전체 Windows Forms 코드 예제 컴파일 및 실행](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))을 참조하세요.  
  
## 참고 항목  
 <xref:System.Windows.Forms.BindingNavigator>   
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.BindingSource>   
 [BindingSource 구성 요소](../../../../docs/framework/winforms/controls/bindingsource-component.md)   
 [방법: 형식에 Windows Forms 컨트롤 바인딩](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)