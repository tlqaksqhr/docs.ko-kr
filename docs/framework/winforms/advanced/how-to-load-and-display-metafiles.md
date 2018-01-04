---
title: "방법: 메타파일 로드 및 표시"
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
- examples [Windows Forms], metafiles
- metafiles [Windows Forms], displaying
ms.assetid: 60af1714-f148-4d85-a739-0557965ffa73
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d7d0f2f15fc9e1dce77b9d8183e2e17b7c35b928
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-load-and-display-metafiles"></a><span data-ttu-id="4b01f-102">방법: 메타파일 로드 및 표시</span><span class="sxs-lookup"><span data-stu-id="4b01f-102">How to: Load and Display Metafiles</span></span>
<span data-ttu-id="4b01f-103"><xref:System.Drawing.Imaging.Metafile> 클래스에서 상속 되는 <xref:System.Drawing.Image> 클래스, 기록, 표시 및 벡터 이미지를 검사 하기 위한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b01f-103">The <xref:System.Drawing.Imaging.Metafile> class, which inherits from the <xref:System.Drawing.Image> class, provides methods for recording, displaying, and examining vector images.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4b01f-104">예</span><span class="sxs-lookup"><span data-stu-id="4b01f-104">Example</span></span>  
 <span data-ttu-id="4b01f-105">화면에 벡터 이미지 (메타 파일)을 표시 하려면는 <xref:System.Drawing.Imaging.Metafile> 개체 및 <xref:System.Drawing.Graphics> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="4b01f-105">To display a vector image (metafile) on the screen, you need a <xref:System.Drawing.Imaging.Metafile> object and a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="4b01f-106">파일 (또는 스트림)의 이름을 전달 하는 <xref:System.Drawing.Imaging.Metafile> 생성자입니다.</span><span class="sxs-lookup"><span data-stu-id="4b01f-106">Pass the name of a file (or a stream) to a <xref:System.Drawing.Imaging.Metafile> constructor.</span></span> <span data-ttu-id="4b01f-107">만든 후는 <xref:System.Drawing.Imaging.Metafile> 개체를 전달 하는 <xref:System.Drawing.Imaging.Metafile> 개체는 <xref:System.Drawing.Graphics.DrawImage%2A> 의 메서드는 <xref:System.Drawing.Graphics> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="4b01f-107">After you have created a <xref:System.Drawing.Imaging.Metafile> object, pass that <xref:System.Drawing.Imaging.Metafile> object to the <xref:System.Drawing.Graphics.DrawImage%2A> method of a <xref:System.Drawing.Graphics> object.</span></span>  
  
 <span data-ttu-id="4b01f-108">이 예에서는 만듭니다는 <xref:System.Drawing.Imaging.Metafile> 개체 EMF (확장된 메타 파일) 파일에서 다음의 왼쪽 위 모퉁이에 있는 이미지를 그립니다 (60, 10).</span><span class="sxs-lookup"><span data-stu-id="4b01f-108">The example creates a <xref:System.Drawing.Imaging.Metafile> object from an EMF (enhanced metafile) file and then draws the image with its upper-left corner at (60, 10).</span></span>  
  
 <span data-ttu-id="4b01f-109">다음 그림에서는 지정된 된 위치에 그려지는 메타 파일을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4b01f-109">The following illustration shows the metafile drawn at the specified location.</span></span>  
  
 <span data-ttu-id="4b01f-110">![이미지 위치](../../../../docs/framework/winforms/advanced/media/imageposition2.png "imageposition2")</span><span class="sxs-lookup"><span data-stu-id="4b01f-110">![Image Position](../../../../docs/framework/winforms/advanced/media/imageposition2.png "imageposition2")</span></span>  
  
 [!code-csharp[System.Drawing.WorkingWithImages#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.WorkingWithImages#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4b01f-111">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="4b01f-111">Compiling the Code</span></span>  
 <span data-ttu-id="4b01f-112">앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.Control.Paint> 이벤트 처리기의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="4b01f-112">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b01f-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4b01f-113">See Also</span></span>  
 [<span data-ttu-id="4b01f-114">이미지, 비트맵, 아이콘 및 메타파일 사용</span><span class="sxs-lookup"><span data-stu-id="4b01f-114">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/working-with-images-bitmaps-icons-and-metafiles.md)
