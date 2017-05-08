---
title: "방법: BindingSource 구성 요소를 사용하여 폼 간에 바인딩된 데이터 공유 | Microsoft Docs"
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
  - "BindingSource 구성 요소[Windows Forms], 예제"
  - "BindingSource, 여러 폼에 사용"
  - "데이터 바인딩, 폼 간 데이터 공유"
  - "예제[Windows Forms], BindingSource 구성 요소"
ms.assetid: a1a49630-db9c-4485-b888-1f62a373a4f7
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# 방법: BindingSource 구성 요소를 사용하여 폼 간에 바인딩된 데이터 공유
<xref:System.Windows.Forms.BindingSource> 구성 요소를 사용하여 폼 간에 데이터를 쉽게 공유할 수 있습니다.  예를 들어 데이터 소스 데이터를 요약하는 하나의 읽기 전용 폼과 데이터 소스에서 현재 선택한 항목에 대한 세부 정보가 포함된 다른 편집 가능한 폼을 표시할 수 있습니다.  이 예제에서는 이 시나리오를 보여 줍니다.  
  
## 예제  
 다음 코드 예제에서는 <xref:System.Windows.Forms.BindingSource> 및 바인딩된 데이터를 폼 간에 공유하는 방법을 보여 줍니다.  이 예제에서는 공유 <xref:System.Windows.Forms.BindingSource>는 자식 폼의 생성자에 전달됩니다.  자식 폼을 통해 사용자는 기본 폼에서 현재 선택한 항목에 대한 데이터를 편집할 수 있습니다.  
  
> [!NOTE]
>  예제에서는 <xref:System.Windows.Forms.BindingSource> 구성 요소에 대한 <xref:System.Windows.Forms.BindingSource.BindingComplete> 이벤트를 처리하여 두 폼을 동기화된 상태로 유지합니다.  이 작업을 수행하는 이유에 대한 자세한 내용은 [방법: 동일한 데이터 소스에 바인딩된 여러 컨트롤의 동기화 상태가 유지되도록 설정](../../../../docs/framework/winforms/multiple-controls-bound-to-data-source-synchronized.md)을 참조하세요.  
  
 [!code-csharp[System.Windows.Forms.BindingSourceMultipleForms#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleForms/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.BindingSourceMultipleForms#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleForms/VB/Form1.vb#1)]  
  
## 코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   System, System.Windows.Forms, System.Drawing, System.Data 및 System.Xml 어셈블리에 대한 참조  
  
 명령줄에서 [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] 또는 [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]용으로 이 예제를 빌드하는 방법에 대한 자세한 내용은 [명령줄에서 빌드](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) 또는 [csc.exe를 사용한 명령줄 빌드](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)를 참조하세요.  [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]에서 코드를 새 프로젝트에 붙여넣어 이 예제를 빌드할 수도 있습니다.  [방법: Visual Studio를 사용하여 전체 Windows Forms 코드 예제 컴파일 및 실행](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))을 참조하세요.  
  
## 참고 항목  
 [BindingSource 구성 요소](../../../../docs/framework/winforms/controls/bindingsource-component.md)   
 [Windows Forms 데이터 바인딩](../../../../docs/framework/winforms/windows-forms-data-binding.md)   
 [방법: 데이터 바인딩에서 발생하는 오류 및 예외 처리](../../../../docs/framework/winforms/controls/how-to-handle-errors-and-exceptions-that-occur-with-databinding.md)