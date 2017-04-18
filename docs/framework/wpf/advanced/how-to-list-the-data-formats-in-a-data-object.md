---
title: "방법: 데이터 개체의 데이터 형식 나열 | Microsoft Docs"
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
  - "데이터 형식[WPF], 목록 표시"
  - "DataFormats 클래스[WPF]"
  - "끌어서 놓기[WPF], 데이터 형식 나열"
ms.assetid: 18e7ba4b-ccef-4815-ae2d-3a32891010c0
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# 방법: 데이터 개체의 데이터 형식 나열
다음 예제에서는 <xref:System.Windows.DataObject.GetFormats%2A> 메서드 오버로드를 사용하여 데이터 개체에서 사용할 수 있는 각 데이터 형식을 나타내는 문자열 배열을 가져오는 방법을 보여 줍니다.  
  
## 예제  
  
### 설명  
 다음 예제 코드에서는 <xref:System.Windows.DataObject.GetFormats%2A> 오버로드를 사용하여 데이터 개체에서 기본적으로 및 자동 변환을 통해 사용할 수 있는 모든 데이터 형식을 나타내는 문자열 배열을 가져옵니다.  
  
### 코드  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getalldataformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getalldataformats)]  
  
## 예제  
  
### 설명  
 다음 예제 코드에서는 <xref:System.Windows.DataObject.GetFormats%2A> 오버로드를 사용하여 데이터 개체에서 사용할 수 있는 데이터 형식만 나타내는 문자열 배열을 가져옵니다. 자동 변환되는 데이터 형식은 필터링됩니다.  
  
### 코드  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats_NativeOnly](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getalldataformats_nativeonly)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats_NativeOnly](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getalldataformats_nativeonly)]  
  
## 참고 항목  
 <xref:System.Windows.IDataObject>   
 [끌어서 놓기 개요](../../../../docs/framework/wpf/advanced/drag-and-drop-overview.md)