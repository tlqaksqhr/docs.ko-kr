---
title: "방법: 프로그래밍 방식으로 XPS 파일 인쇄 | Microsoft Docs"
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
  - "프로그래밍 방식으로 XPS 파일 인쇄"
  - "XPS 파일, 프로그래밍 방식으로 인쇄"
ms.assetid: 0b1c0a3f-b19e-43d6-bcc9-eb3ec4e555ad
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 방법: 프로그래밍 방식으로 XPS 파일 인쇄
<xref:System.Printing.PrintQueue.AddJob%2A> 메서드의 한 오버로드를 사용하면 <xref:System.Windows.Controls.PrintDialog>를 열거나 원칙적으로 어떠한 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]도 열 필요 없이 [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)] 파일을 인쇄할 수 있습니다.  
  
 또한 <xref:System.Windows.Xps.XpsDocumentWriter>의 많은 <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> 및 <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> 메서드를 사용하여 [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)] 파일을 인쇄할 수 있습니다.  자세한 내용은 [Printing an XPS Document](http://msdn.microsoft.com/ko-kr/849555c8-0c4e-48c0-86bc-a5494c69b36c)를 참조하십시오.  
  
 [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)]를 인쇄하는 또 다른 방법은 <xref:System.Windows.Controls.PrintDialog> 컨트롤의 <xref:System.Windows.Controls.PrintDialog.PrintDocument%2A> 또는 <xref:System.Windows.Controls.PrintDialog.PrintVisual%2A> 메서드를 사용하는 것입니다.  [인쇄 대화 상자 호출](../../../../docs/framework/wpf/advanced/how-to-invoke-a-print-dialog.md)를 참조하십시오.  
  
## 예제  
 세 개 매개 변수의 <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29> 메서드를 사용하는 주요 단계는 다음과 같습니다.  아래 예제에서 자세한 내용을 제공합니다.  
  
1.  프린터가 XPSDrv 프린터인지 확인합니다.  XPSDrv에 대한 자세한 내용은 [인쇄 개요](../../../../docs/framework/wpf/advanced/printing-overview.md)를 참조하십시오.  
  
2.  프린터가 XPSDrv 프린터가 아닌 경우 스레드의 아파트를 단일 스레드로 설정합니다.  
  
3.  프린터 서버를 인스턴스화하고 큐 개체를 인쇄합니다.  
  
