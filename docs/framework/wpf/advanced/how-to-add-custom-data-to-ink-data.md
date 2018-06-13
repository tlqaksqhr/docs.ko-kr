---
title: '방법: 잉크 데이터에 사용자 지정 데이터 추가'
ms.date: 03/30/2017
helpviewer_keywords:
- ink data [WPF], adding custom data
- InkCanvas [WPF], displaying
ms.assetid: f02aac6f-3436-4f7c-b6ea-0452cba5332c
ms.openlocfilehash: 40d883f3d3e1d504c8757c31325aa72a03da37e0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33544513"
---
# <a name="how-to-add-custom-data-to-ink-data"></a><span data-ttu-id="331f7-102">방법: 잉크 데이터에 사용자 지정 데이터 추가</span><span class="sxs-lookup"><span data-stu-id="331f7-102">How to: Add Custom Data to Ink Data</span></span>
<span data-ttu-id="331f7-103">serialize 된 잉크 형식 (ISF)로 저장할 때 저장 될 잉크를 사용자 지정 데이터를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="331f7-103">You can add custom data to ink that will be saved when the ink is saved as ink serialized format (ISF).</span></span>  <span data-ttu-id="331f7-104">사용자 지정 데이터를 저장할 수는 <xref:System.Windows.Ink.DrawingAttributes>, <xref:System.Windows.Ink.StrokeCollection>, 또는 <xref:System.Windows.Ink.Stroke>합니다.</span><span class="sxs-lookup"><span data-stu-id="331f7-104">You can save the custom data to the <xref:System.Windows.Ink.DrawingAttributes>, the <xref:System.Windows.Ink.StrokeCollection>, or the <xref:System.Windows.Ink.Stroke>.</span></span>  <span data-ttu-id="331f7-105">3 개의 개체에 사용자 지정 데이터를 저장할 수 없게 하면 데이터를 저장 하는 가장 좋은 위치를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="331f7-105">Being able to save custom data on three objects gives you the ability to decide the best place to save the data.</span></span>  <span data-ttu-id="331f7-106">세 클래스 모두 유사한 메서드를 사용 하 여 저장 하 고 사용자 지정 데이터에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="331f7-106">All three classes use similar methods to store and access custom data.</span></span>  
  
 <span data-ttu-id="331f7-107">사용자 정의 데이터 형식만 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="331f7-107">Only the following types can be saved as custom data:</span></span>  
  
-   <xref:System.Boolean>  
  
-   <span data-ttu-id="331f7-108"><xref:System.Boolean>[]</span><span class="sxs-lookup"><span data-stu-id="331f7-108"><xref:System.Boolean>[]</span></span>  
  
-   <xref:System.Byte>  
  
-   <span data-ttu-id="331f7-109"><xref:System.Byte>[]</span><span class="sxs-lookup"><span data-stu-id="331f7-109"><xref:System.Byte>[]</span></span>  
  
-   <xref:System.Char>  
  
-   <span data-ttu-id="331f7-110"><xref:System.Char>[]</span><span class="sxs-lookup"><span data-stu-id="331f7-110"><xref:System.Char>[]</span></span>  
  
-   <xref:System.DateTime>  
  
-   <span data-ttu-id="331f7-111"><xref:System.DateTime>[]</span><span class="sxs-lookup"><span data-stu-id="331f7-111"><xref:System.DateTime>[]</span></span>  
  
-   <xref:System.Decimal>  
  
-   <span data-ttu-id="331f7-112"><xref:System.Decimal>[]</span><span class="sxs-lookup"><span data-stu-id="331f7-112"><xref:System.Decimal>[]</span></span>  
  
-   <xref:System.Double>  
  
-   <span data-ttu-id="331f7-113"><xref:System.Double>[]</span><span class="sxs-lookup"><span data-stu-id="331f7-113"><xref:System.Double>[]</span></span>  
  
-   <xref:System.Int16>  
  
-   <span data-ttu-id="331f7-114"><xref:System.Int16>[]</span><span class="sxs-lookup"><span data-stu-id="331f7-114"><xref:System.Int16>[]</span></span>  
  
-   <xref:System.Int32>  
  
