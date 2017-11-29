---
title: "방법: 세로 텍스트 만들기"
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
- text [Windows Forms], drawing vertical
- Windows Forms, drawing vertical text
- strings [Windows Forms], drawing vertical
- vertical text [Windows Forms], drawing
ms.assetid: 50c69046-4188-47d9-b949-cc2610ffd337
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d690700224954e71b163f6e22a25e343d7e414ce
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-create-vertical-text"></a><span data-ttu-id="17397-102">방법: 세로 텍스트 만들기</span><span class="sxs-lookup"><span data-stu-id="17397-102">How to: Create Vertical Text</span></span>
<span data-ttu-id="17397-103">사용할 수는 <xref:System.Drawing.StringFormat> 가로 대신 세로로 텍스트는 그릴지를 지정 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="17397-103">You can use a <xref:System.Drawing.StringFormat> object to specify that text be drawn vertically rather than horizontally.</span></span>  
  
## <a name="example"></a><span data-ttu-id="17397-104">예제</span><span class="sxs-lookup"><span data-stu-id="17397-104">Example</span></span>  
 <span data-ttu-id="17397-105">다음 예제에서는 값을 할당 <xref:System.Drawing.StringFormatFlags.DirectionVertical> 에 <xref:System.Drawing.StringFormat.FormatFlags%2A> 속성은 <xref:System.Drawing.StringFormat> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="17397-105">The following example assigns the value <xref:System.Drawing.StringFormatFlags.DirectionVertical> to the <xref:System.Drawing.StringFormat.FormatFlags%2A> property of a <xref:System.Drawing.StringFormat> object.</span></span> <span data-ttu-id="17397-106"><xref:System.Drawing.StringFormat> 를 전달 하는 <xref:System.Drawing.Graphics.DrawString%2A> 의 메서드는 <xref:System.Drawing.Graphics> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="17397-106">That <xref:System.Drawing.StringFormat> object is passed to the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="17397-107">값 <xref:System.Drawing.StringFormatFlags.DirectionVertical> 의 구성원은 <xref:System.Drawing.StringFormatFlags> 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="17397-107">The value <xref:System.Drawing.StringFormatFlags.DirectionVertical> is a member of the <xref:System.Drawing.StringFormatFlags> enumeration.</span></span>  
  
 <span data-ttu-id="17397-108">다음 그림에서는 세로 텍스트를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="17397-108">The following illustration shows the vertical text.</span></span>  
  
 <span data-ttu-id="17397-109">![글꼴 텍스트](../../../../docs/framework/winforms/advanced/media/csfontstext5.png "csfontstext5")</span><span class="sxs-lookup"><span data-stu-id="17397-109">![Fonts Text](../../../../docs/framework/winforms/advanced/media/csfontstext5.png "csfontstext5")</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.FontsAndText#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="17397-110">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="17397-110">Compiling the Code</span></span>  
  
-   <span data-ttu-id="17397-111">앞의 예제는 Windows Forms에서 사용 하도록 설계 되었으며 필요한 <xref:System.Windows.Forms.PaintEventArgs> `e` 의 매개 변수인 <xref:System.Windows.Forms.PaintEventHandler>합니다.</span><span class="sxs-lookup"><span data-stu-id="17397-111">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e` , which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17397-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="17397-112">See Also</span></span>  
 [<span data-ttu-id="17397-113">방법: GDI를 사용하여 텍스트 그리기</span><span class="sxs-lookup"><span data-stu-id="17397-113">How to: Draw Text with GDI</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)