4.  메서드를 호출하여 작업 이름, 인쇄할 파일 및 프린터가 XPSDrv 프린터인지 여부를 나타내는 <xref:System.Boolean> 플래그를 지정합니다.  
  
 아래 예제에서는 디렉터리에 있는 모든 [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] 파일을 일괄 인쇄하는 방법을 보여 줍니다.  디렉터리를 지정하라는 메시지를 응용 프로그램에서 표시하지만 세 개 매개 변수의 <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29> 메서드에는 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]가 필요하지 않습니다.  전달할 수 있는 [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] 파일 이름과 경로가 있는 모든 코드 경로에서 이 메서드를 사용할 수 있습니다.  
  
 <xref:System.Printing.PrintQueue.AddJob%2A>의 세 개 매개 변수 <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29> 오버로드는 <xref:System.Boolean> 매개 변수가 `false`\(XPSDrv 형식이 아닌 프린터가 사용될 경우에 해당\)일 때마다 단일 스레드 아파트에서 실행되어야 합니다.  그러나 [!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)]의 기본 아파트 상태는 다중 스레드입니다.  예제에서는 XPSDrv 형식이 아닌 프린터를 가정하므로 이 기본값을 바꾸어야 합니다.  
  
 기본값을 변경하는 두 가지 방법이 있습니다.  한 가지 방법은 단순히 응용 프로그램의 `Main` 메서드\(대개 "`static void Main(string[] args)`"\) 바로 위 줄에 <xref:System.STAThreadAttribute>\(즉, "`[System.STAThreadAttribute()]`"\)를 추가하는 것입니다.  그러나 대부분의 응용 프로그램에서는 `Main` 메서드가 다중 스레드 아파트 상태를 가져야 하므로 이와 다른 두 번째 방법이 있습니다. 두 번째 방법은 <xref:System.Threading.Thread.SetApartmentState%2A>를 사용하여 아파트 상태가 <xref:System.Threading.ApartmentState>로 설정되는 별개의 스레드에 <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29> 호출을 두는 것입니다.  다음 예제에서는 두 번째 기술을 사용합니다.  
  
 따라서 이 예제에서는 먼저 <xref:System.Threading.Thread> 개체를 인스턴스화하고 **PrintXPS** 메서드를 <xref:System.Threading.ThreadStart> 매개 변수로 전달합니다.  **PrintXPS** 메서드는 이 예제의 뒤에서 정의됩니다. 그런 다음 스레드가 단일 스레드 아파트로 설정됩니다.  `Main` 메서드의 나머지 코드만 새 스레드를 시작합니다.  
  
 이 예제의 핵심은 `static` **BatchXPSPrinter.PrintXPS** 메서드에 있습니다.  인쇄 서버 및 큐를 만든 후에 이 메서드는 [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] 파일이 포함된 디렉터리를 묻는 메시지를 표시합니다.  디렉터리와 디렉터리에 있는 \*.xps 파일의 존재를 확인한 후 이 메서드는 이러한 각 파일을 인쇄 큐에 추가합니다.  이 예제에서는 프린터가 XPSDrv가 아니라고 가정하므로 <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29> 메서드의 마지막 매개 변수에 `false`를 전달합니다.  이러한 이유 때문에 이 메서드는 파일의 [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] 태그를 프린터의 페이지 설명 언어로 변환하기 전에 유효성을 검사합니다.  유효성 검사가 실패하면 예외가 throw됩니다.  예제 코드는 예외를 catch하고 사용자에게 이를 알린 다음 계속해서 다음 [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] 파일을 처리합니다.  
  
 [!code-csharp[BatchPrintXPSFiles#BatchPrintXPSFiles](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BatchPrintXPSFiles/CSharp/Program.cs#batchprintxpsfiles)]
 [!code-vb[BatchPrintXPSFiles#BatchPrintXPSFiles](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BatchPrintXPSFiles/visualbasic/program.vb#batchprintxpsfiles)]  
  
 XPSDrv 프린터를 사용하는 중이면 최종 매개 변수를 `true`로 설정할 수 있습니다.  이 경우 [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)]가 프린터의 페이지 설명 언어이므로 이 메서드는 유효성을 검사하거나 다른 페이지 설명 언어로 변환하지 않고 파일을 프린터로 보냅니다.  응용 프로그램에서 XPSDrv 프린터가 사용될지 여부를 디자인 타임에 확실히 알 수 없는 경우 응용 프로그램을 수정하여 <xref:System.Printing.PrintQueue.IsXpsDevice%2A> 속성을 읽고 발견된 사항에 따라 분기되도록 할 수 있습니다.  
  
 [!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)] 및 [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)] 릴리스 직후에는 사용할 수 있는 XPSDrv 프린터가 거의 없으므로 XPSDrv 형식이 아닌 프린터를 XPSDrv 프린터인 것처럼 사용해야 합니다.  이 작업을 수행하려면 응용 프로그램을 실행하는 컴퓨터에서 다음 레지스트리 키의 파일 목록에 Pipelineconfig.xml을 추가합니다.  
  
 HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\Control\\Print\\Environments\\Windows NT x86\\Drivers\\Version\-3\\*\<PseudoXPSPrinter\>*\\DependentFiles  
  
 여기서 *\<PseudoXPSPrinter\>*는 임의의 인쇄 큐입니다.  그런 다음 컴퓨터를 다시 시작해야 합니다.  
  
 이 가장을 사용하면 예외를 일으키지 않고 `true`를 <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29>의 최종 매개 변수로 전달할 수 있지만 *\<PseudoXPSPrinter\>*가 실제로 XPSDrv 프린터가 아니므로 가비지만 인쇄됩니다.  
  
 **참고** 편의상 위 예제에서는 \*.xps 확장명의 존재 여부를 파일이 [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)]인지 여부의 테스트로 사용합니다.  그러나 [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] 파일은 이 확장명을 가질 필요가 없습니다.  [isXPS.exe\(isXPS 규칙 도구\)](../Topic/isXPS.exe%20\(isXPS%20Conformance%20Tool\).md)는 파일에서 [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] 유효성을 테스트하는 한 방법입니다.  
  
## 참고 항목  
 <xref:System.Printing.PrintQueue>   
 <xref:System.Printing.PrintQueue.AddJob%2A>   
 <xref:System.Threading.ApartmentState>   
 <xref:System.STAThreadAttribute>   
 [XPS](http://www.microsoft.com/whdc/xps/default.mspx)   
 [Printing an XPS Document](http://msdn.microsoft.com/ko-kr/849555c8-0c4e-48c0-86bc-a5494c69b36c)   
 [Managed and Unmanaged Threading](http://msdn.microsoft.com/ko-kr/db425c20-4b2f-4433-bf96-76071c7881e5)   
 [isXPS.exe\(isXPS 규칙 도구\)](../Topic/isXPS.exe%20\(isXPS%20Conformance%20Tool\).md)   
 [WPF의 문서](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)   
 [인쇄 개요](../../../../docs/framework/wpf/advanced/printing-overview.md)