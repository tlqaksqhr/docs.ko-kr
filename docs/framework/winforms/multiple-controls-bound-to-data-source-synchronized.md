---
title: "방법: 동일한 데이터 소스에 바인딩된 여러 컨트롤의 동기화 상태가 유지되도록 설정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], binding multiple
- controls [Windows Forms], synchronizing with data source
ms.assetid: c2f0ecc6-11e6-4c2c-a1ca-0759630c451e
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2573f342530e59fa05e7f24342f251990b2ce47d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-ensure-multiple-controls-bound-to-the-same-data-source-remain-synchronized"></a>방법: 동일한 데이터 소스에 바인딩된 여러 컨트롤의 동기화 상태가 유지되도록 설정
Windows forms에서 데이터 바인딩 작업을 수행할 때 종종 여러 컨트롤은 동일한 데이터 원본에 바인딩됩니다. 일부 경우에는 컨트롤의 바인딩된 속성이 서로 데이터 소스와 동기화 되어 있는지 확인 하려면 추가 단계를 수행 해야 할 수도 있습니다. 이러한 단계는 두 가지 상황에서 필요 합니다.  
  
-   데이터 소스를 구현 하지 않는 경우 <xref:System.ComponentModel.IBindingList>, 따라서를 생성 하 고 <xref:System.ComponentModel.IBindingList.ListChanged> 형식의 이벤트 <xref:System.ComponentModel.ListChangedType.ItemChanged>합니다.  
  
-   데이터 원본 구현 <xref:System.ComponentModel.IEditableObject>합니다.  
  
 옵션을 선택한 경우에 사용할 수 있습니다는 <xref:System.Windows.Forms.BindingSource> 컨트롤에 데이터 소스를 바인딩할 합니다. 후자의 경우 사용 하 여 한 <xref:System.Windows.Forms.BindingSource> 처리는 <xref:System.Windows.Forms.BindingSource.BindingComplete> 이벤트 및 호출 <xref:System.Windows.Forms.BindingManagerBase.EndCurrentEdit%2A> 은 관련 <xref:System.Windows.Forms.BindingManagerBase>합니다.  
  
## <a name="example"></a>예제  
 다음 코드 예제에서는 세 가지 컨트롤을 바인딩하는 방법을 보여 줍니다.-두 개의 텍스트 상자 컨트롤 및 <xref:System.Windows.Forms.DataGridView> 컨트롤-동일한 열에 <xref:System.Data.DataSet> 를 사용 하 여는 <xref:System.Windows.Forms.BindingSource> 구성 요소. 처리 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Forms.BindingSource.BindingComplete> 이벤트 텍스트 상자의 값을 하나의 텍스트 변경 되 면 다른 텍스트 상자에 있는지 확인 및 <xref:System.Windows.Forms.DataGridView> 컨트롤이 올바른 값으로 업데이트 됩니다.  
  
 이 예제에서는 사용는 <xref:System.Windows.Forms.BindingSource> 데이터 원본 및 컨트롤을 바인딩할 합니다. 또는 데이터 원본에 직접 컨트롤을 바인딩할 수를 검색할는 <xref:System.Windows.Forms.BindingManagerBase> 폼의 바인딩에 대 한 <xref:System.Windows.Forms.Control.BindingContext%2A> 처리 하 고는 <xref:System.Windows.Forms.BindingManagerBase.BindingComplete> 에 대 한 이벤트는 <xref:System.Windows.Forms.BindingManagerBase>합니다. 예를 보려면이 작업을 수행 하는 방법에 대 한 도움말 페이지 참조는 <xref:System.Windows.Forms.BindingManagerBase.BindingComplete> 이벤트의 <xref:System.Windows.Forms.BindingManagerBase>합니다.  
  
 [!code-csharp[System.Windows.Forms.BindingSourceMultipleControls#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleControls/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.BindingSourceMultipleControls#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleControls/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
  
-   이 코드 예제에서는  
  
-   <xref:System>, <xref:System.Windows.Forms> 및 <xref:System.Drawing> 어셈블리에 대한 참조  
  
-   포함 하는 폼의 <xref:System.Windows.Forms.Form.Load> 이벤트를 처리 하 고에 대 한 호출에서 `InitializeControlsAndDataSource` 폼의 예제에서 메서드 <xref:System.Windows.Forms.Form.Load> 이벤트 처리기입니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: BindingSource 구성 요소를 사용하여 양식 간에 바인딩된 데이터 공유](../../../docs/framework/winforms/controls/how-to-share-bound-data-across-forms-using-the-bindingsource-component.md)  
 [Windows Forms 데이터 바인딩의 변경 알림](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)  
 [데이터 바인딩과 관련된 인터페이스](../../../docs/framework/winforms/interfaces-related-to-data-binding.md)  
 [Windows Forms 데이터 바인딩](../../../docs/framework/winforms/windows-forms-data-binding.md)
