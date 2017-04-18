---
title: "방법: Windows Forms BindingNavigator 컨트롤을 사용하여 데이터 집합에서 이동 | Microsoft Docs"
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
  - "BindingNavigator 컨트롤[Windows Forms], 데이터 집합에서 이동"
  - "데이터 집합[Windows Forms], 이동"
  - "예제[Windows Forms], BindingNavigator 컨트롤"
ms.assetid: 146d97be-3d97-400e-accb-860bbf47729d
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# 방법: Windows Forms BindingNavigator 컨트롤을 사용하여 데이터 집합에서 이동
데이터 기반 응용 프로그램을 빌드할 때 사용자에게 데이터 컬렉션을 표시해야 하는 경우가 많습니다.  <xref:System.Windows.Forms.BindingSource> 구성 요소와 더불어 <xref:System.Windows.Forms.BindingNavigator> 컨트롤은 컬렉션을 탐색하고 항목을 순차적으로 표시하기 위한 편리하고 확장 가능한 솔루션을 제공합니다.  
  
## 예제  
 다음 코드 예제에서는 <xref:System.Windows.Forms.BindingNavigator> 컨트롤을 사용하여 데이터를 탐색하는 방법을 보여 줍니다.  집합은 <xref:System.Windows.Forms.BindingSource> 구성 요소를 사용하여 <xref:System.Windows.Forms.TextBox> 컨트롤에 바인딩된 <xref:System.Data.DataView>에 포함됩니다.  
  
> [!NOTE]
>  암호와 같은 중요한 정보를 연결 문자열 내에 저장하면 응용 프로그램 보안 문제가 발생할 수 있습니다.  데이터베이스 액세스를 제어할 경우에는 통합 보안이라고도 하는 Windows 인증을 사용하는 방법이 더 안전합니다.  자세한 내용은 [연결 정보 보호](../../../../docs/framework/data/adonet/protecting-connection-information.md)을 참조하세요.  
  
 [!code-csharp[System.Windows.Forms.DataNavigator#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataNavigator/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataNavigator#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataNavigator/VB/form1.vb#1)]  
  
## 코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   System, System.Data, System.Drawing, System.Windows.Forms and System.Xml 어셈블리에 대한 참조  
  
 명령줄에서 [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] 또는 [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]용으로 이 예제를 빌드하는 방법에 대한 자세한 내용은 [명령줄에서 빌드](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) 또는 [csc.exe를 사용한 명령줄 빌드](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)를 참조하세요.  [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]에서 코드를 새 프로젝트에 붙여넣어 이 예제를 빌드할 수도 있습니다.  [방법: Visual Studio를 사용하여 전체 Windows Forms 코드 예제 컴파일 및 실행](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))을 참조하세요.  
  
## 참고 항목  
 <xref:System.Windows.Forms.BindingSource>   
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.BindingSource>   
 [BindingNavigator 컨트롤](../../../../docs/framework/winforms/controls/bindingnavigator-control-windows-forms.md)   
 [BindingSource 구성 요소](../../../../docs/framework/winforms/controls/bindingsource-component.md)   
 [방법: 형식에 Windows Forms 컨트롤 바인딩](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)