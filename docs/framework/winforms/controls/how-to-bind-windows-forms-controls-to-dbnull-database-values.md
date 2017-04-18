---
title: "방법: DBNull 데이터베이스 값에 Windows Forms 컨트롤 바인딩 | Microsoft Docs"
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
  - "BindingSource 구성 요소[Windows Forms], DBNull 값에 바인딩"
  - "컨트롤[Windows Forms], DBNull 값에 바인딩"
  - "예제[Windows Forms], BindingSource 구성 요소"
ms.assetid: 96494e6f-5f40-4f83-af97-bbd7192c2af8
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# 방법: DBNull 데이터베이스 값에 Windows Forms 컨트롤 바인딩
Windows Forms 컨트롤을 데이터 소스에 바인딩하고 데이터 소스가 <xref:System.DBNull> 값을 반환하는 경우 이벤트를 처리, 형식 지정 또는 구문 분석하지 않고 적절한 값을 대체할 수 있습니다.  <xref:System.Windows.Forms.Binding.NullValue%2A> 속성은 데이터 소스 값을 형식 지정 또는 구문 분석할 때 <xref:System.DBNull>을 지정된 개체로 변환합니다.  
  
## 예제  
 다음 예제에서는 두 가지 다른 상황에서 <xref:System.DBNull> 값을 바인딩하는 방법을 보여 줍니다.  첫 번째 예제에서는 문자열 속성에 대해 <xref:System.Windows.Forms.Binding.NullValue%2A>를 설정하는 방법을 보여 주고, 두 번째 예제에서는 이미지 속성에 대해 <xref:System.Windows.Forms.Binding.NullValue%2A>를 설정하는 방법을 보여 줍니다.  
  
 [!code-csharp[System.Windows.Forms.BindingDBNull#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingDBNull/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.BindingDBNull#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingDBNull/VB/form1.vb#1)]  
  
 바인딩된 속성의 형식 및 <xref:System.Windows.Forms.Binding.NullValue%2A> 속성은 같아야 합니다. 그러지 않으면 오류가 발생하고 더 이상 <xref:System.Windows.Forms.Binding.NullValue%2A> 값이 처리되지 않습니다.  이 경우 예외가 발생하지 않습니다.  
  
## 코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   System, System.Data, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조  
  
 명령줄에서 [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] 또는 [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]용으로 이 예제를 빌드하는 방법에 대한 자세한 내용은 [명령줄에서 빌드](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) 또는 [csc.exe를 사용한 명령줄 빌드](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)를 참조하세요.  [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]에서 코드를 새 프로젝트에 붙여넣어 이 예제를 빌드할 수도 있습니다.  [방법: Visual Studio를 사용하여 전체 Windows Forms 코드 예제 컴파일 및 실행](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))을 참조하세요.  
  
## 참고 항목  
 [BindingSource 구성 요소](../../../../docs/framework/winforms/controls/bindingsource-component.md)   
 [방법: 데이터 바인딩에서 발생하는 오류 및 예외 처리](../../../../docs/framework/winforms/controls/how-to-handle-errors-and-exceptions-that-occur-with-databinding.md)   
 [방법: 형식에 Windows Forms 컨트롤 바인딩](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)