-   <span data-ttu-id="331f7-115"><xref:System.Int32>[]</span><span class="sxs-lookup"><span data-stu-id="331f7-115"><xref:System.Int32>[]</span></span>  
  
-   <xref:System.Int64>  
  
-   <span data-ttu-id="331f7-116"><xref:System.Int64>[]</span><span class="sxs-lookup"><span data-stu-id="331f7-116"><xref:System.Int64>[]</span></span>  
  
-   <xref:System.Single>  
  
-   <span data-ttu-id="331f7-117"><xref:System.Single>[]</span><span class="sxs-lookup"><span data-stu-id="331f7-117"><xref:System.Single>[]</span></span>  
  
-   <xref:System.String>  
  
-   <xref:System.UInt16>  
  
-   <span data-ttu-id="331f7-118"><xref:System.UInt16>[]</span><span class="sxs-lookup"><span data-stu-id="331f7-118"><xref:System.UInt16>[]</span></span>  
  
-   <xref:System.UInt32>  
  
-   <span data-ttu-id="331f7-119"><xref:System.UInt32>[]</span><span class="sxs-lookup"><span data-stu-id="331f7-119"><xref:System.UInt32>[]</span></span>  
  
-   <xref:System.UInt64>  
  
-   <span data-ttu-id="331f7-120"><xref:System.UInt64>[]</span><span class="sxs-lookup"><span data-stu-id="331f7-120"><xref:System.UInt64>[]</span></span>  
  
## <a name="example"></a><span data-ttu-id="331f7-121">예제</span><span class="sxs-lookup"><span data-stu-id="331f7-121">Example</span></span>  
 <span data-ttu-id="331f7-122">다음 예제에서는 추가 하 고 사용자 지정 데이터를 검색 하는 <xref:System.Windows.Ink.StrokeCollection>합니다.</span><span class="sxs-lookup"><span data-stu-id="331f7-122">The following example demonstrates how to add and retrieve custom data from a <xref:System.Windows.Ink.StrokeCollection>.</span></span>  
  
 [!code-csharp[HowToAddCustomDataToInk#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml.cs#1)]  
  
 <span data-ttu-id="331f7-123">다음 예제에서는 표시 하는 응용 프로그램을 만듭니다는 <xref:System.Windows.Controls.InkCanvas> 및 두 개의 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="331f7-123">The following example creates an application that displays an <xref:System.Windows.Controls.InkCanvas> and two buttons.</span></span>  <span data-ttu-id="331f7-124">단추를 `switchAuthor`, 두 개의 펜 두 명의 서로 다른 만든에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="331f7-124">The button, `switchAuthor`, enables two pens to be used by two different authors.</span></span>  <span data-ttu-id="331f7-125">단추 `changePenColors` 각 선의 색이 변경의 <xref:System.Windows.Controls.InkCanvas> 작성자에 따라 합니다.</span><span class="sxs-lookup"><span data-stu-id="331f7-125">The button `changePenColors` changes the color of each stroke on the <xref:System.Windows.Controls.InkCanvas> according to the author.</span></span>  <span data-ttu-id="331f7-126">두 개의 응용 프로그램 정의 <xref:System.Windows.Ink.DrawingAttributes> 각 배열에 만든 그린 나타내는 사용자 지정 속성을 추가 하 고 개체는 <xref:System.Windows.Ink.Stroke>합니다.</span><span class="sxs-lookup"><span data-stu-id="331f7-126">The application defines two <xref:System.Windows.Ink.DrawingAttributes> objects and adds a custom property to each one that indicates which author drew the <xref:System.Windows.Ink.Stroke>.</span></span>  <span data-ttu-id="331f7-127">사용자가 클릭할 때 `changePenColors`, 응용 프로그램이 사용자 지정 속성의 값에 따라 stroke의 모양이 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="331f7-127">When the user clicks `changePenColors`, the application changes the appearance of the stroke according to the value of the custom property.</span></span>  
  
 [!code-xaml[HowToAddCustomDataToInk#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml#2)]  
  
 [!code-csharp[HowToAddCustomDataToInk#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml.cs#3)]
