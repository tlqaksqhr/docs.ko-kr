---
title: "방법: 데이터 개체에 데이터 형식이 있는지 확인"
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
- DataFormats class [WPF]
- drag-and-drop [WPF], data formats present
- data formats [WPF], determining if present
ms.assetid: e487a454-c9fc-4e53-aeaa-c458d059ad4c
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9e5eaad64e18ff955340a8e91bfe8bd0e09dd8d7
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-determine-if-a-data-format-is-present-in-a-data-object"></a><span data-ttu-id="96e28-102">방법: 데이터 개체에 데이터 형식이 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="96e28-102">How to: Determine if a Data Format is Present in a Data Object</span></span>
<span data-ttu-id="96e28-103">다음 예제에서는 다양 한를 사용 하는 방법을 보여 <xref:System.Windows.DataObject.GetDataPresent%2A> 특정 데이터 형식의 데이터 개체에 있는지 여부를 쿼리 하 메서드 오버 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="96e28-103">The following examples show how to use the various <xref:System.Windows.DataObject.GetDataPresent%2A> method overloads to query whether a particular data format is present in a data object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="96e28-104">예제</span><span class="sxs-lookup"><span data-stu-id="96e28-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="96e28-105">설명</span><span class="sxs-lookup"><span data-stu-id="96e28-105">Description</span></span>  
 <span data-ttu-id="96e28-106">다음 예제 코드를 사용 하 여는 <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> 설명자 문자열에서 특정 데이터 형식의 존재를 쿼리 하는 오버 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="96e28-106">The following example code uses the <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> overload to query for the presence of a particular data format by descriptor string.</span></span>  
  
### <a name="code"></a><span data-ttu-id="96e28-107">코드</span><span class="sxs-lookup"><span data-stu-id="96e28-107">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_String](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_querydataformats_string)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_String](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_querydataformats_string)]  
  
## <a name="example"></a><span data-ttu-id="96e28-108">예제</span><span class="sxs-lookup"><span data-stu-id="96e28-108">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="96e28-109">설명</span><span class="sxs-lookup"><span data-stu-id="96e28-109">Description</span></span>  
 <span data-ttu-id="96e28-110">다음 예제 코드를 사용 하 여는 <xref:System.Windows.DataObject.GetDataPresent%28System.Type%29> 유형별로 특정 데이터 형식의 존재를 쿼리 하는 오버 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="96e28-110">The following example code uses the <xref:System.Windows.DataObject.GetDataPresent%28System.Type%29> overload to query for the presence of a particular data format by type.</span></span>  
  
### <a name="code"></a><span data-ttu-id="96e28-111">코드</span><span class="sxs-lookup"><span data-stu-id="96e28-111">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_Type](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_querydataformats_type)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_Type](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_querydataformats_type)]  
  
## <a name="example"></a><span data-ttu-id="96e28-112">예제</span><span class="sxs-lookup"><span data-stu-id="96e28-112">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="96e28-113">설명</span><span class="sxs-lookup"><span data-stu-id="96e28-113">Description</span></span>  
 <span data-ttu-id="96e28-114">다음 예제 코드를 사용 하 여는 <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> 설명자 문자열 데이터에 대 한 쿼리를 오버 로드 하 고 자동 변환을 데이터 형식을 처리 하는 방법을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="96e28-114">The following example code uses the <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> overload to query for data by descriptor string, and specifying how to treat auto-convertible data formats.</span></span>  
  
### <a name="code"></a><span data-ttu-id="96e28-115">코드</span><span class="sxs-lookup"><span data-stu-id="96e28-115">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_Autoconvert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_querydataformats_autoconvert)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_Autoconvert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_querydataformats_autoconvert)]  
  
## <a name="see-also"></a><span data-ttu-id="96e28-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="96e28-116">See Also</span></span>  
 <xref:System.Windows.IDataObject>
