---
title: "방법: 응용 프로그램 리소스 사용 | Microsoft Docs"
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
  - "응용 프로그램 리소스"
  - "리소스, 응용 프로그램 리소스"
ms.assetid: 507ea937-5191-406b-8797-0a3d9f94156d
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# 방법: 응용 프로그램 리소스 사용
이 예제에서는 응용 프로그램 리소스를 사용하는 방법을 보여 줍니다.  
  
## 예제  
 다음 예제에서는 응용 프로그램 정의 파일을 보여 줍니다.  응용 프로그램 정의 파일은 리소스 섹션\(<xref:System.Windows.Application.Resources%2A> 속성의 값\)을 정의합니다.  응용 프로그램 수준에 정의된 리소스는 응용 프로그램의 일부인 다른 모든 페이지에 액세스할 수 있습니다.  이 경우 리소스는 선언된 스타일입니다.  컨트롤 템플릿을 포함하는 전체 스타일의 길이가 길 수 있으므로 이 예제는 스타일의 <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> 속성 setter 내에 정의된 컨트롤 템플릿을 생략합니다.  
  
 [!code-xml[ResourcesApplication#PreTemplateResource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/app.xaml#pretemplateresource)]  
[!code-xml[ResourcesApplication#PostTemplateResource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/app.xaml#posttemplateresource)]  
  
 다음 예제에서는 앞의 예제에서 정의한 응용 프로그램 수준 리소스를 참조하는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 페이지를 보여 줍니다.  리소스는 요청한 리소스에 대해 고유한 리소스 키를 지정하는 [StaticResource 태그 확장](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md)을 사용하여 참조됩니다.  현재 페이지에서 키가 "GelButton"인 리소스를 찾지 못했으므로 요청한 리소스에 대한 리소스 조회 범위가 현재 페이지 범위를 벗어나서 정의된 응용 프로그램 수준 리소스로 이어집니다.  
  
 [!code-xml[ResourcesApplication#ConsumingPage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ResourcesApplication/CS/page1.xaml#consumingpage)]  
  
## 참고 항목  
 [XAML 리소스](../../../../docs/framework/wpf/advanced/xaml-resources.md)   
 [응용 프로그램 관리 개요](../../../../docs/framework/wpf/app-development/application-management-overview.md)   
 [방법 항목](../../../../docs/framework/wpf/advanced/resources-how-to-topics.md)