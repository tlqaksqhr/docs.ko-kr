---
title: "방법: 데이터 개체 만들기 | Microsoft Docs"
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
  - "데이터 개체[WPF], 만들기"
  - "DataObject 클래스[WPF], 만들기"
  - "끌어서 놓기[WPF], 데이터 개체 만들기"
ms.assetid: 022fa142-717d-4fea-a53c-3b52e9d91aff
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# 방법: 데이터 개체 만들기
다음 예제에서는 <xref:System.Windows.DataObject> 클래스에서 제공되는 생성자를 사용하여 데이터 개체를 만드는 여러 가지 방법을 보여 줍니다.  
  
## 예제  
  
### 설명  
 다음 예제 코드에서는 새 데이터 개체를 만들고 오버로드된 생성자 중 하나\(<xref:System.Windows.DataObject.%23ctor%28System.Object%29>\)를 사용하여 문자열로 데이터 개체를 초기화합니다.  이 경우 저장된 데이터 형식에 따라 적절한 데이터 형식이 자동으로 결정되고, 저장된 데이터가 기본적으로 자동 변환됩니다.  
  
### 코드  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_simple)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_simple)]  
  
### 설명  
 다음 예제 코드는 이전 코드를 간략하게 줄인 것입니다.  
  
### 코드  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple_Condensed](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_simple_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple_Condensed](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_simple_condensed)]  
  
## 예제  
  
### 설명  
 다음 예제 코드에서는 새 데이터 개체를 만들고 오버로드된 생성자 중 하나\(<xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%29>\)를 사용하여 문자열 및 지정된 데이터 형식으로 데이터 개체를 초기화합니다.  이 경우 데이터 형식은 문자열로 지정되며 <xref:System.Windows.DataFormats> 클래스는 미리 정의된 형식 문자열 집합을 제공합니다.  저장된 데이터는 기본적으로 자동 변환됩니다.  
  
### 코드  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_typestring)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_typestring)]  
  
### 설명  
 다음 예제 코드는 이전 코드를 간략하게 줄인 것입니다.  
  
### 코드  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString_Condensed](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_typestring_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString_Condensed](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_typestring_condensed)]  
  
## 예제  
  
### 설명  
 다음 예제 코드에서는 새 데이터 개체를 만들고 오버로드된 생성자 중 하나\(<xref:System.Windows.DataObject.%23ctor%2A>\)를 사용하여 문자열 및 지정된 데이터 형식으로 데이터 개체를 초기화합니다.  이 경우 데이터 형식은 <xref:System.Type> 매개 변수로 지정됩니다.  저장된 데이터는 기본적으로 자동 변환됩니다.  
  
### 코드  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_type)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_type)]  
  
### 설명  
 다음 예제 코드는 이전 코드를 간략하게 줄인 것입니다.  
  
### 코드  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type_Condensed](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_type_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type_Condensed](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_type_condensed)]  
  
## 예제  
  
### 설명  
 다음 예제 코드에서는 새 데이터 개체를 만들고 오버로드된 생성자 중 하나\(<xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%2CSystem.Boolean%29>\)를 사용하여 문자열 및 지정된 데이터 형식으로 데이터 개체를 초기화합니다.  이 경우 데이터 형식은 문자열로 지정되며 <xref:System.Windows.DataFormats> 클래스는 미리 정의된 형식 문자열 집합을 제공합니다.  이 생성자 오버로드를 사용하면 자동 변환을 허용할지 여부를 호출자가 지정할 수 있습니다.  
  
### 코드  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_autoconvert)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_autoconvert)]  
  
### 설명  
 다음 예제 코드는 이전 코드를 간략하게 줄인 것입니다.  
  
### 코드  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert_Condensed](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_autoconvert_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert_Condensed](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_autoconvert_condensed)]  
  
## 참고 항목  
 <xref:System.Windows.IDataObject>