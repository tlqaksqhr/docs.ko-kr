---
title: '방법: 인쇄 큐의 하위 집합 열거'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- enumerating [WPF], subset of print queues
- print queues [WPF], enumerating subset of
ms.assetid: cc4a1b5b-d46f-4c5e-bc26-22c226e4bee0
ms.openlocfilehash: 3e616b3b61b4b1b561d5bdb7e51525f391901a22
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-enumerate-a-subset-of-print-queues"></a>방법: 인쇄 큐의 하위 집합 열거
프린터의 회사 전체 집합을 관리 하는 정보 기술 (IT) 전문가가 직면 하는 일반적인 상황 특정 한 특성이 있는 프린터의 목록을 생성 하는 것입니다. 이 기능을 제공는 <xref:System.Printing.PrintServer.GetPrintQueues%2A> 의 메서드는 <xref:System.Printing.PrintServer> 개체 및 <xref:System.Printing.EnumeratedPrintQueueTypes> 열거형입니다.  
  
## <a name="example"></a>예제  
 아래 예제에서 코드는 먼저 나열 하려는 인쇄 대기열의 특성을 지정 하는 플래그의 배열을 만듭니다. 이 예제에서는 인쇄 큐 인쇄 서버에 로컬로 설치 되 고 공유를 찾고 있습니다. <xref:System.Printing.EnumeratedPrintQueueTypes> 열거형은 다양 한 비즈니스 가능성이 제공 합니다.  
  
 코드는 다음 만듭니다는 <xref:System.Printing.LocalPrintServer> 개체에서 파생 된 클래스 <xref:System.Printing.PrintServer>합니다. 로컬 인쇄 서버는 응용 프로그램이 실행 되는 컴퓨터.  
  
 마지막 중요 한 단계에 배열을 전달 하는 것은 <xref:System.Printing.PrintServer.GetPrintQueues%2A> 메서드.  
  
 마지막으로 결과가 사용자에게 표시됩니다.  
  
 [!code-cpp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](../../../../samples/snippets/cpp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CPP/Program.cpp#listsubsetofprintqueues)]
 [!code-csharp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CSharp/Program.cs#listsubsetofprintqueues)]
 [!code-vb[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/visualbasic/program.vb#listsubsetofprintqueues)]  
  
 이 예제를 사용 함으로써 확장할 수는 `foreach` 각 인쇄 큐를 통해 단계를 추가로 수행 하는 루프 차단 합니다. 예를 들어 있습니다 수 차단 프린터에서 양면 인쇄 루프 호출 함으로써 지원 하지 않는 각 인쇄 대기열의 <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> 메서드와 이중의 존재 여부에 대 한 반환 되는 값을 테스트 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Printing.PrintServer.GetPrintQueues%2A>  
 <xref:System.Printing.PrintServer>  
 <xref:System.Printing.LocalPrintServer>  
 <xref:System.Printing.EnumeratedPrintQueueTypes>  
 <xref:System.Printing.PrintQueue>  
 <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>  
 [WPF의 문서](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [인쇄 개요](../../../../docs/framework/wpf/advanced/printing-overview.md)  
 [Microsoft XPS Document Writer](http://go.microsoft.com/fwlink/?LinkId=147319)
