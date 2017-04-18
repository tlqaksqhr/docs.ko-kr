---
title: "방법: 팩터리 개체에 Windows Forms 컨트롤 바인딩 | Microsoft Docs"
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
  - "BindingSource 구성 요소[Windows Forms], 팩터리 개체에 바인딩"
  - "BindingSource 구성 요소[Windows Forms], 예제"
  - "컨트롤[Windows Forms], 바인딩"
  - "팩터리 개체, 바인딩"
ms.assetid: 7d59af89-ff82-41d8-a48a-f1fbae788b0d
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# 방법: 팩터리 개체에 Windows Forms 컨트롤 바인딩
데이터와 상호 작용하는 컨트롤을 빌드하는 경우 때로는 다른 개체를 생성하는 개체나 메서드에 컨트롤을 바인딩할 필요가 있습니다.  이러한 개체나 메서드를 팩터리라고 합니다.  예를 들어 데이터 소스는 메모리 또는 형식의 개체가 아니라 메서드 호출의 반환 값일 수 있습니다.  소스가 컬렉션을 반환하는 한 컨트롤을 이러한 종류의 데이터 소스에 바인딩할 수 있습니다.  
  
 <xref:System.Windows.Forms.BindingSource> 컨트롤을 사용하여 컨트롤을 팩터리 개체에 쉽게 바인딩할 수 있습니다.  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.Forms.BindingSource> 컨트롤을 사용하여 <xref:System.Windows.Forms.DataGridView> 컨트롤을 팩터리 메서드에 바인딩하는 방법을 보여 줍니다.  팩터리 메서드는 이름이 `GetOrdersByCustomerId`이며, Northwind 데이터베이스에서 지정된 고객에 대한 모든 주문을 반환합니다.  
  
 [!code-cpp[System.Windows.Forms.DataConnector.BindToFactory#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindToFactory/CPP/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.DataConnector.BindToFactory#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindToFactory/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnector.BindToFactory#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindToFactory/VB/form1.vb#1)]  
  
## 코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   System, System.Data, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조  
  
 명령줄에서 [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] 또는 [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]용으로 이 예제를 빌드하는 방법에 대한 자세한 내용은 [명령줄에서 빌드](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) 또는 [csc.exe를 사용한 명령줄 빌드](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)를 참조하세요.  [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]에서 코드를 새 프로젝트에 붙여넣어 이 예제를 빌드할 수도 있습니다.  [방법: Visual Studio를 사용하여 전체 Windows Forms 코드 예제 컴파일 및 실행](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))을 참조하세요.  
  
## 참고 항목  
 <xref:System.Windows.Forms.BindingNavigator>   
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.BindingSource>   
 [BindingSource 구성 요소](../../../../docs/framework/winforms/controls/bindingsource-component.md)   
 [방법: 형식에 Windows Forms 컨트롤 바인딩](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)