---
title: "방법: 프린터 복제 | Microsoft Docs"
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
  - "인쇄 대기열 복제"
  - "프린터 복제"
  - "인쇄 대기열"
  - "인쇄 대기열, 복제"
  - "프린터, 복제"
ms.assetid: dd6997c9-fe04-40f8-88a6-92e3ac0889eb
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# 방법: 프린터 복제
대부분의 기업에서는 같은 모델의 프린터를 여러 대 구입할 것입니다.  일반적으로 이러한 프린터는 모두 실제로 동일한 구성 설정을 사용하여 설치됩니다.  각 프린터를 설치하는 작업은 시간이 많이 걸리며 오류가 발생할 가능성도 큽니다.  [!INCLUDE[TLA#tla_avalonwinfx](../../../../includes/tlasharptla-avalonwinfx-md.md)]으로 노출되는 <xref:System.Printing.IndexedProperties?displayProperty=fullName> 네임스페이스와 <xref:System.Printing.PrintServer.InstallPrintQueue%2A> 클래스는 기존 인쇄 큐에서 복제되는 추가 인쇄 큐를 얼마든지 즉시 설치할 수 있게 해줍니다.  
  
## 예제  
 아래의 예제에서 두 번째 인쇄 큐는 기존 인쇄 큐에서 복제됩니다.  두 번째 큐는 첫 번째와 이름, 위치, 포트 및 공유 상태만 다릅니다.  이 작업 수행의 주요 단계는 다음과 같습니다.  
  
1.  복제될 기본 프린터에 대해 <xref:System.Printing.PrintQueue> 개체를 만듭니다.  
  
2.  <xref:System.Printing.PrintQueue>의 <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A>에서 <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>를 만듭니다.  이 사전에 있는 각 항목의 <xref:System.Collections.DictionaryEntry.Value%2A> 속성은 <xref:System.Printing.IndexedProperties.PrintProperty>에서 파생된 형식 중 하나의 개체입니다.  이 사전에 있는 항목의 값을 설정하는 방법은 두 가지입니다.  
  
    -   사전의 **Remove** 및 <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.Add%2A> 메서드를 사용하여 항목을 제거한 다음 원하는 값을 사용하여 해당 항목을 다시 추가합니다.  
  
    -   사전의 <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.SetProperty%2A> 메서드를 사용합니다.  
  
     다음 예제에서는 두 가지 방법을 보여 줍니다.  
  
3.  <xref:System.Printing.IndexedProperties.PrintBooleanProperty> 개체를 만들고 개체의 <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A>을 "IsShared"로 설정하고 개체의 <xref:System.Printing.IndexedProperties.PrintBooleanProperty.Value%2A>를 `true`로 설정합니다.  
  
4.  <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>의 "IsShared" 항목 값이 될 <xref:System.Printing.IndexedProperties.PrintBooleanProperty> 개체를 사용합니다.  
  
5.  <xref:System.Printing.IndexedProperties.PrintStringProperty> 개체를 만들고 개체의 <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A>을 "ShareName"으로 설정하고 개체의 <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A>를 적절한 <xref:System.String>으로 설정합니다.  
  
6.  <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>의 "ShareName" 항목 값이 될 <xref:System.Printing.IndexedProperties.PrintStringProperty> 개체를 사용합니다.  
  
7.  다른 <xref:System.Printing.IndexedProperties.PrintStringProperty> 개체를 만들고 개체의 <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A>을 "Location"으로 설정하고 개체의 <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A>를 적절한 <xref:System.String>으로 설정합니다.  
  
8.  <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>의 "Location" 항목 값이 될 두 번째 <xref:System.Printing.IndexedProperties.PrintStringProperty> 개체를 사용합니다.  
  
9. <xref:System.String>의 배열을 만듭니다.  각 항목은 서버에 있는 포트의 이름입니다.  
  
10. <xref:System.Printing.PrintServer.InstallPrintQueue%2A>를 사용하여 새 값으로 새 프린터를 설치합니다.  
  
 예제는 아래와 같습니다.  
  
 [!code-csharp[ClonePrinter#ClonePrinter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ClonePrinter/CSharp/Program.cs#cloneprinter)]
 [!code-vb[ClonePrinter#ClonePrinter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ClonePrinter/visualbasic/program.vb#cloneprinter)]  
  
## 참고 항목  
 <xref:System.Printing.IndexedProperties>   
 <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>   
 <xref:System.Printing.LocalPrintServer>   
 <xref:System.Printing.PrintQueue>   
 <xref:System.Collections.DictionaryEntry>   
 [WPF의 문서](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)   
 [인쇄 개요](../../../../docs/framework/wpf/advanced/printing-overview.md)