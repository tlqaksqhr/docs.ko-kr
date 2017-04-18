---
title: "주석 개요 | Microsoft Docs"
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
  - "문서, 주석"
  - "강조 표시"
  - "스티커 메모"
ms.assetid: 716bf474-29bd-4c74-84a4-8e0744bdad62
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# 주석 개요
종이 문서에 메모나 설명을 적는 것은 당연하게 받아들이는 매우 일반적인 행동입니다.  이러한 메모나 설명은 나중에 참조하기 위해 관심 있는 항목에 표시하거나 정보를 기입하기 위해 문서에 추가하는 "주석"입니다.  인쇄된 문서에 메모를 적는 것은 간단하고 일반적인 일이지만 전자 문서에 개인 주석을 추가하는 기능은 대개 비록 가능하더라도 매우 제한적입니다.  
  
 이 항목에서는 스티커 메모 및 강조 표시 등과 같은 일반적인 주석의 유형을 검토하고, [!INCLUDE[TLA#tla_caf](../../../../includes/tlasharptla-caf-md.md)]에서 [!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)] 문서 보기 컨트롤을 통해 응용 프로그램에 이러한 유형의 주석을 사용하는 방법을 보여 줍니다.  주석을 지원하는 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 문서 보기 컨트롤에는 <xref:System.Windows.Controls.DocumentViewer> 및 <xref:System.Windows.Controls.FlowDocumentPageViewer>와 같은 <xref:System.Windows.Controls.Primitives.DocumentViewerBase>에서 파생된 컨트롤뿐만 아니라 <xref:System.Windows.Controls.FlowDocumentReader> 및 <xref:System.Windows.Controls.FlowDocumentScrollViewer>도 포함됩니다.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="caf1_type_stickynotes"></a>   
## 스티커 메모  
 일반적인 스티커 메모는 정보를 기입한 색상 있는 작은 종이 조각으로 문서에 "붙입니다".  디지털 스티커 메모는 전자 문서에 대해 비슷한 기능을 제공하지만 입력된 텍스트, 필기 메모\(예: [!INCLUDE[TLA#tla_tpc](../../../../includes/tlasharptla-tpc-md.md)] "잉크" 스트로크\) 또는 웹 링크 등과 같은 다양한 유형의 콘텐츠를 포함할 수 있는 유연성을 가집니다.  
  
 다음 그림에서는 강조 표시, 텍스트 스티커 메모 및 잉크 스티커 메모 주석의 예를 보여 줍니다.  
  
 ![강조 표시, 텍스트 및 잉크 스티커 메모 주석](../../../../docs/framework/wpf/advanced/media/caf-stickynote.jpg "CAF\_StickyNote")  
  
 다음 예제에서는 응용 프로그램에서 주석 지원을 설정할 때 사용할 수 있는 방법을 보여 줍니다.  
  
 [!code-csharp[DocViewerAnnotationsXml#DocViewXmlStartAnnotations](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DocViewerAnnotationsXml/CSharp/Window1.xaml.cs#docviewxmlstartannotations)]
 [!code-vb[DocViewerAnnotationsXml#DocViewXmlStartAnnotations](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DocViewerAnnotationsXml/visualbasic/window1.xaml.vb#docviewxmlstartannotations)]  
  
<a name="caf1_type_callouts"></a>   
## 강조 표시  
 사람들은 종이 문서에 표시할 때 밑줄, 강조 표시, 문장에 포함된 단어에 동그라미 표시 또는 여백에 표시 또는 주석 그리기 등의 창조적 방법으로 관심 있는 항목이 시선을 끌 수 있도록 합니다.  [!INCLUDE[TLA#tla_caf](../../../../includes/tlasharptla-caf-md.md)]의 강조 표시 주석은 이와 유사하게 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 문서 보기 컨트롤에 표시되는 정보에 표시를 할 수 있는 기능을 제공합니다.  
  
 다음 그림에서는 강조 표시 주석의 예를 보여 줍니다.  
  
 ![강조 표시 주석](../../../../docs/framework/wpf/advanced/media/caf-callouts.png "CAF\_Callouts")  
  
 사용자는 일반적으로 우선 관심 있는 텍스트나 항목을 선택한 다음 마우스 오른쪽 단추를 클릭하여 주석 옵션의 <xref:System.Windows.Controls.ContextMenu>를 표시합니다.  다음 예제에서는 사용자가 액세스하여 주석을 만들고 관리할 수 있는 라우트된 명령으로 <xref:System.Windows.Controls.ContextMenu>를 선언하는 데 사용할 수 있는 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]을 보여 줍니다.  
  
 [!code-xml[DocViewerAnnotationsXps#CreateDeleteAnnotations](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DocViewerAnnotationsXps/CSharp/Window1.xaml#createdeleteannotations)]  
  
<a name="caf1_framework_data_anchoring"></a>   
## 데이터 고정  
 [!INCLUDE[TLA2#tla_caf](../../../../includes/tla2sharptla-caf-md.md)]에서는 주석을 표시 보기에서의 위치만이 아니라 사용자가 선택하는 데이터에도 바인딩합니다.  따라서 사용자가 표시 창을 스크롤하거나 크기를 변경하여 문서 보기가 변경된 경우 주석은 바인딩된 데이터 선택 항목과 함께 남아 있습니다.  예를 들어 다음 그래픽은 사용자가 텍스트 선택 항목에 추가한 주석을 보여 줍니다.  문서 보기가 변경되면\(스크롤, 크기 조정, 배율 조정 또는 이동 등\) 강조 표시 주석은 원래 데이터 선택 항목과 함께 이동합니다.  
  
 ![주석 데이터 고정](../../../../docs/framework/wpf/advanced/media/caf-dataanchoring.png "CAF\_DataAnchoring")  
  
<a name="matching_annotations_with_annotated_objects"></a>   
## 주석을 주석이 지정된 개체에 연결  
 주석을 해당 주석이 지정된 개체와 연결할 수 있습니다.  예를 들어 주석 창이 있는 간단한 문서 판독기 응용 프로그램을 생각해 보겠습니다.  주석 창은 문서에 고정된 주석 목록의 텍스트를 표시하는 목록 상자일 수 있습니다.  사용자가 목록 상자에서 항목을 선택하면 응용 프로그램이 해당 주석 개체에 고정된 문서의 단락이 표시됩니다.  
  
 다음 예제에서는 주석 창으로 사용되는 목록 상자와 같은 이벤트 처리기를 구현하는 방법을 보여 줍니다.  
  
 [!code-csharp[FlowDocumentAnnotatedViewer#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentAnnotatedViewer/CSharp/Window1.xaml.cs#handler)]
 [!code-vb[FlowDocumentAnnotatedViewer#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentAnnotatedViewer/visualbasic/window1.xaml.vb#handler)]  
  
 다른 예제 시나리오에는 전자 메일을 통해서 문서 판독기 간에 주석 및 스티커 메모를 교환할 수 있도록 하는 응용 프로그램에 대한 내용이 포함됩니다.  이 기능을 통해 이러한 응용 프로그램은 판독기에서 교환하는 주석이 포함된 페이지로 이동할 수 있습니다.  
  
## 참고 항목  
 <xref:System.Windows.Controls.Primitives.DocumentViewerBase>   
 <xref:System.Windows.Controls.DocumentViewer>   
 <xref:System.Windows.Controls.FlowDocumentPageViewer>   
 <xref:System.Windows.Controls.FlowDocumentScrollViewer>   
 <xref:System.Windows.Controls.FlowDocumentReader>   
 <xref:System.Windows.Annotations.IAnchorInfo>   
 [주석 스키마](../../../../docs/framework/wpf/advanced/annotations-schema.md)   
 [ContextMenu 개요](../../../../docs/framework/wpf/controls/contextmenu-overview.md)   
 [명령 개요](../../../../docs/framework/wpf/advanced/commanding-overview.md)   
 [유동 문서 개요](../../../../docs/framework/wpf/advanced/flow-document-overview.md)   
 [How to: Add a Command to a MenuItem](http://msdn.microsoft.com/ko-kr/013d68a0-5373-4a68-bd91-5de574307370)