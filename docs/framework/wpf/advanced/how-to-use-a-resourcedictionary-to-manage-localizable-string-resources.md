---
title: '방법: ResourceDictionary를 사용하여 지역화 가능한 문자열 리소스 관리'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- resources [WPF], packaging string resources
- packaging string resources [WPF]
- ResourceDictionary [WPF]
- localization [WPF], packaging string resources
ms.assetid: 19e7d9a5-20df-4ad3-b157-fe6515902e5e
ms.openlocfilehash: 76ff3f688b5d3e7122254990076edb21fe6ae119
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33544500"
---
# <a name="how-to-use-a-resourcedictionary-to-manage-localizable-string-resources"></a>방법: ResourceDictionary를 사용하여 지역화 가능한 문자열 리소스 관리
사용 하는 방법을 보여 주는이 예제는 <xref:System.Windows.ResourceDictionary> Windows Presentation Foundation (WPF) 응용 프로그램에 대 한 패키지 지역화 가능한 문자열 리소스를 합니다.  
  
### <a name="to-use-a-resourcedictionary-to-manage-localizable-string-resources"></a>ResourceDictionary를 사용하여 지역화 가능한 문자열 리소스를 관리하려면  
  
1.  만들기는 <xref:System.Windows.ResourceDictionary> 필드를 지역화 하려면 문자열을 포함 하는 합니다. 다음 코드는 예제를 보여 줍니다.  
  
     [!code-xaml[StringLocalizationSample#StringResourceDictionary](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/StringResources.xaml#stringresourcedictionary)]  
  
     이 코드에서는 문자열 리소스를 정의 `localizedMessage`, 형식의 <xref:System.String>에서 <xref:System> mscorlib.dll에 네임 스페이스입니다.  
  
2.  추가 된 <xref:System.Windows.ResourceDictionary> 응용 프로그램에 다음 코드를 사용 합니다.  
  
     [!code-xaml[StringLocalizationSample#ReferencingStringResourceDictionary](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/App.xaml#referencingstringresourcedictionary)]  
  
3.  태그에서 문자열 리소스를 사용 하 여 사용 하 여 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 다음과 같습니다.  
  
     [!code-xaml[StringLocalizationSample#GetLocalizedResourceFromMarkup](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/MainWindow.xaml#getlocalizedresourcefrommarkup)]  
  
4.  코드 숨김에서 다음과 같은 코드를 사용하여 문자열 리소스를 사용합니다.  
  
     [!code-csharp[StringLocalizationSample#GetLocalizedResourceFromCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StringLocalizationSample/CSharp/MainWindow.xaml.cs#getlocalizedresourcefromcode)]
     [!code-vb[StringLocalizationSample#GetLocalizedResourceFromCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StringLocalizationSample/VisualBasic/MainWindow.xaml.vb#getlocalizedresourcefromcode)]  
  
5.  응용 프로그램을 지역화합니다. 자세한 내용은 참조 [응용 프로그램 지역화](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md)합니다.
