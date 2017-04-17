---
title: "방법: 바인딩된 데이터 변환 | Microsoft Docs"
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
  - "데이터 바인딩, 바인딩된 데이터 변환"
  - "변환, 바인딩된 데이터"
  - "데이터 바인딩(data binding), 바인딩된 데이터 변환"
ms.assetid: b00aaa19-c6df-4c3b-a9fd-88a0b488df2b
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# 방법: 바인딩된 데이터 변환
이 예제에서는 바인딩에 사용되는 데이터에 변환을 적용하는 방법을 보여 줍니다.  
  
 바인딩 중에 데이터를 변환하려면 <xref:System.Windows.Data.IValueConverter.Convert%2A> 및 <xref:System.Windows.Data.IValueConverter.ConvertBack%2A> 메서드를 포함하는 <xref:System.Windows.Data.IValueConverter> 인터페이스를 구현하는 클래스를 만들어야 합니다.  
  
## 예제  
 다음 예제에서는 년, 월, 일만 표시하도록 전달된 날짜 값을 변환하는 날짜 변환기의 구현을 보여 줍니다.  <xref:System.Windows.Data.IValueConverter> 인터페이스를 구현할 때 다음 예제와 같이 변환에 관련된 데이터 형식을 개발 도구에 표시하는 <xref:System.Windows.Data.ValueConversionAttribute> 특성을 사용하여 구현을 데코레이팅하는 것이 좋습니다.  
  
 [!code-csharp[DataBindingLab#18](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DateConverter.cs#18)]
 [!code-vb[DataBindingLab#18](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/DateConverter.vb#18)]  
  
 변환기를 작성했으면 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 파일에 리소스로 추가할 수 있습니다.  다음 예제에서 *src*는 *DateConverter*가 정의된 네임스페이스에 매핑됩니다.  
  
 [!code-xml[DataBindingLab#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#15)]  
  
 마지막으로 다음 구문을 사용하여 바인딩에서 변환기를 사용할 수 있습니다.  다음 예제에서 <xref:System.Windows.Controls.TextBlock>의 텍스트 콘텐츠는 외부 데이터 소스의 속성인 *StartDate*에 바인딩됩니다.  
  
 [!code-xml[DataBindingLab#17](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#17)]  
  
 위의 예제에서 참조된 스타일 리소스는 이 항목에 표시되지 않은 리소스 섹션에 정의되어 있습니다.  
  
## 참고 항목  
 [바인딩 유효성 검사 구현](../../../../docs/framework/wpf/data/how-to-implement-binding-validation.md)   
 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [방법 항목](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)