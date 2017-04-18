---
title: "방법: 웹 서비스 바인딩 | Microsoft Docs"
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
  - "데이터 바인딩, 웹 서비스"
  - "데이터 바인딩, 웹 서비스"
  - "웹 서비스 바인딩"
ms.assetid: 77e2d373-69ba-4cbd-b6f5-2c83c38fc98b
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# 방법: 웹 서비스 바인딩
이 예제에서는 웹 서비스 메서드 호출에 의해 반환된 개체에 바인딩하는 방법을 보여 줍니다.  
  
## 예제  
 이 예제에서는 [MSDN\/TechNet Publishing System \(MTPS\) Content Service](http://go.microsoft.com/fwlink/?LinkId=95677)를 사용하여 지정한 문서에서 지원되는 언어 목록을 검색합니다.  
  
 웹 서비스를 호출하기 전에 해당 웹 서비스에 대한 참조를 만들어야 합니다.  [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]를 사용하여 MTPS 서비스에 대한 웹 참조를 만들려면 다음 단계를 수행하십시오.  
  
1.  [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)]에서 프로젝트를 엽니다.  
  
2.  **프로젝트** 메뉴에서 **웹 참조 추가**를 클릭합니다.  
  
3.  대화 상자에서 **URL**을 [http:\/\/services.msdn.microsoft.com\/contentservices\/contentservice.asmx?wsdl](http://services.msdn.microsoft.com/contentservices/contentservice.asmx?wsdl)로 설정합니다.  
  
4.  **이동**을 누른 다음 **참조 추가**를 누릅니다.  
  
 그런 다음 웹 서비스 메서드를 호출하여 적절한 컨트롤이나 창의 <xref:System.Windows.FrameworkElement.DataContext%2A>를 반환된 개체로 설정합니다.  MTPS 서비스의 **GetContent** 메서드는 **getContentRequest** 개체에 대한 참조를 사용합니다.  그러므로 다음 예제에서는 먼저 Request 개체를 설정합니다.  
  
 [!code-csharp[BindToWebService#Namespace](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml.cs#namespace)]
 [!code-vb[BindToWebService#Namespace](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BindToWebService/VisualBasic/Window1.xaml.vb#namespace)]  
[!code-csharp[BindToWebService#WebServiceCall](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml.cs#webservicecall)]
[!code-vb[BindToWebService#WebServiceCall](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BindToWebService/VisualBasic/Window1.xaml.vb#webservicecall)]  
  
 <xref:System.Windows.FrameworkElement.DataContext%2A>가 설정된 다음 <xref:System.Windows.FrameworkElement.DataContext%2A>가 설정되었던 개체의 속성에 대한 바인딩을 만들 수 있습니다.  이 예제에서는 <xref:System.Windows.FrameworkElement.DataContext%2A>가 **GetContent** 메서드에서 반환된 **getContentResponse** 개체로 설정됩니다.  다음 예제에서 <xref:System.Windows.Controls.ItemsControl>은 **getContentResponse**에 대한 **availableVersionsAndLocales**의 **locale** 값에 바인딩되고 이 값을 표시합니다.  
  
 [!code-xml[BindToWebService#Binding](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToWebService/CSharp/Window1.xaml#binding)]  
  
 **getContentResponse**의 구조체에 대한 자세한 내용은 [Content Service 설명서](http://services.msdn.microsoft.com/ContentServices/ContentService.asmx)를 참조하십시오.  
  
## 참고 항목  
 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [바인딩 소스 개요](../../../../docs/framework/wpf/data/binding-sources-overview.md)   
 [XAML의 바인딩에 사용할 수 있는 데이터 만들기](../../../../docs/framework/wpf/data/how-to-make-data-available-for-binding-in-xaml.md)