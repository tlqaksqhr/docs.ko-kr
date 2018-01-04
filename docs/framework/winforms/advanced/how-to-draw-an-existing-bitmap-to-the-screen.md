---
title: "방법: 화면에 기존 비트맵 그리기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitmaps [Windows Forms], displaying in Windows Forms
- bitmaps [Windows Forms], loading in Windows Forms applications
- images [Windows Forms], displaying on Windows Forms
ms.assetid: 5bc558d7-b326-4050-a834-b8600da0de95
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7b3c8aef4aee74fbcdcc80301f5d5c1020883341
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-draw-an-existing-bitmap-to-the-screen"></a><span data-ttu-id="3fec7-102">방법: 화면에 기존 비트맵 그리기</span><span class="sxs-lookup"><span data-stu-id="3fec7-102">How to: Draw an Existing Bitmap to the Screen</span></span>
<span data-ttu-id="3fec7-103">쉽게 화면에 기존 이미지를 그릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fec7-103">You can easily draw an existing image on the screen.</span></span> <span data-ttu-id="3fec7-104">만들려면 먼저는 <xref:System.Drawing.Bitmap> 파일 이름을 사용 하는 비트맵 생성자를 사용 하 여 개체 <xref:System.Drawing.Bitmap.%23ctor%28System.String%29>합니다.</span><span class="sxs-lookup"><span data-stu-id="3fec7-104">First you need to create a <xref:System.Drawing.Bitmap> object by using the bitmap constructor that takes a file name, <xref:System.Drawing.Bitmap.%23ctor%28System.String%29>.</span></span> <span data-ttu-id="3fec7-105">이 생성자는 BMP, GIF, JPEG, PNG 및 TIFF를 비롯 한 여러 가지 다른 파일 형식을 사용 하 여 이미지를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fec7-105">This constructor accepts images with several different file formats, including BMP, GIF, JPEG, PNG, and TIFF.</span></span> <span data-ttu-id="3fec7-106">만든 후는 <xref:System.Drawing.Bitmap> 개체를 전달 하는 <xref:System.Drawing.Bitmap> 개체는 <xref:System.Drawing.Graphics.DrawImage%2A> 의 메서드는 <xref:System.Drawing.Graphics> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="3fec7-106">After you have created the <xref:System.Drawing.Bitmap> object, pass that <xref:System.Drawing.Bitmap> object to the <xref:System.Drawing.Graphics.DrawImage%2A> method of a <xref:System.Drawing.Graphics> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3fec7-107">예</span><span class="sxs-lookup"><span data-stu-id="3fec7-107">Example</span></span>  
 <span data-ttu-id="3fec7-108">이 예제에서는 만듭니다는 <xref:System.Drawing.Bitmap> 개체 JPEG 파일에서 다음에 왼쪽 위 모퉁이 비트맵을 그립니다 (60, 10).</span><span class="sxs-lookup"><span data-stu-id="3fec7-108">This example creates a <xref:System.Drawing.Bitmap> object from a JPEG file and then draws the bitmap with its upper-left corner at (60, 10).</span></span>  
  
 <span data-ttu-id="3fec7-109">다음 그림에서는 지정 된 위치의 그린 비트맵을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3fec7-109">The following illustration shows the bitmap drawn at the specified location.</span></span>  
  
 <span data-ttu-id="3fec7-110">![이미지 위치](../../../../docs/framework/winforms/advanced/media/csimageposition1.png "csimageposition1")</span><span class="sxs-lookup"><span data-stu-id="3fec7-110">![Image Position](../../../../docs/framework/winforms/advanced/media/csimageposition1.png "csimageposition1")</span></span>  
  
 [!code-csharp[System.Drawing.WorkingWithImages#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.WorkingWithImages#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3fec7-111">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="3fec7-111">Compiling the Code</span></span>  
 <span data-ttu-id="3fec7-112">앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3fec7-112">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fec7-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3fec7-113">See Also</span></span>  
 [<span data-ttu-id="3fec7-114">Windows Forms의 그래픽 및 그리기</span><span class="sxs-lookup"><span data-stu-id="3fec7-114">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [<span data-ttu-id="3fec7-115">이미지, 비트맵, 아이콘 및 메타파일 사용</span><span class="sxs-lookup"><span data-stu-id="3fec7-115">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
