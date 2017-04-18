---
title: "방법: 지역화할 수 있는 응용 프로그램에서 리소스 사용 | Microsoft Docs"
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
  - "응용 프로그램, 지역화 가능"
  - "지역화 가능 응용 프로그램"
ms.assetid: 08539ad6-7fca-4f34-b82b-ff439e11dfa7
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# 방법: 지역화할 수 있는 응용 프로그램에서 리소스 사용
지역화는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]를 다른 문화권에 맞게 적용하는 것을 의미합니다.  이를 위해서는 제목, 캡션, 목록 상자 항목 등의 텍스트를 번역해야 합니다.  보다 쉬운 번역을 위해 번역될 항목이 리소스 파일에 수집됩니다.  지역화를 위해 리소스 파일을 만드는 방법에 대한 자세한 내용은 [응용 프로그램 지역화](../../../../docs/framework/wpf/advanced/how-to-localize-an-application.md)를 참조하십시오.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램을 지역화할 수 있게 하려면 개발자는 모든 지역화 가능한 리소스를 리소스 어셈블리에 빌드해야 합니다.  리소스 어셈블리는 다른 언어로 지역화되며 코드 숨김은 로드할 리소스 관리 [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)]를 사용합니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램에 필요한 파일 중 하나는 프로젝트 파일\(.proj\)입니다.  응용 프로그램에서 사용하는 모든 리소스는 이 프로젝트 파일에 포함되어야 합니다.  다음 코드 예제에서는 이를 보여 줍니다.  
  
## 예제  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]  
  
 `<Resource Include="data\picture1.jpg"/>`  
  
 `<EmbeddedResource Include="data\stringtable.en-US.restext"/>`  
  
 응용 프로그램에서 리소스를 사용하려면 <xref:System.Resources.ResourceManager>를 인스턴스화하고 사용할 리소스를 로드합니다.  다음에서는 이 작업을 수행하는 방법을 보여 줍니다.  
  
 [!code-csharp[LocalizationResources#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationResources/CSharp/page1.xaml.cs#2)]