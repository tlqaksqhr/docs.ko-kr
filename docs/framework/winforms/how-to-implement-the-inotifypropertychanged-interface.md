---
title: '방법: INotifyPropertyChanged 인터페이스 구현'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- INotifyPropertyChanged interface [Windows Forms], implementing
ms.assetid: eac428af-b43b-46ac-80d9-1a5f88658725
ms.openlocfilehash: 8f64b51a7d56f609399baac613a651e82b91e6df
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33536414"
---
# <a name="how-to-implement-the-inotifypropertychanged-interface"></a><span data-ttu-id="a39eb-102">방법: INotifyPropertyChanged 인터페이스 구현</span><span class="sxs-lookup"><span data-stu-id="a39eb-102">How to: Implement the INotifyPropertyChanged Interface</span></span>
<span data-ttu-id="a39eb-103">다음 코드 예제에서는 구현 하는 방법을 보여 줍니다.는 <xref:System.ComponentModel.INotifyPropertyChanged> 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="a39eb-103">The following code example demonstrates how to implement the <xref:System.ComponentModel.INotifyPropertyChanged> interface.</span></span> <span data-ttu-id="a39eb-104">Windows Forms 데이터 바인딩에 사용 되는 비즈니스 개체에서이 인터페이스를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="a39eb-104">Implement this interface on business objects that are used in Windows Forms data binding.</span></span> <span data-ttu-id="a39eb-105">구현 된 인터페이스는 비즈니스 개체의 속성 변경 내용이 바인딩된 컨트롤에 통신 합니다.</span><span class="sxs-lookup"><span data-stu-id="a39eb-105">When implemented, the interface  communicates to a bound control the property changes on a business object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a39eb-106">예제</span><span class="sxs-lookup"><span data-stu-id="a39eb-106">Example</span></span>  
 [!code-csharp[System.ComponentModel.IPropertyChangeExample#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.IPropertyChangeExample#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/VB/Form1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="a39eb-107">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a39eb-107">See Also</span></span>  
 [<span data-ttu-id="a39eb-108">방법: PropertyNameChanged 패턴 적용</span><span class="sxs-lookup"><span data-stu-id="a39eb-108">How to: Apply the PropertyNameChanged Pattern</span></span>](../../../docs/framework/winforms/how-to-apply-the-propertynamechanged-pattern.md)  
 [<span data-ttu-id="a39eb-109">Windows Forms 데이터 바인딩</span><span class="sxs-lookup"><span data-stu-id="a39eb-109">Windows Forms Data Binding</span></span>](../../../docs/framework/winforms/windows-forms-data-binding.md)  
 [<span data-ttu-id="a39eb-110">방법: BindingSource와 INotifyPropertyChanged 인터페이스를 사용하여 변경 내용 알림 발생</span><span class="sxs-lookup"><span data-stu-id="a39eb-110">How to: Raise Change Notifications Using a BindingSource and the INotifyPropertyChanged Interface</span></span>](../../../docs/framework/winforms/controls/raise-change-notifications--bindingsource.md)  
 [<span data-ttu-id="a39eb-111">Windows Forms 데이터 바인딩의 변경 알림</span><span class="sxs-lookup"><span data-stu-id="a39eb-111">Change Notification in Windows Forms Data Binding</span></span>](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)
