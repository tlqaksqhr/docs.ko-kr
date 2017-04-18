---
title: "방법: 인쇄 대화 상자 호출 | Microsoft Docs"
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
  - "인쇄 대화 상자 중지"
  - "인쇄 대화 상자, 호출"
ms.assetid: e3a2c84c-74fe-45a4-8501-5813f9dbfed2
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# 방법: 인쇄 대화 상자 호출
응용 프로그램에 인쇄 기능을 제공하기 위한 <xref:System.Windows.Controls.PrintDialog> 개체를 간단하게 만들고 열 수 있습니다.  
  
## 예제  
 <xref:System.Windows.Controls.PrintDialog> 컨트롤에서는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], 구성 및 [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] 작업 전송에 대한 단일 진입점을 제공합니다.  [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 태그나 코드를 사용하여 이 컨트롤을 쉽게 사용하고 인스턴스화할 수 있습니다.  다음 예제에서는 코드로 컨트롤을 인스턴스화하고 여는 방법과 해당 컨트롤에서 인쇄하는 방법을 보여 줍니다.  또한 대화 상자에서 페이지의 특정 범위를 설정하는 옵션을 사용자에게 제공하게 하는 방법을 보여 줍니다.  예제 코드에서는 C: 드라이브의 루트에 FixedDocumentSequence.xps 파일이 있다고 가정합니다.  
  
 [!code-csharp[printdialog#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrintDialog/CSharp/Window1.xaml.cs#1)]
 [!code-vb[printdialog#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrintDialog/visualbasic/window1.xaml.vb#1)]  
  
 대화 상자가 열리면 사용자는 자신의 컴퓨터에 설치된 프린터에서 선택할 수 있습니다.  또한 인쇄하는 대신 [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)] 파일을 만드는 [Microsoft XPS Document Writer](http://go.microsoft.com/fwlink/?LinkId=147319)를 선택하는 옵션을 갖게 됩니다.  
  
> [!NOTE]
>  이 항목에서 설명하는 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]의 <xref:System.Windows.Controls.PrintDialog?displayProperty=fullName> 컨트롤을 [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)]의 <xref:System.Windows.Forms.PrintDialog?displayProperty=fullName> 구성 요소와 혼동해서는 안 됩니다.  
  
 대화 상자를 열지 않고 <xref:System.Windows.Controls.PrintDialog.PrintDocument%2A> 메서드를 사용할 수도 있습니다.  이러한 방법으로 이 컨트롤을 보이지 않는 인쇄 구성 요소로 사용할 수 있습니다.  그러나 성능상의 이유로 <xref:System.Printing.PrintQueue.AddJob%2A> 메서드 또는 <xref:System.Windows.Xps.XpsDocumentWriter>의 여러 <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> 및 <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> 메서드 중 하나를 사용하는 것이 좋습니다.  자세한 내용은 [프로그래밍 방식으로 XPS 파일 인쇄](../../../../docs/framework/wpf/advanced/how-to-programmatically-print-xps-files.md)를 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Controls.PrintDialog>   
 [WPF의 문서](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)   
 [인쇄 개요](../../../../docs/framework/wpf/advanced/printing-overview.md)   
 [Microsoft XPS Document Writer](http://go.microsoft.com/fwlink/?LinkId=147319)