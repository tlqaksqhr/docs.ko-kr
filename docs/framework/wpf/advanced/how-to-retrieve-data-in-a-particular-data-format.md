---
title: "방법: 특정 데이터 형식의 데이터 검색 | Microsoft Docs"
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
  - "DataFormats 클래스[WPF], 데이터 검색"
  - "DataObject 클래스[WPF], 데이터 검색"
  - "끌어서 놓기[WPF], 데이터 검색"
ms.assetid: a625acf3-1144-44cd-add7-456aefc3859f
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# 방법: 특정 데이터 형식의 데이터 검색
다음 예제에서는 지정된 형식의 데이터 개체에서 데이터를 검색하는 방법을 보여 줍니다.  
  
## 예제  
  
### 설명  
 다음 예제 코드에서는 <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> 오버로드를 사용하여 먼저 지정된 데이터 형식을 그대로 또는 자동 변환을 통해 사용할 수 있는지 확인합니다. 지정된 형식을 사용할 수 있으면 <xref:System.Windows.DataObject.GetData%28System.String%29> 메서드를 사용하여 데이터를 검색합니다.  
  
### 코드  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getspecificdataformat)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getspecificdataformat)]  
  
## 예제  
  
### 설명  
 다음 예제 코드에서는 <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> 오버로드를 사용하여 먼저 지정된 데이터 형식을 그대로 사용할 수 있는지 확인합니다. 자동 변환 가능 데이터 형식은 필터링됩니다. 지정된 형식을 사용할 수 있으면 <xref:System.Windows.DataObject.GetData%28System.String%29> 메서드를 사용하여 데이터를 검색합니다.  
  
### 코드  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat_Native](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getspecificdataformat_native)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat_Native](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getspecificdataformat_native)]  
  
## 참고 항목  
 <xref:System.Windows.IDataObject>   
 [끌어서 놓기 개요](../../../../docs/framework/wpf/advanced/drag-and-drop-overview.md)