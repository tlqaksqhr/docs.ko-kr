---
title: '방법: PrintTicket 유효성 검사 및 병합'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- merging PrintTickets [WPF]
- PrintTicket [WPF], merging
- validation of PrintTickets [WPF]
- PrintTicket [WPF], validation
ms.assetid: 4fe2d501-d0b0-4fef-86af-6ffe6c162532
ms.openlocfilehash: 11160d7ec59914afbe501ba731c0c04a85ffc4a5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-validate-and-merge-printtickets"></a>방법: PrintTicket 유효성 검사 및 병합
[!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] [Schema](http://go.microsoft.com/fwlink/?LinkId=186397) 유연성이 있고 확장 가능 포함 <xref:System.Printing.PrintCapabilities> 및 <xref:System.Printing.PrintTicket> 요소입니다. 인쇄 장치의 기능을 전자 항목별로 정리 하 고 후자 지정이 장치가 문서, 개별 문서 또는 개별 페이지의 특정 시퀀스에 대해 이러한 기능을 어떻게 사용 해야 합니다.  
  
 인쇄를 지 원하는 응용 프로그램에 대 한 작업의 일반적인 순서는 다음과 같은 것입니다.  
  
1.  프린터의 기능을 확인 합니다.  
  
2.  구성 된 <xref:System.Printing.PrintTicket> 이러한 기능을 사용 하도록 합니다.  
  
3.  유효성 검사는 <xref:System.Printing.PrintTicket>합니다.  
  
 이 문서에서는이 작업을 수행 하는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 아래의 간단한 예제에서 우리에 관심이 프린터 양면 인쇄를 지원할 수 있는지 여부 — 양면 인쇄 합니다. 주요 단계는 다음과 같습니다.  
  
1.  가져오기는 <xref:System.Printing.PrintCapabilities> 개체는 <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> 메서드.  
  
2.  원하는 기능이 있는지 테스트 합니다. 테스트 아래 예제는 <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> 속성의는 <xref:System.Printing.PrintCapabilities> 시트의 옆으로 "페이지"회전 용지 시트의 양쪽에서 인쇄 기능이 있는지에 대 한 개체입니다. 이후 <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> 컬렉션이 사용 하 여는 `Contains` 방식의 <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>합니다.  
  
    > [!NOTE]
    >  이 단계는 엄격 하 게 필요 하지 않습니다. <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> 아래 사용 하는 방법에 각 요청을 확인 합니다는 <xref:System.Printing.PrintTicket> 프린터의 기능에 대 한 합니다. 프린터에서 필요한 기능을 지원 하지 않는, 프린터 드라이버의 대체 요청을 대체 합니다는 <xref:System.Printing.PrintTicket> 메서드에 의해 반환 합니다.  
  
3.  샘플 코드에서는 프린터에서 양면 인쇄를 지 원하는 경우는 <xref:System.Printing.PrintTicket> 양면 라는 메시지가 표시 됩니다. 하지만 응용 프로그램에서 가능한 모든 프린터에서 사용할 수 있는 설정을 지정 하지는 <xref:System.Printing.PrintTicket> 요소입니다. 프로그래머와 프로그램 시간을 모두의 낭비 될 것입니다. 코드는 양면 인쇄 요청만 설정 하 고이 병합 하는 대신, <xref:System.Printing.PrintTicket> 된 기존의 완벽 하 게 구성 하 고 유효성을 검사 <xref:System.Printing.PrintTicket>,이 경우 사용자의 기본 <xref:System.Printing.PrintTicket>합니다.  
  
4.  샘플 적절 하 게 호출 하는 <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> 새, 병합 하는 메서드, 최소한의 <xref:System.Printing.PrintTicket> 이며 기본값은 사용자의 <xref:System.Printing.PrintTicket>합니다. 반환 합니다.는 <xref:System.Printing.ValidationResult> 포함 하는 <xref:System.Printing.PrintTicket> 속성 중 하나로 합니다.  
  
5.  이 샘플에 있는 항목을 다음 테스트 새 <xref:System.Printing.PrintTicket> 양면 인쇄를 요청 합니다. 그렇지 않으면 다음 샘플 하면 사용자에 대 한 새 기본 인쇄 티켓 있습니다. 위의 2 단계 그대로 남아 있었습니다. 프린터 긴 측면 양면 인쇄를 지원 하지 않을 경우에 테스트 결과 `false`합니다. (위의 참고 참조).  
  
6.  하 여 변경 내용을 커밋하는 마지막 중요 단계는 <xref:System.Printing.PrintQueue.UserPrintTicket%2A> 속성은 <xref:System.Printing.PrintQueue> 와 <xref:System.Printing.PrintQueue.Commit%2A> 메서드.  
  
 [!code-csharp[PrintTicketManagment#UsingMergeAndValidate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#usingmergeandvalidate)]
 [!code-vb[PrintTicketManagment#UsingMergeAndValidate](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#usingmergeandvalidate)]  
  
 이 예에서는 빠르게 테스트 수 있도록 나머지 아래 표시 됩니다. 프로젝트 및 네임 스페이스를 만들고 코드 조각은 네임 스페이스 블록에이 문서에 붙여 넣습니다.  
  
 [!code-csharp[PrintTicketManagment#UIForMergeAndValidatePTUtility](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#uiformergeandvalidateptutility)]
 [!code-vb[PrintTicketManagment#UIForMergeAndValidatePTUtility](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#uiformergeandvalidateptutility)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Printing.PrintCapabilities>  
 <xref:System.Printing.PrintTicket>  
 <xref:System.Printing.PrintServer.GetPrintQueues%2A>  
 <xref:System.Printing.PrintServer>  
 <xref:System.Printing.EnumeratedPrintQueueTypes>  
 <xref:System.Printing.PrintQueue>  
 <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>  
 [WPF의 문서](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [인쇄 개요](../../../../docs/framework/wpf/advanced/printing-overview.md)  
 [스키마를 인쇄 합니다.](http://go.microsoft.com/fwlink/?LinkId=186397)
