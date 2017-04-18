---
title: "방법: Windows Forms에서 데이터 탐색 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "CurrencyManager 클래스, Windows Forms 데이터 탐색"
  - "커서, 데이터 소스"
  - "데이터[Windows Forms], 탐색"
  - "데이터 소스, Windows Forms"
  - "Windows Forms, 탐색"
ms.assetid: 97360f7b-b181-4084-966a-4c62518f735b
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# 방법: Windows Forms에서 데이터 탐색
Windows 응용 프로그램에서 데이터 소스의 레코드를 가장 손쉽게 탐색할 수 있는 방법은 <xref:System.Windows.Forms.BindingSource> 구성 요소를 데이터 소스를 바인딩한 다음 컨트롤을 <xref:System.Windows.Forms.BindingSource>에 바인딩하는 것입니다.  그런 다음 <xref:System.Windows.Forms.BindingSource>의 기본 제공 탐색 메서드\(예: <xref:System.Windows.Forms.BindingSource.MoveNext%2A>, <xref:System.Windows.Forms.BindingSource.MoveLast%2A>, <xref:System.Windows.Forms.BindingSource.MovePrevious%2A> 및 <xref:System.Windows.Forms.BindingSource.MoveFirst%2A>\)를 사용할 수 있습니다.  이러한 메서드를 사용하면 <xref:System.Windows.Forms.BindingSource>의 <xref:System.Windows.Forms.BindingSource.Position%2A> 및 <xref:System.Windows.Forms.BindingSource.Current%2A> 속성을 조정할 수 있습니다.  또한 항목을 찾은 다음 <xref:System.Windows.Forms.BindingSource.Position%2A> 속성을 설정하여 해당 항목을 현재 항목으로 설정할 수 있습니다.  
  
### 데이터 소스 내에서의 위치를 증가시키려면  
  
1.  바인딩된 데이터에 대한 <xref:System.Windows.Forms.BindingSource>의 <xref:System.Windows.Forms.BindingSource.Position%2A> 속성을 이동하려는 레코드 위치로 설정합니다.  다음 예제에서는 `nextButton`을 클릭할 때 <xref:System.Windows.Forms.BindingSource>의 <xref:System.Windows.Forms.BindingSource.MoveNext%2A> 메서드를 사용하여 <xref:System.Windows.Forms.BindingSource.Position%2A> 속성을 증가시키는 방법을 보여 줍니다.  <xref:System.Windows.Forms.BindingSource>는 `Northwind` 데이터 집합의 `Customers` 테이블과 관련되어 있습니다.  
  
    > [!NOTE]
    >  [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]에서는 목록 범위를 벗어나는 값으로 위치를 설정할 수 없도록 하기 때문에 <xref:System.Windows.Forms.BindingSource.Position%2A> 속성을 첫 번째 또는 마지막 레코드를 벗어나는 값으로 설정해도 오류가 발생하지 않습니다.  응용 프로그램에서 첫 번째 또는 마지막 레코드를 지나쳤는지 여부를 인식하는 것이 중요하다면 데이터 요소 개수를 초과할지 여부를 테스트하는 논리를 포함해야 합니다.  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.NavigatingData#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#4)]  
  
### 레코드의 시작 또는 끝을 지나쳤는지 여부를 확인하려면  
  
1.  <xref:System.Windows.Forms.BindingSource.PositionChanged> 이벤트에 대한 이벤트 처리기를 만듭니다.  이 처리기에서 제시된 위치 값이 실제 데이터 요소 개수를 초과했는지 여부를 테스트할 수 있습니다.  
  
     다음 예제에서는 마지막 데이터 요소에 도달했는지 여부를 테스트하는 방법을 보여 줍니다.  이 예제에서는 마지막 요소에 있을 경우 폼에 있는 **다음** 단추가 비활성화됩니다.  
  
    > [!NOTE]
    >  코드에서 탐색 중인 목록을 변경해야 할 경우에는 **다음** 단추를 다시 활성화하여 사용자가 새 목록 전체를 찾아볼 수 있도록 하는 것이 중요합니다.  또한 사용하고 있는 특정 <xref:System.Windows.Forms.BindingSource>에 대해 위의 <xref:System.Windows.Forms.BindingSource.PositionChanged> 이벤트가 해당 이벤트 처리 메서드와 연결되어야 합니다.  다음은 <xref:System.Windows.Forms.BindingSource.PositionChanged> 이벤트를 처리하는 메서드의 예제입니다.  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.NavigatingData#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#3)]  
  
### 항목을 찾아서 현재 항목으로 설정하려면  
  
1.  현재 항목으로 설정하려는 레코드를 찾습니다.  데이터 소스에서 <xref:System.ComponentModel.IBindingList>를 구현하는 경우에는 <xref:System.Windows.Forms.BindingSource>의 <xref:System.Windows.Forms.BindingSource.Find%2A> 메서드를 사용하여 이 작업을 수행할 수 있습니다.  <xref:System.ComponentModel.IBindingList>를 구현하는 데이터 소스의 몇 가지 예로는 <xref:System.ComponentModel.BindingList%601> 및 <xref:System.Data.DataView>가 있습니다.  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.NavigatingData#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#2)]  
  
## 참고 항목  
 [Windows Forms에서 지원하는 데이터 소스](../../../docs/framework/winforms/data-sources-supported-by-windows-forms.md)   
 [Windows Forms 데이터 바인딩의 변경 알림](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)   
 [데이터 바인딩 및 Windows Forms](../../../docs/framework/winforms/data-binding-and-windows-forms.md)   
 [Windows Forms 데이터 바인딩](../../../docs/framework/winforms/windows-forms-data-binding.md)