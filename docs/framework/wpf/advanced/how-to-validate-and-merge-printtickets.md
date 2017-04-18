---
title: "방법: PrintTicket 유효성 검사 및 병합 | Microsoft Docs"
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
  - "PrintTicket 병합"
  - "PrintTicket, 병합"
  - "PrintTicket, 유효성 검사"
  - "PrintTicket 유효성 검사"
ms.assetid: 4fe2d501-d0b0-4fef-86af-6ffe6c162532
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# 방법: PrintTicket 유효성 검사 및 병합
[!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] [인쇄 스키마](http://go.microsoft.com/fwlink/?LinkId=186397)에는 유연하고 확장 가능한 <xref:System.Printing.PrintCapabilities> 및 <xref:System.Printing.PrintTicket> 요소가 포함되어 있습니다.  전자는 인쇄 장치의 기능을 항목별로 정리하고 후자는 특정 문서 시퀀스, 개별 문서 또는 개별 페이지와 관련하여 장치에서 이러한 기능을 사용해야 하는 방법을 지정합니다.  
  
 인쇄를 지원하는 응용 프로그램에 대한 일반적인 작업 시퀀스는 다음과 같습니다.  
  
1.  프린터의 기능을 확인합니다.  
  
2.  이러한 기능을 사용하도록 <xref:System.Printing.PrintTicket>을 구성합니다.  
  
3.  <xref:System.Printing.PrintTicket>의 유효성을 검사합니다.  
  
 이 문서에서는 이 작업을 수행하는 방법을 보여 줍니다.  
  
## 예제  
 아래의 간단한 예제에서는 프린터가 양면 인쇄를 지원하는지 여부에만 초점을 둡니다.  주요 단계는 다음과 같습니다.  
  
1.  <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> 메서드를 사용하여 <xref:System.Printing.PrintCapabilities> 개체를 가져옵니다.  
  
2.  원하는 기능이 있는지 테스트합니다.  아래 예제에서는 <xref:System.Printing.PrintCapabilities> 개체의 <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> 속성을 테스트하여 용지를 옆으로 넘기는 "페이지 넘기기"를 하면서 용지의 양면에 인쇄하는 기능이 있는지 확인합니다.  <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A>가 컬렉션이므로 <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>의 `Contains` 메서드를 사용합니다.  
  
    > [!NOTE]
    >  이 단계는 반드시 필요한 것은 아닙니다.  아래 사용된 <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> 메서드는 프린터의 기능에 대해 <xref:System.Printing.PrintTicket>의 각 요청을 검사합니다.  요청된 기능이 프린터에서 지원되지 않을 경우 프린터 드라이브는 메서드에 의해 반환된 <xref:System.Printing.PrintTicket>의 대체 요청을 대체합니다.  
  
3.  프린터에서 양면 인쇄를 지원할 경우 샘플 코드는 양면 인쇄를 요청하는 <xref:System.Printing.PrintTicket>을 만듭니다.  그러나 응용 프로그램은 <xref:System.Printing.PrintTicket> 요소에서 사용할 수 있는 가능한 모든 프린터 설정을 지정하지 않습니다.  이는 프로그래머 및 프로그램 모두에 시간 낭비가 될 수 있습니다.  대신에 코드는 양면 인쇄 요청만 설정한 다음 이 <xref:System.Printing.PrintTicket>을 완전히 구성 및 유효성 검사된 기존의 <xref:System.Printing.PrintTicket>\(이 경우에는 사용자의 기본 <xref:System.Printing.PrintTicket>\)과 병합합니다.  
  
4.  따라서 샘플은 <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> 메서드를 호출하여 새로운 최소 <xref:System.Printing.PrintTicket>을 사용자의 기본 <xref:System.Printing.PrintTicket>과 병합합니다.  이로 인해 <xref:System.Printing.PrintTicket>을 속성 중 하나로 포함하는 <xref:System.Printing.ValidationResult>가 반환됩니다.  
  
5.  그런 다음 샘플은 새 <xref:System.Printing.PrintTicket>이 양면 인쇄를 요청하는지 테스트합니다.  양면 인쇄가 요청될 경우 샘플은 이를 사용자의 새 기본 인쇄 티켓으로 만듭니다.  위의 2단계가 누락되고 프린터에서 옆으로 넘기는 양면 인쇄를 지원하지 않을 경우 테스트 결과는 `false`가 됩니다.  위의 참고 사항을 참조하십시오.  
  
6.  마지막 중요 단계는 <xref:System.Printing.PrintQueue.Commit%2A> 메서드를 사용하여 <xref:System.Printing.PrintQueue>의 <xref:System.Printing.PrintQueue.UserPrintTicket%2A> 속성에 변경 내용을 커밋하는 것입니다.  
  
 [!code-csharp[PrintTicketManagment#UsingMergeAndValidate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#usingmergeandvalidate)]
 [!code-vb[PrintTicketManagment#UsingMergeAndValidate](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#usingmergeandvalidate)]  
  
 이 예제를 신속하게 테스트할 수 있도록 나머지 부분이 아래 나와 있습니다.  프로젝트와 네임스페이스를 만들어 이 문서의 두 코드 조각을 네임스페이스 블록에 붙여넣습니다.  
  
 [!code-csharp[PrintTicketManagment#UIForMergeAndValidatePTUtility](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#uiformergeandvalidateptutility)]
 [!code-vb[PrintTicketManagment#UIForMergeAndValidatePTUtility](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#uiformergeandvalidateptutility)]  
  
## 참고 항목  
 <xref:System.Printing.PrintCapabilities>   
 <xref:System.Printing.PrintTicket>   
 <xref:System.Printing.PrintServer.GetPrintQueues%2A>   
 <xref:System.Printing.PrintServer>   
 <xref:System.Printing.EnumeratedPrintQueueTypes>   
 <xref:System.Printing.PrintQueue>   
 <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>   
 [WPF의 문서](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)   
 [인쇄 개요](../../../../docs/framework/wpf/advanced/printing-overview.md)   
 [Print Schema](http://go.microsoft.com/fwlink/?LinkId=186397)