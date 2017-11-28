---
title: "방법: TextBox 텍스트의 소스를 업데이트하는 시점 제어"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- source updates [WPF], timing of
- data binding [WPF], timing of source updates
- timing of source updates [WPF]
ms.assetid: ffb7b96a-351d-4c68-81e7-054033781c64
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c923a24f5abfdb059a436206a15181a67d03068f
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-control-when-the-textbox-text-updates-the-source"></a>방법: TextBox 텍스트의 소스를 업데이트하는 시점 제어
이 항목에서는 사용 하는 방법을 설명는 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 바인딩 소스 업데이트의 타이밍을 제어 하는 속성입니다. 항목에서는 사용 된 <xref:System.Windows.Controls.TextBox> 예를 들어 컨트롤입니다.  
  
## <a name="example"></a>예제  
 <xref:System.Windows.Controls.TextBox>.<xref:System.Windows.Controls.TextBox.Text%2A> 속성에는 기본 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 값 <xref:System.Windows.Data.UpdateSourceTrigger.LostFocus>합니다. 즉, 경우에 응용 프로그램에 <xref:System.Windows.Controls.TextBox> 데이터 바인딩된 <xref:System.Windows.Controls.TextBox>.<xref:System.Windows.Controls.TextBox.Text%2A> 속성에 입력 한 텍스트는 <xref:System.Windows.Controls.TextBox> 될 때까지 소스를 업데이트 하지 않습니다는 <xref:System.Windows.Controls.TextBox> 포커스를 잃을 (예를 들어, 클릭는 반대쪽<xref:System.Windows.Controls.TextBox>).  
  
 입력 하는 원본으로 업데이트 되기를 원하는 경우, 설정 된 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 에 대 한 바인딩 <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>합니다. 다음 예제에서는 `Text` 둘 다는 <xref:System.Windows.Controls.TextBox> 및 <xref:System.Windows.Controls.TextBlock> 동일한 소스 속성에 바인딩됩니다. <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 의 속성은 <xref:System.Windows.Controls.TextBox> 바인딩으로 설정 된 <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>합니다.  
  
 [!code-xaml[SimpleBinding#USTHowTo](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml#usthowto)]  
  
 결과적으로 <xref:System.Windows.Controls.TextBlock> 사용자가 텍스트를 (변경 되기 때문에 소스) 같은 텍스트를 표시는 <xref:System.Windows.Controls.TextBox>샘플의 다음 스크린 샷에서 예와 같이:  
  
 ![단순 데이터 바인딩 샘플 스크린샷](../../../../docs/framework/wpf/data/media/databindingsimplebindingsample2.png "DataBindingSimpleBindingSample2")  
  
 대화 상자 또는 사용자가 편집 가능한 폼 하 고 사용자가 완료 되는 필드를 편집 하 고 "확인"을 클릭 될 때까지 원본 업데이트 연기 하려는 설정할 수 있습니다는 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 값에 대 한 바인딩 <xref:System.Windows.Data.UpdateSourceTrigger.Explicit>다음 예제와 같이,:  
  
 [!code-xaml[UpdateSource#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UpdateSource/CSharp/Window1.xaml#2)]  
  
 설정 하는 경우는 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 값을 <xref:System.Windows.Data.UpdateSourceTrigger.Explicit>, 응용 프로그램 호출 하는 경우에 소스 값 변경의 <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> 메서드. 다음 예제에서는 호출 하는 방법을 보여 줍니다. <xref:System.Windows.Data.BindingExpression.UpdateSource%2A> 에 대 한 `itemNameTextBox`:  
  
 [!code-csharp[UpdateSource#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UpdateSource/CSharp/Window1.xaml.cs#1)]
 [!code-vb[UpdateSource#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/UpdateSource/VisualBasic/Window1.xaml.vb#1)]  
  
> [!NOTE]
>  다른 컨트롤의 속성에 대 한 동일한 기법을 사용할 수 있지만 대부분의 다른 속성 기본값 한지 염두에서에 둬야 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 값 <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>합니다. 자세한 내용은 참조는 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 속성 페이지.  
  
> [!NOTE]
>  <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 속성 소스 업데이트를 처리 하 고 따라서만 관련 된 <xref:System.Windows.Data.BindingMode.TwoWay> 또는 <xref:System.Windows.Data.BindingMode.OneWayToSource> 바인딩. 에 대 한 <xref:System.Windows.Data.BindingMode.TwoWay> 및 <xref:System.Windows.Data.BindingMode.OneWayToSource> 작업이 면 속성 변경 알림을 제공 하는 소스 개체 요구 사항에 대 한 바인딩을 합니다. 자세한 내용은 이 항목에 제시된 샘플을 참조하세요. 또한 [속성 변경 알림 구현](../../../../docs/framework/wpf/data/how-to-implement-property-change-notification.md)을 참조할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법 항목](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
