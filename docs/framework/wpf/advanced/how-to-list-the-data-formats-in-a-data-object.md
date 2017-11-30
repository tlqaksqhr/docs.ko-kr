---
title: "방법: 데이터 개체의 데이터 형식 나열"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drag-and-drop [WPF], listing data formats
- DataFormats class [WPF]
- data formats [WPF], listing
ms.assetid: 18e7ba4b-ccef-4815-ae2d-3a32891010c0
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9ef5657aefdf1c229b4f1749881cce1148435a8d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-list-the-data-formats-in-a-data-object"></a><span data-ttu-id="b5e9d-102">방법: 데이터 개체의 데이터 형식 나열</span><span class="sxs-lookup"><span data-stu-id="b5e9d-102">How to: List the Data Formats in a Data Object</span></span>
<span data-ttu-id="b5e9d-103">다음 예제를 사용 하는 방법을 보여 줍니다는 <xref:System.Windows.DataObject.GetFormats%2A> 메서드 오버 로드 된 데이터 개체에서 사용할 수 있는 각 데이터 형식을 나타내는 문자열의 배열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b5e9d-103">The following examples show how to use the <xref:System.Windows.DataObject.GetFormats%2A> method overloads get an array of strings denoting each data format that is available in a data object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b5e9d-104">예제</span><span class="sxs-lookup"><span data-stu-id="b5e9d-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="b5e9d-105">설명</span><span class="sxs-lookup"><span data-stu-id="b5e9d-105">Description</span></span>  
 <span data-ttu-id="b5e9d-106">다음 예제 코드를 사용 하 여는 <xref:System.Windows.DataObject.GetFormats%2A> 오버 로드를 통해 데이터 개체 (네이티브 및 자동 변환 가능)에서 사용할 수 있는 모든 데이터 형식을 나타내는 문자열의 배열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b5e9d-106">The following example code uses the <xref:System.Windows.DataObject.GetFormats%2A> overload to get an array of strings denoting all data formats available in a data object (both native and auto-convertible).</span></span>  
  
### <a name="code"></a><span data-ttu-id="b5e9d-107">코드</span><span class="sxs-lookup"><span data-stu-id="b5e9d-107">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getalldataformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getalldataformats)]  
  
## <a name="example"></a><span data-ttu-id="b5e9d-108">예제</span><span class="sxs-lookup"><span data-stu-id="b5e9d-108">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="b5e9d-109">설명</span><span class="sxs-lookup"><span data-stu-id="b5e9d-109">Description</span></span>  
 <span data-ttu-id="b5e9d-110">다음 예제 코드를 사용 하 여는 <xref:System.Windows.DataObject.GetFormats%2A> 오버 로드를 나타내는 데이터 개체 (자동 변환을 데이터 형식은 필터링 됩니다.)에 사용할 수 있는 데이터 형식만 문자열의 배열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b5e9d-110">The following example code uses the <xref:System.Windows.DataObject.GetFormats%2A> overload to get an array of strings denoting only data formats available in a data object (auto-convertible data formats are filtered).</span></span>  
  
### <a name="code"></a><span data-ttu-id="b5e9d-111">코드</span><span class="sxs-lookup"><span data-stu-id="b5e9d-111">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats_NativeOnly](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getalldataformats_nativeonly)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetAllDataFormats_NativeOnly](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getalldataformats_nativeonly)]  
  
## <a name="see-also"></a><span data-ttu-id="b5e9d-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b5e9d-112">See Also</span></span>  
 <xref:System.Windows.IDataObject>  
 [<span data-ttu-id="b5e9d-113">끌어서 놓기 개요</span><span class="sxs-lookup"><span data-stu-id="b5e9d-113">Drag and Drop Overview</span></span>](../../../../docs/framework/wpf/advanced/drag-and-drop-overview.md)
