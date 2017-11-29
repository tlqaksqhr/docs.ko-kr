---
title: "방법: 속성 변경 알림 구현"
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
- notifications of change [WPF]
- data binding [WPF], property change notifications
- change notifications [WPF]
- properties [WPF], change notifications
ms.assetid: 30b59d9e-8c3a-4349-aa82-4be837e841cf
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6674628acd4ea6b18f98a0ab5e20935220595de5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-implement-property-change-notification"></a><span data-ttu-id="017b3-102">방법: 속성 변경 알림 구현</span><span class="sxs-lookup"><span data-stu-id="017b3-102">How to: Implement Property Change Notification</span></span>
<span data-ttu-id="017b3-103">지원 하기 위해 <xref:System.Windows.Data.BindingMode.OneWay> 또는 <xref:System.Windows.Data.BindingMode.TwoWay> 바인딩 소스 (예: 사용자가 폼을 편집할 때 자동으로 업데이트 미리 보기 창이에), 동적 변경 내용을 자동으로 반영 하 여 바인딩 대상 속성을 사용 하려면 바인딩 클래스 적절 한 속성 변경 알림을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="017b3-103">To support <xref:System.Windows.Data.BindingMode.OneWay> or <xref:System.Windows.Data.BindingMode.TwoWay> binding to enable your binding target properties to automatically reflect the dynamic changes of the binding source (for example, to have the preview pane updated automatically when the user edits a form), your class needs to provide the proper property changed notifications.</span></span> <span data-ttu-id="017b3-104">구현 하는 클래스를 만드는 방법을 보여 주는이 예제 <xref:System.ComponentModel.INotifyPropertyChanged>합니다.</span><span class="sxs-lookup"><span data-stu-id="017b3-104">This example shows how to create a class that implements <xref:System.ComponentModel.INotifyPropertyChanged>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="017b3-105">예제</span><span class="sxs-lookup"><span data-stu-id="017b3-105">Example</span></span>  
 <span data-ttu-id="017b3-106">구현 하려면 <xref:System.ComponentModel.INotifyPropertyChanged> 선언 하는 <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> 이벤트를 만들고는 `OnPropertyChanged` 메서드.</span><span class="sxs-lookup"><span data-stu-id="017b3-106">To implement <xref:System.ComponentModel.INotifyPropertyChanged> you need to declare the <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> event and create the `OnPropertyChanged` method.</span></span> <span data-ttu-id="017b3-107">그런 다음 변경 알림이 필요한 각 속성이 업데이트될 때마다 `OnPropertyChanged`를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="017b3-107">Then for each property you want change notifications for, you call `OnPropertyChanged` whenever the property is updated.</span></span>  
  
 [!code-csharp[SimpleBinding#PersonClass](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Person.cs#personclass)]
 [!code-vb[SimpleBinding#PersonClass](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Person.vb#personclass)]  
  
 <span data-ttu-id="017b3-108">방법의 예를 보려면 `Person` 클래스 지 원하는 데 사용할 수 있습니다 <xref:System.Windows.Data.BindingMode.TwoWay> 참조 바인딩 [텍스트 텍스트 소스를 업데이트 하는 시기를 제어](../../../../docs/framework/wpf/data/how-to-control-when-the-textbox-text-updates-the-source.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="017b3-108">To see an example of how the `Person` class can be used to support <xref:System.Windows.Data.BindingMode.TwoWay> binding, see [Control When the TextBox Text Updates the Source](../../../../docs/framework/wpf/data/how-to-control-when-the-textbox-text-updates-the-source.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="017b3-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="017b3-109">See Also</span></span>  
 [<span data-ttu-id="017b3-110">바인딩 소스 개요</span><span class="sxs-lookup"><span data-stu-id="017b3-110">Binding Sources Overview</span></span>](../../../../docs/framework/wpf/data/binding-sources-overview.md)  
 [<span data-ttu-id="017b3-111">데이터 바인딩 개요</span><span class="sxs-lookup"><span data-stu-id="017b3-111">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="017b3-112">방법 항목</span><span class="sxs-lookup"><span data-stu-id="017b3-112">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
