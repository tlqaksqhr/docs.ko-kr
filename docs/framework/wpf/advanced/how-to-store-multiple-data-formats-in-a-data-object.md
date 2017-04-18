---
title: "방법: 데이터 개체에 여러 데이터 형식 저장 | Microsoft Docs"
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
  - "DataFormats 클래스[WPF], 여러 형식 저장"
  - "DataObject 클래스[WPF], 여러 형식 저장"
  - "끌어서 놓기[WPF], 여러 형식 저장"
ms.assetid: 941ace29-29c4-4c26-b75b-ea7d06aa0d69
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# 방법: 데이터 개체에 여러 데이터 형식 저장
다음 예제에서는 <xref:System.Windows.DataObject.SetData%28System.String%2CSystem.Object%29> 메서드를 사용하여 데이터를 여러 형식으로 데이터 개체에 추가하는 방법을 보여 줍니다.  
  
## 예제  
  
### 설명  
  
### 코드  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_StoreMultipleFormats](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_storemultipleformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_StoreMultipleFormats](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_storemultipleformats)]  
  
## 참고 항목  
 <xref:System.Windows.IDataObject>   
 [끌어서 놓기 개요](../../../../docs/framework/wpf/advanced/drag-and-drop-overview.md)