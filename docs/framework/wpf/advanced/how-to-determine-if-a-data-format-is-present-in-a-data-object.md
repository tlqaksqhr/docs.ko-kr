---
title: '방법: 데이터 개체에 데이터 형식이 있는지 확인'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataFormats class [WPF]
- drag-and-drop [WPF], data formats present
- data formats [WPF], determining if present
ms.assetid: e487a454-c9fc-4e53-aeaa-c458d059ad4c
ms.openlocfilehash: e3e2f47df0ae1fdf0fe875827473f2c3a1b53fb5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33543421"
---
# <a name="how-to-determine-if-a-data-format-is-present-in-a-data-object"></a>방법: 데이터 개체에 데이터 형식이 있는지 확인
다음 예제에서는 다양 한를 사용 하는 방법을 보여 <xref:System.Windows.DataObject.GetDataPresent%2A> 특정 데이터 형식의 데이터 개체에 있는지 여부를 쿼리 하 메서드 오버 로드 합니다.  
  
## <a name="example"></a>예제  
  
### <a name="description"></a>설명  
 다음 예제 코드를 사용 하 여는 <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> 설명자 문자열에서 특정 데이터 형식의 존재를 쿼리 하는 오버 로드 합니다.  
  
### <a name="code"></a>코드  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_String](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_querydataformats_string)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_String](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_querydataformats_string)]  
  
## <a name="example"></a>예제  
  
### <a name="description"></a>설명  
 다음 예제 코드를 사용 하 여는 <xref:System.Windows.DataObject.GetDataPresent%28System.Type%29> 유형별로 특정 데이터 형식의 존재를 쿼리 하는 오버 로드 합니다.  
  
### <a name="code"></a>코드  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_Type](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_querydataformats_type)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_Type](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_querydataformats_type)]  
  
## <a name="example"></a>예제  
  
### <a name="description"></a>설명  
 다음 예제 코드를 사용 하 여는 <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> 설명자 문자열 데이터에 대 한 쿼리를 오버 로드 하 고 자동 변환을 데이터 형식을 처리 하는 방법을 지정 합니다.  
  
### <a name="code"></a>코드  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_Autoconvert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_querydataformats_autoconvert)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_Autoconvert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_querydataformats_autoconvert)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.IDataObject>
