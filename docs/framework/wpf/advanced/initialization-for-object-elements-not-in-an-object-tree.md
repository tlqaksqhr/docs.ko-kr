---
title: "개체 트리에 없는 개체 요소 초기화 | Microsoft Docs"
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
  - "요소, 초기화"
  - "요소 초기화"
  - "논리 트리(logical tree)"
  - "시각적 트리(visual tree)"
ms.assetid: 7b8dfc9b-46ac-4ce8-b7bb-035734d688b7
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# 개체 트리에 없는 개체 요소 초기화
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 초기화의 몇 가지 측면은 일반적으로 [논리 트리](GTMT) 또는 [시각적 트리](GTMT)에 연결되는 요소에 의존하는 프로세스로 지연됩니다.  이 항목에서는 두 트리에 연결되지 않는 요소를 초기화하기 위해 필요할 수 있는 단계를 설명합니다.  
  
   
  
## 요소 및 논리 트리  
 코드에서 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 클래스의 인스턴스를 만들 때 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 클래스에 대한 개체 초기화의 몇 가지 측면은 클래스 생성자 호출 시 실행되는 코드의 일부가 아님을 알아 두어야 합니다.  특히 컨트롤 클래스의 경우 해당 컨트롤의 시각적 표현 대부분은 생성자에 정의되지 않고  컨트롤의 템플릿에 의해 정의됩니다.  템플릿의 소스는 다양할 수 있지만 대부분의 경우 템플릿은 테마 스타일에서 가져옵니다.  템플릿은 실제로 런타임에 바인딩됩니다. 즉, 컨트롤 레이아웃 준비가 될 때까지는 필요한 템플릿이 해당 컨트롤에 연결되지 않습니다.  또한 컨트롤은 루트에서 렌더링 화면에 연결되는 논리 트리에 연결되기 전까지는 레이아웃 준비가 되지 않습니다.  모든 자식 요소의 렌더링을 논리 트리에 정의된 대로 시작하는 것은 루트 수준 요소입니다.  
  
 시각적 트리도 이 프로세스에 참가합니다.  템플릿을 통하는 시각적 트리의 일부인 요소도 연결되기 전까지 완전히 인스턴스화되지 않습니다.  
  
 이 동작의 결과로 요소의 완성된 시각적 특성에 의존하는 특정 작업에서 추가적인 단계를 필요로 하게 됩니다.  이에 대한 예로 생성되었지만 아직 트리에 연결되지 않은 클래스의 시각적 특성을 가져오려고 하는 경우를 생각해 볼 수 있습니다.  예를 들어 <xref:System.Windows.Media.Imaging.RenderTargetBitmap>에서 <xref:System.Windows.Media.Imaging.RenderTargetBitmap.Render%2A>를 호출하려고 할 때 전달 중인 시각적 표시가 트리에 연결되지 않은 요소인 경우, 해당 요소는 추가적인 초기화 단계가 완료되어야 시각적으로 완성됩니다.  
  
### BeginInit 및 EndInit를 사용하여 요소 초기화  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 다양한 클래스가 <xref:System.ComponentModel.ISupportInitialize> 인터페이스를 구현합니다.  인터페이스의 <xref:System.ComponentModel.ISupportInitialize.BeginInit%2A> 및 <xref:System.ComponentModel.ISupportInitialize.EndInit%2A> 메서드를 사용하여 초기화 단계\(예: 렌더링에 영향을 주는 속성 값 설정\)가 포함된 코드 영역을 표시합니다.  시퀀스에서 <xref:System.ComponentModel.ISupportInitialize.EndInit%2A>가 호출된 뒤에는 레이아웃 시스템에서 요소를 처리하고 암시적 스타일을 찾을 수 있습니다.  
  
 속성을 설정하는 요소가 <xref:System.Windows.FrameworkElement> 또는 <xref:System.Windows.FrameworkContentElement> 파생 클래스인 경우 <xref:System.ComponentModel.ISupportInitialize>로 캐스팅하는 대신 <xref:System.Windows.FrameworkElement.BeginInit%2A> 및 <xref:System.Windows.FrameworkElement.EndInit%2A>의 클래스 버전을 호출할 수 있습니다.  
  
### 샘플 코드  
 다음 예제는 느슨한 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일의 렌더링 [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] 및 <xref:System.Windows.Markup.XamlReader.Load%28System.IO.Stream%29?displayProperty=fullName>를 사용하여 렌더링에 영향을 주는 속성을 조정하는 다른 [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] 호출 주위에 <xref:System.Windows.FrameworkElement.BeginInit%2A> 및 <xref:System.Windows.FrameworkElement.EndInit%2A>를 적절하게 배치하는 방법을 보여 주는 콘솔 응용 프로그램용 샘플 코드입니다.  
  
 예제에서는 main 함수만 보여 줍니다.  함수 `Rasterize` 및 `Save`\(표시되지 않음\)는 이미지 처리 및 IO를 처리하는 유틸리티 함수입니다.  
  
 [!code-csharp[InitializeElements#Main](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InitializeElements/CSharp/initializeelements.cs#main)]
 [!code-vb[InitializeElements#Main](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InitializeElements/VisualBasic/initializeelements.vb#main)]  
  
## 참고 항목  
 [WPF의 트리](../../../../docs/framework/wpf/advanced/trees-in-wpf.md)   
 [WPF 그래픽 렌더링 개요](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)   
 [XAML 개요\(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)