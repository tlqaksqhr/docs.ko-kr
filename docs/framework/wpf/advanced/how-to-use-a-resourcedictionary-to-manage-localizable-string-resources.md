---
title: "방법: ResourceDictionary를 사용하여 지역화 가능한 문자열 리소스 관리 | Microsoft Docs"
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
  - "지역화[WPF], 문자열 리소스 패키징"
  - "문자열 리소스 패키징"
  - "ResourceDictionary[WPF]"
  - "리소스[WPF], 문자열 리소스 패키징"
ms.assetid: 19e7d9a5-20df-4ad3-b157-fe6515902e5e
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# 방법: ResourceDictionary를 사용하여 지역화 가능한 문자열 리소스 관리
이 예제에서는 <xref:System.Windows.ResourceDictionary>를 사용하여 [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] 응용 프로그램의 지역화 가능한 문자열 리소스를 패키지하는 방법을 보여 줍니다.  
  
### ResourceDictionary를 사용하여 지역화 가능한 문자열 리소스를 관리하려면  
  
1.  지역화할 문자열이 포함된 <xref:System.Windows.ResourceDictionary>를 만듭니다.  다음 코드에서는 이러한 예제를 보여 줍니다.  
  
     [!code-xml[StringLocalizationSample#StringResourceDictionary](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/StringResources.xaml#stringresourcedictionary)]  
  
     이 코드는 mscorlib.dll의 <xref:System> 네임스페이스에서 <xref:System.String> 형식의 문자열 리소스 `localizedMessage`를 정의합니다.  
  
2.  다음 코드를 사용하여 <xref:System.Windows.ResourceDictionary>를 응용 프로그램에 추가합니다.  
  
     [!code-xml[StringLocalizationSample#ReferencingStringResourceDictionary](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/App.xaml#referencingstringresourcedictionary)]  
  
3.  다음과 같은 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]을 사용하여 태그의 문자열 리소스를 사용합니다.  
  
     [!code-xml[StringLocalizationSample#GetLocalizedResourceFromMarkup](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/MainWindow.xaml#getlocalizedresourcefrommarkup)]  
  
4.  다음과 같은 코드를 사용하여 코드 숨김 코드의 문자열 리소스를 사용합니다.  
  
     [!code-csharp[StringLocalizationSample#GetLocalizedResourceFromCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/MainWindow.xaml.cs#getlocalizedresourcefromcode)]
     [!code-vb[StringLocalizationSample#GetLocalizedResourceFromCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StringLocalizationSample/VisualBasic/MainWindow.xaml.vb#getlocalizedresourcefromcode)]  
  
5.  응용 프로그램을 지역화합니다.  자세한 내용은 [응용 프로그램 지역화](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md)를 참조하십시오.