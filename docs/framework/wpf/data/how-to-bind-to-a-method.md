---
title: "방법: 메서드 바인딩"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data binding [WPF], binding to methods using ObjectDataProvider
- binding [WPF], to methods
- methods [WPF], binding to
ms.assetid: 5f55e71e-2182-42a0-88d1-700cc1427a7a
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0c276e9da3eaaf786038a117532848364b03e9b4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-bind-to-a-method"></a>방법: 메서드 바인딩
다음 예제를 사용 하 여 메서드를 바인딩하는 방법을 보여 줍니다 <xref:System.Windows.Data.ObjectDataProvider>합니다.  
  
## <a name="example"></a>예제  
 이 예에서 `TemperatureScale`는 `ConvertTemp` 메서드가 있는 클래스입니다. 이 메서드에서는 두 개의 매개 변수(`double` 중 하나와 `enum` 형식 `TempType)` 중 하나)를 사용하고 지정된 값을 한 온도 눈금에서 다른 눈금으로 변환합니다. 다음 예제에서는 <xref:System.Windows.Data.ObjectDataProvider> 인스턴스화하는 데 사용 되는 `TemperatureScale` 개체입니다. `ConvertTemp` 메서드는 지정된 두 매개 변수를 사용하여 호출합니다.  
  
 [!code-xaml[BindToMethod#WindowResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToMethod/CS/Window1.xaml#windowresources)]  
  
 이제 메서드를 리소스로 사용할 수 있으므로, 해당 결과에 바인딩할 수 있습니다. 다음 예제에서는 <xref:System.Windows.Controls.TextBox.Text%2A> 속성은 <xref:System.Windows.Controls.TextBox> 및 <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> 의 <xref:System.Windows.Controls.ComboBox> 메서드의 두 매개 변수에 바인딩됩니다. 그러면 변환될 대상 온도와 변환될 소스 온도 눈금을 지정할 수 있습니다. <xref:System.Windows.Data.Binding.BindsDirectlyToSource%2A> 로 설정 되어 `true` 에 바인딩할 때문에 <xref:System.Windows.Data.ObjectDataProvider.MethodParameters%2A> 의 속성은 <xref:System.Windows.Data.ObjectDataProvider> 인스턴스와 래핑된 개체의 속성이 아니라는 <xref:System.Windows.Data.ObjectDataProvider> (의 `TemperatureScale` 개체).  
  
 <xref:System.Windows.Controls.ContentControl.Content%2A> 마지막 <xref:System.Windows.Controls.Label> 사용자의 콘텐츠를 변경 하는 경우 업데이트는 <xref:System.Windows.Controls.TextBox> 나 선택한은 <xref:System.Windows.Controls.ComboBox>합니다.  
  
 [!code-xaml[BindToMethod#UI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BindToMethod/CS/Window1.xaml#ui)]  
  
 변환기 `DoubleToString` double 걸리고로 문자열 변환는 <xref:System.Windows.Data.IValueConverter.Convert%2A> 방향 (변수인 바인딩 대상에 바인딩 소스의 <xref:System.Windows.Controls.TextBox.Text%2A> 속성)으로 변환 하 고는 `string` 에 `double` 에 <xref:System.Windows.Data.IValueConverter.ConvertBack%2A> 방향입니다.  
  
 `InvalidationCharacterRule` 는 <xref:System.Windows.Controls.ValidationRule> 잘못 된 문자를 확인 하는 합니다. 빨간색 테두리가 있는 기본 오류 템플릿을 주위에서 <xref:System.Windows.Controls.TextBox>, 입력된 값을 double 값이 아닌 사용자가 알리기 위해 나타납니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법 항목](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)  
 [열거형 바인딩](../../../../docs/framework/wpf/data/how-to-bind-to-an-enumeration.md)
