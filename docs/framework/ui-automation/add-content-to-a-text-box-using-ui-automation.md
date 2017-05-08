---
title: "Add Content to a Text Box Using UI Automation | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "adding content to text boxes"
  - "text boxes, adding content"
  - "UI Automation, adding content to text boxes"
ms.assetid: 8bdd1a73-1ecb-4a05-a891-a7827ebb767f
caps.latest.revision: 13
author: "Xansky"
ms.author: "mhopkins"
manager: "markl"
caps.handback.revision: 13
---
# Add Content to a Text Box Using UI Automation
> [!NOTE]
>  이 문서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위해 작성되었습니다.  [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows Automation API: UI Automation](http://go.microsoft.com/fwlink/?LinkID=156746)을 참조하십시오.  
  
 이 항목에는 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)]를 사용하여 한 줄 텍스트 상자에 텍스트를 삽입하는 방법을 보여 주는 예제 코드가 나와 있습니다.  여기에서는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]를 적용할 수 없는 여러 줄 텍스트 컨트롤 및 서식 있는 텍스트 컨트롤에 사용할 수 있는 대체 메서드도 제공합니다.  비교를 위해 예제에서는 Win32 메서드를 사용하여 동일한 결과를 얻는 방법도 보여 줍니다.  
  
## 예제  
 다음 예제에서는 대상 응용 프로그램의 일련의 텍스트 컨트롤을 단계적으로 처리합니다.  먼저 <xref:System.Windows.Automation.AutomationElement.TryGetCurrentPattern%2A> 메서드를 사용하여 각 텍스트 컨트롤을 테스트함으로써 <xref:System.Windows.Automation.ValuePattern> 개체를 가져올 수 있는지 확인합니다.  텍스트 컨트롤이 <xref:System.Windows.Automation.ValuePattern>을 지원하는 경우 <xref:System.Windows.Automation.ValuePattern.SetValue%2A> 메서드를 사용하여 사용자 정의 문자열을 텍스트 컨트롤에 삽입합니다.  그렇지 않으면 <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=fullName> 메서드를 사용합니다.  
  
 [!code-csharp[InsertText#InsertText](../../../samples/snippets/csharp/VS_Snippets_Wpf/InsertText/CSharp/Window1.xaml.cs#inserttext)]
 [!code-vb[InsertText#InsertText](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InsertText/VisualBasic/Window1.xaml.vb#inserttext)]  
  
## 참고 항목  
 [TextPattern Insert Text Sample](http://msdn.microsoft.com/ko-kr/67353f93-7ee2-42f2-ab76-5c078cf6ca16)