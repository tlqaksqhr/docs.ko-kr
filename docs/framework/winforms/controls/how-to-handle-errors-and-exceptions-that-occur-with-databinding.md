---
title: "방법: 데이터 바인딩에서 발생하는 오류 및 예외 처리 | Microsoft Docs"
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
  - "BindingSource 구성 요소[Windows Forms], 오류 및 예외 처리"
  - "데이터 바인딩, 오류 처리"
  - "데이터 바인딩, 예제"
  - "오류 처리, 데이터 바인딩"
  - "오류 처리, 예제"
  - "예제[Windows Forms], 오류 처리"
ms.assetid: eddc5bad-9513-47df-ab28-f02d8dff7892
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# 방법: 데이터 바인딩에서 발생하는 오류 및 예외 처리
기본 비즈니스 개체를 컨트롤에 바인딩할 때 종종 해당 개체에서 예외와 오류가 발생합니다.  이들 오류와 예외를 가로채고 특정 <xref:System.Windows.Forms.Binding>, <xref:System.Windows.Forms.BindingSource> 또는 <xref:System.Windows.Forms.CurrencyManager> 구성 요소에 대한 <xref:System.Windows.Forms.Binding.BindingComplete> 이벤트를 처리하여 오류 정보를 복구하거나 사용자에게 전달할 수 있습니다.  
  
## 예제  
 이 코드 예제에서는 데이터 바인딩 작업 중에 발생하는 오류와 예외를 처리하는 방법을 보여 줍니다.  <xref:System.Windows.Forms.Binding> 개체의 <xref:System.Windows.Forms.Binding.BindingComplete?displayProperty=fullName> 이벤트를 처리하여 오류를 가로채는 방법을 보여 줍니다.  이 이벤트를 처리하여 오류와 예외를 가로채려면 바인딩 서식 지정을 사용하도록 설정해야 합니다.  바인딩이 생성되거나 바인딩 컬렉션에 추가될 때 서식 지정을 사용하도록 설정하거나 <xref:System.Windows.Forms.Binding.FormattingEnabled%2A> 속성을 `true`로 설정하여 사용하도록 설정합니다.  
  
 [!code-cpp[System.Windows.Forms.DataConnectorBindingComplete#3](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorBindingComplete/CPP/form1.cpp#3)]
 [!code-csharp[System.Windows.Forms.DataConnectorBindingComplete#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorBindingComplete/CS/form1.cs#3)]
 [!code-vb[System.Windows.Forms.DataConnectorBindingComplete#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorBindingComplete/VB/form1.vb#3)]  
  
 코드가 실행 중일 때 부분 이름으로 빈 문자열이 입력되거나 부분 숫자로 100보다 작은 값이 입력되면 메시지 상자가 표시됩니다.  이들 텍스트 상자 바인딩에 대한 <xref:System.Windows.Forms.Binding.BindingComplete?displayProperty=fullName> 이벤트를 처리한 결과로 나타나는 것입니다.  
  
## 코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   System, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조  
  
 명령줄에서 [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] 또는 [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]용으로 이 예제를 빌드하는 방법에 대한 자세한 내용은 [명령줄에서 빌드](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) 또는 [csc.exe를 사용한 명령줄 빌드](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)를 참조하세요.  [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]에서 코드를 새 프로젝트에 붙여넣어 이 예제를 빌드할 수도 있습니다.  [방법: Visual Studio를 사용하여 전체 Windows Forms 코드 예제 컴파일 및 실행](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))을 참조하세요.  
  
## 참고 항목  
 <xref:System.Windows.Forms.Binding.BindingComplete?displayProperty=fullName>   
 <xref:System.Windows.Forms.BindingSource.BindingComplete?displayProperty=fullName>   
 [BindingSource 구성 요소](../../../../docs/framework/winforms/controls/bindingsource-component.md)