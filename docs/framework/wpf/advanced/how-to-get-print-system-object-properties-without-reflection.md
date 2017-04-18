---
title: "방법: 리플렉션을 사용하지 않고 인쇄 시스템 개체 속성 가져오기 | Microsoft Docs"
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
  - "PrintSystemObject, 속성 가져오기"
ms.assetid: 43560f28-183d-41c1-b9d1-de7c2552273e
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# 방법: 리플렉션을 사용하지 않고 인쇄 시스템 개체 속성 가져오기
리플렉션을 사용하여 개체에 대한 속성 및 해당 속성의 형식을 항목별로 정리하면 응용 프로그램 성능이 느려질 수 있습니다.  <xref:System.Printing.IndexedProperties> 네임스페이스는 리플렉션을 사용하여 이 정보를 가져올 수 있는 방법을 제공합니다.  
  
## 예제  
 이 작업의 단계는 다음과 같습니다.  
  
1.  해당 형식의 인스턴스를 만듭니다.  아래의 예제에서 형식은 [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)]에서 제공하는 <xref:System.Printing.PrintQueue> 형식이지만 <xref:System.Printing.PrintSystemObject>에서 파생된 형식에 대해 거의 동일한 코드가 작동해야 합니다.  
  
2.  형식의 <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A>에서 <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>를 만듭니다.  이 사전에 있는 각 항목의 <xref:System.Collections.DictionaryEntry.Value%2A> 속성은 <xref:System.Printing.IndexedProperties.PrintProperty>에서 파생된 형식 중 하나의 개체입니다.  
  
3.  사전의 멤버를 열거합니다.  멤버 각각에 대해 다음을 수행합니다.  
  
4.  각 항목의 값을 <xref:System.Printing.IndexedProperties.PrintProperty>로 업캐스트하고 이를 사용하여 <xref:System.Printing.IndexedProperties.PrintProperty> 개체를 만듭니다.  
  
5.  <xref:System.Printing.IndexedProperties.PrintProperty> 개체 각각에 대해 <xref:System.Printing.IndexedProperties.PrintProperty.Value%2A>의 형식을 가져옵니다.  
  
 [!code-csharp[GetPrintObjectPropertyTypesWithoutReflection#ShowPropertyTypesWithoutReflection](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GetPrintObjectPropertyTypesWithoutReflection/CSharp/Program.cs#showpropertytypeswithoutreflection)]
 [!code-vb[GetPrintObjectPropertyTypesWithoutReflection#ShowPropertyTypesWithoutReflection](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GetPrintObjectPropertyTypesWithoutReflection/visualbasic/program.vb#showpropertytypeswithoutreflection)]  
  
## 참고 항목  
 <xref:System.Printing.IndexedProperties.PrintProperty>   
 <xref:System.Printing.PrintSystemObject>   
 <xref:System.Printing.IndexedProperties>   
 <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>   
 <xref:System.Printing.LocalPrintServer>   
 <xref:System.Printing.PrintQueue>   
 <xref:System.Collections.DictionaryEntry>   
 [WPF의 문서](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)   
 [인쇄 개요](../../../../docs/framework/wpf/advanced/printing-overview.md)