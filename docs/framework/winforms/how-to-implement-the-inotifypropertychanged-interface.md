---
title: "방법: INotifyPropertyChanged 인터페이스 구현"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- INotifyPropertyChanged interface [Windows Forms], implementing
ms.assetid: eac428af-b43b-46ac-80d9-1a5f88658725
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7ded5d11c9a9f93848e17c372e961f9f6a3b4226
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-implement-the-inotifypropertychanged-interface"></a>방법: INotifyPropertyChanged 인터페이스 구현
다음 코드 예제에서는 구현 하는 방법을 보여 줍니다.는 <xref:System.ComponentModel.INotifyPropertyChanged> 인터페이스입니다. Windows Forms 데이터 바인딩에 사용 되는 비즈니스 개체에서이 인터페이스를 구현 합니다. 구현 된 인터페이스는 비즈니스 개체의 속성 변경 내용이 바인딩된 컨트롤에 통신 합니다.  
  
## <a name="example"></a>예  
 [!code-csharp[System.ComponentModel.IPropertyChangeExample#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.IPropertyChangeExample#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/VB/Form1.vb#1)]  
  
## <a name="see-also"></a>참고 항목  
 [방법: PropertyNameChanged 패턴 적용](../../../docs/framework/winforms/how-to-apply-the-propertynamechanged-pattern.md)  
 [Windows Forms 데이터 바인딩](../../../docs/framework/winforms/windows-forms-data-binding.md)  
 [방법: BindingSource와 INotifyPropertyChanged 인터페이스를 사용하여 변경 내용 알림 발생](../../../docs/framework/winforms/controls/raise-change-notifications--bindingsource.md)  
 [Windows Forms 데이터 바인딩의 변경 알림](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)
