---
title: "방법: XDocument, XElement 또는 LINQ for XML 쿼리 결과에 바인딩 | Microsoft Docs"
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
  - "데이터 바인딩[WPF], XDocument에 바인딩"
  - "데이터 바인딩[WPF], XElement에 바인딩"
ms.assetid: 6a629a49-fe1c-465d-b76a-3dcbf4307b64
caps.latest.revision: 21
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 21
---
# 방법: XDocument, XElement 또는 LINQ for XML 쿼리 결과에 바인딩
이 예제에서는 <xref:System.Xml.Linq.XDocument>를 사용하여 XML 데이터를 <xref:System.Windows.Controls.ItemsControl>에 바인딩하는 방법을 설명합니다.  
  
## 예제  
 다음 XAML 코드에서는 <xref:System.Windows.Controls.ItemsControl>을 정의하고 `Planet` 데이터 형식의 데이터 템플릿을 `http://planetsNS` XML 네임스페이스에 포함합니다.  네임스페이스를 사용하는 XML 데이터 형식에는 중괄호로 묶은 네임스페이스가 포함되어야 하며, XAML 태그 확장이 나타나는 위치에 네임스페이스를 사용하는 경우에는 네임스페이스 앞에 중괄호 이스케이프 시퀀스를 추가해야 합니다.  이 코드는 <xref:System.Xml.Linq.XElement> 클래스의 <xref:System.Xml.Linq.XContainer.Element%2A> 및 <xref:System.Xml.Linq.XElement.Attribute%2A> 메서드에 해당하는 동적 속성에 바인딩됩니다.  동적 속성을 사용하면 XAML을 메서드 이름을 공유하는 동적 속성에 바인딩할 수 있습니다.  자세한 내용은 [LINQ to XML 동적 속성](../Topic/LINQ%20to%20XML%20Dynamic%20Properties.md)을 참조하십시오.  XML에 대한 기본 네임스페이스 선언은 특성 이름에 적용되지 않습니다.  
  
 [!code-xml[XLinqExample#StackPanelResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#stackpanelresources)]  
[!code-xml[XLinqExample#ItemsControl](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml#itemscontrol)]  
  
 다음 C\# 코드에서는 <xref:System.Xml.Linq.XDocument.Load%2A>를 호출하고 `http://planetsNS` XML 네임스페이스에서 `SolarSystemPlanets`이라는 요소의 모든 하위 요소에 대한 스택 패널 데이터 컨텍스트를 설정합니다.  
  
 [!code-csharp[XLinqExample#LoadDCFromFile](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#loaddcfromfile)]
 [!code-vb[XLinqExample#LoadDCFromFile](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#loaddcfromfile)]  
  
 XML 데이터는 <xref:System.Windows.Data.ObjectDataProvider>를 사용하여 XAML 리소스로 저장할 수 있습니다.  전체 예제는 [L2DBForm.xaml 소스 코드](../Topic/L2DBForm.xaml%20Source%20Code.md)를 참조하십시오.  다음 샘플에서는 코드에서 데이터 컨텍스트를 개체 리소스로 설정하는 방법을 보여 줍니다.  
  
 [!code-csharp[XLinqExample#LoadDCFromXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#loaddcfromxaml)]
 [!code-vb[XLinqExample#LoadDCFromXAML](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#loaddcfromxaml)]  
  
 <xref:System.Xml.Linq.XContainer.Element%2A> 및 <xref:System.Xml.Linq.XElement.Attribute%2A>에 매핑되는 동적 속성에서는 XAML 내에서의 유연성을 제공합니다.  또한 코드를 LINQ for XML 쿼리 결과에 바인딩할 수도 있습니다.  이 예제에서는 요소 값별로 정렬된 쿼리 결과에 바인딩됩니다.  
  
 [!code-csharp[XLinqExample#BindToResults](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XLinqExample/CSharp/Window1.xaml.cs#bindtoresults)]
 [!code-vb[XLinqExample#BindToResults](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/XLinqExample/visualbasic/window1.xaml.vb#bindtoresults)]  
  
## 참고 항목  
 [바인딩 소스 개요](../../../../docs/framework/wpf/data/binding-sources-overview.md)   
 [LINQ to XML을 사용한 WPF 데이터 바인딩 개요](../Topic/WPF%20Data%20Binding%20with%20LINQ%20to%20XML%20Overview.md)   
 [LINQ to XML을 사용한 WPF 데이터 바인딩 예제](../Topic/WPF%20Data%20Binding%20Using%20LINQ%20to%20XML%20Example.md)   
 [LINQ to XML 동적 속성](../Topic/LINQ%20to%20XML%20Dynamic%20Properties.md)