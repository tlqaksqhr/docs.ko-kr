---
title: "방법: Windows Forms에서 키 컬렉션 액세스"
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
- keyed collections [Windows Forms]
- collections [Windows Forms], accessing with keys
ms.assetid: b9b79b8b-d9bf-4f8c-b9d6-9578bc3219d3
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 852e82aff12dc39adeba6ea2dada5934ae55f951
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-access-keyed-collections-in-windows-forms"></a>방법: Windows Forms에서 키 컬렉션 액세스
-   키로 개별 컬렉션 항목에 액세스할 수 있습니다. 이 기능은 Windows Forms 응용 프로그램에서 일반적으로 사용 되는 많은 컬렉션 클래스에 추가 되었습니다. 다음 목록에서는 액세스할 수 있는 키 컬렉션에 있는 컬렉션 클래스 중 일부를 보여 줍니다.  
  
-   <xref:System.Windows.Forms.ListView.ListViewItemCollection>  
  
-   <xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection>  
  
-   <xref:System.Windows.Forms.Control.ControlCollection>  
  
-   <xref:System.Windows.Forms.TabControl.TabPageCollection>  
  
-   <xref:System.Windows.Forms.TreeNodeCollection>  
  
 컬렉션의 항목에 연결 된 키 일반적으로 항목의 이름입니다. 다음 절차는 일반적인 작업을 수행할 컬렉션 클래스를 사용 하는 방법을 보여 줍니다.  
  
### <a name="to-find-and-give-focus-to-a-nested-control-in-a-control-collection"></a>찾아 컨트롤 컬렉션에서 중첩 된 컨트롤에 포커스를 이동  
  
-   사용 하 여는 <xref:System.Windows.Forms.Control.ControlCollection.Find%2A> 및 <xref:System.Windows.Forms.Control.Focus%2A> 를 찾아 포커스를 컨트롤의 이름을 지정 하는 메서드.  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#1)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#1)]  
  
### <a name="to-access-an-image-in-an-image-collection"></a>이미지는 이미지 컬렉션에 액세스 하려면  
  
-   사용 하 여는 <xref:System.Windows.Forms.ImageList.ImageCollection.Item%2A> 속성을 통해 액세스 하려는 이미지의 이름을 지정 합니다.  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#2)]  
  
### <a name="to-set-a-tab-page-as-the-selected-tab"></a>선택된 된 탭으로 탭 페이지를 설정 하려면  
  
-   사용 하 여는 <xref:System.Windows.Forms.TabControl.SelectedTab%2A> 속성과 함께 <xref:System.Windows.Forms.TabControl.TabPageCollection.Item%2A> 속성을 통해 선택된 된 탭으로 설정 하는 탭 페이지의 이름을 지정 합니다.  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#3)]  
  
## <a name="see-also"></a>참고 항목  
 [Windows Forms 시작](../../../docs/framework/winforms/getting-started-with-windows-forms.md)  
 [방법: Windows Forms ImageList 구성 요소를 사용하여 이미지 추가 또는 제거](../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)
