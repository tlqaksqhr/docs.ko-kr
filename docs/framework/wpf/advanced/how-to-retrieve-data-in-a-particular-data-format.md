---
title: "방법: 특정 데이터 형식의 데이터 검색"
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
- drag-and-drop [WPF], retrieving data
- DataFormats class [WPF], retrieving data
- DataObject class [WPF], retrieving data
ms.assetid: a625acf3-1144-44cd-add7-456aefc3859f
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8e6513fd6d8d443b76059626c0e40991e35830c6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-retrieve-data-in-a-particular-data-format"></a><span data-ttu-id="ba5da-102">방법: 특정 데이터 형식의 데이터 검색</span><span class="sxs-lookup"><span data-stu-id="ba5da-102">How to: Retrieve Data in a Particular Data Format</span></span>
<span data-ttu-id="ba5da-103">다음 예에서는 지정된 된 형식으로의 데이터 개체에서 데이터를 검색 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ba5da-103">The following examples show how to retrieve data from a data object in a specified format.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ba5da-104">예제</span><span class="sxs-lookup"><span data-stu-id="ba5da-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="ba5da-105">설명</span><span class="sxs-lookup"><span data-stu-id="ba5da-105">Description</span></span>  
 <span data-ttu-id="ba5da-106">다음 예제 코드를 사용 하 여는 <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> (기본적으로 또는 자동 변환을 통해) 오버 로드를 먼저 지정된 된 데이터에 서식을 지정 하는 경우를 확인은 사용할 수 있으며 예제를 사용 하 여 데이터를 검색 지정한 형식이 있는 경우는 <xref:System.Windows.DataObject.GetData%28System.String%29> 메서드.</span><span class="sxs-lookup"><span data-stu-id="ba5da-106">The following example code uses the <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> overload to first check if a specified data format is available (natively or by auto-convert); if the specified format is available, the example retrieves the data by using the <xref:System.Windows.DataObject.GetData%28System.String%29> method.</span></span>  
  
### <a name="code"></a><span data-ttu-id="ba5da-107">코드</span><span class="sxs-lookup"><span data-stu-id="ba5da-107">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getspecificdataformat)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getspecificdataformat)]  
  
## <a name="example"></a><span data-ttu-id="ba5da-108">예제</span><span class="sxs-lookup"><span data-stu-id="ba5da-108">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="ba5da-109">설명</span><span class="sxs-lookup"><span data-stu-id="ba5da-109">Description</span></span>  
 <span data-ttu-id="ba5da-110">다음 예제 코드를 사용 하 여는 <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> 먼저 지정된 된 데이터 형식의 고유 하 게 사용할 수 있는지를 확인 하는 오버 로드 (자동 변환을 데이터 형식은 필터링 됨);이 예제에서는 지정 된 형식이 있는 경우는 를사용하여데이터를검색<xref:System.Windows.DataObject.GetData%28System.String%29>메서드.</span><span class="sxs-lookup"><span data-stu-id="ba5da-110">The following example code uses the <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> overload to first check if a specified data format is available natively (auto-convertible data formats are filtered); if the specified format is available, the example retrieves the data by using the <xref:System.Windows.DataObject.GetData%28System.String%29> method.</span></span>  
  
### <a name="code"></a><span data-ttu-id="ba5da-111">코드</span><span class="sxs-lookup"><span data-stu-id="ba5da-111">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat_Native](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getspecificdataformat_native)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat_Native](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getspecificdataformat_native)]  
  
## <a name="see-also"></a><span data-ttu-id="ba5da-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ba5da-112">See Also</span></span>  
 <xref:System.Windows.IDataObject>  
 [<span data-ttu-id="ba5da-113">끌어서 놓기 개요</span><span class="sxs-lookup"><span data-stu-id="ba5da-113">Drag and Drop Overview</span></span>](../../../../docs/framework/wpf/advanced/drag-and-drop-overview.md)
