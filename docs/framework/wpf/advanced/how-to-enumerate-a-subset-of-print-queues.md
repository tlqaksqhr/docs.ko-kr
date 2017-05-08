---
title: "방법: 인쇄 큐의 하위 집합 열거 | Microsoft Docs"
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
  - "열거, 인쇄 대기열 하위 집합"
  - "인쇄 대기열, 하위 집합 열거"
ms.assetid: cc4a1b5b-d46f-4c5e-bc26-22c226e4bee0
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# 방법: 인쇄 큐의 하위 집합 열거
전사적 프린터 집합을 관리하는 IT\(정보 기술\) 전문가가 직면한 일반적인 상황은 특정 특성을 갖는 프린터 목록을 생성하는 것입니다.  <xref:System.Printing.PrintServer> 개체의 <xref:System.Printing.PrintServer.GetPrintQueues%2A> 메서드 및 <xref:System.Printing.EnumeratedPrintQueueTypes> 열거형에서 이 기능을 제공합니다.  
  
## 예제  
 아래 예제의 코드는 나열하려는 인쇄 큐의 특성을 지정하는 플래그의 배열을 만들면서 시작합니다.  이 예제에서는 프린터 서버에 로컬로 설치되어 공유되는 인쇄 큐를 찾습니다.  <xref:System.Printing.EnumeratedPrintQueueTypes> 열거형은 다른 많은 가능성을 제공합니다.  
  
 그런 다음 코드는 <xref:System.Printing.PrintServer>에서 파생된 클래스인 <xref:System.Printing.LocalPrintServer> 개체를 만듭니다.  로컬 인쇄 서버는 응용 프로그램이 실행되고 있는 컴퓨터입니다.  
  
 마지막 중요 단계는 배열을 <xref:System.Printing.PrintServer.GetPrintQueues%2A> 메서드에 전달하는 것입니다.  
  
 마지막으로 결과가 사용자에게 표시됩니다.  
  
 [!code-cpp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](../../../../samples/snippets/cpp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CPP/Program.cpp#listsubsetofprintqueues)]
 [!code-csharp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](../../../../samples/snippets/csharp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CSharp/Program.cs#listsubsetofprintqueues)]
 [!code-vb[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/visualbasic/program.vb#listsubsetofprintqueues)]  
  
 각 인쇄 큐를 단계적으로 처리하는 `foreach` 루프에서 추가 스크리닝을 수행하게 하여 이 예제를 확장할 수 있습니다.  예를 들어 루프에서 각 인쇄 큐의 <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> 메서드를 호출하고 반환된 값에서 양면 인쇄가 있는지 테스트하여 양면 인쇄를 지원하지 않는 프린터를 걸러낼 수 있습니다.  
  
## 참고 항목  
 <xref:System.Printing.PrintServer.GetPrintQueues%2A>   
 <xref:System.Printing.PrintServer>   
 <xref:System.Printing.LocalPrintServer>   
 <xref:System.Printing.EnumeratedPrintQueueTypes>   
 <xref:System.Printing.PrintQueue>   
 <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>   
 [WPF의 문서](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)   
 [인쇄 개요](../../../../docs/framework/wpf/advanced/printing-overview.md)   
 [Microsoft XPS Document Writer](http://go.microsoft.com/fwlink/?LinkId=147319)