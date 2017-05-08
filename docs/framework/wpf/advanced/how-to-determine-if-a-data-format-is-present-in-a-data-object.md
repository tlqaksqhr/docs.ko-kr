---
title: "방법: 데이터 개체에 데이터 형식이 있는지 확인 | Microsoft Docs"
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
  - "데이터 형식[WPF], 존재 여부 결정"
  - "DataFormats 클래스[WPF]"
  - "끌어서 놓기[WPF], 데이터 형식 있음"
ms.assetid: e487a454-c9fc-4e53-aeaa-c458d059ad4c
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# 방법: 데이터 개체에 데이터 형식이 있는지 확인
다음 예제에서는 다양한 <xref:System.Windows.DataObject.GetDataPresent%2A> 메서드 오버로드를 사용하여 데이터 개체에 특정 데이터 형식이 있는지 쿼리하는 방법을 보여 줍니다.  
  
## 예제  
  
### 설명  
 다음 예제 코드에서는 <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> 오버로드를 사용하여 설명자 문자열을 기준으로 특정 데이터 형식이 있는지 쿼리하는 방법을 보여 줍니다.  
  
### 코드  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_String](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_querydataformats_string)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_String](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_querydataformats_string)]  
  
## 예제  
  
### 설명  
 다음 예제 코드에서는 <xref:System.Windows.DataObject.GetDataPresent%28System.Type%29> 오버로드를 사용하여 형식을 기준으로 특정 데이터 형식이 있는지 쿼리하는 방법을 보여 줍니다.  
  
### 코드  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_Type](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_querydataformats_type)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_Type](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_querydataformats_type)]  
  
## 예제  
  
### 설명  
 다음 예제 코드에서는 <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> 오버로드를 사용하여 설명자 문자열을 기준으로 데이터를 쿼리하고 자동 변환할 수 있는 데이터 형식의 처리 방법을 지정합니다.  
  
### 코드  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_Autoconvert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_querydataformats_autoconvert)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_Autoconvert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_querydataformats_autoconvert)]  
  
## 참고 항목  
 <xref:System.Windows.IDataObject>