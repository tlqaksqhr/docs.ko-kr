---
title: '방법: Windows Form에 선 그리기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
f1_keywords:
- Graphics.DrawLine
helpviewer_keywords:
- examples [Windows Forms], drawing lines on forms
- drawing [Windows Forms], lines
- lines [Windows Forms], drawing
- drawing lines
ms.assetid: 55c1dbeb-75d0-430c-9814-a24b8971ad8c
ms.openlocfilehash: da83699b1f7a3c2e6c781040ca0be7ec2c9a6df0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33523344"
---
# <a name="how-to-draw-a-line-on-a-windows-form"></a><span data-ttu-id="ca030-102">방법: Windows Form에 선 그리기</span><span class="sxs-lookup"><span data-stu-id="ca030-102">How to: Draw a Line on a Windows Form</span></span>
<span data-ttu-id="ca030-103">이 예제에서는 폼에 선을 그립니다.</span><span class="sxs-lookup"><span data-stu-id="ca030-103">This example draws a line on a form.</span></span> <span data-ttu-id="ca030-104">일반적으로 폼에 그릴 때 처리 하는 폼의 <xref:System.Windows.Forms.Control.Paint> 이벤트 사용 하 여 그리기를 수행 하 고는 <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> 의 속성은 <xref:System.Windows.Forms.PaintEventArgs>이 예제에 나온 것 처럼</span><span class="sxs-lookup"><span data-stu-id="ca030-104">Typically, when you draw on a form, you handle the form’s  <xref:System.Windows.Forms.Control.Paint> event and perform the drawing using the <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> property of the <xref:System.Windows.Forms.PaintEventArgs>, as shown in this example</span></span>  
  
## <a name="example"></a><span data-ttu-id="ca030-105">예제</span><span class="sxs-lookup"><span data-stu-id="ca030-105">Example</span></span>  
 [!code-csharp[System.Drawing.UsingAPen#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingAPen#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ca030-106">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="ca030-106">Compiling the Code</span></span>  
 <span data-ttu-id="ca030-107">앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.PaintEventArgs> 이벤트 처리기의 매개 변수인 `e`<xref:System.Windows.Forms.Control.Paint>가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ca030-107">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="ca030-108">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="ca030-108">Robust Programming</span></span>  
 <span data-ttu-id="ca030-109">항상 호출 해야 <xref:System.IDisposable.Dispose%2A> 와 같은 시스템 리소스를 사용 하는 개체에 <xref:System.Drawing.Pen> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="ca030-109">You should always call <xref:System.IDisposable.Dispose%2A> on any objects that consume system resources, such as <xref:System.Drawing.Pen> objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca030-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ca030-110">See Also</span></span>  
 <xref:System.Drawing.Graphics.DrawLine%2A>  
 <xref:System.Windows.Forms.Control.OnPaint%2A>  
 [<span data-ttu-id="ca030-111">그래픽 프로그래밍 시작</span><span class="sxs-lookup"><span data-stu-id="ca030-111">Getting Started with Graphics Programming</span></span>](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)  
 [<span data-ttu-id="ca030-112">펜을 사용하여 선과 도형 그리기</span><span class="sxs-lookup"><span data-stu-id="ca030-112">Using a Pen to Draw Lines and Shapes</span></span>](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)  
 [<span data-ttu-id="ca030-113">Windows Forms의 그래픽 및 그리기</span><span class="sxs-lookup"><span data-stu-id="ca030-113">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
