---
title: '방법: 프린터 복제'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- print queues [WPF]
- cloning printers [WPF]
- printers [WPF], cloning
- print queues [WPF], cloning
- cloning print queues [WPF]
ms.assetid: dd6997c9-fe04-40f8-88a6-92e3ac0889eb
ms.openlocfilehash: 8f3a9c3b4d9f4bcbe3a6ffcff9868aa7b19b8f28
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-clone-a-printer"></a>방법: 프린터 복제
대부분의 기업, 어느 시점 부터는 구입할지 동일한 모델의 여러 프린터입니다. 일반적으로 모든 설치 실제로 동일한 구성 설정을 사용 합니다. 각 프린터를 설치 시간이 오래 걸릴 수 및 오류가 발생 하기 쉽습니다. <xref:System.Printing.IndexedProperties?displayProperty=nameWithType> 네임 스페이스 및 <xref:System.Printing.PrintServer.InstallPrintQueue%2A> Microsoft.NET Framework로 노출 되는 클래스를 사용 하면 즉시 추가 인쇄 큐는 복제를 개수에 관계 없이 기존 인쇄 대기열에서 설치할 수 있습니다.  
  
## <a name="example"></a>예제  
 아래 예제에서는 두 번째 인쇄 큐는 기존 인쇄 대기열에서 복제 됩니다. 두 번째 다른 첫 번째에서 이름, 위치, 포트 및 공유 상태에만 합니다. 이 작업을 위한 주요 단계는 다음과 같습니다.  
  
1.  만들기는 <xref:System.Printing.PrintQueue> 기존 프린터에 복제에 대 한 개체입니다.  
  
2.  만들기는 <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> 에서 <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A> 의 <xref:System.Printing.PrintQueue>합니다. <xref:System.Collections.DictionaryEntry.Value%2A> 이 사전에 있는 각 항목의 속성은 개체에서 파생 된 형식 중 하나의 <xref:System.Printing.IndexedProperties.PrintProperty>합니다. 이 사전에 있는 항목의 값을 설정 하는 방법은 두 가지가 있습니다.  
  
    -   사전을 사용 하 여 **제거** 및 <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.Add%2A> 메서드 하는 항목을 제거 하 고 원하는 값으로 다시 추가 합니다.  
  
    -   사전을 사용 하 여 <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.SetProperty%2A> 메서드.  
  
     다음 예제에서는 두 가지 방법을 보여 줍니다.  
  
3.  만들기는 <xref:System.Printing.IndexedProperties.PrintBooleanProperty> 개체 및 설정의 <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> "IsShared"를 및 해당 <xref:System.Printing.IndexedProperties.PrintBooleanProperty.Value%2A> 를 `true`합니다.  
  
4.  사용 하 여는 <xref:System.Printing.IndexedProperties.PrintBooleanProperty> 개체의 값 수는 <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>의 "IsShared" 항목입니다.  
  
5.  만들기는 <xref:System.Printing.IndexedProperties.PrintStringProperty> 개체 및 설정 해당 <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> 을 "ShareName" 및 해당 <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> 를 적절 한 <xref:System.String>합니다.  
  
6.  사용 하 여는 <xref:System.Printing.IndexedProperties.PrintStringProperty> 개체의 값 수는 <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>의 "ShareName" 항목입니다.  
  
7.  다른 만들 <xref:System.Printing.IndexedProperties.PrintStringProperty> 개체 및 설정의 <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> "위치" 및 해당 <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> 를 적절 한 <xref:System.String>합니다.  
  
8.  두 번째 <xref:System.Printing.IndexedProperties.PrintStringProperty> 개체의 값 수는 <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>의 "위치" 항목입니다.  
  
9. 배열을 만들어 <xref:System.String>s입니다. 각 항목에는 서버에서 포트의 이름입니다.  
  
10. 사용 하 여 <xref:System.Printing.PrintServer.InstallPrintQueue%2A> 새 값으로 새 프린터를 설치 합니다.  
  
 아래 예가입니다.  
  
 [!code-csharp[ClonePrinter#ClonePrinter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ClonePrinter/CSharp/Program.cs#cloneprinter)]
 [!code-vb[ClonePrinter#ClonePrinter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ClonePrinter/visualbasic/program.vb#cloneprinter)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Printing.IndexedProperties>  
 <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>  
 <xref:System.Printing.LocalPrintServer>  
 <xref:System.Printing.PrintQueue>  
 <xref:System.Collections.DictionaryEntry>  
 [WPF의 문서](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [인쇄 개요](../../../../docs/framework/wpf/advanced/printing-overview.md)
