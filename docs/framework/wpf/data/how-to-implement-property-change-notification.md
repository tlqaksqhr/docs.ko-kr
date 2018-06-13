---
title: '방법: 속성 변경 알림 구현'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- notifications of change [WPF]
- data binding [WPF], property change notifications
- change notifications [WPF]
- properties [WPF], change notifications
ms.assetid: 30b59d9e-8c3a-4349-aa82-4be837e841cf
ms.openlocfilehash: a9c0fb433e2fa65e28db3b793e038b49f9d6353b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33555992"
---
# <a name="how-to-implement-property-change-notification"></a>방법: 속성 변경 알림 구현
지원 하기 위해 <xref:System.Windows.Data.BindingMode.OneWay> 또는 <xref:System.Windows.Data.BindingMode.TwoWay> 바인딩 소스 (예: 사용자가 폼을 편집할 때 자동으로 업데이트 미리 보기 창이에), 동적 변경 내용을 자동으로 반영 하 여 바인딩 대상 속성을 사용 하려면 바인딩 클래스 적절 한 속성 변경 알림을 제공 해야 합니다. 구현 하는 클래스를 만드는 방법을 보여 주는이 예제 <xref:System.ComponentModel.INotifyPropertyChanged>합니다.  
  
## <a name="example"></a>예제  
 구현 하려면 <xref:System.ComponentModel.INotifyPropertyChanged> 선언 하는 <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> 이벤트를 만들고는 `OnPropertyChanged` 메서드. 그런 다음 변경 알림이 필요한 각 속성이 업데이트될 때마다 `OnPropertyChanged`를 호출합니다.  
  
 [!code-csharp[SimpleBinding#PersonClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Person.cs#personclass)]
 [!code-vb[SimpleBinding#PersonClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Person.vb#personclass)]  
  
 방법의 예를 보려면 `Person` 클래스 지 원하는 데 사용할 수 있습니다 <xref:System.Windows.Data.BindingMode.TwoWay> 참조 바인딩 [텍스트 텍스트 소스를 업데이트 하는 시기를 제어](../../../../docs/framework/wpf/data/how-to-control-when-the-textbox-text-updates-the-source.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [바인딩 소스 개요](../../../../docs/framework/wpf/data/binding-sources-overview.md)  
 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [방법 항목](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
